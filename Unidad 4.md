### ==🟠CAPA DE RED Y DE TRANSPORTE==


### IPv4
IPv4 es el protocolo de la capa de red que direcciona y enruta los paquetes entre redes, usando direcciones de 32 bits (unos 4,300 millones en total).

==HISTORIA DE IPv4==
IPv4 se definio en 1981 (RFC 791) dentro de la familia TCP/IP, diseñada por Vint Cerf y Bob Kahn

EN 1983 ARPANET adopto TCP/IP, el origen de lo que hoy es internet

==🟢Cómo se agotaron las direcciones ==
Las 4,300 millones de direcciones parecían suficientes, pero se repartieron en bloques por clases: una Clase A daba más de 16 millones a una sola organización. Además, los dispositivos conectados crecieron sin parar.

En 2011 la IANA entregó sus últimos bloques a los registros regionales. Se alargó la vida de IPv4 con CIDR, las direcciones privadas y NAT; la solución definitiva es IPv6.

### IP publica
207.249.139.85
 
 **IP pública:** Es la dirección que identifica a tu red (a través de tu router) en todo **Internet**. Es única a nivel global, la asigna tu proveedor de servicios de internet (ISP) y es visible para las páginas o servicios externos a los que te conectas.
### IP privada 
172.26.35.100
 
 **IP privada:** Es la dirección que tu router le asigna a cada **dispositivo** (computadora, teléfono, televisión inteligente, impresora) dentro de tu red local o **LAN**. No es visible en Internet y los mismos números se pueden repetir en millones de hogares u oficinas diferentes.


### Características de IPv4
Es sin conexión(cada paquete viaja por separado), de mejor esfuerzo(no garantiza la entrega) e independientemente del medio (funciona sobre cobre; fibra o WI-fi)

### Encabezado IPv4
El encabezado mide 20 bytes como minimo y lleva la IP de origen, la IP de destino, el TTL (limite de saltos) y el campo protocolo (TCP)

### IPv6
Ipv6 usa direcciones de 128 bits y se creo pq las direcciones IPv4 se agotaron; permite un número práctimente ilimitado de dispositivos

### Historia IPv6
A inicios de los años 90 el IETF empezó a diseñar el reemplazo de IPv4 al prever que sus direcciones se agotarian.

Su especificación se publicó en 1995, se actualizó en 1998 (RFC 2460) y hoy está vigente en el RFC 8200 (2017).

La Evolución de las Direcciones IP:

### Cuantas direcciones tiene IPv6
Con 128 bits hay 2^128 direcciones: unos 340 sextillones (3.4 × 10^38), es decir, 2^96 veces más que IPv4.

### Ventajas de IPv6
Ventajas de IPv6

Ofrece un espacio de direcciones enorme, un encabezado simplificado de 40 bytes, autoconfiguración de direcciones y no usa broadcast: lo reemplaza el multicast.

### División de la red en grupos
Una red grande se divide en subredes: grupos de dispositivos organizados por ubicación, función o departamento, cada uno con su propio rango de direcciones.

### Por que dividir una red
Al dividir se reduce el tráfico de broadcast, mejora el rendimiento, se aplican políticas de seguridad por grupo y se facilita la administración.