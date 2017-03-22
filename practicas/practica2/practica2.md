
			#Documentaci�n para la pr�ctica 2  

**Para conectar ambos servidores virtulizados**, como trabajo con VirtualBox, he definido una red NAT en cada m�quina con el mismo nombre y le he dado permiso para que sea posible la conexi�n a dicha red virtualizada.

Probado el funcionamiento del comando scp: 
`scp 10.0.2.15:/tmp/f.txt /tmp`
que lo que hace es copiar el archivo f.txt del host 10.0.2.15 al directorio /tmp de la
m�quina donde he introducido el comando.

imagen pruebaSCP.PNG 

Para establecer la configuraci�n de ssh sin clave :
Para generar la clave p�blica y privada yo he utilizado el algoritmo de encriptaci�n RSA:
**ssh-keygen -t -rsa**

genclavepubyPri.PNG
![captura 1](URL)

Copiamos esa clave que acabamos de generar y la pasamos a la m�quina remota para obtener ese acceso sin contrase�a:
`ssh-copy-id -i .ssh/id_rsa.pub ipmaquinaremota`
passwd: ...

despues de este paso deber�a dejarnos realizar ssh a la m�quina remota sin pedirnos la
clave
En caso de que haya alg�n error (por equivocaci�n con el ssh): rm -rf ~/.ssh, aunque
en mi caso no he tenido ning�n problema:

sshSinContrasenia.PNG


Para realizar una tarea programada que se realice de forma autom�tica, utilizamos Cron
Esto es lo que he hecho yo para llevar a cabo la actualizaci�n por minuto de /var/www/
en mi m�quina secundaria:


Para llevar a cabo el funcionamiento de cron he editado el archivo crontab de la m�quina 2 para que en cada minuto ejecute el siguiente comando: 
`rsync -avz -e ssh aliavc96@maquina2:/var/www/ /var/www/`
que lo que hace es que copia el directorio especificado de la m�quina 1 en la m�quina 2. El prop�sito de esta ejecuci�n es mantener una copia de seguridad de /var/www/ en 
caso de que la m�quina 1 falle.

cron.PNG
CRONfUNCIONANDO.png



