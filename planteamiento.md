# Sistema IoT de Control y Validación de Acceso para Vehículos de Movilidad Personal mediante Tecnología NFC y Computación en la Nube

## 1. Planteamiento del Problema

<p style="text-align: justify;">En el contexto de la movilidad urbana sostenible, la Universidad Industrial de Santander (UIS) ha visto un incremento significativo en el uso de vehículos ligeros, como bicicletas y monopatines eléctricos, por parte de la comunidad estudiantil. Sin embargo, este crecimiento no ha venido acompañado de sistemas de control de acceso eficientes. Actualmente, el registro en los puntos de entrada suele ser manual o inexistente, lo que genera cuellos de botella en las horas pico y, lo más grave, una vulnerabilidad en la seguridad de los activos de los estudiantes.</p>

<p style="text-align: justify;">Nuestro proyecto surge de la necesidad de establecer un **carril exclusivo y automatizado** que no solo agilice el flujo vehicular y peatonal, sino que garantice la trazabilidad total de cada unidad, llevando un registro de entrada, salida e identificación en los puntos de control, proporcionando una seguridad más robusta, un historial de las unidades, métricas del flujo de estudiantes, control en el estado de los vehiculos que entran y salen de la univesidad. La problemática no es solo la entrada y salida, sino la falta de un mecanismo confiable para la gestión de préstamos entre usuarios y la verificación de identidad del propietario en tiempo real; el proyecto se plantea como un prototipado contruido desde la base por y para estudiantes acomplandolo a las necesidades y características de nuestra universidad y poniendo en práctivcas las habilidades aprendidas por los participantes. </p>


<p style="text-align: justify;">Para resolver esto, proponemos una solución basada en el **Internet de las Cosas (IoT)**. Utilizamos el microcontrolador **ESP32-C6** (de última generación con soporte para Wi-Fi 6) y el módulo **PN532** para crear un ecosistema de validación por **NFC** (Near Field Communication)**. A diferencia de los sistemas tradicionales, nuestra propuesta vincula una etiqueta física adherida al vehículo con un "expediente digital" en una base de datos relacional, accesible mediante una aplicación móvil personalizada. Esto permite que el personal de seguridad no solo vea un ID, sino una ficha técnica completa con fotografía del dueño y del vehículo, reduciendo a cero el margen de error por suplantación.</p>


---

## 2. Objetivos del Proyecto

### 2.1. Objetivo General
Diseñar y desarrollar un sistema IoT integral para la gestión, control y validación de acceso de bicicletas y monopatines en el campus de la UIS, mediante el uso de hardware embebido y una arquitectura de software distribuida (App-Servidor-Dispositivo).

### 2.2. Objetivos Específicos
* **Sustentación de Hardware:** Evaluar y seleccionar componentes electrónicos que equilibren costo y rendimiento, priorizando la eficiencia energética del ESP32-C6 y la precisión de lectura del módulo PN532 bajo el protocolo I2C.
* **Desarrollo de Arquitectura de Software:** Construir una aplicación móvil en **Android Studio** que funcione como el nodo de control para el personal de vigilancia, permitiendo la consulta instantánea de la base de datos tras cada escaneo.
* **Gestión de Datos Relacionales:** Estructurar una base de datos que garantice la integridad de la información, vinculando identificadores únicos (UID) de etiquetas NFC con perfiles de usuario, registros fotográficos y estados de movilidad (dentro/fuera/préstamo).
* **Seguridad y Encriptación (Proyección):** Implementar protocolos de escritura en las páginas de usuario de las etiquetas NTAG215 para evitar la clonación y asegurar que solo las etiquetas autorizadas por la institución sean reconocidas por el sistema.

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
