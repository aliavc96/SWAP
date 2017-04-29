
# Documentación para la práctica 2  

**Para conectar ambos servidores virtulizados**, como trabajo con VirtualBox, he definido una red NAT en cada máquina con el mismo nombre y le he dado permiso para que sea posible la conexión a dicha red virtualizada.

Probado el funcionamiento del comando scp: 

`scp 10.0.2.15:/tmp/f.txt /tmp`

que lo que hace es copiar el archivo f.txt del host 10.0.2.15 al directorio /tmp de la
máquina donde he introducido el comando.


![captura 1](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/pruebascp.PNG)

Para establecer la configuración de ssh sin clave:
En el caso de generar la clave pública y privada, yo he utilizado el algoritmo de encriptación RSA:

`ssh-keygen -t -rsa`

![captura 1](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/pruebascp.PNG)


![captura 2](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/genclavePubyPriv.PNG)

Copiamos esa clave que acabamos de generar y la pasamos a la máquina secundaria para obtener ese acceso sin contraseña:

![captura 2](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/genclavePubyPriv.PNG)

`ssh-copy-id -i .ssh/id_rsa.pub ipmaquina2`


Después de este paso debería dejarnos realizar ssh a la máquina secundaria sin pedirnos la
clave.
En caso de que haya algún error con el ssh: 

`rm -rf ~/.ssh`  

En mi caso no he tenido ningún problema:

![captura 3](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/sshSinContrasenia.PNG)


Para configurar una tarea programada que se realice de forma automática, utilizamos Cron.

Para llevar a cabo el funcionamiento de cron he editado el archivo crontab de la máquina 2 de modo que en cada minuto ejecute el
siguiente comando: 

`rsync -avz -e ssh aliavc96@maquina2:/var/www/ /var/www/`


Lo que hace es copiar el directorio especificado de la máquina 1 en la máquina 2 de forma automática y periódica. El propósito de
esta ejecución es mantener una copia de seguridad de /var/www/ en caso de que la máquina 1 falle.

![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/cron.PNG)


![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/cronFuncionando.PNG)



