# Formulario de Registro de Proyecto de Grado - UIS

## Título del Proyecto
**Desarrollo de un Prototipo de plataforma IoT para el Control de Acceso de Vehiculos de Movilidad personal en el campo UIS de Bucaramanga utiilizando Tecnología NFC y Arquitectura en la Nube**

---

## Justificación y/o Planteamiento del problema
A nivel global, la movilidad urbana sostenible ha experimentado una transformación acelerada; en América Latina, entre el 1% y el 5% de los viajes urbanos se realizan en medios no motorizados, mientras que en ciudades de referencia internacional como Copenhague o Ámsterdam este porcentaje supera el 30%. En Colombia, este fenómeno se refleja con contundencia en capitales como Bogotá, donde se realizan más de 886.000 viajes diarios en bicicleta (equivalentes al 7,3% de los desplazamientos diarios), constituyéndose como un eje estratégico de transporte. A nivel local, en el Área Metropolitana de Bucaramanga se ha establecido como meta que para el año 2030 el 5% de los viajes urbanos se realicen en bicicleta. Este crecimiento global y nacional impacta de forma directa a la comunidad estudiantil de la Universidad Industrial de Santander (UIS). No obstante, este cambio en la dinámica de transporte no estuvo acompañado por la modernización de los esquemas de supervisión, lo que dejó al descubierto una vulnerabilidad crítica en la infraestructura del campus. En la actualidad, el control en los puntos de acceso depende de registros manuales obsoletos, lo que genera cuellos de botella significativos durante las horas pico y convierte a las entradas en puntos propensos a la suplantación de identidad y al hurto recurrente de estos vehículos.

El problema fundamental radica en la carencia de control institucional sobre la trazabilidad de los Vehículos de Movilidad Personal (VMP). La universidad no cuenta con un sistema capaz de verificar en tiempo real si quien transporta una unidad es su legítimo propietario, ni de registrar con precisión los flujos de entrada, salida o préstamos autorizados. Los métodos tradicionales de vigilancia resultan ineficaces para prevenir el robo por falsificación de comprobantes de propiedad. Además, la falta de métricas sobre la permanencia de los vehículos dificulta la toma de decisiones fundamentadas dentro del concepto de Smart Campus.

Para abordar esta problemática de manera técnica y económicamente viable, se plantea el desarrollo de un prototipo IoT distribuido de control de acceso. A diferencia de soluciones tradicionales que requieren inversiones masivas en hardware dedicado, este proyecto asegura su viabilidad presupuestal aprovechando los módulos de lectura NFC nativos de los dispositivos móviles del personal de vigilancia para leer etiquetas de bajo costo (NTAG215) adheridas a los VMP. El uso de la tecnología presente en los smartphones elimina la necesidad de microcontroladores externos, facilitando su adopción. El diseño de este ecosistema aborda una alta complejidad técnica al integrar tres pilares de investigación: 1) programación móvil de bajo nivel para escritura y validación criptográfica (HMAC) en etiquetas NFC, 2) arquitectura Cloud distribuida para soportar alta concurrencia, y 3) analítica de datos algorítmica para la predicción de flujos vehiculares. 

El desarrollo de este proyecto se enmarca en la construcción de un prototipo funcional. Este concepto de prototipado no reduce la complejidad del proyecto, sino que delimita su validación a una **prueba piloto rigurosa que constará de 50 usuarios activos y se desplegará en 2 porterías estratégicas** de la universidad. Esta muestra permitirá evaluar bajo estrés la latencia de red, la usabilidad para el celador y la seguridad del sistema. El impacto institucional es notable: de acuerdo con registros de la División de Planta Física de la UIS, al campus ingresan diariamente entre 600 y 700 bicicletas (alcanzando picos de 1.000 unidades) para una infraestructura de más de 400 biciparqueaderos. Esto sugiere que entre un 2,5% y un 4,5% de la población estudiantil utiliza VMP; sin embargo, la institución carece de un sistema para consolidar estos datos.

Dada la modalidad de Proyecto de Investigación, se formula la siguiente pregunta problema: **¿De qué manera el desarrollo y la implementación de un prototipo IoT, fundamentado en la validación criptográfica mediante tecnología NFC nativa de dispositivos móviles y servicios en la nube, optimiza la seguridad, el tiempo de registro y la trazabilidad operativa de los Vehículos de Movilidad Personal (VMP) en el campus central de la UIS?**

---

## Objetivo General
Desarrollar un prototipo de plataforma IoT que integre hardware embebido, tecnología NFC, plataforma móvil y servicio en la nube para control de acceso y trazabilidad en tiempo real para Vehículos de Movilidad Personal (VMP) en el campus central UIS.

---

## Objetivos Específicos
* **Desarrollo del Nodo Móvil y Criptografía NFC:** Construir una aplicación móvil nativa que utilice el hardware NFC de los smartphones para ejecutar operaciones de bajo nivel, implementando protocolos de autenticación y firma digital (HMAC) en las páginas de memoria de etiquetas NTAG215 para prevenir su clonación.
* **Diseño de la Arquitectura Cloud y Alta Concurrencia:** Estructurar una base de datos relacional y un backend en la nube mediante API RESTful que garantice la gestión centralizada, la integridad de los perfiles estudiantiles y la alta disponibilidad del sistema durante los picos de acceso peatonal.
* **Simulación Analítica y Smart Campus:** Implementar un motor analítico que transforme la trazabilidad histórica de los accesos en métricas operativas (flujos, tiempos de permanencia, congestión), presentadas en un dashboard administrativo.
* **Validación mediante Prueba Piloto (Metodología Espiral):** Evaluar el desempeño del sistema IoT mediante la ejecución de una prueba piloto controlada con 50 usuarios y 2 porterías del campus UIS, analizando la viabilidad técnica, los tiempos de respuesta del lector NFC del celular y la estabilidad de la red.

---

## Resultado y/o productos a entregar
1. **Aplicación Móvil Segura (Frontend NFC):** APK con módulos de lectura/escritura NFC de bajo nivel, manejo de firmas criptográficas (HMAC), capacidades offline-first y autenticación basada en roles (Vigilante/Estudiante).
2. **Infraestructura Cloud y Base de Datos (Backend):** Entorno de servicios desplegado en la nube con endpoints de alta concurrencia y modelo de datos relacional para el historial de trazabilidad de VMP.
3. **Plataforma Analítica Smart Campus:** Dashboard web interactivo para la visualización de métricas de flujo vehicular, horas pico y tiempos de estancia dentro del campus.
4. **Prueba Piloto y Documento Final:** Documento técnico de grado que incluye el análisis de la prueba piloto (50 usuarios en 2 porterías), resultados de la metodología espiral, diseño arquitectónico, pruebas de resistencia a vulnerabilidades (clonación NFC) y manuales de usuario.

---

## Actividades a Realizar
El proyecto se desarrollará bajo la **metodología en espiral**, lo que permite un control iterativo de riesgos técnicos, adaptabilidad a nuevos requisitos y refinamiento continuo del software a través de cuatro ciclos principales, garantizando que el trabajo de los tres investigadores se integre de forma progresiva:

1. **Fase 1: Análisis y Especificación de Riesgos (Ciclo Inicial)**
   - Definición de requerimientos técnicos para el uso del hardware NFC nativo en dispositivos móviles.
   - Diseño del tamaño de la muestra y protocolos para la prueba piloto (50 usuarios / 2 porterías).
   - Investigación y selección del modelo matemático para la firma criptográfica (HMAC) en etiquetas NTAG215.
2. **Fase 2: Diseño de Arquitectura y Seguridad (Ciclo de Diseño)**
   - Diseño de la base de datos relacional y modelado del backend para soportar alta concurrencia.
   - Diseño de la arquitectura *offline-first* para la aplicación móvil, garantizando el funcionamiento ante caídas de red.
   - Elaboración de diagramas de componentes (App Móvil - Cloud - Dashboard).
3. **Fase 3: Desarrollo e Integración (Ciclo de Construcción)**
   - Codificación del módulo móvil: interacción con la API de Android NFC para la lectura/escritura segura de etiquetas.
   - Despliegue de los servicios en la nube (API RESTful) y conexión segura HTTPS.
   - Desarrollo del dashboard analítico y programación de algoritmos de métricas de movilidad.
4. **Fase 4: Prueba Piloto, Validación y Documentación (Ciclo de Evaluación)**
   - Ejecución de la prueba piloto en el campus central de la UIS.
   - Recolección de métricas de latencia de red, tiempos de escaneo en portería y análisis de vulnerabilidades físicas (intentos de clonación de etiquetas).
   - Redacción del informe final, corrección iterativa de fallos detectados en el piloto y entrega de la memoria técnica.

---

## Palabras y/o Términos Clave
Criptografía NFC (HMAC), Hardware Nativo Móvil, Prueba Piloto, Alta Concurrencia, Metodología Espiral, Arquitectura en la Nube, Internet de las Cosas (IoT), Smart Campus, Trazabilidad, Vehículos de Movilidad Personal (VMP).

---

## Referencias
* Área Metropolitana de Bucaramanga. (2018). *Estrategia de la bicicleta como medio de transporte para Bucaramanga y su Área Metropolitana*. AMB. https://www.amb.gov.co/wp-content/uploads/Estrategia-de-la-Bicicleta-para-el-AMB-Publicada.pdf
* Ríos, R., Taddia, A. P., Pardo, C. F., & Lleras, N. (2015). *Ciclo-inclusión en América Latina y el Caribe: Guía de diseño para fomentar el uso de la bicicleta*. Banco Interamericano de Desarrollo (BID). https://doi.org/10.18235/0000164
* Secretaría Distrital de Movilidad. (2024, 3 de junio). *Bogotá promueve la movilidad sostenible con más de 886.000 viajes diarios en bicicleta*. Alcaldía Mayor de Bogotá. https://www.movilidadbogota.gov.co/noticias/bogota-promueve-la-movilidad-sostenible-con-mas-de-886000-viajes-diarios-en-bicicleta
* Universidad Industrial de Santander. (2022, 22 de junio). *Nos "montamos" al Día sin Carro y sin Moto… En la UIS promovemos el uso de la "bici"*. Comunicaciones UIS. https://comunicaciones.uis.edu.co/nos-montamos-al-dia-sin-carro-y-sin-moto-en-la-uis-promovemos-el-uso-de-la-bici/
