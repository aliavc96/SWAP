# Ejercicios del tema 7

### Ejercicio 7.1

**�Qu� tama�o de unidad de unidad RAID se obtendr� al configurar un RAID 0 a partir de dos discos de 100 GB y
100 GB?**
**�Qu� tama�o de unidad de unidad RAID se obtendr� al configurar un RAID 0 a partir de tres discos de 200 GB
cada uno?**

Tanto en el primer como en el segundo caso, el tama�o del Raid ser� la suma de los tama�os de los discos, o sea 200
y 400 GB.


### Ejercicio 7.2

**�Qu� tama�o de unidad de unidad RAID se obtendr� al configurar un RAID 1 a partir de dos discos de 100 GB y
100 GB?**
**�Qu� tama�o de unidad de unidad RAID se obtendr� al configurar un RAID 1 a partir de tres discos de 200 GB
cada uno?**

En este caso, al tratarse de RAID 1, uno de los discos ser� un espejo del otro, es decir, uno de ellos actuar� como copia 
de seguridad del segundo. Por tanto los tama�os ser�n de 100 y 200 GB.

### Ejercicio 7.3

**Buscar informaci�n sobre los sistemas de ficheros en red m�s utilizados en la actualidad y comparar sus caracter�sticas.
Hacer una lista de ventajas e inconvenientes de todos ellos, as� como grandes sistemas en los que se utilicen.**

- NFS (network filesystem): desarrollado inicialmente por Sun Microsystems, suele ser la opci�n por defecto para sistema 
de ficheros en red sobre GNU/Linux. El protocolo es independiente de la m�quina, del sistema operativo y del protocolo 
de transporte, ya que implementa o�nC RPC. Es interesante se�alar que todas las opciones son s�ncronas (respecto al trabajo
sobre el fichero).

- CIFS (common internet filesystem): tambi�n conocido como SMB o Samba, la implementaci�n m�s utilizada es la desarrollada
por Microsoft, y es utilizado en sistemas Windows. Permite compartir ficheros e impresoras por la red, y Linux puede implementar 
tanto la versi�n de servidor como de cliente. Es decir, permite la convivencia simult�nea de sistemas Windows y GNU/Linux en
la misma red de �rea local.

Fuente: http://recursostic.educacion.es/observatorio/web/es/software/software-general/549-raul-juncos-

**Configurar en una m�quina virtual un servidor NFS. Montar desde otra m�quina virtual en la misma subred la carpeta 
exportada y comprobar que ambas pueden acceder a la misma para lectura y escritura.**

Esto ya lo hice como parte opcional de la pr�ctica 6:

https://github.com/aliavc96/SWAP/blob/master/practicas/practica6/p6.md

