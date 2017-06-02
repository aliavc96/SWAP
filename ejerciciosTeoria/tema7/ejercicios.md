# Ejercicios del tema 7

### Ejercicio 7.1

**¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de dos discos de 100 GB y
100 GB?**
**¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de tres discos de 200 GB
cada uno?**

Tanto en el primer como en el segundo caso, el tamaño del Raid será la suma de los tamaños de los discos, o sea 200
y 400 GB.


### Ejercicio 7.2

**¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de dos discos de 100 GB y
100 GB?**
**¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de tres discos de 200 GB
cada uno?**

En este caso, al tratarse de RAID 1, uno de los discos será un espejo del otro, es decir, uno de ellos actuará como copia 
de seguridad del segundo. Por tanto los tamaños serán de 100 y 200 GB.

### Ejercicio 7.3

**Buscar información sobre los sistemas de ficheros en red más utilizados en la actualidad y comparar sus características.
Hacer una lista de ventajas e inconvenientes de todos ellos, así como grandes sistemas en los que se utilicen.**

- NFS (network filesystem): desarrollado inicialmente por Sun Microsystems, suele ser la opción por defecto para sistema 
de ficheros en red sobre GNU/Linux. El protocolo es independiente de la máquina, del sistema operativo y del protocolo 
de transporte, ya que implementa o­nC RPC. Es interesante señalar que todas las opciones son síncronas (respecto al trabajo
sobre el fichero).

- CIFS (common internet filesystem): también conocido como SMB o Samba, la implementación más utilizada es la desarrollada
por Microsoft, y es utilizado en sistemas Windows. Permite compartir ficheros e impresoras por la red, y Linux puede implementar 
tanto la versión de servidor como de cliente. Es decir, permite la convivencia simultánea de sistemas Windows y GNU/Linux en
la misma red de área local.

Fuente: http://recursostic.educacion.es/observatorio/web/es/software/software-general/549-raul-juncos-

**Configurar en una máquina virtual un servidor NFS. Montar desde otra máquina virtual en la misma subred la carpeta 
exportada y comprobar que ambas pueden acceder a la misma para lectura y escritura.**

Esto ya lo hice como parte opcional de la práctica 6:

https://github.com/aliavc96/SWAP/blob/master/practicas/practica6/p6.md

