# Ejercicios del tema 5

### Ejercicio 5.1 

**Buscar informaci�n sobre c�mo calcular el n�mero de conexiones por segundo.**

Para calcular el n�mero de conexiones por segundo podemos por ejemplo utilizar el balanceador 
de carga Nginx (instalado en las sesiones de pr�cticas) y con el m�dulo HttpStubStatusModule
podremos saber:
 
 - El n�mero de conexiones abiertas (es decir, concurrentes).
 - Estad�sticas sobre las conexiones abiertas
 - **Conexiones por segundo** 


### Ejercicio 5.2

**Revisar los an�lisis de tr�fico que se ofrecen en: http://bit.ly/1g0dkKj
y observar como fluye el tr�fico de red en Wireshark**

Wireshark ya lo ten�a instalado pues le he dado varios usos y, cuando queremos acceder
a una p�gina web con el protocolo HTTP, con Wireshark podemos ver con claridad todos 
los paquetes que se envian y reciben desde que se establece la conexi�n (ACKs) hasta que se
cierra.
No solo podremos ver el tipo de paquetes que son sino tambi�n su contenido. HTTP es un protocolo
no seguto y la informaci�n no va cifrada, por lo que cualquier dato introducido en la p�gina 
web podr� ser detectado por este sniffer.



### Ejercicio 5.3

**Buscar informaci�n sobre caracter�sticas, disponibilidad paradiversos SO, etc de herramientas
para monitorizar las prestaciones de un servidor.**

- Utilizando el propio monitor del sistema 
- Con I-Nex: es una aplicaci�n que no est� orientada a mostrarnos c�mo est� funcionando nuestro
 equipo, sino a mostrarnos absolutamente toda la informaci�n relacionada con �l.
- ps: Imprime los procesos en ejecuci�n y estad�sticas asociadas. Tiene miles de opciones.
- top: Porcentaje y tiempo de CPU, as� como uso de memoria, de procesos e hilos
- vmstat: Utilizaci�n de la memoria virtual (VM) del sistema.
- free: Consumo global de la VM.
- pmap: Detalles de la UVM de un proceso.
- netstat: Muestra conexiones de red, tablas de enrutamiento, estadisticas sobre interfaces, 
entre otros.

La informaci�n ha sido obtenida del siguiente enlace:
https://www.genbeta.com/linux/como-monitorizar-constantemente-el-rendimiento-de-tu-distro-gnu-linux

