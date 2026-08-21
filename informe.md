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
A nivel global, la movilidad urbana sostenible ha experimentado una transformación acelerada; en América Latina, entre el 1% y el 5% de los viajes urbanos se realizan en medios no motorizados, mientras que en ciudades de referencia internacional como Copenhague o Ámsterdam este porcentaje supera el 30% (Ríos et al., 2015). En Colombia, este fenómeno se refleja con contundencia en capitales como Bogotá, donde se realizan más de 886.000 viajes diarios en bicicleta (equivalentes al 7,3% de los desplazamientos diarios), constituyéndose como un eje estratégico de transporte (Secretaría Distrital de Movilidad, 2024). A nivel local, en el Área Metropolitana de Bucaramanga se ha establecido como meta que para el año 2030 el 5% de los viajes urbanos se realicen en bicicleta (Área Metropolitana de Bucaramanga [AMB], 2018). Como preámbulo a la necesidad de justificar este proyecto, este crecimiento global y nacional impacta de forma directa a la comunidad estudiantil de la Universidad Industrial de Santander (UIS). No obstante, este cambio en la dinámica de transporte no estuvo acompañado por la modernización de los esquemas de supervisión, lo que dejó al descubierto una vulnerabilidad crítica en la infraestructura del campus. En la actualidad, el control en los puntos de acceso depende de registros manuales obsoletos. Esta ineficiencia operativa genera cuellos de botella significativos durante las horas pico y convierte a las entradas en puntos propensos a la suplantación de identidad y al hurto recurrente de estos vehículos.

El problema fundamental va más allá de las demoras en las porterías; radica en la carencia de control institucional sobre la trazabilidad de los vehículos de movilidad personal. La universidad no cuenta con un sistema capaz de verificar en tiempo real si quien transporta una unidad es su legítimo propietario, ni de registrar con precisión los flujos de entrada, salida o préstamos autorizados entre usuarios. Los métodos tradicionales de vigilancia resultan ineficaces para prevenir el robo por falsificación de comprobantes de propiedad, mientras que la falta de métricas sobre la permanencia de los vehículos dificulta la planificación de espacios de parqueo y la toma de decisiones fundamentadas dentro del concepto de Smart Campus.

Para erradicar esta problemática, se plantea el desarrollo de un ecosistema IoT distribuido de control de acceso y trazabilidad en tiempo real. Esta solución integra hardware embebido de bajo consumo y alta precisión (ESP32-C6 y PN532), tecnología de identificación por radiofrecuencia (NFC) mediante etiquetas NTAG215 vinculadas criptográficamente al vehículo, y un entorno en la nube conectado a una aplicación móvil especializada para el personal de vigilancia. Al sustituir la validación manual por un carril exclusivo automatizado que comunica el lector físico con la app mediante Bluetooth Low Energy (BLE), el sistema contrarresta el error humano y despliega de forma instantánea la ficha digital del estudiante con su respectivo registro fotográfico. De este modo, la propuesta no solo elimina el riesgo de clonación y suplantación, sino que convierte una debilidad de seguridad en un modelo de gestión eficiente y seguro.

Finalmente, el desarrollo de este prototipo resulta de alto interés institucional para la Universidad Industrial de Santander. De acuerdo con registros de la División de Planta Física de la UIS, al campus ingresan diariamente entre 600 y 700 bicicletas (alcanzando picos de hasta 1.000 unidades en jornadas especiales) para una infraestructura de más de 400 biciparqueaderos (Universidad Industrial de Santander [UIS], 2022). Según nuestros cálculos estas cifras sugieren que entre un 2,5% y un 4,5% de la población estudiantil activa utiliza la bicicleta como medio de transporte habitual; no obstante, la institución carece de un sistema automatizado para consolidar datos exactos en tiempo real. Mediante la evaluación funcional de este prototipo, la universidad podrá validar la captura de métricas precisas sobre el flujo diario de Vehículos de Movilidad Personal (VMP). Esta toma de conciencia basada en datos reales representará un activo estratégico clave para fundamentar la toma de decisiones, planificar infraestructura de parqueo y promover campañas enfocadas en el bienestar institucional y la movilidad sostenible.


## Resultado y/o productos a entregar
1. **Módulo de Hardware de Captura NFC:** Prototipo funcional de hardware embebido configurado para la lectura de etiquetas NFC y transmisión de datos, diseñado con protección para entornos exteriores.
2. **Aplicación Móvil Multiplataforma:** Solución móvil con autenticación basada en roles (estudiantes y personal de vigilancia) que incluye el módulo de control operativo para portería (visualización de estados, fotos de propietario/vehículo, cambios de estado y gestión de préstamos) y el panel de usuario para estudiantes (consulta de perfil, estado de sus VMP y opción de préstamo).
3. **Plataforma de Backend y Base de Datos:** Infraestructura de servicios en la nube y repositorio de datos estructurado para la gestión centralizada de usuarios, vehículos y el almacenamiento histórico de los eventos de acceso.
4. **Sistema de Credenciales NFC:** Conjunto de etiquetas NFC inicializadas y configuradas con protocolos de seguridad para la identificación única de los VMP autorizados.
5. **Informe Final de Proyecto de Grado:** Documentación técnica integral que consolida el análisis de requerimientos, la arquitectura del sistema, el diseño lógico, los resultados de las pruebas de validación y los manuales de operación.

---

## Actividades a Realizar !!!
1. **Fase 1: Análisis y Especificación de Requerimientos (Ciclo Inicial)**
   - Recolección de información: Levantamiento de los requerimientos funcionales y no funcionales actuales del control de acceso a VMP en el campus central de la UIS.
   - Especificación técnica: Definición de las características operativas, restricciones de hardware, conectividad y flujos de usuario (tanto para estudiantes como para el personal de vigilancia).
2. **Diseño de la Arquitectura y Modelado del Sistema (Ciclo de Diseño)**
   - Diseño de la arquitectura integral: Elaboración de los diagramas de bloques y esquemas de comunicación entre el hardware de captura, los servicios en la nube y la plataforma móvil.
   - Modelado de datos y seguridad: Diseño de la estructura lógica de la base de datos relacional y definición de los protocolos de identificación segura (etiquetas NFC y esquemas de autenticación).
3. **Desarrollo e Integración de Componentes (Ciclo de Construcción)**
   - Implementación del hardware y credenciales: Configuración del módulo de captura NFC y parametrización de las etiquetas de identificación para los vehículos autorizados.
   - Construcción del backend y nube: Desarrollo de la infraestructura de servicios en la nube (API RESTful) y despliegue de la base de datos para la gestión centralizada.
   - Desarrollo de la aplicación multiplataforma: Creación de las interfaces móviles con autenticación por roles, integrando el panel de control operativo para vigilancia y el panel de gestión personal para estudiantes.
4. **Fase 4: Pruebas, Validación y Documentación (Ciclo de Evaluación)**
   - Pruebas de integración y latencia: Evaluación de la comunicación entre el hardware, la nube y la aplicación móvil midiendo los tiempos de respuesta y la estabilidad del sistema.
   - Validación en entorno controlado: Simulación de los escenarios de acceso, trazabilidad histórica y gestión de préstamos de VMP bajo condiciones similares a las del campus UIS.
   - Entrega final: Consolidación de la memoria técnica, manuales de usuario y operación del prototipo.

---

## Palabras y/o Términos Clave
Internet de las Cosas (IoT), NFC (Near Field Communication), ESP32-C6, PN532, NTAG215, Bluetooth Low Energy (BLE), Movilidad Sostenible, Smart Campus, Flutter, Control de Acceso, Criptografía Aplicada, HMAC.
