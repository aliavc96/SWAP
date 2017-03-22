
#Documentación para la práctica 2  

**Para conectar ambos servidores virtulizados**, como trabajo con VirtualBox, he definido una red NAT en cada máquina con el mismo nombre y le he dado permiso para que sea posible la conexión a dicha red virtualizada.

Probado el funcionamiento del comando scp: 
`scp 10.0.2.15:/tmp/f.txt /tmp`
que lo que hace es copiar el archivo f.txt del host 10.0.2.15 al directorio /tmp de la
máquina donde he introducido el comando.

imagen pruebaSCP.PNG 
![captura 1](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/pruebascp.PNG)

Para establecer la configuración de ssh sin clave :
Para generar la clave pública y privada yo he utilizado el algoritmo de encriptación RSA:
`ssh-keygen -t -rsa`

![captura 2](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/genclavePubyPriv.PNG)

Copiamos esa clave que acabamos de generar y la pasamos a la máquina remota para obtener ese acceso sin contraseña:
`ssh-copy-id -i .ssh/id_rsa.pub ipmaquinaremota`
passwd: ...

despues de este paso debería dejarnos realizar ssh a la máquina remota sin pedirnos la
clave
En caso de que haya algún error (por equivocación con el ssh): rm -rf ~/.ssh, aunque
en mi caso no he tenido ningún problema:

![captura 3](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/genclavePubyPriv.PNG)


Para realizar una tarea programada que se realice de forma automática, utilizamos Cron
Esto es lo que he hecho yo para llevar a cabo la actualización por minuto de /var/www/
en mi máquina secundaria:


Para llevar a cabo el funcionamiento de cron he editado el archivo crontab de la máquina 2 para que en cada minuto ejecute el siguiente comando: 
`rsync -avz -e ssh aliavc96@maquina2:/var/www/ /var/www/`
que lo que hace es que copia el directorio especificado de la máquina 1 en la máquina 2. El propósito de esta ejecución es mantener una copia de seguridad de /var/www/ en 
caso de que la máquina 1 falle.

![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/cron.PNG)

![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/cronFuncionando.PNG)



