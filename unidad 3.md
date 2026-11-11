
El ancho de banda, el rendimiento y la latencia se miden ==con herramientas específicas de red== que evalúan la capacidad teórica, la velocidad real de transferencia y el tiempo de respuesta de los datos. [

1. Ancho de banda (Capacidad máxima)

- **Qué es:** Es el límite teórico máximo de datos que pueden transmitirse por un enlace de red en un periodo determinado. 
- 
- **Cómo se mide:** Se expresa en bits por segundo (bps, Kbps, Mbps, Gbps). 
    - Se consulta directamente en los contratos del proveedor de internet o en las especificaciones del hardware (puertos del router, tarjetas de red).
    - Monitoreo de red con protocolos como **SNMP** (Simple Network Management Protocol)
1. Rendimiento (_Throughput_ o caudal efectivo)

- **Qué es:** Es la cantidad real de datos útiles que se transmiten o reciben con éxito a través de la red en un tiempo dado (considerando pérdidas, congestión y sobrecarga de protocolos). 
- **Cómo se mide:** Se expresa en unidades de velocidad por segundo (Mbps, Kbps). 
- **Herramientas de medición:**
    - **Test de velocidad en línea** (para medir la conexión a internet).
    - **iPerf** (o **iperf3**), que permite hacer pruebas de rendimiento real entre un equipo servidor y un cliente en la red local sin depender del tráfico externo del proveedor.
    - Herramientas técnicas de análisis como **PRTG Network Monitor** o **TTCP**. 

3. Latencia (_Ping_ o RTT - _Round Trip Time_)

- **Qué es:** Es el tiempo exacto que tarda un paquete de datos en viajar desde el origen hasta su destino y regresar. 
- **Cómo se mide:** Se expresa en **milisegundos (ms)**.
- **Herramientas de medición:**
    - El comando **`ping`** desde la consola del sistema operativo (enviando paquetes ICMP a una IP o dominio para ver el tiempo de ida y vuelta).
    - El comando **`traceroute`** (o `tracert`) para identificar la latencia y los saltos intermedios por los que pasa el paquete a través de los routers.
    - Plataformas continuas de monitoreo de red como **Kentik Synthetics**


### Como se mide su desempeño?
1. Pruebas de estrés y saturación (_Sustained Load Testing_)

Consiste en forzar la red al máximo para ver en qué punto se degrada el servicio.

- **Metodología:** Se generan flujos masivos de datos para ocupar todo el ancho de banda disponible (usando herramientas como **iPerf3**). Al mismo tiempo, se ejecutan pruebas de latencia (`ping`).
- **Qué se busca:** Identificar el fenómeno llamado **Bufferbloat** (cuando los routers acumulan paquetes en cola debido a la saturación, provocando que la latencia se dispare a cientos de milisegundos).

2. Monitoreo pasivo y activo (SaaS y SRE)

Las empresas no solo miden la red en un momento exacto, sino de forma constante.

- **Monitoreo Activo (Sintético):** Herramientas como **ThousandEyes** o **Datadog** envían paquetes artificiales de forma regular (cada minuto, por ejemplo) a servidores en la nube para medir latencia y rendimiento constante, simulando el comportamiento de un usuario.
- **Monitoreo Pasivo:** Analizadores de tráfico (como **Wireshark** o flujos de **NetFlow**) examinan el tráfico real de los usuarios en tiempo real para detectar caídas en el rendimiento o pérdida de paquetes sin interferir en la red.
- Simulación de escenarios reales

Se utilizan herramientas para recrear el comportamiento de aplicaciones críticas (como llamadas de Zoom, bases de datos o transferencias de archivos masivos). El desempeño se mide bajo el estándar del **Factor R** o **MOS (Mean Opinion Score)**, que califica numéricamente del 1 al 5 si la combinación de ancho de banda, rendimiento y latencia es óptima para la experiencia humana.

### Tipos de cable
cobre -> UTP -> señales -> RJ-45 -> 100 metris electricos
### Tipos de cable: cobre
El cable trenzado (UTP) transmite señales eléctricas con conector ==🔵***RJ-45,***=== alcanza hasta ==🟢***100 metros***=== y es el mas usado en LAN; trenzado reduce la interferencia

### UTP: ¿Por que los cables van en pares?
Los 8 hilos del UTP forman 4 pares trenzados. Cada par envía la señal con polaridad opuesta en sus dos hilos; la interferencia afecta a ambos por igual y el receptor la cancela al comparar los dos.

Cada par tiene un trenzado distinto para reducir la diafonía entre pares vecinos.

La fibra óptica transmite pulsos de luz: llega a mayores distancias y es inmune a la interferencia electromagnética, pero es más costosa y delicada de instalar.

### Medios inalambricos
Transmiten por ondas de radio (Wi-Fi, Bluetooth, celular); dan movilidad, pero el medio es compartido, sufre interferencia y requiere medidas de seguridad.

### Actividad 3.1
Figura explicando porque van en pares


20/07/2026
### Capa fisica
Es la primera capa del modelo OSI: transporta los bits como señales electricas, de luz o de radio a tráves del medio, sin interpretar el contenido

### Principios componentes
La capa fisica se comppone de tres elementos: los medios fisicos (cables, conectores y dispositivos), la codificación de los datos y la señalizacion que los transmite 

### Principio: parametros
Su desempeño se mide con tres parametros: el ancho de banda (capacidad máxima), el rendimiento (lo que se transfiere) y la latencia (el retardo en llegar)

### La capa fisica: señales de comunicación
Una señal es una variación de una propiedad física que representa bits: cambios de voltaje en cobre, pulsos de luz en fibra u ondas de radio en el aire

### Señalización y codificación física
La codificación convierte los bits en un patrón predefinido que facilita la sincronía y la detección de errores; la señalización define cómo se representa ese patrón en el medio

### Medios fisicos: conexion de la comunicación 
Un dispositivo se conecta mediante su tarjeta de red (NIC), un puerto, un conector y el medio; la NIC convierte los bits en la señal que el medio puede transportar

### Ethernet capa 1 y 2
Ethernet (IEEE 802.3) es el estándar dominante en LAN y trabaja en dos capas: en la capa 1 define medios y señalización, y en la capa 2 define las tramas y las direcciones MAC

### Envenenamiento ARP (ARP poisoning)

ARP no verifica quién responde: un atacante envía respuestas ARP falsas para que otros equipos asocien su MAC con la IP de otro dispositivo, por ejemplo la del router, y asíintercepta el tráfico (ataque de intermediario).

Se mitiga con inspección dinámica de ARP (DAI) en el switch y con entradas ARP estáticas en los equipos críticos

### ARP: de dirección IP a dirección MAC

El protocolo ARP permite descubrir la dirección MAC de un dispositivo a partir de su dirección IP. Envía una petición por broadcast; solo el dueño de esa IP responde por unicast, y el resultado se guarda en la tabla ARP
### Actividad 3.2
==🔵¿Por que los puntos de intercambio reducen la latencia?==
porque permiten que las redes intercambien tráfico de forma mas directa ya que se elimina largas distancias geográficas

==Campo 1==
Dato de ejemplo: 10101010 10101010 10101010 10101010 10101010 10101010 10101010 10101011 (8 bytes)

Nombre del campo: Padding (o relleno)

Para qué sirve: Sirve para completar el tamaño requerido de un bloque de datos o una estructura cifrada cuando la información original no alcanza los bytes necesarios. También se utiliza en redes para sincronización o para asegurar que los datos cumplan con una longitud estándar antes de ser procesados por un algoritmo

==🟣Campo 2==
Dato de ejemplo: FFFF.FFFF.FFFF (6 bytes)

Nombre del campo: Dirección MAC de destino (Destination MAC Address)

Para qué sirve: Sirve para enviar un mensaje a todos los dispositivos que se encuentran dentro de la misma red local para que todos la reciban y procesen

==🔴Campo 3==
Dato de ejemplo: 0001.4321.ABCD (6 bytes)

Nombre del campo: Dirección MAC de origen (Source MAC Address)

Para qué sirve: Identifica de manera única al dispositivo que está enviando la trama. Permite que el receptor sepa qn le mandó los datos y sepa a dónde responder

==🔵Campo 4==
Dato de ejemplo: 0x0806 (2 bytes)

Nombre del campo: Tipo / EtherType

Para qué sirve: Indica q protocolo de capa superior viene encapsulado dentro de la carga útil de la trama Ethernet. Esto ayuda al receptor a saber cómo procesar los datos que trae el paquete

==🟢Campo 5==
Dato de ejemplo: ¿Quién tiene la IP 192.168.1.2? Responde a 192.168.1.1 (entre 46 y 1500 bytes)

Nombre del campo: Datos / Carga útil (Payload / ARP Request)

Para qué sirve: Contiene la información que transporta la trama. En este caso una trama ARP, lleva la petición en texto preguntando qué dispositivo físico (MAC) corresponde a una determinada dirección IP dentro de la red local

==🔵Campo 6==
Dato de ejemplo: 0x3A7F91C2 (4 bytes)

Nombre del campo: FCS (Frame Check Sequence) / Código de redundancia cíclica (CRC)

Para qué sirve: Es un valor de verificación de errores de 4 bytes que se coloca al final de la trama Ethernet. Sirve para comprobar que los datos no se hayan corrompido o alterado durante la transmisión por el medio físico

---
Switch de capa 3

Además de conmutar por MAC, puede enrutar usando la dirección IP del paquete y su tabla de rutas, y conecta varias redes o VLAN entre sí.

Capa 2 frente a сара 3

Capa 2: lee la MAC, trabaja en una sola red, necesita un router para comunicar redes distintas y cuesta menos.

Capa 3: lee MAC e IP, conecta varias redes o VLAN, enruta por sí mismo y a alta velocidad, y cuesta más,

Ejemplo: de una red a otra

Un equipo de la red 192.168.1.0/24 quiere hablar con la 192.168.2.0/24. Con un switch de capa 2 hace falta un router; un switch de capa 3 mira la IP de destino y crea una trama nueva hacia la otra red

Reemplaza a un router?

No del todo: el router sigue siendo mejor para conectar con el exterior (WAN, Internet) y para funciones como NAT. El switch de capa 3 se usa en campus y centros de datos para enrutar entre VLAN a alta velocidad

### Fibra Óptica


Estructura MAC
Es un cable de vidrio o plástico muy delgado que transmite los datos como pulsos de luz en lugar de señales eléctricas

Es un cable de vidrio o plástico muy delgado que transmite los datos como pulsos de luz en lugar de señales eléctricas

La luz viaja por el núcleo y rebota en sus paredes por reflexión total interna, porque el revestimiento que lo rodea desvia la luz de vuelta hacia adentro

De adentro hacia afuera: el núcleo, que conduce la luz; el revestimiento, que la mantiene dentro; el recubrimiento, que protege el vidrio; y la cubierta exterior

Componentes de un enlace de fibra

Se necesita el cable de fibra con conectores en sus extremos y un transceptor (SFP) que convierte la señal eléctrica en luz; un convertidor de medios une equipos de cobre con la fibra.

Petch

Transceptores (SFP)

Es un módulo intercambiable que se inserta en el puerto del switch o router y convierte la señal eléctrica en luz y la luz en señal eléctrica; se elige según el tipo de fibra, la distancia y la velocidad

Tipos de transceptores

Por velocidad: SFP 1 Gbps, SFP+ 10 Gbps, SFP28 25 Gbps, QSFP+ 40 Gbps y QSFP28 100 Gbps.

Por fibra: SX para multimodo y LX para monomodo

Ventajas de la fibra óptica

Ofrece mucho ancho de banda, llega a mayores distancias, es inmune a la interferencia electromagnética y es más difícil de intervenir sin ser detectado

Desventajas de la fibra óptica

Los equipos y conectores cuestan más, la instalación y los empalmes requieren herramientas especializadas, y el cable es frágil si se dobla demasiado

Dónde se usa la fibra óptica

En el backbone de Internet, en los cables submarinos, en los enlaces entre edificios de un campus y en los centros de datos

UTP frente a fibra óptica

UTP: señal eléctrica, hasta 100 m, económico, sensible a la interferencia.

Fibra: pulsos de luz, desde cientos de metros hasta decenas de kilómetros, más costosa, inmune a la interferencia
### Dirección MAC
LA dirección MAC es la identificación de 48 bits que tiene cada tarjeta red y que sirve para identificar el origen del destino de una trama dentro de la LAN (capa 2)

### Para qué sirve la MAC
Los switches usan la MAC, para decidir porque puerto reenviar cada trama y construyen su tabal de direcciones aprendiendo la MAC de origen

### Estructura de la MAC
Los primeros 24 bits  (OUI) identifican el fabricante y los ultimos 

### La MAC puede cambiar

Viene grabada de fábrica en 

### Unicast, multicast y broadcast 
Según a cuántos equipos va dirigida, una comunicación puede ser unicast (a uno), multicast (a un grupo) o broadcast (a todos).

### Unicast: de uno a uno

La trama va a un solo destinatario, identificado por su MAC específica, es el tipo de tráfico más común, como abrir una página web o copiar un archivo

### Unicast en el switch
El switch busca la MAC de destino en su tabla de direcciones y envía la trama solo por el puerto donde está ese equipo; si no la conoce, la inunda por todos los puertos

### Multicast: de uno a un grupo
La trama de grupo de equipos que se unieron a él; los démas la ignoran. EN IPv4 usa direcciones 224.0.0.0 a 239.255.255 y MAC que empiezan con 01:00:5E

### broadcast: de uno a todo
La tarma llega a todos los equipos de la red, con MAC de destino FF:FF:FF:FF:FF:FF; todos la reciben y la procesan

### Para que sirve el unicast











![[Pasted image 20261105154811.png]]