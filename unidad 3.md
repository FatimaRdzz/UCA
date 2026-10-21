
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


