# Ejercicios del tema 6

### Ejercicio 6.1 

**Aplicar con iptables una política de denegar todo el tráfico en una de las máquinas de prácticas.
Comprobar el funcionamiento. 
Aplicar con iptables una política de permitir todo el tráfico en una de las máquinas de prácticas.
Comprobar el funcionamiento.**

Para denegar el tráfico con **iptables** basta con aplicar estos comandos:
`iptables -P INPUT DROP`

`iptables -P OUTPUT DROP`

`iptables -P FORWARD DROP`

Para dejar pasar todo el tráfico basta con deshacernos de las reglas aplicadas en iptables:

`iptables -P INPUT ACCEPT`

`iptables -P OUTPUT ACCEPT`

`iptables -P FORWARD ACCEPT`

### Ejercicio 6.2

**Comprobar qué puertos tienen abiertos nuestras máquinas, su estado, y qué programa o 
demonio lo ocupa.**

Para ello podemos aplicar la siguiente orden: 
`sudo nmap localhost`
para ver los puertos abiertos (pero no a internet)
Para ver los puertos abiertoa hacia internet.

`sudo nmap IPSERVER`


### Ejercicio 6.3

**Buscar información acerca de los tipos de ataques más comunes en servidores web 
(p.ej. secuestros de sesión). Detallar en qué consisten, y cómo se pueden evitar.**

Uno de los ataques más comunes producidos es el ataque de denegación de servicio (DoS o DDoS):

"En seguridad informática, un ataque de denegación de servicio, también llamado ataque DoS (por
sus siglas en inglés), es un ataque a un sistema de computadoras o red que causa que un 
servicio o recurso sea inaccesible a los usuarios legítimos. Normalmente provoca la pérdida 
de la conectividad con la red por el consumo del ancho de banda de la red de la víctima
o sobrecarga de los recursos computacionales del sistema atacado. Un ejemplo notable de ello 
se produjo el 27 de marzo de 2013, cuando el ataque de una empresa a otra inundó la red de 
correos basura provocando una ralentización general de Internet e incluso llegó a afectar 
a puntos clave como el nodo central de Londres.
Los ataques DoS se generan mediante la saturación de los puertos con múltiples flujos de 
información, haciendo que el servidor se sobrecargue y no pueda seguir prestando su servicio.
Por eso se le denomina denegación, pues hace que el servidor no pueda atender a la cantidad 
enorme de solicitudes. Esta técnica es usada por los crackers o piratas informáticos para dejar 
fuera de servicio servidores objetivo.
Una ampliación del ataque DoS es el llamado ataque de denegación de servicio distribuido 
(DDoS por sus siglas en inglés) el cual se lleva a cabo generando un gran flujo de información 
desde varios puntos de conexión. La forma más común de realizar un DDoS es a través de una red
de bots, siendo esta técnica el ciberataque más usual y eficaz por su sencillez tecnológica."
 
Fuente: https://es.wikipedia.org/wiki/Ataque_de_denegaci%C3%B3n_de_servicio
