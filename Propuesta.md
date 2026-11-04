
<img src="https://www.fi.uba.ar/images/logo-fiuba.png" alt="Logo FIUBA" width="50%">

# Propuesta – Trabajo Final
## Prototipo MVP de Nodo Wearable para Espacios Confinados

### ¿Qué es un espacio confinado?

Se considera espacio confinado a un recinto que presenta dificultades para el ingreso y egreso de personas, no está diseñado para la ocupación continua y puede presentar condiciones ambientales peligrosas.

Algunos ejemplos son tanques, cisternas, cámaras subterráneas, pozos, silos y determinados conductos o recipientes industriales.

## 1. Selección del proyecto a implementar

### 1.1. Problemática

Los trabajos realizados en espacios confinados presentan riesgos asociados tanto a las condiciones ambientales como a las características físicas del entorno. Entre los principales peligros se encuentran la exposición a gases tóxicos, las concentraciones inadecuadas de oxígeno y los accidentes físicos que pueden provocar caídas o períodos prolongados de inmovilidad.

La problemática involucra distintos actores:

- **Operarios:** son quienes se encuentran expuestos directamente a los riesgos. Necesitan dispositivos que no dificulten su trabajo y que permitan advertirles de manera clara ante situaciones potencialmente peligrosas.
- **Responsables de Seguridad e Higiene y supervisores:** necesitan disponer de información sobre las condiciones del entorno y el estado del trabajador para mejorar la supervisión durante las tareas.
- **Equipos de rescate:** pueden beneficiarse de la disponibilidad de información sobre las condiciones del entorno y los eventos detectados ante una eventual situación de emergencia.
- **Empresas contratistas:** deben procurar equipamiento adecuado para sus trabajadores, considerando también las restricciones económicas asociadas a su adquisición.

### 1.2. Necesidad identificada

A partir de la problemática planteada, se identifica la necesidad de contar con medios que permitan reconocer oportunamente determinadas condiciones potencialmente peligrosas durante la realización de tareas en espacios confinados, advertir al trabajador ante dichas situaciones y facilitar la disponibilidad de información para el personal responsable de la supervisión.

Esta necesidad contempla dos aspectos complementarios:

- **Protección del operario:** disponer de información sobre determinadas condiciones del entorno y del estado de movimiento del trabajador, junto con mecanismos que permitan advertirle localmente ante situaciones de alerta.
- **Supervisión:** facilitar el acceso a información sobre las condiciones ambientales y los eventos detectados durante la tarea, de manera que pueda ser consultada por el personal responsable. Esto resulta especialmente relevante ante una eventual emergencia, ya que conocer las condiciones que originaron el incidente puede contribuir a planificar las acciones de asistencia o rescate antes de ingresar al espacio confinado, evitando exponer a otras personas a riesgos que aún no han sido identificados.

### 1.3. Objetivo del proyecto y resultados esperados

El objetivo del proyecto es desarrollar un prototipo funcional que permita monitorear determinadas condiciones ambientales y situaciones asociadas al estado de movimiento de un trabajador durante la realización de tareas en espacios confinados. Se busca identificar condiciones potencialmente peligrosas, generar alertas que adviertan sobre dichas situaciones y facilitar la disponibilidad de información para el personal responsable de la supervisión.

Como resultado, se espera obtener un prototipo integrado que permita:
- Adquirir y procesar información correspondiente a variables ambientales y de movimiento.
- Identificar condiciones que superen determinados umbrales o patrones de funcionamiento establecidos.
- Generar alertas ante las situaciones detectadas.
- Proporcionar información al usuario mediante mecanismos de visualización y señalización.
- Comunicar eventos relevantes a un dispositivo externo.
- Permitir la configuración de parámetros de funcionamiento y conservarlos entre reinicios.

### 1.4. Proyectos similares

A partir de la problemática y la necesidad identificadas, se plantean tres alternativas de solución para el monitoreo de trabajadores en espacios confinados. Estas alternativas contemplan diferentes configuraciones y alcances funcionales, que serán comparados para seleccionar la más adecuada para desarrollar en el marco del trabajo final.

1. **A1 – Sistema de monitoreo fijo:** equipos instalados en el espacio confinado para monitorear las condiciones ambientales y generar alertas.

2. **A2 – Equipo portátil de monitoreo:** dispositivo transportable por el trabajador que permite monitorear variables ambientales y generar alertas durante la realización de las tareas.

3. **A3 – Nodo wearable:** dispositivo integrado al equipamiento del trabajador que combina el monitoreo de variables ambientales, la detección de períodos prolongados de inmovilidad y la generación de alertas locales, con posibilidad de transmitir información a un dispositivo externo.

Para comparar las alternativas se definieron los siguientes criterios, considerando tanto las necesidades de protección y supervisión como la viabilidad de implementación. Los criterios seleccionados, junto con sus respectivas ponderaciones y descripciones, se presentan en la **Tabla 1.1**.

| Criterio | Ponderación | Descripción |
|---|---:|---|
| Protección del operario | 25 % | Capacidad de la solución para advertir sobre condiciones potencialmente peligrosas y situaciones que puedan comprometer la seguridad del trabajador. |
| Movilidad | 20 % | Facilidad para utilizar la solución durante el desplazamiento y la realización de tareas dentro del espacio confinado. |
| Supervisión remota | 20 % | Posibilidad de transmitir información sobre las mediciones, las condiciones detectadas y los eventos registrados hacia un dispositivo externo, de manera que el personal responsable pueda disponer de información relevante ante una situación de emergencia. |
| Viabilidad técnica | 15 % | Posibilidad de implementar la solución utilizando los recursos, conocimientos y componentes disponibles. |
| Complejidad de implementación | 10 % | Esfuerzo de diseño, desarrollo e integración requerido para implementar la alternativa. |
| Costo | 10 % | Costo estimado de los componentes y recursos necesarios para implementar la solución. |

*Tabla 1.1: Criterios de evaluación y ponderaciones de las alternativas.*

La ponderación de los criterios se estableció de acuerdo con su importancia relativa para el proyecto.

La **protección del operario** recibe el mayor peso (25 %), ya que constituye el propósito principal de la solución y se busca priorizar aquellas alternativas que permitan advertir oportunamente sobre situaciones potencialmente peligrosas.

La **movilidad** se pondera con un 20 %, dado que se considera importante que la solución pueda acompañar al trabajador durante la realización de sus tareas, sin depender exclusivamente de instalaciones fijas dentro del espacio confinado.

La **supervisión remota** recibe una ponderación del 20 %, debido a la importancia de disponer de información sobre las condiciones ambientales y los eventos detectados ante una eventual emergencia. Esta información puede contribuir a que el personal responsable evalúe la situación y planifique las acciones de asistencia o rescate antes de ingresar al espacio confinado, reduciendo la exposición a riesgos adicionales.

La **viabilidad técnica** recibe una ponderación del 15 %, debido a que la alternativa seleccionada debe poder implementarse utilizando los conocimientos, recursos y componentes disponibles en el marco del trabajo final.

Por último, la **complejidad de implementación** y el **costo** reciben un 10 % cada uno. Se consideran aspectos relevantes para la selección, aunque se prioriza obtener una solución funcional y técnicamente viable por sobre minimizar al máximo el esfuerzo de desarrollo o el presupuesto requerido.


Se utilizó una escala de valoración de 1 a 5, donde 1 representa una condición muy desfavorable y 5 una condición muy favorable. Para los criterios de complejidad y costo, una mayor puntuación representa una menor complejidad o un menor costo de implementación.

La puntuación final de cada alternativa se obtiene mediante la suma de los productos entre la valoración asignada a cada criterio y su ponderación correspondiente. Los resultados de esta evaluación se presentan en la **Tabla 1.2**.

| Criterio | Ponderación | A1 | A2 | A3 |
|---|---:|---:|---:|---:|
| Protección del operario | 25 % | 3 | 4 | 5 |
| Movilidad | 20 % | 1 | 4 | 5 |
| Supervisión remota | 20 % | 4 | 3 | 4 |
| Viabilidad técnica | 15 % | 3 | 4 | 4 |
| Complejidad de implementación | 10 % | 3 | 3 | 2 |
| Costo | 10 % | 3 | 4 | 2 |
| **Puntuación final** | **100 %** | **2,80** | **3,70** | **4,05** |

*Tabla 1.2: Comparación ponderada de las alternativas de proyecto.*

### 1.5. Selección del proyecto

A partir de la comparación realizada, se seleccionó la alternativa **A3 – Nodo wearable**, que obtuvo la mayor puntuación ponderada (4,05). Esta opción presenta ventajas en términos de movilidad y protección del operario, al integrar el monitoreo de variables ambientales con la detección de períodos prolongados de inmovilidad y la generación de alertas locales.

Si bien implica una mayor complejidad de implementación y un costo superior al de algunas de las alternativas consideradas, se considera técnicamente viable dentro del alcance académico del trabajo final.

De esta manera, el proyecto a desarrollar consiste en un prototipo de dispositivo wearable destinado al monitoreo de determinadas condiciones ambientales y situaciones asociadas al estado de movimiento de un trabajador en espacios confinados, con capacidad de generar alertas locales y transmitir información relevante a un dispositivo externo.

### 1.6. Alcance del MVP

El prototipo comprenderá la integración del hardware, el desarrollo del firmware y la verificación funcional de las principales capacidades del sistema.

Se incluyen:

- Adquisición de temperatura ambiental mediante un sensor LM35.
- Detección de gases combustibles y humo mediante un sensor MQ-2.
- Adquisición de aceleración y velocidad angular mediante un sensor MPU-6050.
- Detección de inmovilidad prolongada, con un tiempo inicial de 30 segundos, y generación de una prealarma cancelable de 15 segundos.
- Señalización visual mediante LEDs indicadores de estado y generación de alertas sonoras mediante un buzzer.
- Visualización de información mediante LCD.
- Comunicación Bluetooth de bajo consumo (BLE) mediante un módulo HM-10, para transmitir información y eventos detectados a un dispositivo externo.
- Configuración de parámetros de funcionamiento mediante pulsadores y joystick.
- Selección de perfiles de usuario mediante el menú de configuración, con cuatro perfiles disponibles y parámetros de funcionamiento independientes para cada uno.
- Almacenamiento persistente de los parámetros de configuración de cada perfil y del perfil activo mediante el uso de la memoria Flash interna del microcontrolador.

La utilización del sensor MQ-2 tendrá fines exclusivamente experimentales y de demostración. Este sensor permite detectar determinados gases combustibles y humo, pero no es suficiente para evaluar integralmente las condiciones atmosféricas de un espacio confinado. Una evaluación de este tipo requeriría incorporar sensores específicos para los distintos gases de interés, como oxígeno y monóxido de carbono, entre otros. Existen distintas tecnologías de detección, como los sensores electroquímicos, infrarrojos no dispersivos (NDIR) y catalíticos, cuya incorporación no se contempla en este MVP debido al mayor costo de estos componentes y a las limitaciones de alcance del proyecto. Asimismo, el MQ-2 presenta un consumo energético y requerimientos de calentamiento que representan limitaciones para la autonomía y portabilidad del dispositivo.

La tecnología Bluetooth se selecciona por su simplicidad de integración y por resultar adecuada para las pruebas de comunicación previstas en el prototipo. Sin embargo, su alcance limitado representa una restricción para una aplicación real en espacios confinados, especialmente cuando se requiere transmitir información hacia una estación de supervisión ubicada a mayor distancia. Como posible evolución del sistema, podría evaluarse la incorporación de tecnología LoRa, que permitiría establecer enlaces de comunicación de mayor alcance.

Quedan fuera del alcance de este MVP:

- La detección de gases distintos de aquellos a los que responde el sensor MQ-2, incluyendo la medición de concentración de oxígeno.
- La medición precisa y confiable de concentraciones de gases tóxicos.
- La validación del dispositivo para su utilización en operaciones industriales reales.
- La certificación del equipo para atmósferas explosivas.
- La implementación de una estación de supervisión industrial o infraestructura de comunicaciones de largo alcance.
- La implementación de un enlace de comunicación LoRa.

### 1.7. Diagrama en bloques

[Pendiente de incorporar el diagrama general del sistema, identificando el microcontrolador, los sensores, los periféricos de interacción, los actuadores y el módulo de comunicación Bluetooth.]


## 2. Elicitación de requisitos y casos de uso

En el mercado argentino existen diferentes soluciones comerciales orientadas al monitoreo de condiciones ambientales y a la protección de trabajadores en entornos industriales. Entre ellas se encuentran los detectores portátiles multigás, que permiten medir distintas variables atmosféricas y generar alertas ante condiciones potencialmente peligrosas. Algunos equipos incorporan también funciones de comunicación inalámbrica y detección de situaciones asociadas a la falta de movimiento del trabajador.

Como ejemplo puede mencionarse el **MicroRAE de Honeywell**, comercializado en Argentina por distribuidores especializados. Este dispositivo permite monitorear simultáneamente distintos gases, como oxígeno, gases combustibles, monóxido de carbono y sulfuro de hidrógeno. Además, incorpora una alarma configurable de hombre caído y opciones de conectividad inalámbrica para transmitir información y estados de alarma a sistemas externos.

Otra alternativa disponible es el **Hardkraft GM300**, un detector portátil que permite medir gases combustibles, monóxido de carbono, sulfuro de hidrógeno y oxígeno, con señalización visual y sonora ante condiciones de alerta.

Estas soluciones presentan funcionalidades similares a algunas de las contempladas en este proyecto y constituyen referencias del tipo de equipamiento utilizado en aplicaciones industriales. Sin embargo, el prototipo propuesto busca integrar y centralizar en un único dispositivo wearable distintos sensores y funcionalidades que habitualmente pueden encontrarse distribuidos en equipos o soluciones independientes. De esta manera, se plantea una solución que acompañe al trabajador durante la realización de sus tareas y permita combinar el monitoreo de variables ambientales, la detección de períodos prolongados de inmovilidad y la generación de alertas locales.

### 2.1. Requisitos funcionales

A partir de las necesidades identificadas y de los actores involucrados, se establecen los requisitos funcionales que describen las capacidades que deberá proporcionar el prototipo. La **Tabla 2.1** reúne estos requisitos, identificados mediante códigos únicos para facilitar su referencia durante el desarrollo y la evaluación del sistema. Su definición permite establecer de manera concreta qué funciones se espera implementar y cuáles deberán contemplarse en los casos de uso.

| ID | Requisito | Descripción |
|---|---|---|
| RF-01 | Monitoreo de temperatura | El sistema deberá adquirir periódicamente la temperatura del entorno mediante el sensor LM35 y actualizar el valor disponible para su procesamiento. |
| RF-02 | Detección de gases | El sistema deberá adquirir una señal analógica mediante el sensor MQ-2, utilizada para detectar determinados gases combustibles y humo. |
| RF-03 | Detección de temperatura elevada | El sistema deberá comparar la temperatura adquirida con un umbral configurado y generar una condición de alerta cuando se supere dicho valor. |
| RF-04 | Detección de señal de gas elevada | El sistema deberá comparar la señal analógica proveniente del MQ-2 con un umbral configurado y generar una condición de alerta cuando corresponda. |
| RF-05 | Monitoreo inercial | El sistema deberá adquirir datos de aceleración y velocidad angular mediante el módulo MPU-6050. |
| RF-06 | Detección de inmovilidad | El sistema deberá procesar los datos del MPU-6050 para identificar períodos prolongados de inmovilidad. Como parámetro inicial se establece un período de 30 segundos sin movimiento detectado para iniciar una secuencia de prealarma. La inmovilidad no constituirá por sí sola una confirmación de caída. |
| RF-07 | Prealarma cancelable | Ante la detección de una condición persistente de inmovilidad, el sistema deberá iniciar una prealarma de 15 segundos que permita al operario cancelar el evento mediante un botón. Si no se recibe una cancelación durante ese intervalo, se generará una alerta de emergencia. |
| RF-08 | Generación de alertas locales | El sistema deberá señalizar visualmente los estados de funcionamiento y las condiciones de alerta mediante LEDs, y generar señales sonoras mediante un buzzer ante las condiciones de alarma definidas. La señalización visual deberá permitir distinguir el funcionamiento normal, las situaciones de prealarma, las alarmas activas y las fallas detectadas. |
| RF-09 | Comunicación Bluetooth | El sistema deberá transmitir información de estado y eventos relevantes mediante el módulo HM-10 hacia una aplicación externa, siempre que exista una conexión Bluetooth disponible. |
| RF-10 | Visualización local | El sistema deberá mostrar información de funcionamiento, mediciones y estados de alerta mediante una pantalla LCD. |
| RF-11 | Selección de perfil de usuario | El sistema deberá permitir seleccionar uno de los perfiles de usuario disponibles mediante el menú de configuración y cargar los parámetros asociados al perfil seleccionado. |
| RF-12 | Configuración | El sistema deberá permitir modificar los umbrales de temperatura y de señal analógica, así como los tiempos de detección de inmovilidad y de prealarma, correspondientes al perfil activo, mediante un menú interactivo accesible desde pulsadores y joystick. |
| RF-13 | Persistencia de configuración | El sistema deberá almacenar en la memoria Flash interna los parámetros de funcionamiento de cada perfil de usuario y el perfil activo, de modo que se conserven ante un reinicio. |
| RF-14 | Gestión de eventos simultáneos | El sistema deberá conservar y procesar los eventos de alerta detectados, evitando que una condición sobrescriba o descarte otra que también requiera atención. |
| RF-15 | Detección de fallas | El sistema deberá identificar las fallas de adquisición o comunicación con los periféricos que puedan ser detectadas por el firmware y señalizar el estado de falla correspondiente. |

*Tabla 2.1: Requisitos funcionales del sistema.*

### 2.2. Requisitos no funcionales

Además de las funciones previstas, el prototipo deberá cumplir determinadas condiciones relacionadas con su arquitectura, funcionamiento e integración. La **Tabla 2.2** presenta los requisitos no funcionales, que establecen las restricciones técnicas y los criterios de implementación derivados de la consigna de la asignatura.

| ID | Requisito | Descripción |
|---|---|---|
| RNF-01 | Arquitectura Bare Metal | El firmware deberá ejecutarse sin sistema operativo, mediante una arquitectura basada en eventos. |
| RNF-02 | Ejecución cíclica | El sistema deberá implementar un ejecutor cíclico cuya vuelta principal tenga una duración inferior a 1 ms. |
| RNF-03 | Temporización | Se deberá implementar una base de tiempo de 1 ms mediante SysTick y su correspondiente callback. |
| RNF-04 | No bloqueo | Las tareas de adquisición, procesamiento, visualización y comunicación deberán implementarse de manera no bloqueante. |
| RNF-05 | Modularidad | El firmware deberá organizarse siguiendo la estructura Escrutar, Procesar y Actuar. |
| RNF-06 | Máquinas de estado | El funcionamiento deberá modelarse mediante máquinas de estado con interfaces explícitas para intercambiar información y eventos. |
| RNF-07 | Bajo consumo | El firmware deberá contemplar estrategias de bajo consumo, evitando la ejecución innecesaria del microcontrolador cuando no existan tareas pendientes, siempre que ello sea compatible con los requerimientos de temporización y adquisición del sistema. |
| RNF-08 | Interacción | El sistema deberá contar con un menú interactivo y al menos dos modos de operación diferenciados. |
| RNF-09 | Integración de periféricos | Se deberán utilizar interfaces de comunicación SPI y/o I2C para la conexión y gestión de los periféricos correspondientes. |
| RNF-10 | Montaje | Los componentes deberán integrarse sobre una placa base, sin utilizar protoboard ni cables Dupont. |

*Tabla 2.2: Requisitos no funcionales del sistema.*

### 2.3. Casos de uso

Una vez definidos los requisitos del sistema, se describen los principales escenarios de interacción mediante casos de uso. Se contemplan cuatro situaciones representativas: el monitoreo de las condiciones ambientales, la detección de inmovilidad prolongada, la selección de perfiles de usuario y configuración de parámetros y la recepción de notificaciones. Cada caso especifica los actores involucrados, las condiciones necesarias para su ejecución y los pasos que componen el escenario principal y sus posibles alternativas.

#### CU-01: Monitorear condiciones ambientales

| Elemento | Descripción |
|---|---|
| **Actor principal** | Operario. |
| **Objetivo** | Detectar condiciones ambientales que superen los umbrales definidos para el funcionamiento del prototipo. |
| **Precondiciones** | a) El dispositivo se encuentra encendido. b) El sistema completó su inicialización. c) Existe un perfil de usuario activo y sus parámetros de funcionamiento se encuentran cargados. d) Los sensores y periféricos necesarios se encuentran disponibles. |
| **Flujo principal** | a) El sistema adquiere periódicamente la temperatura mediante el LM35. b) El sistema adquiere la señal analógica proveniente del MQ-2. c) Los valores obtenidos son procesados y comparados con los umbrales configurados en el perfil activo. d) Si las mediciones se encuentran dentro de los rangos establecidos y no existen otras condiciones de alerta o falla, el sistema continúa en modo NORMAL y mantiene encendido el LED verde. e) Si alguna medición supera su umbral, el sistema genera el evento de alerta correspondiente. f) El módulo de actuación activa el LED rojo y el buzzer para señalizar la condición de alarma. El LED verde se apaga mientras exista una alarma activa. g) El sistema actualiza la información mostrada en la pantalla LCD. h) El sistema transmite la notificación correspondiente mediante Bluetooth, si existe una conexión disponible. |
| **Flujos alternativos** | a) Si la temperatura supera el umbral configurado, se genera una alerta por temperatura elevada. b) Si la señal analógica del MQ-2 supera el umbral configurado, se genera una alerta por superación del umbral de señal. c) Si ambas condiciones ocurren simultáneamente, el sistema deberá conservar y procesar ambos eventos. d) Si se detecta una falla de adquisición, el sistema deberá señalizar el error sin interpretar la medición inválida como una condición segura. |
| **Postcondiciones** | a) El evento queda identificado por el sistema. b) Las alertas correspondientes permanecen activas mientras persista la condición definida. c) La información del evento queda disponible para su comunicación externa. |

*Caso de uso CU-01 – Monitorear condiciones ambientales.*

#### CU-02: Detectar inmovilidad prolongada

| Elemento | Descripción |
|---|---|
| **Actor principal** | Operario. |
| **Objetivo** | Identificar una posible situación de emergencia asociada a la falta prolongada de movimiento del trabajador. |
| **Precondiciones** | a) El dispositivo se encuentra encendido y en modo NORMAL. b) Existe un perfil de usuario activo con sus parámetros de funcionamiento cargados. c) El módulo MPU-6050 se encuentra operativo. |
| **Flujo principal** | a) El sistema adquiere periódicamente información de aceleración y velocidad angular. b) El firmware procesa las mediciones para identificar variaciones compatibles con movimiento. c) Cuando se detecta una condición persistente de inmovilidad, se inicia el temporizador correspondiente. d) Si la inmovilidad se mantiene durante el período configurado en el perfil activo, inicialmente establecido en 30 segundos, se genera un evento de prealarma. e) El sistema apaga el LED verde, activa el parpadeo del LED rojo y genera una señal sonora mediante el buzzer para advertir al operario. Se inicia un temporizador de prealarma de acuerdo con el valor configurado, inicialmente establecido en 15 segundos. f) Durante ese intervalo, el operario puede cancelar la prealarma mediante un botón. g) Si el operario cancela la prealarma, el sistema registra la cancelación y retoma el monitoreo. La señalización se actualiza de acuerdo con las demás condiciones que permanezcan activas. h) Si transcurre el tiempo de prealarma sin recibir una cancelación, el sistema genera una alerta de emergencia. El LED rojo permanece encendido y se activa la señal sonora correspondiente. i) El evento se comunica mediante Bluetooth al dispositivo externo, si existe una conexión disponible. |
| **Flujos alternativos** | a) Si se detecta movimiento antes de alcanzar el tiempo establecido, el temporizador de inmovilidad se reinicia. b) Si el operario cancela la prealarma, no se genera la alerta de emergencia asociada a ese evento. c) La cancelación de la prealarma no deberá desactivar otras alarmas ambientales que permanezcan activas. d) Si el enlace Bluetooth no se encuentra disponible, el sistema mantiene la alerta local. |
| **Postcondiciones** | a) El evento queda identificado como inmovilidad prolongada. b) Si no se cancela la prealarma, se genera una notificación de emergencia. c) El sistema continúa monitoreando las condiciones del dispositivo y mantiene las señalizaciones correspondientes a los eventos activos. |

*Caso de uso CU-02 – Detectar inmovilidad prolongada.*

#### CU-03: Gestionar perfiles y parámetros de configuración

| Elemento | Descripción |
|---|---|
| **Actor principal** | Técnico o responsable de configuración. |
| **Objetivo** | Seleccionar un perfil de usuario y consultar o modificar los parámetros de funcionamiento asociados a dicho perfil. |
| **Precondiciones** | a) El dispositivo se encuentra encendido. b) El dispositivo dispone de cuatro perfiles de usuario, inicializados con parámetros predeterminados o previamente configurados. c) El sistema permite acceder al modo SETUP. |
| **Flujo principal** | a) El usuario ingresa al modo SETUP mediante los controles definidos. b) El sistema presenta el menú de configuración en la pantalla LCD. c) El usuario selecciona la opción de gestión de perfiles mediante el joystick. d) El sistema muestra los cuatro perfiles disponibles (Usuario 1, Usuario 2, Usuario 3 y Usuario 4), indicando cuál se encuentra activo. e) El usuario selecciona y confirma el perfil que desea utilizar. f) El sistema recupera los parámetros asociados al perfil seleccionado y lo establece como perfil activo. g) El sistema permite consultar los parámetros correspondientes al perfil activo. h) El usuario selecciona el parámetro que desea modificar y ajusta su valor mediante los controles disponibles. i) El usuario confirma la modificación. j) El sistema verifica que el valor ingresado se encuentre dentro del rango permitido. k) El nuevo parámetro se almacena en la memoria Flash interna, asociado al perfil activo. l) El sistema informa que la configuración fue guardada. m) El usuario sale del modo SETUP y retorna al modo NORMAL. |
| **Flujos alternativos** | a) Si el usuario cancela la selección de perfil, el sistema conserva el perfil que se encontraba activo. b) Si un perfil no posee una configuración previamente almacenada, el sistema utiliza los valores predeterminados definidos para ese perfil. c) Si el valor ingresado no es válido, el sistema informa el error y solicita una nueva configuración. d) Si el usuario cancela la modificación de un parámetro, se conserva el valor previamente almacenado. e) Si ocurre un error durante el almacenamiento, el sistema informa la falla y no confirma la actualización de la configuración. f) Si ocurre un error al recuperar los parámetros de un perfil, el sistema evita aplicar una configuración inválida. |
| **Postcondiciones** | a) El perfil seleccionado queda establecido como perfil activo. b) Los parámetros confirmados quedan actualizados y almacenados en la memoria Flash interna, asociados al perfil correspondiente. c) La configuración del perfil activo se utiliza durante el funcionamiento del dispositivo. d) Los parámetros de los demás perfiles permanecen sin modificaciones. |

*Caso de uso CU-03 – Gestionar perfiles y parámetros de configuración.*
#### CU-04: Recibir notificaciones del dispositivo

| Elemento | Descripción |
|---|---|
| **Actor principal** | Supervisor de Seguridad e Higiene. |
| **Objetivo** | Recibir información y eventos detectados por el dispositivo wearable. |
| **Precondiciones** | a) El módulo HM-10 se encuentra operativo. b) Existe una aplicación o herramienta externa de recepción conectada al dispositivo mediante Bluetooth. c) El dispositivo receptor se encuentra dentro del alcance del enlace. |
| **Flujo principal** | a) La aplicación o herramienta externa establece una conexión Bluetooth con el módulo HM-10. b) El sistema wearable transmite información de estado y mediciones. c) La aplicación o herramienta externa recibe y presenta la información. d) Ante una condición de alerta, el dispositivo transmite una notificación asociada al evento. e) La aplicación o herramienta externa identifica el tipo de evento recibido y lo presenta al supervisor. |
| **Flujos alternativos** | a) Si la conexión se interrumpe, el sistema continúa generando las alertas locales. b) Si el enlace vuelve a estar disponible y se restablece la comunicación, el sistema podrá reanudar la transmisión de información. |
| **Postcondiciones** | a) El supervisor dispone de la información transmitida por el dispositivo mientras el enlace se encuentra operativo. |

*Caso de uso CU-04 – Recibir notificaciones del dispositivo.*
