# Sistema IoT de Control y Validación de Acceso para Vehículos de Movilidad Personal mediante Tecnología NFC y Computación en la Nube

## 1. Planteamiento del Problema

<p style="text-align: justify;">La transición hacia modelos de movilidad sostenible ha impulsado un incremento masivo en el uso de Vehículos de Movilidad Personal (VMP) —principalmente bicicletas y monopatines eléctricos— por parte de la comunidad estudiantil de la Universidad Industrial de Santander (UIS). No obstante, este cambio en la dinámica de transporte no estuvo acompañado por la modernización de los esquemas de supervisión, lo que dejó al descubierto una vulnerabilidad crítica en la infraestructura del campus. En la actualidad, el control en los puntos de acceso depende de registros manuales obsoletos o, en la mayoría de las porterías, de un esquema de nula verificación. Esta ineficiencia operativa genera cuellos de botella significativos durante las horas pico y convierte a las entradas en puntos propensos a la suplantación de identidad y al hurto sistemático de activos de alto valor económico.</p>

<p style="text-align: justify;">La raíz del problema excede la congestión peatonal y se sitúa en la ceguera operativa e institucional respecto a la trazabilidad de los vehículos. La universidad no cuenta con un sistema capaz de verificar en tiempo real si quien transporta una unidad es su legítimo propietario, ni de registrar con precisión los flujos de entrada, salida o préstamos autorizados entre usuarios. Los métodos tradicionales de vigilancia resultan ineficaces para prevenir el robo por sustitución de tarjetas o falsificación de comprobantes de propiedad, mientras que la falta de métricas sobre la permanencia de los vehículos dificulta la planificación de espacios de parqueo y la toma de decisiones fundamentadas dentro del concepto de Smart Campus. </p>


<p style="text-align: justify;">Para erradicar esta problemática, se plantea el desarrollo e implementación de un ecosistema IoT distribuido de control de acceso y trazabilidad en tiempo real. Esta solución integra hardware embebido de bajo consumo y alta precisión (ESP32-C6 y PN532), tecnología de identificación por radiofrecuencia (NFC) mediante etiquetas NTAG215 vinculadas criptográficamente al vehículo, y un entorno en la nube conectado a una aplicación móvil especializada para el personal de vigilancia. Al sustituir la validación manual por un carril exclusivo automatizado que comunica el lector físico con la app mediante Bluetooth Low Energy (BLE), el sistema contrarresta el error humano y despliega de forma instantánea la ficha digital del estudiante con su respectivo registro fotográfico. De este modo, la propuesta no solo elimina el riesgo de clonación y suplantación, sino que convierte una debilidad de seguridad en un modelo de gestión eficiente, seguro y escalable adaptado a las necesidades de la universidad.</p>


---

## 2. Objetivos del Proyecto

### 2.1. Objetivo General
Diseñar e implementar un sistema IoT distribuido de control de acceso y trazabilidad en tiempo real para Vehículos de Movilidad Personal (VMP) en la Universidad Industrial de Santander, integrando hardware embebido, tecnología NFC con validación criptográfica y una plataforma móvil conectada a la nube para mitigar los riesgos de suplantación y hurto en el campus.

### 2.2. Objetivos Específicos
* **Sustentación e Integración de Hardware:** Evaluar y configurar la arquitectura de hardware embebido basada en el SoC **ESP32-C6** y el módulo lector **PN532** bajo el protocolo I2C, garantizando alta precisión de lectura NFC, bajo consumo energético y tolerancia a interrupciones en tiempo real.
* **Desarrollo del Nodo Móvil de Control:** Construir una aplicación móvil nativa en **Android Studio** para el personal de vigilancia que permita la recepción de datos vía Bluetooth Low Energy (BLE) y la consulta instantánea a servicios en la nube para el despliegue de fichas de verificación visual.
* **Gestión de Datos y Trazabilidad:** Estructurar una base de datos relacional orientada a la gestión de expedientes digitales, garantizando la integridad de la información al vincular identificadores únicos de etiquetas NFC con perfiles estudiantiles, registros fotográficos y estados de movilidad (ingreso, salida, préstamo).
* **Seguridad y Criptografía Aplicada:** Implementar protocolos de autenticación y escritura estructurada mediante firmas digitales (HMAC) en las páginas de memoria de las etiquetas **NTAG215**, previniendo la clonación de transpondedores y asegurando la validación exclusiva de vehículos autorizados por la institución.

---
## 3. Seguimiento y Registro de Hallazgos Técnicos

### 3.1. Arquitectura de Hardware y Comunicación
Durante las fases iniciales de desarrollo, hemos consolidado la comunicación entre el **ESP32-C6** y el lector **PN532**. La elección del protocolo **I2C** fue estratégica: permite una transferencia de datos bidireccional utilizando únicamente dos hilos de datos (SDA en GPIO 21 y SCL en GPIO 22), lo que simplifica el diseño del circuito y reduce el ruido electromagnético.

Hemos validado que el ESP32-C6 ofrece una estabilidad superior en la gestión de interrupciones, lo cual es crítico cuando el sistema debe estar en "modo de escucha" constante esperando a que un usuario acerque su etiqueta NFC.

### 3.2. Análisis de Memoria en Etiquetas NTAG215
Uno de los hallazgos más relevantes en nuestra investigación técnica es la estructura de memoria de las etiquetas **NTAG215**. Estas etiquetas cuentan con 136 páginas de memoria (544 bytes en total):
* **Páginas de Sistema (0-3):** Bloqueadas para configuración de fábrica y almacenamiento del UID único.
* **Páginas de Usuario (4-129):** Es aquí donde reside el potencial de nuestro proyecto de grado. En lugar de usar la etiqueta como un simple ID pasivo, hemos diseñado un método para escribir datos específicos en estas páginas (4 bytes por página). Esto nos permite almacenar tokens de validación que el sistema verifica antes de consultar la base de datos, añadiendo una capa de seguridad física al dispositivo.

### 3.3. Integración con el Ecosistema Móvil
La aplicación desarrollada en Android Studio actúa como el puente humano del sistema. Al recibir el UID capturado por el hardware, la App realiza una consulta `GET/POST` hacia el servidor. Si el vehículo está registrado, la interfaz despliega automáticamente:
1. Nombre y código del estudiante.
2. Fotografía del propietario para verificación visual.
3. Características del vehículo (marca, color, serial).
4. Botones de acción para cambiar el estado (ej. marcar como "Salida" o "En Préstamo").

---

## 4. Proyecciones y Mejoras de Grado

Para que este proyecto alcance el estándar de excelencia exigido por los evaluadores de la UIS, hemos identificado tres ejes de mejora que se ejecutarán en las siguientes fases:

1. **Robustez ante Fallos de Red:** Actualmente, el sistema depende de una conexión constante. Implementaremos un modo de "almacenamiento local temporal" (Buffer) en el ESP32 para que, en caso de caída del Wi-Fi, los registros se guarden y se sincronicen automáticamente al recuperar la conexión.Queremos que los datos que va llevar el celador (nuestro verificador) sean llevados al sensor via bluethoot y que el id unico que sea reconocido en la señal la app sea la encargada de bajar toda la información de la nube.

2. **Cifrado de Datos en Memoria:** Elevaremos la seguridad pasando de una lectura de UID simple a un sistema de **Autenticación por HMAC** (Hash-based Message Authentication Code). Se escribirá una firma digital en las páginas de usuario de la NFC que solo nuestro código podrá descifrar, haciendo imposible que una tarjeta clonada gane acceso.

3. **Escalabilidad y Analítica de Datos:** La base de datos se optimizará para manejar grandes volúmenes de usuarios, permitiendo generar reportes estadísticos sobre las horas de mayor flujo y la duración promedio de estancia de los vehículos en el campus, datos de alto valor para la planeación administrativa de la universidad.**(Smart campus)**


![UIS](uis.jpg)
