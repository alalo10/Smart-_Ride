# Formulario de Registro de Proyecto de Grado - UIS

## Título del Proyecto
**Desarrollo de un Prototipo de plataforma IoT para el control de acceso de vehículos de movilidad personal mediante tecnología NFC en el Smart Campus UIS**

---

## Objetivo General:
Desarrollar un prototipo de plataforma móvil IoT, compuesto por una aplicación con tecnología NFC y servicios en la nube de Smart Campus UIS, para implementar un sistema de control de acceso y trazabilidad en tiempo real de Vehículos de Movilidad Personal (VMP) en el campus central de la UIS.

---

## Objetivos Específicos:
* Identificar (o Definir?) los requerimientos funcionales y no funcionales del sistema de control de acceso mediante la recolección de especificaciones técnicas para la identificación de VMP y usuarios en el campus UIS.

* Diseñar la arquitectura integral del sistema IoT y el modelo de base de datos, integrando la tecnología NFC de los teléfonos móviles y los servicios en la nube para garantizar la gestión centralizada y la trazabilidad histórica de los registros de entrada y salida de los VMP en el campus.

* Desarrollar el prototipo funcional de la plataforma IoT, incluyendo lectura NFC, el backend en la nube y la interfaz móvil para materializar el control de acceso y el almacenamiento de los registros.

* Validación de la integración de la plataforma mediante el diseño de un plan de pruebas evaluando su desempeño en un entorno controlado de Smart Campus que simule el acceso de los VMP al campus UIS.

---

## Justificación y/o Planteamiento del problema:
A nivel global, la movilidad urbana sostenible ha experimentado una transformación acelerada; en América Latina, entre el 1% y el 5% de los viajes urbanos se realizan en medios no motorizados, mientras que en ciudades de referencia internacional como Copenhague o Ámsterdam este porcentaje supera el 30% (Ríos et al., 2015). En Colombia, este fenómeno se refleja con contundencia en capitales como Bogotá, donde se realizan más de 886.000 viajes diarios en bicicleta (equivalentes al 7,3% de los desplazamientos diarios), constituyéndose como un eje estratégico de transporte (Secretaría Distrital de Movilidad, 2024). A nivel local, en el Área Metropolitana de Bucaramanga se ha establecido como meta que para el año 2030 el 5% de los viajes urbanos se realicen en bicicleta (Área Metropolitana de Bucaramanga [AMB], 2018). Como preámbulo a la necesidad de justificar este proyecto, este crecimiento global y nacional impacta de forma directa a la comunidad estudiantil de la Universidad Industrial de Santander (UIS). No obstante, este cambio en la dinámica de transporte no estuvo acompañado por la modernización de los esquemas de supervisión, lo que dejó al descubierto una vulnerabilidad crítica en la infraestructura del campus. En la actualidad, el control en los puntos de acceso depende de registros manuales obsoletos. Esta ineficiencia operativa genera cuellos de botella significativos durante las horas pico y convierte a las entradas en puntos propensos a la suplantación de identidad y al hurto recurrente de estos vehículos.

El problema fundamental va más allá de las demoras en las porterías; radica en la carencia de control institucional sobre la trazabilidad de los vehículos de movilidad personal. La universidad no cuenta con un sistema capaz de verificar en tiempo real si quien transporta una unidad es su legítimo propietario, ni de registrar con precisión los flujos de entrada, salida o préstamos autorizados entre usuarios. Los métodos tradicionales de vigilancia resultan ineficaces para prevenir el robo por falsificación de comprobantes de propiedad, mientras que la falta de métricas sobre la permanencia de los vehículos dificulta la planificación de espacios de parqueo y la toma de decisiones fundamentadas dentro del concepto de Smart Campus.

Para erradicar esta problemática, se plantea el desarrollo de un ecosistema IoT distribuido de control de acceso y trazabilidad en tiempo real. Esta solución integra tecnología de identificación por radiofrecuencia (NFC) incorporada en los dispositivos móviles y etiquetas vinculadas al vehículo, a su vez, un entorno en la nube conectado a una aplicación móvil especializada para el personal de vigilancia. Al sustituir la validación manual por un sistema automatizado que comunica el lector NFC con la app mediante los servidores de la nube, el sistema contrarresta el error humano y desplegará de forma instantánea la ficha digital del estudiante con su respectivo registro fotográfico. De este modo, la propuesta no solo eliminará el riesgo de clonación y suplantación, sino que convertirá una debilidad de seguridad en un modelo de gestión eficiente y seguro.

Finalmente, el desarrollo de este prototipo contemplará una maqueta funcional, app, bases de datos, servicio en la nube y la comunicación entre un hardware NFC de teléfonos móviles, lo cual resultará de alto interés institucional para la Universidad Industrial de Santander. De acuerdo con registros de la División de Planta Física de la UIS, al campus ingresan diariamente entre 600 y 700 bicicletas (alcanzando picos de hasta 1.000 unidades en jornadas especiales) para una infraestructura de más de 400 biciparqueaderos (Universidad Industrial de Santander [UIS], 2022). Según nuestros cálculos estas cifras sugieren que entre un 2,5% y un 4,5% de la población estudiantil activa utiliza la bicicleta como medio de transporte habitual; no obstante, la institución carece de un sistema automatizado para consolidar datos exactos en tiempo real. Mediante la evaluación funcional de este prototipo, la universidad podrá validar la captura de métricas precisas sobre el flujo diario de Vehículos de Movilidad Personal (VMP). Esta toma de conciencia basada en datos reales representará un activo estratégico clave para fundamentar la toma de decisiones, planificar infraestructura de parqueo y promover campañas enfocadas en el bienestar institucional y la movilidad sostenible.


## Resultado y/o productos a entregar
1. **Aplicación Móvil Multiplataforma:** Solución móvil con autenticación basada en roles (estudiantes, personal de vigilancia y administrador) que incluye el módulo de control operativo para portería (lectura de etiquetas NFC, visualización de estados, fotos de propietario/vehículo y cambios de estado), el panel de usuario para estudiantes (consulta de perfil, estado de sus VMP y opción de préstamo) y el panel administrativo de gestión del sistema (lectura de etiquteas NFC y registro de usuarios).
2. **Entorno de Backend, Frontend y Base de Datos:** Infraestructura de servicios en la nube y repositorio de datos estructurado para la gestión centralizada de usuarios, vehículos y el almacenamiento histórico de los eventos de acceso.
3. **Informe Final de Proyecto de Grado:** Documentación técnica integral que consolida el análisis de requerimientos, la arquitectura del sistema, el diseño lógico, los resultados de las pruebas de validación y los manuales de operación.

---

## Actividades a Realizar
Teniendo en cuenta que planeamos hacer varios ciclos de análisis, diseño, desarrollo e implementación para corregir en cada ciclo cualquier falla posible, mejorar los sistemas desarrollados y llegar a un prototipo óptimo de nuestro proyecto, hemos elegido una metodología en espiral con el fin de hacer un control de riesgo. En cada ciclo analizaremos y reduciremos los peligros antes de avanzar al siguiente nivel, lo que nos permitirá un desarrollo iterativo en la construcción del software. De esta manera, podremos redefinir el diseño paso a paso mediante cambios flexibles, adaptarnos a nuevos requisitos posibles durante el proceso y realizar una revisión constante para asegurar el resultado. Finalmente, identificamos cuatro fases guía con sus respectivas actividades para llevar a cabo el proyecto:
1. **Fase 1: Análisis y Especificación de Requerimientos (Ciclo Inicial)**
   - Recolección de información: Levantamiento de los requerimientos funcionales y no funcionales actuales del control de acceso a VMP en el campus central de la UIS.
   - Especificación técnica: Definición de las características operativas, restricciones de hardware, conectividad y flujos de usuario (tanto para estudiantes como para el personal de vigilancia).
2. **Fase 2: Diseño de la Arquitectura y Modelado del Sistema (Ciclo de Diseño)**
   - Diseño de la arquitectura integral: Elaboración de los diagramas de bloques y esquemas de comunicación entre el hardware de captura, los servicios en la nube y la plataforma móvil.
   - Modelado de datos y seguridad: Diseño de la estructura lógica de la base de datos relacional y definición de los protocolos de identificación segura (etiquetas NFC y esquemas de autenticación).
3. ** Fase 3: Desarrollo e Integración de Componentes (Ciclo de Construcción)**
   - Construcción del backend y nube: Desarrollo de la infraestructura de servicios en la nube (API RESTful) y despliegue de la base de datos para la gestión centralizada.
   - Desarrollo de la aplicación multiplataforma: Creación de las interfaces móviles con autenticación por roles, integrando el panel de control operativo para vigilancia, el panel de gestión personal para estudiantes y el panel administrativo.
4. **Fase 4: Pruebas, Validación y Documentación (Ciclo de Evaluación)**
   - Pruebas de integración: Evaluación de la comunicación entre el hardware, la nube y la aplicación móvil midiendo los tiempos de respuesta y la estabilidad del sistema.
   - Validación en entorno controlado: Simulación de los escenarios de acceso, trazabilidad histórica y gestión de préstamos de VMP bajo condiciones similares a las del campus UIS utilizando una maqueta funcional y el entorno de Smart campus.
   - Entrega final: Consolidación de la memoria técnica, manuales de usuario y operación del prototipo.

---

## Palabras y/o Términos Clave
Arquitectura en la Nube, Autenticación por Roles, Control de Acceso, Internet de las Cosas (IoT), Movilidad Sostenible, Near Field Communication (NFC), Prototipo Funcional, Smart Campus, Trazabilidad, Vehículos de Movilidad Personal (VMP).

## Referencias
* Área Metropolitana de Bucaramanga. (2018). Estrategia de la bicicleta como medio de transporte para Bucaramanga y su Área Metropolitana. AMB. https://www.amb.gov.co/wp-content/uploads/Estrategia-de-la-Bicicleta-para-el-AMB-Publicada.pdf
* Ríos, R., Taddia, A. P., Pardo, C. F., & Lleras, N. (2015). Ciclo-inclusión en América Latina y el Caribe: Guía de diseño para fomentar el uso de la bicicleta. Banco Interamericano de Desarrollo (BID). https://doi.org/10.18235/0000164
* Secretaría Distrital de Movilidad. (2024, 3 de junio). Bogotá promueve la movilidad sostenible con más de 886.000 viajes diarios en bicicleta. Alcaldía Mayor de Bogotá. https://www.movilidadbogota.gov.co/noticias/bogota-promueve-la-movilidad-sostenible-con-mas-de-886000-viajes-diarios-en-bicicleta
* Universidad Industrial de Santander. (2022, 22 de junio). Nos "montamos" al Día sin Carro y sin Moto… En la UIS promovemos el uso de la "bici". Comunicaciones UIS. https://comunicaciones.uis.edu.co/nos-montamos-al-dia-sin-carro-y-sin-moto-en-la-uis-promovemos-el-uso-de-la-bici/
