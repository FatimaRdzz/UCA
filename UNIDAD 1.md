### Actividad 1.1
¿Qué esperan aprender de esta materia?
 - Espero aprender sobre la configuración y la seguridad de las redes, ademas de sus complementos

### Actividad 1.2
- Considero que las redes son fundamentales, ya que en la actualidad interactuamos de manera casi exclusiva a través de ellas. nuestra vida cotidiana está fuertemente ligada a su uso. Además, en estas plataformas se gestiona información de gran relevancia, por lo que su pérdida ocasionaría graves contratiempos y dificultaría considerablemente nuestras actividades.

### ¿Que es una red computacional?
Una red computacional es un sistema complejo de intercambio de información, requiriendo una combinación de infraestructura física y reglas lógicas para una comunicación efectiva

### 5 pilares de una red computacional
Nodos: EL origen y el destino
- Dispositivos que envían y reciben datos dentro del ecosistema de la red

Enlaces: El camino físico
- Medios físicos o inalámbricos que establecen la conexión entre diferentes nodos

Direcciones: Identidad digital
- Identificadores de IP y MAC únicos que permiten localizar un dispositivo de origen y destino

Protocolos: El lenguaje comun
- Reglas estrictas de formato y sintaxis que rigen comunicacion entre dispositivos

Enrutamiento: Gestión de rutas
- Proceso de decision para determinar el camino más eficiente para los datos

### Nodos
Nodo 1:
- celular
- Computadora
- Audifonos
- Lavadora inteligente
- servidor 

(Direcciones)
- Ipv4
- MAC
- IP6

(Etheinel)

Nodo 2: 
- Celular
- computadora
- modem
- wiki mesh
- satelite

(Fibra optica)
- Monimodo: Distancias largas
- Multimodo: Servidores

Nodo 3:
- Antenas
- Servidor
- switch
- router

(Wifi)
- 5Mh2
- 3.5 gbps
- 2.4 Mhz
- 500 mbps

(bluethoot)
.

Nodo 4:
- Celular
- Computadora
- Lavadora inteligente
- Servidor 

(5G)

### 2 Enlaces: El camino físico

Medios Guiados (Con cables)

- **Cable de par trenzado:** El clásico cable de red (UTP/STP). Es **económico y flexible**, pero sufre interferencias a largas distancias.

- **Cable coaxial:** El cable de la televisión por cable. Tiene **buen blindaje** contra interferencias, pero es más rígido y costoso.

- **Fibra óptica:** Transmite datos mediante **pulsos de luz**. Ofrece la **máxima velocidad y distancia**, y es inmune a las interferencias eléctricas.

Medios No Guiados (Inalámbricos)

- **Ondas de radio:** Se propagan en todas direcciones. Ideales para **redes Wi-Fi y móviles**, pero son fáciles de interferir.

- **Microondas:** Viajan en línea recta (requieren visión directa entre antenas). Se usan para **enlaces satelitales** y torres de telefonía.

- **Infrarrojos:** Requieren alineación directa y distancias muy cortas (como el **control remoto** de la TV). No atraviesan paredes.

### 3 Direcciones: Identidad Digital
Direcciones
-IPv4
-IPv6
-DNS
### 4 Protocolos: El leguaje común 
- **1. Capa de Aplicación:** Es el nivel con el que interactúas directamente. Transforma tus acciones (como hacer clic en un enlace) en datos de red usando protocolos como **HTTP/HTTPS** (páginas web) o **SMTP** (correos).
- **2. Capa de Transporte:** Modula la conexión entre los dos puntos. Utiliza **TCP** si se requiere que los datos lleguen completos y sin errores (como un mensaje de texto), o **UDP** si se prioriza la velocidad inmediata (como una llamada de voz).
- **3. Capa de Internet:** Se encarga de la lógica de la ruta. Utiliza el protocolo **IP** para asignar direcciones a los dispositivos y decidir qué camino deben tomar los paquetes de datos para llegar a su destino.
- **4. Capa de Acceso a la Red:** Traduce los datos lógicos en impulsos físicos. Es la encargada de coordinar cómo el hardware (tarjetas de red, antenas) envía los bits a través de tecnologías como **Ethernet** (cable) o **Wi-Fi**.

### 5 Enrutamiento: Gestión de rutas

Conceptos Clave

- **Dirección IP de destino:** El router analiza cada paquete que le llega, lee la dirección IP hacia dónde va y decide a qué otra red enviarlo.
- **Tabla de enrutamiento:** Es el **mapa interno** que tiene cada router. Contiene una lista de rutas conocidas y las instrucciones de a dónde mandar los datos según su destino.
- **Métricas:** Son los criterios que usa el router para decidir cuál es el "mejor" camino. Puede ser la ruta **más corta**, la **más rápida** (con más ancho de banda) o la **menos saturada**.

## Actividad 1.4 

## 4 Características que deben tener las redes hoy en dia

Tolerancia a fallas: Es la capacidad de una red para seguir operando cuando falla un enlace o un dispositivo , sin que la comunicación se detenga por completo. 

Estabilidad en el software: Es la capacidad de una red para crecer (mas usuarios , mas dispositivos , mas servicios) 

Calidad de servicio:La calidad de servicio, es el conjunto de mecanismos que decide que trafico se atiende primero cuando la red no tiene capacidad suficiente para todo al mismo tiempo

Seguridad: Se refiere a proteger la red y la información que circula por ella contra accesos o interrupciones no autorizadas

Ataques mas comunes 

-Suplantacion de MAC/IP (Spoofing)
-Ataque de intermediario (man-in-the-middle)
-Acceso no autorizado a un punto de acceso inalambrico
-Pishing e ingenieria social

Arquitectura de redes: Una arquitectura de red es el conjunto de reglas y decisiones de diseño que definen como se organiza una red para que la comunicacion funcione

Modelos de referencia: Una red se diseña divido en capas independientes, donde cada capa resuelve un problema especifico 

 Modelo OSI 

1-Physical
2-Data Link
3- Network
4- Transport 
5- Session 
6- Presentation 
7- Application

Modelo TCP/IP

Aplicación
Genera el mensaje (HTTP, DNS, correo.)
La aplicación genera el mensaje original: por ejemplo, el cuerpo de una petición HTTP o un correo. Todavía no lleva ningún encabezado de red.

Transporte
Divide y numera segmentos (TCP/UDP)
La capa de transporte agrega su encabezado: define el puerto de origen y destino, y numera el segmento para poder reordenarlo después.

Internet
Agrega direcciones IP de origen y destino
La capa de internet agrega su encabezado: incluye la dirección IP de origen y de destino, la información que usará el router para decidir la ruta.

Acceso a la red
Agrega direcciones MAC y transmite como señal
La capa de acceso a la red agrega su encabezado: incluye la dirección MAC del siguiente salto y prepara los datos para convertirse en señal.

Acceso a la red
Agrega direcciones MAC y transmite como señal
El paquete viaja por el medio físico —cable, fibra u ondas de radio— y llega a la capa de acceso a la red del receptor, todavía completamente encapsulado.

Internet
Agrega direcciones IP de origen y destino. La capa de acceso a la red del receptor retira su encabezado y entrega el resto hacia arriba

Transporte
Divide y numera segmentos (TCP/UDP) La capa de internet del receptor retira su encabezado y lo entrega a la capa de transporte, que usará el número de puerto para identificar la aplicación correcta.

Aplicación
Genera el mensaje (HTTP, DNS, correo. La capa de transporte del receptor retira su encabezado. La aplicación recibe el mensaje original intacto: exactamente el mismo dato con el que empezamos en el emisor.

Encapsulamiento
Al bajar por las capas , cada una envuelve el dato con su propio encabezado ; al llegar al destino , el proceso se invierte y cada retira el encabezado que le corresponde


### Actividad 1.5

Arquitectura client  Servidor

¿Qué es?
Modelo de red donde las tareas se dividen entre los proveedores de recursos o servicios (servidores) y los demandantes (clientes). El cliente envía una petición y el servidor central responde

Pauta: El servidor gestiona los datos, la lógica de negocio y los permisos.

 Escalabilidad vertical: Para mejorr el rendimiento suele requerirse aumentar la capacidad del servidor

### P2P

Que es? Red descentralizada donde cada participante actúa simultáneamente como cliente y servidor, compartiendo recursos directamente sin pasar por un equipo central

Pautas
- No existe una entidad central que valide o controle las conexiones.

-La red sigue funcionando aunque se desconecten varios nodos.

### Blochchain

¿Qué es?
Registro compartido e inmutable formado por una cadena de bloques de datos protegidos criptográficamente distribuido a través de una red P2P

- La información no se almacena en un solo servidor central. Se distribuye en una red de computadoras llamadas **nodos**, donde cada una guarda una copia exacta del registro. 
- Inmutabilidad: Una vez que un dato o bloque se escribe en la cadena, no se puede borrar ni modificar. Para alterar un registro del pasado, se tendría que hackear simultáneamente a más de la mitad de los nodos de la red, lo que es computacionalmente inviable.
- Criptografía:Cada bloque de información se asegura mediante un código alfanumérico único llamado hash