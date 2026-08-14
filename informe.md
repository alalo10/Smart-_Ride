# Formulario de Registro de Proyecto de Grado - UIS

## Título del Proyecto
**Sistema IoT de Control y Validación de Acceso para Vehículos de Movilidad Personal mediante Tecnología NFC y Computación en la Nube**

---

## Justificación y/o Planteamiento del problema
La transición hacia modelos de movilidad sostenible ha impulsado un incremento masivo en el uso de Vehículos de Movilidad Personal (VMP) —principalmente bicicletas y monopatines eléctricos— por parte de la comunidad estudiantil de la Universidad Industrial de Santander (UIS). No obstante, este cambio en la dinámica de transporte no estuvo acompañado por la modernización de los esquemas de supervisión, lo que dejó al descubierto una vulnerabilidad crítica en la infraestructura del campus. En la actualidad, el control en los puntos de acceso depende de registros manuales obsoletos o en la mayoría de las porterías, de un esquema de nula verificación. Esta ineficiencia operativa genera cuellos de botella significativos durante las horas pico y convierte a las entradas en puntos propensos a la suplantación de identidad y al hurto sistemático de activos de alto valor económico.

La raíz del problema excede la congestión peatonal y se sitúa en la ceguera operativa e institucional respecto a la trazabilidad de los vehículos. La universidad no cuenta con un sistema capaz de verificar en tiempo real si quien transporta una unidad es su legítimo propietario, ni de registrar con precisión los flujos de entrada, salida o préstamos autorizados entre usuarios. Los métodos tradicionales de vigilancia resultan ineficaces para prevenir el robo por falsificación de comprobantes de propiedad, mientras que la falta de métricas sobre la permanencia de los vehículos dificulta la planificación de espacios de parqueo y la toma de decisiones fundamentadas dentro del concepto de *Smart Campus*.

Para erradicar esta problemática, se plantea el desarrollo e implementación de un ecosistema IoT distribuido de control de acceso y trazabilidad en tiempo real. Esta solución integra hardware embebido de bajo consumo y alta precisión (**ESP32-C6** y **PN532**), tecnología de identificación por radiofrecuencia (NFC) mediante etiquetas **NTAG215** vinculadas criptográficamente al vehículo, y un entorno en la nube conectado a una aplicación móvil especializada para el personal de vigilancia. Al sustituir la validación manual por un carril exclusivo automatizado que comunica el lector físico con la app mediante Bluetooth Low Energy (BLE), el sistema contrarresta el error humano y despliega de forma instantánea la ficha digital del estudiante con su respectivo registro fotográfico. De este modo, la propuesta no solo elimina el riesgo de clonación y suplantación, sino que convierte una debilidad de seguridad en un modelo de gestión eficiente, seguro y escalable adaptado a las necesidades de la universidad.

Finalmente, es una propuesta interesante para la universidad debido a que en la universidad existe cerca de un 2.5% a un 4.5% del total de estudiantes que tienen una bicicleta pero la universidad no presenta una cifra exacta, con este proyecto pueden ver los datos exactos por día y pueden ser mas consientes de los datos que arroja y aprovecharlos para realizar mas actividades, campañas que sean para el beneficio de la universidad.

---

## Objetivo General
Diseñar e implementar un sistema IoT distribuido de control de acceso y trazabilidad en tiempo real para Vehículos de Movilidad Personal (VMP) en la Universidad Industrial de Santander, integrando hardware embebido, tecnología NFC con validación criptográfica y una plataforma móvil conectada a la nube para mitigar los riesgos de suplantación y hurto en el campus.

---

## Objetivos Específicos
* **Sustentación e Integración de Hardware:** Evaluar y configurar la arquitectura de hardware embebido basada en el SoC **ESP32-C6** y el módulo lector **PN532** bajo el protocolo I2C, garantizando alta precisión de lectura NFC, bajo consumo energético y tolerancia a interrupciones en tiempo real.
* **Desarrollo del Nodo Móvil de Control:** Construir una aplicación móvil desarrollada en **Flutter** para el personal de vigilancia que permita la recepción de datos vía Bluetooth Low Energy (BLE) y la consulta instantánea a servicios en la nube para el despliegue de fichas de verificación visual.
* **Gestión de Datos y Trazabilidad:** Estructurar una base de datos relacional orientada a la gestión de expedientes digitales en donde vamos a utilizar el lenguaje SQL, garantizando la integridad de la información al vincular identificadores únicos de etiquetas NFC con perfiles estudiantiles, registros fotográficos y estados de movilidad (ingreso, salida, préstamo).
* **Seguridad y Criptografía Aplicada:** Implementar protocolos de autenticación y escritura estructurada mediante firmas digitales (HMAC) en las páginas de memoria de las etiquetas **NTAG215**, previniendo la clonación de transpondedores y asegurando la validación exclusiva de vehículos autorizados por la institución.

---

## Resultado y/o productos a entregar
1. **Prototipo de Hardware Embebido:** Dispositivo físico integrado por un SoC ESP32-C6 y módulo lector NFC PN532 configurado con comunicación BLE e I2C, ensamblado dentro de un gabinete de protección apto para portería.
2. **Aplicación Móvil:** APK funcional desarrollada en Flutter para el personal de vigilancia, optimizada para recepción vía BLE, validación de firmas criptográficas HMAC, consultas HTTP RESTful y despliegue visual de fichas técnicas de propiedad.
3. **Servicio Cloud y Base de Datos Relacional:** Infraestructura en la nube con endpoints API RESTful y base de datos relacional configurada para la gestión de usuarios, vehículos, etiquetas NTAG215 e historial de eventos en tiempo real.
4. **Conjunto de Etiquetas NFC Programadas:** Juego de etiquetas NTAG215 inicializadas y firmadas criptográficamente con tokens de seguridad únicos.
5. **Documento Final de Grado:** Informe técnico detallado que incluye la arquitectura del sistema, esquemas de circuitos, modelo entidad-relación, pruebas de seguridad, métricas de rendimiento y manuales de usuario/operación.

---

## Actividades a Realizar
1. **Fase 1: Configuración e Integración de Hardware**
   - Configuración del microcontrolador ESP32-C6 e interfaz de comunicación I2C con el módulo PN532.
   - Programación del firmware para lectura de etiquetas NTAG215, manejo de interrupciones y transmisión BLE.
2. **Fase 2: Diseño e Implementación de la Base de Datos y Servicios Cloud**
   - Modelado de la base de datos relacional (usuarios, vehículos, UID, registros de acceso y estados).
   - Desarrollo e implementación de la API RESTful para la gestión de peticiones y sincronización de datos en tiempo real.
3. **Fase 3: Desarrollo de la Aplicación Móvil en Flutter**
   - Diseño de la interfaz de usuario (UI/UX) adaptada al flujo de trabajo del personal de vigilancia.
   - Implementación de módulos de comunicación BLE con el hardware y consumo de la API RESTful.
   - Integración de vistas para desplegar expedientes, fotografías y controles de cambio de estado.
4. **Fase 4: Implementación del Esquema de Seguridad Criptográfica**
   - Desarrollo del algoritmo de firma digital/HMAC y mapeo de la estructura de memoria en las páginas de usuario de la NTAG215.
   - Pruebas de resistencia a la clonación y validación de autenticidad en el hardware.
5. **Fase 5: Integración, Pruebas de Campo y Documentación**
   - Pruebas del sistema completo en entorno real (porterías del campus).
   - Evaluación del tiempo de respuesta y tolerancia a fallos de red.
   - Redacción de la memoria técnica y preparación de la sustentación final.

---

## Palabras y/o Términos Clave
Internet de las Cosas (IoT), NFC (Near Field Communication), ESP32-C6, PN532, NTAG215, Bluetooth Low Energy (BLE), Movilidad Sostenible, Smart Campus, Flutter, Control de Acceso, Criptografía Aplicada, HMAC.
