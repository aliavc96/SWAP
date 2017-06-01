# Ejercicios del tema 5

### Ejercicio 5.1 

**Buscar información sobre cómo calcular el número de conexiones por segundo.**

Para calcular el número de conexiones por segundo podemos por ejemplo utilizar el balanceador 
de carga Nginx (instalado en las sesiones de prácticas) y con el módulo HttpStubStatusModule
podremos saber:
 
 - El número de conexiones abiertas (es decir, concurrentes).
 - Estadísticas sobre las conexiones abiertas
 - **Conexiones por segundo** 


### Ejercicio 5.2

**Revisar los análisis de tráfico que se ofrecen en: http://bit.ly/1g0dkKj
y observar como fluye el tráfico de red en Wireshark**

Wireshark ya lo tenía instalado pues le he dado varios usos y, cuando queremos acceder
a una página web con el protocolo HTTP, con Wireshark podemos ver con claridad todos 
los paquetes que se envian y reciben desde que se establece la conexión (ACKs) hasta que se
cierra.
No solo podremos ver el tipo de paquetes que son sino también su contenido. HTTP es un protocolo
no seguto y la información no va cifrada, por lo que cualquier dato introducido en la página 
web podrá ser detectado por este sniffer.



### Ejercicio 5.3

**Buscar información sobre características, disponibilidad paradiversos SO, etc de herramientas
para monitorizar las prestaciones de un servidor.**

- Utilizando el propio monitor del sistema 
- Con I-Nex: es una aplicación que no está orientada a mostrarnos cómo está funcionando nuestro
 equipo, sino a mostrarnos absolutamente toda la información relacionada con él.
- ps: Imprime los procesos en ejecución y estadísticas asociadas. Tiene miles de opciones.
- top: Porcentaje y tiempo de CPU, así como uso de memoria, de procesos e hilos
- vmstat: Utilización de la memoria virtual (VM) del sistema.
- free: Consumo global de la VM.
- pmap: Detalles de la UVM de un proceso.
- netstat: Muestra conexiones de red, tablas de enrutamiento, estadisticas sobre interfaces, 
entre otros.

La información ha sido obtenida del siguiente enlace:
https://www.genbeta.com/linux/como-monitorizar-constantemente-el-rendimiento-de-tu-distro-gnu-linux

