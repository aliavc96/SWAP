# Ejercicios del tema 6

### Ejercicio 6.1 

**Aplicar con iptables una pol�tica de denegar todo el tr�fico en una de las m�quinas de pr�cticas.
Comprobar el funcionamiento. 
Aplicar con iptables una pol�tica de permitir todo el tr�fico en una de las m�quinas de pr�cticas.
Comprobar el funcionamiento.**

Para denegar el tr�fico con **iptables** basta con aplicar estos comandos:
`iptables -P INPUT DROP`

`iptables -P OUTPUT DROP`

`iptables -P FORWARD DROP`

Para dejar pasar todo el tr�fico basta con deshacernos de las reglas aplicadas en iptables:

`iptables -P INPUT ACCEPT`

`iptables -P OUTPUT ACCEPT`

`iptables -P FORWARD ACCEPT`

### Ejercicio 6.2

**Comprobar qu� puertos tienen abiertos nuestras m�quinas, su estado, y qu� programa o 
demonio lo ocupa.**

Para ello podemos aplicar la siguiente orden: 
`sudo nmap localhost`
para ver los puertos abiertos (pero no a internet)
Para ver los puertos abiertoa hacia internet.

`sudo nmap IPSERVER`


### Ejercicio 6.3

**Buscar informaci�n acerca de los tipos de ataques m�s comunes en servidores web 
(p.ej. secuestros de sesi�n). Detallar en qu� consisten, y c�mo se pueden evitar.**

Uno de los ataques m�s comunes producidos es el ataque de denegaci�n de servicio (DoS o DDoS):

"En seguridad inform�tica, un ataque de denegaci�n de servicio, tambi�n llamado ataque DoS (por
sus siglas en ingl�s), es un ataque a un sistema de computadoras o red que causa que un 
servicio o recurso sea inaccesible a los usuarios leg�timos. Normalmente provoca la p�rdida 
de la conectividad con la red por el consumo del ancho de banda de la red de la v�ctima
o sobrecarga de los recursos computacionales del sistema atacado. Un ejemplo notable de ello 
se produjo el 27 de marzo de 2013, cuando el ataque de una empresa a otra inund� la red de 
correos basura provocando una ralentizaci�n general de Internet e incluso lleg� a afectar 
a puntos clave como el nodo central de Londres.
Los ataques DoS se generan mediante la saturaci�n de los puertos con m�ltiples flujos de 
informaci�n, haciendo que el servidor se sobrecargue y no pueda seguir prestando su servicio.
Por eso se le denomina denegaci�n, pues hace que el servidor no pueda atender a la cantidad 
enorme de solicitudes. Esta t�cnica es usada por los crackers o piratas inform�ticos para dejar 
fuera de servicio servidores objetivo.
Una ampliaci�n del ataque DoS es el llamado ataque de denegaci�n de servicio distribuido 
(DDoS por sus siglas en ingl�s) el cual se lleva a cabo generando un gran flujo de informaci�n 
desde varios puntos de conexi�n. La forma m�s com�n de realizar un DDoS es a trav�s de una red
de bots, siendo esta t�cnica el ciberataque m�s usual y eficaz por su sencillez tecnol�gica."
 
Fuente: https://es.wikipedia.org/wiki/Ataque_de_denegaci%C3%B3n_de_servicio
