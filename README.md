RAT (Remote Administration Tool) using port-knocking. No TCP/UDP port listening.

++++++++ KNOCK-OUT ++++++++

Knock-Out es un programa con arquitectura Cliente/Servidor.
El servidor es el programa que estara analizando el trafico en ciertos
puertos especificados en el archivo de configuracion, dichos puertos
pueden estar abiertos o cerrados, ya que para tocar en ellos solamente
sera necesario enviar un paquete y no establecer una conexion completa
en el caso de TCP.

Una vez que se han tocado correctamente los puertos en el servidor,
este envia una shell a un puerto de la maquina de quien toco dichos
puertos(en caso de que el metodo sea "reverse" en la configuracion),
es decir, que el servidor lee los encabezados IP y reconoce de  donde
vienen las peticiones(toques a puertos).

En caso de que el metodo sea "bind", el servidor pone una shell en un
puerto local (lado del servidor) y asi cualquiera podra conectarse a
ese puerto e interactuar con la shell (con privilegios de root, por que
para correr el servidor, son necesarios privilegios de administrador).

Para tocar los puertos hay varias formas, una es utilizando el cliente
especialmente programado (knock-outc). Lee el archivo FORMA_DE_USO para
ver otras opciones.

Tanto cliente como servidor requieren de ciertas librerias, lee el
archivo REQUERIMIENTOS.

Finalmente, para construir los programas (cliente o servidor) lee las
instrucciones en el archivo COMPILACION.


++++++++ SUPPORTED PROTOCOLS ++++++++

+ Data Link
 - Ethernet
 - Linux Cooked

+ Network
 - IP

+ Transmision
 - TCP
 - UDP


++++++++ REQUIREMENTS ++++++++

[[[ SERVER ]]]
knock-outd requires libpcap

Debian based systems:
$sudo apt-get install libpcap-dev

Manual download and compilation:
http://www.tcpdump.org


[[[ CLIENT ]]]
knock-outc requires libnet

Debian based systems:
$sudo apt-get install libnet1-dev

Manual download and compilation:
https://sourceforge.net/projects/libnet-dev/
