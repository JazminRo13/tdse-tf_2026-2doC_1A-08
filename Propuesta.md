 <img src="https://github.com/user-attachments/assets/15600b18-f73b-4ba3-a959-47f0048a1ab6" alt="image2" width="50%">

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

La integración de funciones de monitoreo y alerta en un dispositivo personal constituye una oportunidad para desarrollar una solución portátil que facilite la identificación temprana de determinadas situaciones de riesgo.

### 1.2. Necesidad identificada

A partir de la problemática planteada, se identifica la necesidad de contar con medios que permitan reconocer oportunamente determinadas condiciones potencialmente peligrosas durante la realización de tareas en espacios confinados, advertir al trabajador ante dichas situaciones y facilitar la disponibilidad de información para el personal responsable de la supervisión.

Esta necesidad contempla dos aspectos complementarios:

- **Protección del operario:** disponer de información sobre determinadas condiciones del entorno y del estado de movimiento del trabajador, junto con mecanismos que permitan advertirle localmente ante situaciones de alerta.
- **Supervisión:** facilitar el acceso a información sobre los eventos detectados durante la tarea, de manera que pueda ser consultada por personal responsable cuando se encuentre disponible un medio de comunicación.

### 1.3. Proyecto seleccionado

Se propone desarrollar un **nodo wearable para el monitoreo y la alerta temprana de trabajadores en espacios confinados**.

El dispositivo integrará un sensor de temperatura, una entrada analógica destinada a simular una señal asociada a la presencia de gases y un sensor inercial. Un microcontrolador será responsable de adquirir y procesar la información, gestionar los estados del sistema y activar distintos mecanismos de señalización.

Además, contará con un enlace Bluetooth que permitirá transmitir información y alertas hacia una aplicación externa de recepción, siempre que el dispositivo receptor se encuentre dentro del alcance de comunicación.

El sistema contemplará las siguientes funcionalidades principales:

1. Monitorear la temperatura del entorno mediante un sensor analógico.
2. Simular la adquisición de una señal asociada a la presencia de gases mediante una entrada analógica.
3. Detectar períodos prolongados de inmovilidad mediante un sensor inercial.
4. Activar alertas locales visuales y sonoras ante las condiciones definidas.
5. Comunicar eventos relevantes a un dispositivo externo mediante Bluetooth.
6. Permitir la configuración de parámetros de funcionamiento mediante un menú interactivo y la selección de perfiles predefinidos mediante Dip Switches.
8. Almacenar la configuración para conservarla entre reinicios.

### 1.4. Objetivo general

Desarrollar un prototipo funcional de un dispositivo wearable capaz de adquirir y procesar información ambiental e inercial, detectar condiciones de alerta previamente definidas y generar respuestas locales y notificaciones hacia un dispositivo externo mediante una arquitectura de firmware basada en eventos y máquinas de estado.

### 1.5. Alcance del MVP

El prototipo comprenderá la integración del hardware, el desarrollo del firmware y la verificación funcional de las principales capacidades del sistema.

Se incluyen:

- Adquisición de temperatura mediante LM35.
- Simulación de una señal analógica de gases mediante un trimpot.
- Adquisición de aceleración y velocidad angular mediante MPU-6050.
- Detección de inmovilidad prolongada, con un tiempo inicial de 30 segundos, y generación de una prealarma cancelable de 15 segundos.
- Selección de perfiles de funcionamiento predefinidos mediante Dip Switches.
- Señalización mediante LEDs y buzzer.
- Visualización de información mediante LCD.
- Comunicación Bluetooth mediante HM-10.
- Configuración de parámetros mediante botones y joystick.
- Almacenamiento persistente de parámetros de configuración.
- Implementación de una arquitectura de firmware no bloqueante y orientada a eventos.

Quedan fuera del alcance de este MVP:

- La medición real de concentraciones de gases tóxicos.
- La medición de concentración de oxígeno.
- La validación del dispositivo para su utilización en operaciones industriales reales.
- La certificación del equipo para atmósferas explosivas.
- La implementación de una estación de supervisión industrial o infraestructura de comunicaciones de largo alcance.

---

## 2. Elicitación de requisitos y casos de uso

### 2.1. Actores involucrados

Se identifican los siguientes actores principales:

| Actor | Descripción |
|---|---|
| Operario | Usuario directo del dispositivo. Recibe información y alertas locales durante la simulación de una tarea en un espacio confinado. |
| Supervisor de Seguridad e Higiene | Puede recibir información y notificaciones transmitidas por Bluetooth mediante una aplicación externa, mientras se encuentre dentro del alcance del enlace. |
| Técnico o responsable de configuración | Interactúa con el menú SETUP para modificar los parámetros de funcionamiento del sistema. |

El personal de rescate se considera un actor indirectamente beneficiado por la disponibilidad de información sobre eventos detectados, aunque no interviene directamente en el funcionamiento del prototipo.

### 2.2. Requisitos funcionales

Los requisitos funcionales describen las acciones que deberá realizar el sistema.

| ID | Requisito | Descripción |
|---|---|---|
| RF-01 | Monitoreo de temperatura | El sistema deberá adquirir periódicamente la temperatura del entorno mediante el sensor LM35 y actualizar el valor disponible para su procesamiento. |
| RF-02 | Simulación de gases | El sistema deberá adquirir una señal analógica mediante un trimpot de 10 kΩ, utilizada para simular variaciones en una variable asociada a la presencia de gases. |
| RF-03 | Detección de temperatura elevada | El sistema deberá comparar la temperatura adquirida con un umbral configurado y generar una condición de alerta cuando se supere dicho valor. |
| RF-04 | Detección de señal de gas elevada | El sistema deberá comparar la señal analógica simulada con un umbral configurado y generar una condición de alerta cuando corresponda. |
| RF-05 | Monitoreo inercial | El sistema deberá adquirir datos de aceleración y velocidad angular mediante el módulo MPU-6050. |
| RF-06 | Detección de inmovilidad | El sistema deberá procesar los datos del MPU-6050 para identificar períodos prolongados de inmovilidad. Como parámetro inicial se establece un período de 30 segundos sin movimiento detectado para iniciar una secuencia de prealarma. La inmovilidad no constituirá por sí sola una confirmación de caída. |
| RF-07 | Prealarma cancelable | Ante la detección de una condición persistente de inmovilidad, el sistema deberá iniciar una prealarma de 15 segundos que permita al operario cancelar el evento mediante un botón. Si no se recibe una cancelación durante ese intervalo, se generará una alerta de emergencia. |
| RF-08 | Generación de alertas locales | El sistema deberá activar señales visuales y sonoras ante las condiciones de alarma definidas. |
| RF-09 | Comunicación Bluetooth | El sistema deberá transmitir información de estado y eventos relevantes mediante el módulo HM-10 hacia una aplicación externa, siempre que exista una conexión Bluetooth disponible. |
| RF-10 | Visualización local | El sistema deberá mostrar información de funcionamiento, mediciones y estados de alerta mediante una pantalla LCD. |
| RF-11 | Configuración | El sistema deberá permitir modificar los umbrales de temperatura y de señal analógica, así como los tiempos de detección de inmovilidad y de prealarma, mediante un menú interactivo accesible desde botones y joystick. |
| RF-12 | Persistencia de configuración | El sistema deberá almacenar los parámetros configurados en memoria no volátil, de modo que se conserven ante un reinicio. |
| RF-13 | Gestión de eventos simultáneos | El sistema deberá conservar y procesar los eventos de alerta detectados, evitando que una condición sobrescriba o descarte otra que también requiera atención. |
| RF-14 | Detección de fallas | El sistema deberá identificar las fallas de adquisición o comunicación con los periféricos que puedan ser detectadas por el firmware y señalizar el estado de falla correspondiente. |
| RF-15 | Selección de perfiles | El sistema deberá permitir seleccionar perfiles de funcionamiento predefinidos mediante los Dip Switches, utilizando la configuración correspondiente durante su operación. |

### 2.3. Requisitos no funcionales

Los requisitos no funcionales establecen restricciones y características de calidad del sistema.

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

### 2.4. Casos de uso

A continuación se describen los principales escenarios de interacción entre los actores y el sistema.

#### CU-01: Monitorear condiciones ambientales

**Actor principal:** Operario.

**Objetivo:** Detectar condiciones ambientales que superen los umbrales definidos para el funcionamiento del prototipo.

**Precondiciones:**
- El dispositivo se encuentra encendido.
- El sistema completó su inicialización.
- Los sensores y periféricos necesarios se encuentran disponibles.

**Flujo principal:**
1. El sistema adquiere periódicamente la temperatura mediante el LM35.
2. El sistema adquiere la señal analógica proveniente del trimpot.
3. Los valores obtenidos son procesados y comparados con los umbrales configurados.
4. Si las mediciones se encuentran dentro de los rangos establecidos, el sistema continúa en modo NORMAL.
5. Si alguna medición supera su umbral, el sistema genera el evento de alerta correspondiente.
6. El módulo de actuación activa la señalización visual y sonora.
7. El sistema actualiza la información mostrada en la pantalla LCD.
8. El sistema transmite la notificación correspondiente mediante Bluetooth, si existe una conexión disponible.

**Flujos alternativos:**
- Si la temperatura supera el umbral configurado, se genera una alerta por temperatura elevada.
- Si la señal analógica supera el umbral configurado, se genera una alerta por señal de gas elevada.
- Si ambas condiciones ocurren simultáneamente, el sistema deberá conservar y procesar ambos eventos.
- Si se detecta una falla de adquisición, el sistema deberá señalizar el error sin interpretar la medición inválida como una condición segura.

**Postcondiciones:**
- El evento queda identificado por el sistema.
- Las alertas correspondientes permanecen activas mientras persista la condición definida.
- La información del evento queda disponible para su comunicación externa.

#### CU-02: Detectar inmovilidad prolongada

**Actor principal:** Operario.

**Actor secundario:** Supervisor de Seguridad e Higiene.

**Objetivo:** Identificar una posible situación de emergencia asociada a la falta prolongada de movimiento del trabajador.

**Precondiciones:**
- El dispositivo se encuentra encendido y en modo NORMAL.
- El módulo MPU-6050 se encuentra operativo.

**Flujo principal:**
1. El sistema adquiere periódicamente información de aceleración y velocidad angular.
2. El firmware procesa las mediciones para identificar variaciones compatibles con movimiento.
3. Cuando se detecta una condición persistente de inmovilidad, se inicia el temporizador correspondiente.
4. Si la inmovilidad se mantiene durante el período configurado, inicialmente establecido en 30 segundos, se genera un evento de prealarma.
5. El sistema activa una señalización local que advierte al operario e inicia un temporizador de prealarma de 15 segundos.
6. Durante ese intervalo, el operario puede cancelar el evento mediante un botón.
7. Si el operario cancela la prealarma, el sistema registra la cancelación y retorna al monitoreo normal.
8. Si transcurren los 15 segundos sin recibir una cancelación, el sistema genera una alerta de emergencia.
9. El evento se comunica mediante Bluetooth al dispositivo externo, si existe una conexión disponible.

**Flujos alternativos:**
- Si se detecta movimiento antes de alcanzar el tiempo establecido, el temporizador de inmovilidad se reinicia.
- Si el operario cancela la prealarma, no se genera la alerta remota de emergencia asociada a ese evento.
- Si el enlace Bluetooth no se encuentra disponible, el sistema mantiene la alerta local y gestiona los intentos de transmisión de acuerdo con la política de reintentos definida.

**Postcondiciones:**
- El evento queda identificado como inmovilidad prolongada.
- Si no se cancela la prealarma, se genera una notificación de emergencia.
- El sistema continúa funcionando o permanece en el estado de alarma correspondiente.

#### CU-03: Configurar parámetros del dispositivo

**Actor principal:** Técnico o responsable de configuración.

**Objetivo:** Modificar los parámetros de funcionamiento del dispositivo.

**Precondiciones:**
- El dispositivo se encuentra encendido.
- El sistema permite acceder al modo SETUP.

**Flujo principal:**
1. El usuario ingresa al modo SETUP mediante la combinación de controles definida.
2. El sistema presenta el menú de configuración en la pantalla LCD.
3. El usuario navega por las opciones mediante el joystick.
4. El usuario selecciona el parámetro que desea modificar.
5. El sistema permite ajustar el valor mediante los controles disponibles.
6. El usuario confirma la modificación.
7. El sistema verifica que el valor ingresado se encuentre dentro del rango permitido.
8. El nuevo parámetro se almacena en memoria no volátil.
9. El sistema informa que la configuración fue guardada.
10. El usuario sale del modo SETUP y retorna al modo NORMAL.

**Flujos alternativos:**
- Si el valor ingresado no es válido, el sistema informa el error y solicita una nueva configuración.
- Si el usuario cancela la operación, se conserva el valor previamente almacenado.
- Si ocurre un error durante el almacenamiento, el sistema informa la falla y conserva, cuando sea posible, la última configuración válida.

**Postcondiciones:**
- Los parámetros quedan actualizados y almacenados.
- La nueva configuración se utiliza durante el funcionamiento normal del dispositivo.

#### CU-04: Recibir notificaciones del dispositivo

**Actor principal:** Supervisor de Seguridad e Higiene.

**Objetivo:** Recibir información y eventos detectados por el dispositivo wearable.

**Precondiciones:**
- El módulo HM-10 se encuentra operativo.
- Existe una aplicación externa conectada al dispositivo mediante Bluetooth.
- El dispositivo receptor se encuentra dentro del alcance del enlace.

**Flujo principal:**
1. La aplicación establece una conexión Bluetooth con el módulo HM-10.
2. El sistema wearable transmite información de estado y mediciones.
3. La aplicación recibe y presenta la información.
4. Ante una condición de alerta, el dispositivo transmite una notificación asociada al evento.
5. La aplicación identifica el tipo de evento recibido y lo presenta al supervisor.

**Flujos alternativos:**
- Si la conexión se interrumpe, el sistema continúa generando las alertas locales.
- Cuando la conexión vuelve a estar disponible, el sistema podrá reanudar la comunicación.
- Los intentos de transmisión deberán ser controlados para evitar bloqueos o retransmisiones indefinidas.

**Postcondiciones:**
- El supervisor dispone de la información transmitida por el dispositivo mientras el enlace se encuentra operativo.
  
#### CU-05: Seleccionar perfil de funcionamiento

**Actor principal:** Técnico o responsable de configuración.

**Objetivo:** Seleccionar un perfil predefinido para establecer parámetros de funcionamiento del dispositivo.

**Precondiciones:**
- El dispositivo se encuentra apagado o en una condición que permita actualizar el perfil de funcionamiento.
- Los Dip Switches se encuentran disponibles.

**Flujo principal:**
1. El usuario selecciona una combinación de Dip Switches correspondiente al perfil deseado.
2. El sistema lee el estado de los Dip Switches durante la inicialización.
3. El sistema identifica el perfil seleccionado.
4. El sistema carga los parámetros asociados al perfil.
5. El dispositivo inicia su funcionamiento utilizando la configuración seleccionada.

**Flujos alternativos:**
- Si la combinación seleccionada no corresponde a un perfil definido, el sistema utiliza un perfil predeterminado.
- Si ocurre un error durante la lectura de las entradas, el sistema señaliza la condición de falla correspondiente.

**Postcondiciones:**
- El sistema inicia su funcionamiento utilizando los parámetros del perfil seleccionado.
- 
---

## 3. Hardware

### 3.1. Hardware obligatorio

El desarrollo contempla los componentes obligatorios establecidos por la cátedra.

| Componente | Función dentro del sistema |
|---|---|
| NUCLEO-F103RB | Plataforma de desarrollo basada en el microcontrolador STM32F103RB. Ejecutará el firmware Bare Metal y gestionará los periféricos. |
| Dip Switches | Permitirán seleccionar perfiles de funcionamiento predefinidos mediante distintas combinaciones de sus posiciones. |
| Botones | Se utilizarán para confirmar acciones, cancelar prealarmas y navegar por las funciones del dispositivo. |
| LEDs | Proporcionarán señalización visual de los estados de funcionamiento y condiciones de alerta. |
| Buzzer | Generará alertas sonoras ante las condiciones de alarma definidas. |
| Módulo HM-10 | Permitirá la comunicación Bluetooth Low Energy con una aplicación externa para transmitir información y notificaciones. |
| Memoria no volátil | Permitirá almacenar los parámetros de configuración para conservarlos entre reinicios. Se propone utilizar una EEPROM externa. |
| Sensores analógicos | Se utilizarán para adquirir señales de temperatura y para simular una variable asociada a la presencia de gases. |

Para la interconexión de los componentes se utilizará una placa base con los módulos y conectores soldados. No se utilizarán protoboards ni cables Dupont.

### 3.2. Hardware adicional

Se proponen los siguientes componentes adicionales, sujetos a la aprobación de los docentes responsables:

| Componente | Función dentro del sistema | Interfaz |
|---|---|---|
| Sensor LM35 | Medición analógica de la temperatura del entorno. | ADC |
| Trimpot de 10 kΩ | Generación de una señal analógica variable para simular cambios en una variable asociada a la presencia de gases. | ADC |
| MPU-6050 | Adquisición de aceleración y velocidad angular para identificar movimiento e inmovilidad prolongada. | I2C |
| Joystick analógico | Navegación por las opciones del menú SETUP. | ADC |
| LCD 16x2 con interfaz I2C | Visualización de mediciones, estados y opciones de configuración. | I2C |

El sensor LM35 permitirá trabajar con una variable ambiental real, mientras que el trimpot permitirá simular diferentes niveles de una señal analógica para verificar la lógica de detección y generación de alarmas. Esta última implementación no constituye una medición real de concentración de gases.

El MPU-6050 incorpora un acelerómetro y un giroscopio de tres ejes. La información obtenida permitirá analizar patrones de movimiento y períodos prolongados de inmovilidad.

La pantalla LCD facilitará la interacción con el usuario, permitiendo visualizar los valores adquiridos, el estado del sistema y las opciones disponibles durante la configuración.

### 3.3. Interconexión del hardware

La placa NUCLEO-F103RB actuará como unidad central del sistema.

Se propone la siguiente distribución de interfaces:

- **ADC:** LM35, trimpot y joystick.
- **I2C:** MPU-6050, LCD y EEPROM externa.
- **UART:** módulo Bluetooth HM-10.
- **GPIO:** botones, Dip Switches, LEDs y buzzer.

Los periféricos que compartan una misma interfaz deberán administrarse mediante una lógica que evite conflictos de acceso. En particular, se deberá verificar la compatibilidad de las direcciones I2C de los dispositivos conectados al bus.

Las operaciones de adquisición y comunicación deberán implementarse sin bloquear la ejecución principal del firmware.

---

## 4. Programación

### 4.1. Programación obligatoria

El firmware se desarrollará en lenguaje C, utilizando una arquitectura Bare Metal, sin sistema operativo.

Se implementará un sistema orientado a eventos (*Event-Triggered System*), organizado de manera modular bajo el esquema:

- **Escrutar:** adquisición de información proveniente de sensores, entradas y periféricos.
- **Procesar:** evaluación de mediciones, condiciones de funcionamiento y eventos.
- **Actuar:** actualización de salidas, generación de alertas, visualización y transmisión de información.

La arquitectura deberá contemplar los siguientes elementos:

**Ejecutor cíclico y Super-Loop**

Se implementará un ejecutor cíclico basado en una estructura Super-Loop, cuya vuelta principal deberá tener una duración inferior a 1 ms.

La ejecución de las tareas no deberá depender de esperas activas ni de retardos bloqueantes. Las operaciones que requieran tiempos de espera deberán gestionarse mediante temporizadores y estados internos.

**Base de tiempo**

Se utilizará el SysTick del microcontrolador para generar una interrupción periódica cada 1 ms.

A partir de esta interrupción se actualizarán las referencias temporales utilizadas por las distintas tareas y se invocarán los mecanismos de temporización correspondientes mediante callbacks.

Las rutinas ejecutadas durante la interrupción deberán mantenerse acotadas, evitando realizar dentro de ellas operaciones extensas de adquisición, procesamiento o comunicación. Las tareas correspondientes serán gestionadas desde el ejecutor principal.

**Gestión no bloqueante de periféricos**

Los periféricos deberán gestionarse mediante polling no bloqueante, interrupciones o DMA, según corresponda.

En particular, se deberá evitar que las operaciones de comunicación I2C, UART y actualización de pantalla bloqueen el Super-Loop.

**Máquinas de estado**

Se propone organizar el funcionamiento del firmware mediante tres máquinas de estado principales:

1. **Máquina de estados de sensores:** administrará la adquisición de mediciones, el procesamiento inicial de los datos y la identificación de errores de comunicación o adquisición.
2. **Máquina de estados del sistema:** gestionará los modos de operación, la evaluación de condiciones y la generación de eventos.
3. **Máquina de estados de actuadores:** administrará las señales visuales y sonoras, la pantalla y las notificaciones transmitidas.

Las máquinas de estado intercambiarán información mediante estructuras de datos y eventos definidos explícitamente. De esta manera, se busca mantener la independencia entre los módulos y evitar dependencias directas innecesarias.

**Modos de operación**

Se contemplan los siguientes modos principales:

- **NORMAL:** adquisición y procesamiento continuo de información, evaluación de condiciones y actualización de las salidas.
- **SETUP:** navegación por el menú y modificación de parámetros de configuración.
- **ALARM:** gestión de las condiciones de alerta y activación de los mecanismos de señalización.
- **FAULT:** identificación y señalización de errores que comprometan el funcionamiento de alguno de los periféricos.

**Menú interactivo**

El menú permitirá modificar los parámetros necesarios para el funcionamiento del dispositivo, incluyendo los umbrales de temperatura y de señal analógica, el tiempo de detección de inmovilidad y la duración de la prealarma.

La selección inicial de perfiles de funcionamiento se realizará mediante los Dip Switches, cuyos estados serán leídos durante la inicialización del sistema.

**Bajo consumo**

Se contemplarán estrategias de bajo consumo mediante la reducción de actividad del microcontrolador cuando no existan tareas pendientes, siempre que ello sea compatible con los requerimientos de temporización y adquisición del sistema.

### 4.2. Programación adicional

Se propone incorporar las siguientes funcionalidades adicionales, sujetas a la aprobación de los docentes responsables:

**Rutina de debouncing mediante temporizadores decrecientes**

Se implementará un mecanismo de eliminación de rebotes para las entradas provenientes de los botones.

La rutina utilizará temporizadores decrecientes para validar los cambios de estado de las entradas, evitando que las oscilaciones eléctricas propias de los contactos mecánicos generen múltiples eventos ante una única pulsación.

**Detección de inmovilidad mediante MPU-6050**

Se desarrollará una rutina de procesamiento de datos inerciales para identificar períodos prolongados de inmovilidad.

El algoritmo utilizará información del acelerómetro y del giroscopio para distinguir períodos de movimiento de condiciones persistentes de inmovilidad. El tiempo inicial de detección de inmovilidad se establece en 30 segundos, mientras que la duración inicial de la prealarma se establece en 15 segundos. Ambos parámetros podrán modificarse desde el menú SETUP.

Estos valores constituyen parámetros preliminares de diseño y no umbrales normativos. La inmovilidad no será considerada por sí sola una confirmación de caída.

**Gestión de eventos y prioridades**

Se implementará un mecanismo de gestión de eventos que permita conservar las distintas condiciones de alerta detectadas.

En caso de producirse eventos simultáneos, el sistema deberá evitar que uno sobrescriba al otro. Asimismo, se establecerá una prioridad para las notificaciones de emergencia respecto de la transmisión periódica de información.

---

## 5. Estrategia de verificación inicial

La validación del prototipo se realizará mediante pruebas funcionales en un entorno controlado.

Se proponen las siguientes verificaciones:

| ID | Verificación | Criterio de aceptación |
|---|---|---|
| V-01 | Adquisición de temperatura | Obtener lecturas del LM35 y actualizar el valor disponible para procesamiento. |
| V-02 | Simulación de señal de gases | Variar el trimpot y comprobar que el sistema reconoce los cambios de la señal analógica. |
| V-03 | Alarma ambiental | Superar los umbrales configurados y verificar la activación de las señales visuales y sonoras correspondientes. |
| V-04 | Adquisición inercial | Obtener y procesar datos de aceleración y velocidad angular del MPU-6050. |
| V-05 | Detección de inmovilidad | Mantener el dispositivo sin movimiento durante el período configurado y verificar el inicio de la prealarma. |
| V-06 | Cancelación de prealarma | Accionar el botón correspondiente durante la prealarma y verificar que se cancela el evento. |
| V-07 | Alerta de emergencia | No cancelar la prealarma y verificar la activación de la alerta local y el intento de notificación Bluetooth. |
| V-08 | Comunicación Bluetooth | Verificar el establecimiento de la conexión y la recepción de mensajes en una aplicación externa. |
| V-09 | Configuración | Modificar parámetros mediante el menú y comprobar que los cambios se almacenan correctamente. |
| V-10 | Persistencia | Reiniciar el dispositivo y comprobar que se recuperan los últimos parámetros almacenados. |
| V-11 | Gestión de fallas | Interrumpir o simular la pérdida de comunicación con un periférico y verificar la señalización del estado de error. |
| V-12 | Ejecución del firmware | Verificar la ejecución no bloqueante de las tareas y el cumplimiento de los requisitos temporales establecidos por la cátedra. |
| V-13 | Gestión de eventos simultáneos | Generar dos condiciones de alerta simultáneas y verificar que ambas sean conservadas y procesadas por el sistema. |
| V-14 | Reinicio del temporizador de inmovilidad | Generar movimiento antes de alcanzar el tiempo configurado y verificar que el temporizador de inmovilidad se reinicia. |
| V-15 | Visualización local | Verificar que la pantalla LCD presenta correctamente las mediciones, los estados de funcionamiento y las condiciones de alerta. |
| V-16 | Comunicación interrumpida | Interrumpir el enlace Bluetooth durante una condición de alerta y comprobar que las alertas locales continúan funcionando sin bloquear el firmware. |

Las pruebas permitirán verificar el funcionamiento de los principales módulos y la integración entre hardware y firmware. Los resultados se utilizarán para identificar posibles errores y realizar los ajustes necesarios durante el desarrollo del prototipo.
