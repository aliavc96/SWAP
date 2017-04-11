
<<<<<<< HEAD
# Documentaci�n para la pr�ctica 2  
=======
# Documentación para la práctica 2  
>>>>>>> 27c6d0068602eb1837defbb291776b75be2c24a7

**Para conectar ambos servidores virtulizados**, como trabajo con VirtualBox, he definido una red NAT en cada máquina con el mismo nombre y le he dado permiso para que sea posible la conexión a dicha red virtualizada.

Probado el funcionamiento del comando scp: 

`scp 10.0.2.15:/tmp/f.txt /tmp`

que lo que hace es copiar el archivo f.txt del host 10.0.2.15 al directorio /tmp de la
máquina donde he introducido el comando.


![captura 1](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/pruebascp.PNG)

Para establecer la configuración de ssh sin clave:
En el caso de generar la clave pública y privada, yo he utilizado el algoritmo de encriptación RSA:

`ssh-keygen -t -rsa`

<<<<<<< HEAD

![captura 1](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/pruebascp.PNG)

Para establecer la configuraci�n de ssh sin clave:
En el caso de generar la clave p�blica y privada, yo he utilizado el algoritmo de encriptaci�n RSA:

`ssh-keygen -t -rsa`

![captura 2](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/genclavePubyPriv.PNG)

Copiamos esa clave que acabamos de generar y la pasamos a la m�quina secundaria para obtener ese acceso sin contrase�a:
=======
![captura 2](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/genclavePubyPriv.PNG)

Copiamos esa clave que acabamos de generar y la pasamos a la máquina secundaria para obtener ese acceso sin contraseña:
>>>>>>> 27c6d0068602eb1837defbb291776b75be2c24a7

`ssh-copy-id -i .ssh/id_rsa.pub ipmaquina2`

passwd: ...

<<<<<<< HEAD
Despu�s de este paso deber�a dejarnos realizar ssh a la m�quina secundaria sin pedirnos la
clave.
En caso de que haya alg�n error con el ssh: 

`rm -rf ~/.ssh`  

En mi caso no he tenido ning�n problema:
=======
Después de este paso debería dejarnos realizar ssh a la máquina secundaria sin pedirnos la
clave.
En caso de que haya algún error con el ssh: 

`rm -rf ~/.ssh`  

En mi caso no he tenido ningún problema:
>>>>>>> 27c6d0068602eb1837defbb291776b75be2c24a7

![captura 3](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/sshSinContrasenia.PNG)


<<<<<<< HEAD
Para configurar una tarea programada que se realice de forma autom�tica, utilizamos Cron.

Para llevar a cabo el funcionamiento de cron he editado el archivo crontab de la m�quina 2 de modo que en cada minuto ejecute el
=======
Para configurar una tarea programada que se realice de forma automática, utilizamos Cron.

Para llevar a cabo el funcionamiento de cron he editado el archivo crontab de la máquina 2 de modo que en cada minuto ejecute el
>>>>>>> 27c6d0068602eb1837defbb291776b75be2c24a7
siguiente comando: 

`rsync -avz -e ssh aliavc96@maquina2:/var/www/ /var/www/`

<<<<<<< HEAD
Lo que hace es copiar el directorio especificado de la m�quina 1 en la m�quina 2 de forma autom�tica y peri�dica. El prop�sito de
esta ejecuci�n es mantener una copia de seguridad de /var/www/ en caso de que la m�quina 1 falle.
=======
Lo que hace es copiar el directorio especificado de la máquina 1 en la máquina 2 de forma automática y periódica. El propósito de
esta ejecución es mantener una copia de seguridad de /var/www/ en caso de que la máquina 1 falle.
>>>>>>> 27c6d0068602eb1837defbb291776b75be2c24a7

![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/cron.PNG)


![captura 4](https://github.com/aliavc96/SWAP/blob/master/practicas/practica2/cronFuncionando.PNG)



