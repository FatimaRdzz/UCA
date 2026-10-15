
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

### Actividad 3.1
Figura explicando porque van en pares