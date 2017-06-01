# Ejercicios del tema 4

### Ejercicio 4.1 

**Buscar información sobre cuánto costaría en la actualidad un mainframe. Comparar 
precio y potencia entre esa máquina y una granja web de unas prestaciones similares**

He estado viendo los Mainframe de IBM y el  zEnterprise BC12 cuesta unos 75000 dólares.
Además existe un blog con opiniones sobre el coste de los mainframe, y hay un comentario que dice lo siguiente:

"I was talking to an IBM salesman tonight and he said the break even point is about 200 servers which are running oracle 
on multiple cores. At $50k/licence/core that suggests $4-$10 million++ per mainframe."
Esta opinión fue dada en el año 2015.

Las características del  zEnterprise BC12 dadas por IMB son las siguientes:

El zBC12, con hasta un total de 18 microprocesadores que funcionan a
4,2 gigahercios (GHz), mejora hasta en un 36 % el rendimiento por core,
en un 58 % la capacidad de procesamiento general del sistema y hasta en
un 62 % la capacidad total en comparación con su predecesor,
el z114.1 También ofrece hasta 496 gigabytes (GB) de memoria
disponible (dos veces más que el z114) para mejorar de forma
drástica el rendimiento de las cargas de trabajo limitadas por la
memoria.

- Ofrece hasta 496 gigabytes (GB) de memoria
disponible (dos veces más que el z114) para mejorar de forma
drástica el rendimiento de las cargas de trabajo limitadas por la
memoria.

- Un rendimiento mejorado también se
consigue con la reducción de sobrecargas en la gestión de
memoria del sistema a través de las mejoras de IBM z/OS
combinadas con el soporte de hardware de zBC12 para páginas
de 2 GB. Se espera que estas ventajas sean especialmente útiles
para sectores como los mercados financieros, donde las
aplicaciones se actualizan continuamente.

- La tecnología IBM z Systems Parallel Sysplex permite niveles
de escalabilidad y disponibilidad superiores acoplando los
sistemas mainframe entre sí. El uso de la agrupación en clúster
de Parallel Sysplex hace que los grupos de servidores z Systems
estén diseñados para ofrecer una disponibilidad de hasta el
99,999 % a nivel de aplicación.

- Escalabilidad vertical: de 50 a más de 4900 millones de
instrucciones por segundo (MIPS) de propósito general en un
único espacio

- Escalabilidad horizontal: un único IFL del zBC12 puede
consolidar hasta 32 cores x86 (utilizando procesadores de la
serie Intel Sandy Bridge) o más de 400 en un único espacio.

- Escalabilidad interna: procesadores especializados,
procesadores criptográficos, hypervisores.

- Escalabilidad más allá de los límites tradicionales: cuando se
configura con el zBX, que soporta la integración de hasta
112 servidores distribuidos blade o DataPower XI50z4 



Podríamos montar una granja web con Servidores de torre PowerEdge T630 de Dell.
tienen un precio de 1107 euros cada uno y con las siguientes características:

- Rendimiento versátil y eficiente: disfrute de tiempos de respuesta rápidos con la gama de procesadores
Intel® Xeon® E5-2600 v4 más reciente, la memoria DDR4 y siete ranuras de E/S.

- Capacidad ampliada, funciones sin precedentes: gracias a la compatibilidad con hasta un 50 % más de discos duros que 
en las generaciones anteriores, el PowerEdge T630 ofrece nuevas funciones para pymes y oficinas remotas que realizan tareas
relacionadas con correo y mensajería, imágenes médicas, virtualización de servidores y escritorios y renderizado de gráficos
con presupuesto limitado. El T630, que admite hasta 32 discos duros de 2,5" o 18 de 3,5", puede almacenar más buzones de correo 
de mayor tamaño, lo que permite reducir drásticamente el coste por cada buzón. Las configuraciones de almacenamiento flexibles 
permiten satisfacer los requisitos exigentes de las cargas de trabajo, al mismo tiempo que la gran cantidad de 
espacio en las unidades permite la ampliación rentable en el servidor.

- Almacenamiento rápido, información rápida: hasta cuatro unidades de estado sólido PCIe NVMe Express Flash y el controlador RAID 
PowerEdge 12Gb (PERC9) opcional convierten al PowerEdge T630 en la opción idónea para una amplia gama de cargas de trabajo con mayores
necesidades de IOPS, incluidas bases de datos, planificación de recursos para empresas (ERP) y asistencia para la toma de decisiones.
Para acelerar todavía más las aplicaciones, el T630 ofrece la opción de aprovechar las ventajas de SanDisk® DAS Cache opcional para 
que el acceso a los datos sea aún más rápido. Las opciones de asignación de niveles de almacenamiento en servidor y RAID multimodo 
también ayudan a optimizar el almacenamiento virtual para VMware® vSAN™ y Espacios de almacenamiento de Microsoft.

Aceleración potente de la GPU: desde el renderizado de gráficos hasta la implementación de escritorios virtuales, la compatibilidad 
con hasta un máximo de cuatro aceleradores de GPU opcionales permite un rendimiento y una capacidad adicionales.

Montando una granja web con 20 de estos servidores, estaríamos llegando al rendimiento del Mainframe mencionado antes y con unos costes 
mucho más bajos

Funtes: 
https://www.quora.com/How-much-does-an-IBM-mainframe-cost
https://www-03.ibm.com/systems/es/z/hardware/zenterprise/zbc12.html
http://www.dell.com/es/empresas/p/poweredge-t630/pd



### Ejercicio 4.2

**Buscar información sobre precio y características de balanceadores hardware específicos. Compara las prestaciones que ofrecen unos y otros.**

Kemp ofrece balanceadores de cargga hardware y en su misma página web es posible la comparación de
sus productos. Hay uno que me ha llamado la atención pues es un balanceador desarrollado por Kemp 
y  Dell llamado LoadMaster R320 (producto desarrollado en 2013). 
Este balanceador incluye los últimos avances en balanceo de carga de Nivel 4 y 7, switching de contenido, aceleración SSL, switching de contenido 
en Nivel 7, caching, compresión, IPS, IP y persistencia de nivel 7.
Los comerciantes dicen: "LoadMaster R320 de KEMP permite a los clusters de centros de datos
distribuir de forma eficiente e inteligente el tráfico de la red entre los servidores de aplicaciones y la web. Una capa de optimización de recurso
 delante de los servidores de aplicaciones y de la infraestructura otorga a los administradores de TI mayor control para adaptarse a los cambios de
 la red y conseguir el mejor rendimiento de la infraestructura y de la web."
Las especificaciones son las siguientes:
Servers Supported: 1,000 Physical /1,000 Virtual
Max Balancer L4 Throughput Up To 7Gbps
Max Balancer L7 Throughput Up To 6.5Gbps
25,600,000 L4 Concurrent Connections
96,000 L7 (http) requests per second
2,600 SSL TPS (2K Keys)
8,000 SSL TPS (1K Keys)

A nivel hardware:
Intel Quad Core Processor
6 x GbE Auto-negotiating, Full Duplex Eth. Ports
2 x 10GbE SFP+ Ports
Solid State Drive (SSD)
8 GB RAM
Local admin via console/VGA and USB
Integrated Management NIC – iDRAC Enterprise
Dimensions: 434 x 642.3 x 42.8mm. Weight ~ 15.4lbs (7Kg)
Dual 350W Power Supplies

Aquí podemos encontrar más balanceadores de de carga Kemp con sus respectivas comparaciones:
https://kemptechnologies.com/es/server-load-balancing-appliances/product-matrix.html



### Ejercicio 4.3

**Buscar información sobre los métodos de balanceo que implementan los dispositivos
recogidos en el ejercicio 4.2.**

Métodos de balanceo de LoadMaster R320 de KEMP:

Su página web dice que "Todos nuestros loadmasters apoyan soluciones clave de Microsoft y son certificados. El soporte técnico de Kemp 
cuenta con muchos años de experiencia en la configuración y el balanceo de carga para las aplicaciones de Microsoft. KEMP Loadmaster cuenta
con plantillas de configuración para instalar fácilmente y optimizar el tráfico para cargas de trabajo de Microsoft."

Características de KEMP Load Balancer:

- Layer 4 and Layer 7 Load Balancing and Cookie Persistence
- SSL Offload/SSL Acceleration
- Application Acceleration: HTTP Caching, Compression & IPS Security 
- WAF - Web Application Firewall
- Global Server Load Balancing
- Edge Security Pack (Microsoft TMG Replacement)
- Application Health Checking
- Adaptive (Server Resource) Load Balancing
- Content Switching

En general los balanceadores de carga Kemp tienen diversas implementaciones para llevar a cabo el 
balanceo.



### Ejercicio 4.4:

**Instala y configura en una máquina virtual el balanceador
ZenLoadBalancer.**

Esta instalación y configuración ya la llevé a cabo para realizar la práctica 4 de SWAP.
A continuación se muestra el link con el repositorio donde explico cómo instalar y configurar 
ZEN (en el apartado Zen Load Balancer):

https://github.com/aliavc96/SWAP/blob/master/practicas/practica3/practica3.md


### Ejercicio 4.6

**Buscar información sobre los bloques de IP para los distintos
países o continentes.**

Aquí podemos obtener los rangos IP de las operadoras españolas:
https://www.redeszone.net/2011/01/25/listado-de-rangos-de-ip-utilizados-por-los-operadores-en-espana-ipv4/
Esta página web muestra a qué pais corresponde una determinada ip:
https://www.countryipblocks.net/paid-services-or-free-services


### Ejercicio 4.7

**Buscar información sobre métodos y herramientas paraimplementar GSLB**

Los balanceadores de carga KEMP pfrecen servicios y herramientas para implementar el balanceo de 
carga global.

Características de KEMP Load Balancer:

Layer 4 and Layer 7 Load Balancing and Cookie Persistence
SSL Offload/SSL Acceleration
Application Acceleration: HTTP Caching, Compression & IPS Security 
WAF - Web Application Firewall
**Global Server Load Balancing**
Edge Security Pack (Microsoft TMG Replacement)
Application Health Checking
Adaptive (Server Resource) Load Balancing
Content Switching

Link:
https://kemptechnologies.com/Balanceador-da-carga/
