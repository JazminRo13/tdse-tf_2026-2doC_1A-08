# Propuesta de Trabajo Final: Prototipo MVP de Nodo Wearable para Espacios Confinados

## 1. Selección del proyecto a implementar
El presente trabajo se basa en el desarrollo de un Producto Mínimo Viable (MVP) para un sistema de seguridad industrial (*wearable*) orientado a operarios que trabajan en espacios confinados. El sistema permite monitorear de forma local el estrés térmico del operario, simular la lectura de niveles de gases tóxicos, alertar mediante indicadores visuales y sonoros, registrar eventos en memoria, y transmitir el estado del operario de forma remota para supervisión.

## 2. Requisitos y Hardware del Proyecto

### Hardware Obligatorio & Adicional
* **Microcontrolador:** Placa NUCLEO-F103RB (STM32).
* **Entradas Digitales (Botones / Dip Switch):** Botón para confirmar alarmas locales, Dip Switch para seleccionar el perfil del usuario/operario.
* **Salidas Visuales / Sonoras:** LEDs (para indicar estado de pre-alerta y peligro), Display LCD 16x2 I2C (para mostrar datos críticos y menú local), Módulo Buzzer Activo.
* **Sensores Analógicos (ADC):** Módulo LM35 (temperatura térmica), Módulo Joystick (simula sensor inercial / "Hombre Caído"), Trimpot 10k (simula concentración de gas CO).
* **Comunicaciones (UART):** Módulo Bluetooth HM-10 (transmisión de telemetría a superficie, emulando enlace RF).
* **Almacenamiento (I2C/SPI):** Memoria externa E2PROM para *Data Logging* de eventos de alarma.

### Programación Obligatoria & Patrones
* Programación en lenguaje C Bare Metal (sin RTOS), basada en *Event-Triggered System*.
* Arquitectura basada en *Statecharts* (Modelos `Sensor`, `System`, `Actuator`), estructura Escrutar/Procesar/Actuar.
* Temporización estricta por *Super-Loop* y SysTick (Vuelta < 1ms), código 100% no bloqueante.
* Implementación de al menos dos modos de operación (ej. `ST_NORMAL`, `ST_ALARM`, `ST_SETUP`).
* *System Setup Menu* navegable mediante el joystick para calibrar los umbrales térmicos en campo.

## 3. Casos de Uso Principales

1. **Alerta de Estrés Térmico (Umbral ADC):** El sistema escruta continuamente el LM35. Si la temperatura supera el límite configurado (ej. 40°C), el `System` entra en estado `ST_ALARM`. Se ordena encender el LED rojo, el Buzzer y se muestra el aviso de peligro en el Display LCD. El evento queda almacenado con marca de tiempo relativa en la EEPROM.
2. **Detección de Hombre Caído (Joystick):** Si el eje X o Y del joystick sale del umbral de reposo durante un tiempo prolongado `tick` determinado (simulando que el operario está en el piso sin moverse), el sistema entra en pre-alarma sonando el buzzer. Si el operario no presiona el botón para cancelarlo antes del *timeout*, se envía la trama de auxilio vía Bluetooth HM-10.
3. **Calibración en Campo (Menú Setup):** Mediante una combinación del Dip Switch, el operario ingresa al modo `ST_SETUP`. A través del Display LCD y moviendo el joystick de forma vertical/horizontal, navega y ajusta el umbral de disparo de temperatura o sensibilidad de caída.
