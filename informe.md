# Formulario de Registro de Proyecto de Grado - UIS

## Título del Proyecto
**Desarrollo de un Prototipo de plataforma IoT para el Control de Acceso de Vehiculos de Movilidad personal en el campo UIS de Bucaramanga utiilizando Tecnología NFC y Arquitectura en la Nube**

---

## Objetivo General:
Desarrollar un prototipo de plataforma IoT que integre hardware embebido, tecnología NFC, plataforma móvil y servicio en la nube para control de acceso y trazabilidad en tiempo real para Vehículos de Movilidad Personal (VMP) en el campus central UIS.

---

## Objetivos Específicos:
* Analizar los requerimientos funcionales y no funcionales del sistema de control de acceso mediante la recolección de especificaciones técnicas para la identificación de VMP y usuarios en el campus UIS.

* Diseñar y definir la arquitectura integral del sistema IoT y el modelo de base de datos, integrando el hardware embebido, la tecnología NFC y los servicios en la nube para garantizar la gestión centralizada y la trazabilidad histórica de los registros de entrada y salida de los VMP en el campus.

* Desarrollar el prototipo funcional de la plataforma IoT, incluyendo el módulo de hardware embebido con lectura NFC, el backend en la nube y la interfaz móvil, para materializar el control de acceso y el almacenamiento de los registros.

* Validar el funcionamiento del prototipo de la plataforma IoT mediante pruebas de integración, latencia de comunicación y seguridad, evaluando su desempeño en un entorno controlado que simule el acceso de los VMP al campus UIS.

---

## Justificación y/o Planteamiento del problema:
La transición hacia modelos de movilidad sostenible ha impulsado un incremento masivo en el uso de Vehículos de Movilidad Personal (VMP) —principalmente bicicletas y monopatines eléctricos— BUSCAR DATOS INTERNACIONALES, DATOS NACIONALES, BUSCAR PREAMBULO A LA JUSTIFICACIÓN

por parte de la comunidad estudiantil de la Universidad Industrial de Santander (UIS). No obstante, este cambio en la dinámica de transporte no estuvo acompañado por la modernización de los esquemas de supervisión, lo que dejó al descubierto una vulnerabilidad crítica en la infraestructura del campus. En la actualidad, el control en los puntos de acceso depende de registros manuales obsoletos. Esta ineficiencia operativa genera cuellos de botella significativos durante las horas pico y convierte a las entradas en puntos propensos a la suplantación de identidad y al hurto recurrente de estos vehículos.

El problema fundamental va más allá de las demoras en las porterías; radica en la carencia de control institucional sobre la trazabilidad de los vehículos de movilidad personal. La universidad no cuenta con un sistema capaz de verificar en tiempo real si quien transporta una unidad es su legítimo propietario, ni de registrar con precisión los flujos de entrada, salida o préstamos autorizados entre usuarios. Los métodos tradicionales de vigilancia resultan ineficaces para prevenir el robo por falsificación de comprobantes de propiedad, mientras que la falta de métricas sobre la permanencia de los vehículos dificulta la planificación de espacios de parqueo y la toma de decisiones fundamentadas dentro del concepto de *Smart Campus*.

Para erradicar esta problemática, se plantea el desarrollo e implementación de un ecosistema IoT distribuido de control de acceso y trazabilidad en tiempo real. Esta solución integra hardware embebido de bajo consumo y alta precisión (**ESP32-C6** y **PN532**), tecnología de identificación por radiofrecuencia (NFC) mediante etiquetas **NTAG215** vinculadas criptográficamente al vehículo, y un entorno en la nube conectado a una aplicación móvil especializada para el personal de vigilancia. Al sustituir la validación manual por un carril exclusivo automatizado que comunica el lector físico con la app mediante Bluetooth Low Energy (BLE), el sistema contrarresta el error humano y despliega de forma instantánea la ficha digital del estudiante con su respectivo registro fotográfico. De este modo, la propuesta no solo elimina el riesgo de clonación y suplantación, sino que convierte una debilidad de seguridad en un modelo de gestión eficiente y seguro que, gracias a su diseño escalable, iniciará su despliegue en dos porterías estratégicas con la capacidad de expandirse progresivamente por toda la universidad.

Finalmente, la propuesta resulta de alto interés institucional para la Universidad Industrial de Santander, dado que se estima que entre el 2.5% y el 4.5% de la población estudiantil utiliza la bicicleta como medio de transporte habitual; no obstante, la institución no dispone de cifras exactas ni consolidadas al respecto. Con la implementación de este proyecto, la universidad podrá acceder a métricas precisas y en tiempo real sobre el flujo diario de vehículos de movilidad personal. Esta toma de conciencia basada en datos representará un activo estratégico clave para fundamentar la toma de decisiones, planificar infraestructura y promover actividades o campañas enfocadas en el bienestar institucional y el fomento de la movilidad sostenible.

## Resultado y/o productos a entregar
1. **Módulo de Hardware de Captura NFC:** Prototipo funcional de hardware embebido configurado para la lectura de etiquetas NFC y transmisión de datos, diseñado con protección para entornos exteriores.
2. **Aplicación Móvil Multiplataforma:** Solución móvil con autenticación basada en roles (estudiantes y personal de vigilancia) que incluye el módulo de control operativo para portería (visualización de estados, fotos de propietario/vehículo, cambios de estado y gestión de préstamos) y el panel de usuario para estudiantes (consulta de perfil, estado de sus VMP y opción de préstamo).
3. **Plataforma de Backend y Base de Datos:** Infraestructura de servicios en la nube y repositorio de datos estructurado para la gestión centralizada de usuarios, vehículos y el almacenamiento histórico de los eventos de acceso.
4. **Sistema de Credenciales NFC:** Conjunto de etiquetas NFC inicializadas y configuradas con protocolos de seguridad para la identificación única de los VMP autorizados.
5. **Informe Final de Proyecto de Grado:** Documentación técnica integral que consolida el análisis de requerimientos, la arquitectura del sistema, el diseño lógico, los resultados de las pruebas de validación y los manuales de operación.

---

## Actividades a Realizar !!!
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
5. **Fase 5: Integración Hardware, Software y Documentación**
   - Pruebas del sistema completo en entorno real (porterías del campus).
   - Evaluación del tiempo de respuesta y tolerancia a fallos de red.
   - Redacción de la memoria técnica y preparación de la sustentación final.

---

## Palabras y/o Términos Clave
Internet de las Cosas (IoT), NFC (Near Field Communication), ESP32-C6, PN532, NTAG215, Bluetooth Low Energy (BLE), Movilidad Sostenible, Smart Campus, Flutter, Control de Acceso, Criptografía Aplicada, HMAC.
