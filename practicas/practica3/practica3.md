

# Documentación para la práctica 3: Balanceadores de Carga


**Pasos a seguir**:

La maquina 3 (que es la que hará de balanceador de carga) no debe contener Apache, pues se va a instalar un software de balanceo,
su función es estar escuchando en el puerto 80 peticiones web, de modo que va a recoger una petición y la va a derivar a las
máquinas servidoras finales. Estas máquinas finales devolverán la respuesta al balanceador de modo que éste lo enviará a su "destino".

Además el balanceador oculta (protege) a los servidores finales.

Tenemos que instalar:
- Apache (mod_proxy)
- nginx
- haproxy

## Balanceador de carga Nginx

Con nginx tras hacer un curl a la ip del balanceador, nos dará la bienvenida.

En el archivo de configuración /etc/nginx/nginx.conf tenemos los siguientes includes:
- Include 1 --> hace refenrencia al balanceador de carga
- Include 2 --> hace referecia al servidor web.

En caso de que nos de problemas, tendremos que comentar el include del servidor web

Una vez terminado de configurar procedemos a reiniciarlo: 

`service nginx restart`

Haciendo de nuevo el curl ip_balanceador nos debe responder como debe.
También deberemos retroceder a la práctica 2 y comentar lo que pusimos en el archivo crontab para que los servidores no sean
"maestro-esclavo" sino independientes.


![captura 1](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/balanceadorNginxFuncionando.PNG)


Para aclarar un poco lo que se muestra en la imagen, la ip de mi balanceador de carga
se corresponde con la 10.0.2.8, la ip de mi primer servidor es la 10.0.2.7 y la de mi segundo servidor se corresponde con 10.0.2.15

Para comprobar el rendimiento de Nginx voy ha utilizar Apache Benchmark en Ubuntu 16.04.
Con respecto a la configuración de Nginx, he dejado la que tenía por defecto, es decir, con el algoritmo Round Robin y con la misma
carga asignada a ambas máquinas. Hago esto porque los servidores tienen las mismas características (uno es un clon del otro).

Estos han sido los resultados obtenidos con Apache Benchmark:

Con la orden 

`ab -n 18900 -c 350 http://10.0.2.8/index.html`

This is ApacheBench, Version 2.3 <$Revision: 1706008 $>

Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/

Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking 10.0.2.8 (be patient)


Server Software:        nginx/1.10.0

Server Hostname:        10.0.2.8

Server Port:            80

Document Path:          /index.html

Document Length:        53 bytes

Concurrency Level:      350

**Time taken for tests:   16.119 seconds**

Complete requests:      18900

Failed requests:        9450
  
 (Connect: 0, Receive: 0, Length: 9450, Exceptions: 0)

Total transferred:      5594400 bytes

HTML transferred:       963900 bytes

Requests per second:    1172.53 [#/sec] (mean)

Time per request:       298.500 [ms] (mean)

Time per request:       0.853 [ms] (mean, across all concurrent requests)

Transfer rate:          338.93 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0   76 439.3      0    7018

Processing:    35   94 286.6     72   12843

Waiting:       35   94 286.6     72   12842

Total:         60  170 564.8     72   15832


## Balanceador de carga HaProxy


Con respecto al balanceador de carga HaProxy, he intentado que su configuración sea lo más parecida posible a la que viene por defecto en Nginx.

![captura 2](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/funcionamientoHaProxy.PNG)

He lanzado Apache Benchmark con los parámetros que he utilizado para comprobar el funcionamiento de nginx:

Con la orden 

`ab -n 18900 -c 350 http://10.0.2.8/index.html`


This is ApacheBench, Version 2.3 <$Revision: 1706008 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking 10.0.2.8 (be patient)


Server Software:        Apache/2.4.18

Server Hostname:        10.0.2.8

Server Port:            80

Document Path:          /index.html

Document Length:        49 bytes


Concurrency Level:      350

**Time taken for tests:   8.252 seconds**

Complete requests:      18900

Failed requests:        9305

   (Connect: 0, Receive: 0, Length: 9305, Exceptions: 0)
   
Total transferred:      5612720 bytes

HTML transferred:       963320 bytes

Requests per second:    2290.39 [#/sec] (mean)

Time per request:       152.812 [ms] (mean)

Time per request:       0.437 [ms] (mean, across all concurrent requests)

Transfer rate:          664.23 [Kbytes/sec] received

Connection Times (ms)

              min  mean[+/-sd] median   max
			  
Connect:        0    3   5.6      2      63

Processing:    17  149  14.2    148     212

Waiting:       17  148  14.1    148     211

Total:         61  151  12.7    151     230



## Zen Load Balancer

Para la configuración de Zen, he cargado la ISO en una máquina virtual (VirtualBox), con 1024 MB de RAM, 20 GB de disco duro reservado
de forma dinámica. Además la he añadido a la red NAT donde se encuentran los servidores y Ubuntu 16.04.

Durante la intalación, le he puesto una IP fija que ha sido la 10.0.2.10, de modo que no me coincidiese con ninguna de las máquinas
conectadas a la red NAT.
Una vez instalada, he accedido a la interfaz web a través del link: http://10.0.2.10:444. Obviamente esta interfaz creada para la
configuración de Zen se encuentra protegida, aunque **el usuario y contraseña que tiene por defecto es admin y admin**.

![captura 3](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/InterfazGraficaZen.PNG)

Posteriormente he creado una granja web 


![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/creacionGranjaWeb.PNG)


y le he añadido los dos servidores. Además he tratado de llevar a cabo una configuración lo más parecida posible al del resto de
balanceadores de carga que he probado, como se puede ver en la imagen:

![captura 5](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/configuracionGranjaWeb.PNG)

Después de configurar la granja web, la he levantado y he hecho el test del Apache Benchmark desde un Ubuntu con las mismas opciones utilizadas
para el resto de balanceadores. Aquí los resultados:

Orden utilizada: 

`ab -n 18900 -c 350 http://10.0.2.10/index.html > /home/aliavc96/Escritorio/pruebaApacheBenchmarZen
`



This is ApacheBench, Version 2.3 <$Revision: 1706008 $>

Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/

Licensed to The Apache Software Foundation, http://www.apache.org/


Benchmarking 10.0.2.10 (be patient)

Server Software:        Apache/2.4.18

Server Hostname:        10.0.2.10

Server Port:            80


Document Path:          /index.html

Document Length:        49 bytes


Concurrency Level:      350

**Time taken for tests:   6.284 seconds**

Complete requests:      18900

Failed requests:        9531
   (Connect: 0, Receive: 0, Length: 9531, Exceptions: 0)
Total transferred:      5613624 bytes

HTML transferred:       964224 bytes

Requests per second:    3007.73 [#/sec] (mean)

Time per request:       116.367 [ms] (mean)

Time per request:       0.332 [ms] (mean, across all concurrent requests)

Transfer rate:          872.41 [Kbytes/sec] received


Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0   41 200.0      7    3024

Processing:     4   70  66.3     71    1856
Waiting:        3   70  66.3     71    1856

Total:          7  111 220.0     78    3537




## Balanceador de Carga Pound

Aclarar que este balanceador ha sido probado por mi compañero Antonio Campoy, y tanto las pruebas como la documentación de este apartado
son suyas.


Una vez instalado configuramos pound editando el archivo de configuración /etc/pound/pound.conf.

Solo editamos la parte final, que quedaría así:

		ListenHTTP
			Address ipBALANCEADOR
			Port 80

			#Allow PUT and DELETE also (by default only GET, POST and HEAD)?:
			#xHTTP		0
			Service
				BackEnd
					Address ipM1
					Port    80
					Priority 1
				End
				BackEnd
					Address ipM2
					Port	80
					Priority 1
				End
			End
		End

Para arrancar pound utilizamos la siguiente orden:

`sudo service pound start`

Al principio he tenido un problema, pues no me arrancaba cuando lo iniciaba. Al parecer en el fichero /etc/default/pound hay una
variable startup, que yo tenía a 0, la he puesto a 1, y al reiniciar la máquina directamente ha iniciado pound (por suerte ya que cuando
arrancamos la máquina si no hemos quitado los ficheros de inicio se produce 'una guerra' entre los balanceadores instalados).

Una vez lanzado comprobamos que funciona:


![captura 6](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/Poundimg1.PNG)

He podido comprobar que por defecto pound no utiliza round-robin (como nginx y haproxy).

Por eso en la captura para comprobar que es Pound el que funciona he utilizado la orden:
	
`ps aux | grep pound`
 
Hasta que me salieran ambos servidores para que se vea en la captura.
	
	
Probando el rendimiento de Pound con Apache Benchmark:

`ab -m 10000 -c 300 http://ip3/index.html`


![captura 6](https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/pruebaApacheBenchmarkPound.PNG)




## Conclusión final

Puedo decir que a pesar de que influyen muchos aspectos externos a los balanceadores de carga instalados, pues yo me encuentro
trabajando en Windows 10, y empleo máquinas virtuales para comprobar el funcionamiento de estos balanceadores, obtenemos que los
mejores resultados provienen Zen Load Balancer.






