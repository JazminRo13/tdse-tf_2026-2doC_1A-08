# **Nodo Wearable para Espacios Confinados**
## **Informe de Avance**

**FIUBA - Electrónica - Taller de Sistemas Embebidos**

**Trabajo Final - 2026, 2do cuatrimestre - Curso 1A, Grupo 08**

**Repositorio:** `tdse-tf_2026-2doC_1A-08`

| Padrón | Apellidos, Nombres | Fecha |
| :----- | :----------------- | :---: |
| 98214 (responsable de la entrega) | Romero, Federico | 20/11/2026 |
| 97182 | Romero, Jazmin | |
| 104364 | Santellan, Marino | |

A continuación se detalla el informe de avance del Trabajo Final a partir de los requisitos definidos en [propuesta.md](propuesta.md).

| Estado | Descripción |
| :----: | :---------- |
| 🟢 | Ya implementado |
| 🟡 | En proceso de implementarse |
| 🔴 | No se implementará |

---

## Requisitos funcionales

#### Sensado

| Req ID | Descripción | Estado |
| :----: | :---------- | :----: |
| RF-01 | **Monitoreo de temperatura.** El sistema deberá adquirir periódicamente la temperatura del entorno mediante el sensor LM35 y actualizar el valor disponible para su procesamiento. | 🟢 |
| RF-02 | **Detección de gases.** El sistema deberá adquirir una señal analógica mediante el sensor MQ-2, utilizada para detectar determinados gases combustibles y humo. | 🟢 |
| RF-05 | **Monitoreo inercial.** El sistema deberá adquirir datos de aceleración y velocidad angular mediante el módulo MPU-6050. | 🟡 |
| RF-15 | **Detección de fallas.** El sistema deberá identificar las fallas de adquisición o comunicación con los periféricos que puedan ser detectadas por el firmware y señalizar el estado de falla correspondiente. | 🟡 |

#### Procesamiento y alertas

| Req ID | Descripción | Estado |
| :----: | :---------- | :----: |
| RF-03 | **Detección de temperatura elevada.** El sistema deberá comparar la temperatura adquirida con un umbral configurado y generar una condición de alerta cuando se supere dicho valor. | 🟡 |
| RF-04 | **Detección de señal de gas elevada.** El sistema deberá comparar la señal analógica proveniente del MQ-2 con un umbral configurado y generar una condición de alerta cuando corresponda. | 🟡 |
| RF-06 | **Detección de inmovilidad.** El sistema deberá procesar los datos del MPU-6050 para identificar períodos prolongados de inmovilidad. Como parámetro inicial se establece un período de 30 segundos sin movimiento detectado para iniciar una secuencia de prealarma. La inmovilidad no constituirá por sí sola una confirmación de caída. | 🟡 |
| RF-07 | **Prealarma cancelable.** Ante la detección de una condición persistente de inmovilidad, el sistema deberá iniciar una prealarma de 15 segundos que permita al operario cancelar el evento mediante un botón. Si no se recibe una cancelación durante ese intervalo, se generará una alerta de emergencia. | 🟡 |
| RF-14 | **Gestión de eventos simultáneos.** El sistema deberá conservar y procesar los eventos de alerta detectados, evitando que una condición sobrescriba o descarte otra que también requiera atención. | 🟡 |

#### Señalización y comunicación

| Req ID | Descripción | Estado |
| :----: | :---------- | :----: |
| RF-08 | **Generación de alertas locales.** El sistema deberá señalizar visualmente los estados de funcionamiento y las condiciones de alerta mediante LEDs, y generar señales sonoras mediante un buzzer ante las condiciones de alarma definidas. La señalización visual deberá permitir distinguir el funcionamiento normal, las situaciones de prealarma, las alarmas activas y las fallas detectadas. | 🟡 |
| RF-09 | **Comunicación Bluetooth.** El sistema deberá transmitir información de estado y eventos relevantes mediante el módulo HM-10 hacia una aplicación externa, siempre que exista una conexión Bluetooth disponible. | 🟡 |
| RF-10 | **Visualización local.** El sistema deberá mostrar información de funcionamiento, mediciones y estados de alerta mediante una pantalla LCD. | 🟢 |

#### Configuración

| Req ID | Descripción | Estado |
| :----: | :---------- | :----: |
| RF-11 | **Selección de perfil de usuario.** El sistema deberá permitir seleccionar uno de los perfiles de usuario disponibles mediante el menú de configuración y cargar los parámetros asociados al perfil seleccionado. | 🟢 |
| RF-12 | **Configuración.** El sistema deberá permitir modificar los umbrales de temperatura y de señal analógica, así como los tiempos de detección de inmovilidad y de prealarma, correspondientes al perfil activo, mediante un menú interactivo accesible desde pulsadores y joystick. | 🟢 |
| RF-13 | **Persistencia de configuración.** El sistema deberá almacenar en la memoria Flash interna los parámetros de funcionamiento de cada perfil de usuario y el perfil activo, de modo que se conserven ante un reinicio. | 🟢 |

---

## Requisitos no funcionales

| Req ID | Descripción | Estado |
| :----: | :---------- | :----: |
| RNF-01 | **Arquitectura Bare Metal.** El firmware deberá ejecutarse sin sistema operativo, mediante una arquitectura basada en eventos. | 🟡 |
| RNF-02 | **Ejecución cíclica.** El sistema deberá implementar un ejecutor cíclico cuya vuelta principal tenga una duración inferior a 1 ms. | 🟡 |
| RNF-03 | **Temporización.** Se deberá implementar una base de tiempo de 1 ms mediante SysTick y su correspondiente callback. | 🟢 |
| RNF-04 | **No bloqueo.** Las tareas de adquisición, procesamiento, visualización y comunicación deberán implementarse de manera no bloqueante. | 🟡 |
| RNF-05 | **Modularidad.** El firmware deberá organizarse siguiendo la estructura Escrutar, Procesar y Actuar. | 🟡 |
| RNF-06 | **Máquinas de estado.** El funcionamiento deberá modelarse mediante máquinas de estado con interfaces explícitas para intercambiar información y eventos. | 🟡 |
| RNF-07 | **Bajo consumo.** El firmware deberá contemplar estrategias de bajo consumo, evitando la ejecución innecesaria del microcontrolador cuando no existan tareas pendientes, siempre que ello sea compatible con los requerimientos de temporización y adquisición del sistema. | 🟡 |
| RNF-08 | **Interacción.** El sistema deberá contar con un menú interactivo y al menos dos modos de operación diferenciados. | 🟢 |
| RNF-09 | **Integración de periféricos.** Se deberán utilizar interfaces de comunicación SPI y/o I2C para la conexión y gestión de los periféricos correspondientes. | 🟡 |
| RNF-10 | **Montaje.** Los componentes deberán integrarse sobre una placa base, sin utilizar protoboard ni cables Dupont. | 🟡 |
