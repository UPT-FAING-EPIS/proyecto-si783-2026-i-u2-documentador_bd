<center>

![./media/logo-upt.png](./media/logo-upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERÍA**

**Escuela Profesional de Ingeniería de Sistemas**

**Informe Final**

**Proyecto: Sistema de Documentación de Base de Datos**

Curso: Base de Datos II

Docente: Mag. Patrick Cuadros Quiroga

Integrantes:

***Andia Navarro, Diego Fabrizio (2022073906)***

***Quispe Chileno, Clara Briyith Mayra (2024080129)***

**Tacna – Perú**

***2026***

</center>

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

Sistema *de documentación de base de datos*

Informe del Proyecto Final

Versión *{1.0}*

| CONTROL DE VERSIONES ||||||
| :-: | :- | :- | :- | :- | :- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1.0 | MPV | ELV | ARV | 10/10/2020 | Versión Original |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# ÍNDICE GENERAL

[1. Antecedentes](#antecedentes)

[2. Planteamiento del Problema](#planteamiento-del-problema)

[2.1.- Problema](#21--problema)

[2.2.- Justificación](#22--justificación)

[2.3.- Alcance](#23--alcance)

[3. Objetivos](#3-objetivos)

[3.1.- Objetivo General](#31--objetivo-general)

[3.2.- Objetivos Específicos](#32--objetivos-específicos)

[4.- Marco Teórico](#4--marco-teórico)

[4.1.- Bases de Datos](#41--bases-de-datos)

[4.2.- Documentación de Bases de Datos](#42--documentación-de-bases-de-datos)

[4.3.- Modelos de Lenguaje y Automatización de Texto](#43--modelos-de-lenguaje-y-automatización-de-texto)

[4.4.- Auditoría de Datos y Normalización](#44--auditoría-de-datos-y-normalización)

[4.5.- Análisis de Esquemas SQL con Python](#45--análisis-de-esquemas-sql-con-python)

[5. Desarrollo de la Solución](#5-desarrollo-de-la-solución)

[5.1.- Análisis de Factibilidad](#51--análisis-de-factibilidad)

[5.1.1.- Factibilidad Técnica](#511--factibilidad-técnica)

[5.1.2.- Factibilidad Económica](#512--factibilidad-económica)

[5.1.3.- Factibilidad Operativa](#513--factibilidad-operativa)

[5.1.4.- Factibilidad Social](#514--factibilidad-social)

[5.1.5.- Factibilidad Legal](#515--factibilidad-legal)

[5.1.6.- Factibilidad Ambiental](#516--factibilidad-ambiental)

[5.2.- Tecnología de Desarrollo](#52--tecnología-de-desarrollo)

[5.3.- Metodología de implementación](#53--metodología-de-implementación)

[6.- Cronograma](#6--cronograma)

[7.- Presupuesto](#7--presupuesto)

[8.- Conclusiones](#8--conclusiones)

[Recomendaciones](#recomendaciones)

[Bibliografía](#bibliografía)

[Anexos](#anexos)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## Antecedentes

Las bases de datos constituyen el núcleo fundamental de cualquier sistema de información moderno. Desde aplicaciones web hasta sistemas empresariales de gran escala, la correcta gestión de la información depende directamente de una base de datos bien diseñada y, sobre todo, adecuadamente documentada. Sin embargo, la documentación de bases de datos ha sido históricamente una de las tareas más descuidadas en el ciclo de desarrollo de software.

Durante décadas, la documentación de bases de datos se realizó de manera manual mediante el uso de diagramas dibujados a mano, archivos de texto plano, hojas de cálculo y documentos de Word desactualizados. Este enfoque artesanal presentaba limitaciones evidentes como la alta inversión de tiempo, propensión a errores humanos, inconsistencia entre la documentación y la realidad del sistema, y rápida obsolescencia ante cualquier cambio en la estructura de datos. A medida que los sistemas de información crecieron en complejidad, la brecha entre el estado real de las bases de datos y su documentación se amplió considerablemente. En muchas organizaciones, resulta común encontrar bases de datos con decenas o centenares de tablas, relaciones implícitas, convenciones de nomenclatura no documentadas y reglas de negocio implementadas a nivel de base de datos que nunca fueron registradas en ningún documento formal.

Con el tiempo surgieron herramientas especializadas que intentaron resolver parcialmente este problema. Gestores de bases de datos como MySQL, pgAdmin, DBeaver, etc. incorporaron funcionalidades básicas de visualización de esquemas y generación de diagramas Entidad-Relación. Sin embargo, estas herramientas presentan limitaciones importantes: requieren conexión directa al servidor de base de datos en producción, están vinculadas generalmente a un gestor específico sin soporte multiplataforma, no ofrecen análisis crítico del diseño ni recomendaciones de mejora, no generan documentación narrativa sino sólo diagramas o listas de tablas, y herramientas avanzadas que requieren licencias de pago costosas.

La irrupción de los modelos de lenguaje de gran escala (LLM) a partir de 2020 abrió nuevas posibilidades para la automatización de tareas cognitivas complejas dentro del desarrollo de software. Esta evolución tecnológica permitió plantear una nueva generación de herramientas de documentación que no solo describen la estructura de una base de datos, sino que la comprenden, la evalúan críticamente y generan recomendaciones inteligentes de mejora, tal como lo haría un arquitecto de datos con experiencia.

En el transcurso del análisis y desarrollo del proyecto, se identificó la necesidad de desarrollar proyectos que integren el conocimiento teórico de bases de datos con tecnologías modernas de análisis e inteligencia artificial. El presente proyecto surge en este contexto académico como una respuesta concreta a una problemática real y vigente: la falta de herramientas accesibles, inteligentes y de código abierto para la documentación automatizada de bases de datos.

El sistema de documentador de base de datos representa una propuesta innovadora en este panorama, al combinar dos enfoques complementarios como un motor de análisis técnico local desarrollado en Python, capaz de analizar con precisión la estructura de bases de datos SQL y NoSQL, detectar relaciones explícitas e implícitas mediante algoritmos de coincidencia difusa, calcular métricas de normalización y convertir esquemas entre nueve tecnologías diferentes. Esta combinación única posiciona al sistema como una herramienta de valor tanto en entornos académicos, donde facilita el aprendizaje sobre diseño de bases de datos, como en entornos profesionales, donde reduce significativamente el tiempo y esfuerzo invertido en la documentación técnica.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## Planteamiento del Problema

### 2.1.- Problema

La gestión eficiente de sistemas de información depende en gran medida de la calidad y disponibilidad de la documentación de sus bases de datos. Sin embargo, en la práctica cotidiana del desarrollo de software se observa de manera recurrente una problemática central, la cual radica en la ausencia o deficiencia de documentación estructurada y actualizada de las bases de datos. Esta situación se manifiesta en las siguientes dimensiones concretas:

- **Documentación inexistente o desactualizada:** La mayoría de los proyectos de software priorizan el desarrollo funcional sobre la documentación técnica. Como resultado, las bases de datos crecen y evolucionan sin que su documentación sea actualizada de forma paralela, generando una brecha progresiva entre el estado real del sistema y la información disponible sobre él.

- **Complejidad estructural no documentada:** Los sistemas heredados o desarrollados por múltiples programadores a lo largo del tiempo presentan estructuras de bases de datos complejas, con relaciones implícitas entre tablas, convenciones de nomenclatura no documentadas y reglas de negocio implementadas a nivel de base de datos que no están registradas en ningún documento formal.

- **Dependencia del conocimiento tácito:** La falta de documentación genera una dependencia crítica del conocimiento individual de ciertos desarrolladores o administradores de bases de datos. Cuando estas personas no están disponibles, el equipo pierde acceso a información fundamental para el mantenimiento del sistema.

- **Elevados costos de análisis y mantenimiento:** Los desarrolladores que se incorporan a un proyecto deben invertir tiempo considerable en explorar y comprender la estructura de la base de datos antes de poder realizar cualquier modificación. Este retrabajo constante incrementa los costos de desarrollo y aumenta la probabilidad de cometer errores.

- **Ausencia de herramientas inteligentes y accesibles:** Las herramientas existentes para documentación de bases de datos son costosas, están vinculadas a gestores específicos, no ofrecen análisis crítico del diseño y no se benefician de las capacidades de la inteligencia artificial moderna.

### 2.2.- Justificación

El proyecto propone una solución que combina un motor de análisis en Python con un módulo de inteligencia artificial para superar las limitaciones de las herramientas existentes. De esta manera, el sistema no solo permite realizar un análisis técnico preciso, con detección de claves, relaciones y métricas de normalización, sino que también ofrece una evaluación crítica del diseño, sugerencias de mejora y documentación descriptiva. Esta combinación de funciones no suele encontrarse de forma completa en herramientas gratuitas disponibles en el mercado.

Además, el sistema ha sido planteado utilizando herramientas de código abierto como Node.js, Python y librerías con licencias libres, junto con servicios que ofrecen planes gratuitos como Supabase y Vercel. Esto permite reducir considerablemente los costos de desarrollo e implementación, especialmente si se compara con soluciones comerciales de documentación que suelen requerir pagos anuales elevados por licencia.

Desde el punto de vista del uso práctico, el sistema reduce de manera significativa el tiempo dedicado a la documentación manual de bases de datos, permitiendo que los equipos de desarrollo enfoquen sus esfuerzos en actividades de mayor valor dentro del proceso de software. Esta automatización mejora la productividad y disminuye la carga repetitiva asociada a la elaboración de documentación técnica.

El proyecto también tiene un valor importante en el ámbito académico, ya que integra conocimientos de distintas áreas de la Ingeniería de Sistemas, como diseño de bases de datos, desarrollo web, análisis de sistemas y gestión de proyectos. Esto lo convierte en una experiencia aplicada que fortalece el aprendizaje y permite poner en práctica conceptos vistos en el curso.

Finalmente, al tratarse de una herramienta web accesible y basada en tecnologías de libre uso, el sistema puede ser adoptado por distintos equipos de desarrollo sin depender de grandes recursos económicos. Esto favorece el acceso a una solución profesional de documentación y contribuye a que más personas puedan organizar y comprender mejor sus bases de datos.

### 2.3.- Alcance

El Sistema de documentación de base de datos comprende varias funcionalidades dentro de su alcance, orientadas principalmente a facilitar la lectura, análisis, documentación y organización de esquemas de bases de datos. Entre las funciones incluidas se encuentra la carga de archivos de esquemas en formatos como .sql, .json, .xlsx, .yaml, .csv y .dbml, así como el análisis automático de su estructura para identificar tablas, campos, tipos de datos, claves primarias y claves foráneas, tanto explícitas como implícitas.

También forma parte del alcance la generación de documentación técnica estructurada, incluyendo diccionarios de datos, descripciones de tablas y relaciones, además de la creación de diagramas Entidad–Relación interactivos con opciones de zoom y exportación en formato SVG. El sistema igualmente permite detectar problemas estructurales como redundancias, relaciones poco definidas o ausencia de normalización, con el fin de ofrecer una visión más clara del estado del esquema analizado.

Dentro de las funcionalidades contempladas se encuentra además la generación de reportes de auditoría con observaciones y recomendaciones, apoyada por inteligencia artificial, así como la conversión de esquemas entre distintas tecnologías como MySQL, PostgreSQL, SQLite, MongoDB mediante Mongoose, Prisma, GraphQL, JSON Schema, CSV y YAML. A esto se suma la exportación de documentación en formatos PDF, la gestión de usuarios con autenticación, roles y compartición de documentación, la generación de datos de prueba sintéticos basados en el esquema analizado y el soporte para el análisis de bases de datos NoSQL, especialmente MongoDB.

Por otro lado, existen ciertas funcionalidades que no forman parte del alcance del proyecto. El sistema no realiza modificaciones directas sobre la base de datos ni ejecuta cambios automáticos en el esquema. Tampoco se conecta de manera directa y en tiempo real a servidores de producción, ni incorpora una versión avanzada de esquemas con comparación entre diferentes versiones.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 3. Objetivos

### 3.1.- Objetivo General

Desarrollar un sistema web híbrido que combine inteligencia artificial y análisis técnico local para automatizar la documentación, auditoría y conversión de esquemas de bases de datos SQL y NoSQL, reduciendo el tiempo de documentación manual y mejorando la calidad, accesibilidad y comprensión de la información estructural de los sistemas de datos.

### 3.2.- Objetivos Específicos

- Implementar un motor de análisis técnico en Python que extraiga automáticamente metadatos de bases de datos como tablas, campos, tipos de datos, claves primarias y foráneas, relaciones explícitas e implícitas, índices y métricas de normalización a partir de archivos de esquema en múltiples formatos.

- Desarrollar un módulo de visualización de diagramas Entidad–Relación interactivos, con controles de zoom, navegación y exportación en formato SVG, que faciliten la comprensión visual de la estructura y las relaciones de la base de datos.

- Construir un convertidor de esquemas profesional que permita transformar la estructura de la base de datos analizada a nueve formatos y tecnologías diferentes, facilitando procesos de migración y adopción de nuevas tecnologías.

- Desarrollar una interfaz web moderna e intuitiva que permita a usuarios de distintos perfiles técnicos realizar el flujo completo de documentación, desde la carga y análisis hasta la visualización y exportación, sin necesidad de instalación de software adicional ni conocimientos técnicos avanzados.

- Habilitar la exportación de reportes en formatos estándar, generando documentos completos y listos para presentación o archivo formal, que incluyan la documentación técnica, el análisis de auditoría y los diagramas ER.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 4.- Marco Teórico

### 4.1.- Bases de Datos

Una base de datos es una colección organizada de información estructurada o datos, normalmente almacenada de forma electrónica en un sistema informático. Las bases de datos son gestionadas por un Sistema de Gestión de Bases de Datos, que actúa como interfaz entre los datos almacenados y los usuarios o aplicaciones que los utilizan.

Los tipos principales de bases de datos relevantes para este proyecto son las bases de datos relacionales, que organizan los datos en tablas con filas y columnas relacionadas entre sí mediante claves primarias y foráneas, y utilizan el lenguaje SQL para la gestión de datos, como MySQL, PostgreSQL, SQLite y MariaDB; y las bases de datos no relacionales, que almacenan datos en formatos flexibles como documentos JSON, grafos o pares clave-valor, siendo más adecuadas para datos no estructurados o semiestructurados, como MongoDB, Redis y Cassandra.

### 4.2.- Documentación de Bases de Datos

La documentación de bases de datos consiste en describir de manera formal y estructurada la composición de una base de datos, incluyendo sus tablas, atributos, tipos de datos, claves, relaciones, restricciones, índices y reglas de negocio implementadas a nivel de datos.

Los artefactos más comunes de la documentación de bases de datos incluyen el diccionario de datos, que es un catálogo detallado de cada tabla y campo con su descripción, tipo de dato, restricciones y relaciones; el diagrama Entidad–Relación, que representa gráficamente las entidades del sistema y sus relaciones; y el modelo físico, que describe la implementación real en el gestor de base de datos, incluyendo tipos de datos específicos, índices y particiones. La documentación adecuada de bases de datos es un factor crítico para la mantenibilidad, escalabilidad y transferencia de conocimiento en proyectos de software.

### 4.3.- Modelos de Lenguaje y Automatización de Texto

Los modelos de lenguaje de gran escala son sistemas capaces de comprender y generar texto con alta coherencia a partir de grandes volúmenes de información previamente aprendida. En el contexto del presente proyecto, se utilizan como apoyo para interpretar la estructura de una base de datos a partir de su representación en texto, generar documentación descriptiva para cada tabla y campo, evaluar el diseño del esquema desde una perspectiva de arquitectura de datos, identificar problemas de normalización, redundancias y antipatrones de diseño, y proponer mejoras específicas y fundamentadas para optimizar el modelo de datos. La integración de estos modelos en herramientas de desarrollo de software representa una tendencia importante dentro de la industria tecnológica actual.

### 4.4.- Auditoría de Datos y Normalización

La auditoría de datos es el proceso de evaluación sistemática de la calidad, integridad, consistencia y organización de los datos almacenados en una base de datos. Sus objetivos principales son identificar errores, detectar inconsistencias, evaluar el cumplimiento de estándares y proponer mejoras.

La normalización es el proceso de organizar los atributos y tablas de una base de datos relacional para minimizar la redundancia y las dependencias indeseables. Se define en términos de formas normales:

- La primera forma normal elimina grupos repetidos, asegurando que cada celda contenga un único valor atómico.

- La segunda forma normal cumple la primera forma normal y elimina dependencias parciales de la clave primaria.

- La tercera forma normal cumple la segunda forma normal y elimina dependencias transitivas entre atributos no clave.

- La forma normal de Boyce-Codd es una versión más estricta de la tercera forma normal para eliminar anomalías.

El sistema analiza automáticamente el grado de normalización del esquema como parte de su proceso de auditoría.

### 4.5.- Análisis de Esquemas SQL con Python

El análisis automatizado de esquemas SQL implica la extracción y procesamiento programático de los metadatos contenidos en un archivo de definición de base de datos. Las herramientas y librerías utilizadas en este proyecto incluyen:

- **sqlglot:** Librería de código abierto para parsear, analizar y transformar sentencias SQL de múltiples dialectos.

- **sqlparse:** Herramienta para el análisis sintáctico no validante de sentencias SQL.

- **sql-metadata:** Librería para extracción de metadatos SQL.

- **Pandas:** Librería de análisis de datos que facilita el procesamiento tabular de la información extraída.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 5. Desarrollo de la Solución

El Sistema de documentación de base de datos fue desarrollado como una aplicación web full-stack que integra distintas tecnologías para ofrecer un proceso completo de documentación y análisis de esquemas de bases de datos. Su objetivo principal es facilitar la comprensión de la estructura de datos, generar documentación técnica de forma automatizada y apoyar la revisión del diseño de manera clara y ordenada.

El flujo de procesamiento funciona de la siguiente manera. El usuario carga un archivo de esquema desde la interfaz web mediante arrastrar y soltar o selección manual. Luego, el servidor Node.js recibe el archivo y lo almacena temporalmente para iniciar el proceso de análisis. Después de ello, se ejecuta el motor de análisis en Python, el cual procesa la información y devuelve los resultados técnicos en formato JSON. Posteriormente, el servidor integra los resultados obtenidos y los envía al frontend para que puedan ser visualizados en la interfaz. Finalmente, el usuario puede revisar la documentación generada, observar los diagramas Entidad–Relación, exportar los resultados en PDF.

### 5.1.- Análisis de Factibilidad

#### 5.1.1.- Factibilidad Técnica

El proyecto es técnicamente viable debido a que las tecnologías utilizadas se encuentran disponibles y son accesibles para el equipo de desarrollo. Las computadoras personales con las que se cuenta son suficientes para el desarrollo y las pruebas locales, ya que poseen las características necesarias para ejecutar el entorno de trabajo. Además, Node.js y Python son tecnologías maduras, ampliamente documentadas y de uso extendido en el desarrollo de aplicaciones web y de procesamiento de datos.

Por otro lado, los servicios en la nube utilizados para autenticación y almacenamiento permiten cubrir las necesidades del proyecto sin requerir una infraestructura compleja. También se dispone de librerías de código abierto que facilitan el análisis de esquemas, la manipulación de datos y la generación de documentación.

#### 5.1.2.- Factibilidad Económica

El proyecto presenta una inversión total de S/ 3,925.00, distribuida entre costos generales, costos operativos, costos del ambiente y costos de personal. Los costos generales corresponden a materiales y papelería, los costos operativos incluyen internet, energía y transporte, mientras que los costos del ambiente contemplan infraestructura y servicios necesarios para el desarrollo. La mayor parte de la inversión está representada por la valoración del esfuerzo humano dedicado al proyecto.

Los indicadores financieros muestran que el proyecto es económicamente viable, ya que el valor beneficio-costo es favorable, el valor actual neto es positivo y la tasa interna de retorno supera ampliamente el costo de oportunidad considerado. Esto demuestra que la propuesta genera un retorno positivo frente a la inversión realizada.

#### 5.1.3.- Factibilidad Operativa

El sistema es operativamente viable porque funciona como una aplicación web y no requiere instalación en el equipo del usuario. La interfaz fue diseñada con un enfoque sencillo e intuitivo, permitiendo completar el flujo principal de uso en poco tiempo y sin necesidad de capacitación especializada. Además, los usuarios objetivo cuentan con los conocimientos básicos necesarios para interpretar la documentación generada.

Otro aspecto importante es que el sistema trabaja en modo de solo lectura, por lo que no modifica las bases de datos analizadas ni genera riesgos sobre la información original. Esto facilita su adopción en entornos académicos y de desarrollo.

#### 5.1.4.- Factibilidad Social

El proyecto tiene un impacto social positivo porque permite que equipos de desarrollo y usuarios con distintos niveles de experiencia accedan a una herramienta útil para comprender y documentar bases de datos de forma más ordenada. También contribuye a reducir la dependencia del conocimiento técnico de una sola persona, fomentando una mejor distribución de la información dentro de los equipos.

Asimismo, promueve una cultura de documentación más responsable y sistemática, y sirve como apoyo en la formación académica dentro de la Ingeniería de Sistemas, ya que aplica conocimientos reales en un caso práctico.

#### 5.1.5.- Factibilidad Legal

El proyecto cumple con las normativas legales aplicables, ya que utiliza herramientas de código abierto con licencias permitidas para su uso académico y desarrollo. Además, respeta la Ley N.° 29733 de Protección de Datos Personales del Perú, debido a que trabaja en modo de solo lectura y no conserva información sensible de las bases de datos analizadas más allá del tiempo necesario para el procesamiento.

También se distribuye bajo una licencia libre, lo que permite su uso dentro del contexto académico sin conflictos legales relacionados con propiedad intelectual o uso de software.

#### 5.1.6.- Factibilidad Ambiental

El impacto ambiental del proyecto es mínimo y favorable. Al tratarse de una solución digital, reduce el uso de papel al generar documentación electrónica en lugar de documentos impresos. Además, aprovecha equipos ya disponibles, evitando la necesidad de adquirir hardware adicional.

El sistema también se apoya en infraestructura en la nube, lo que contribuye a un mejor aprovechamiento de recursos tecnológicos y a una menor huella ambiental en comparación con soluciones locales más pesadas. Finalmente, al ser un proyecto de software, no genera residuos industriales ni elementos contaminantes.

### 5.2.- Tecnología de Desarrollo

El sistema será desarrollado utilizando tecnologías modernas que permitan un buen rendimiento y escalabilidad:

- **Backend:** Node.js o Python

- **Frontend:** HTML, CSS y JavaScript

- **Base de datos:** MySQL o PostgreSQL

- **Inteligencia Artificial:** modelos de lenguaje

- **Plataforma:** aplicación web

### 5.3.- Metodología de implementación

Para el desarrollo del sistema se adoptó una metodología ágil incremental combinada con la elaboración de documentación formal, estructurada en tres artefactos principales alineados con los estándares de la Ingeniería de Software tales como:

- **Documento de Visión:** define los objetivos, alcance y actores del sistema

- **SRS:** describe los requisitos funcionales y no funcionales

- **SAD:** define la arquitectura del sistema

Esta metodología permite una mejor organización del proyecto y reduce riesgos durante el desarrollo.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 6.- Cronograma

El desarrollo del proyecto se organiza en diferentes etapas que permiten avanzar de forma ordenada, asegurando que cada fase cumpla con sus objetivos antes de pasar a la siguiente. Este enfoque progresivo ayuda a reducir errores y facilita el control del avance del proyecto.

| **Fase** | **Actividad principal** | **Semanas** | **Descripción** |
| --- | --- | --- | --- |
| Fase 1 | Análisis del problema | Semana 1 | Identificación de necesidades, revisión del contexto, definición del problema y de los objetivos, y elaboración del Documento de Visión. |
| Fase 2 | Diseño del sistema | Semana 2 | Definición de la arquitectura del sistema, diseño de la API REST y los endpoints, elaboración del SRS y SAD, y diseño de la base de datos en Supabase. |
| Fase 3 | Desarrollo del prototipo: Módulo Core | Semanas 3 y 4 | Implementación del servidor Node.js con Express, desarrollo del motor de análisis en Python, creación del generador de diagramas e integración entre el servidor y el motor Python. |
| Fase 4 | Desarrollo del prototipo: Módulo Avanzado | Semanas 5 y 6 | Integración con la API, desarrollo del convertidor de esquemas, generación de datos de prueba, implementación del frontend, sistema de usuarios y exportación en PDF y Word. |
| Fase 5 | Pruebas del sistema | Semana 6 | Pruebas funcionales, pruebas de integración entre los módulos principales, pruebas con archivos reales y corrección de errores detectados. |
| Fase 6 | Despliegue y documentación final | Semana 7 | Despliegue en producción, elaboración del Informe de Factibilidad, elaboración del informe general, manuales de usuario y entrega final. |

Duración total: 7 semanas aproximadamente, equivalentes a 2 meses.

Fecha de inicio: Abril de 2026.

Fecha de entrega: Junio de 2026.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 7.- Presupuesto

El presupuesto del proyecto considera principalmente los recursos necesarios para el desarrollo e implementación del sistema. Al tratarse de un proyecto académico con uso de tecnologías accesibles, los costos se mantienen relativamente bajos.

Los principales componentes del presupuesto incluyen:

- **Recursos humanos:** tiempo invertido en el desarrollo, análisis y pruebas del sistema

- **Herramientas tecnológicas:** software de desarrollo, editores de código y plataformas de apoyo

- **Servicios en la nube (opcional):** uso de servidores o APIs de inteligencia artificial

- **Infraestructura básica:** equipos de cómputo y conexión a internet

Una ventaja importante de este proyecto es que puede desarrollarse utilizando herramientas open source, lo que reduce significativamente los costos. En caso de utilizar servicios de inteligencia artificial en la nube, el costo dependerá del nivel de uso, pero en una etapa inicial se puede trabajar con planes gratuitos o de bajo costo.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 8.- Conclusiones

El sistema desarrollado responde de manera efectiva a la problemática identificada, ya que automatiza el proceso de documentación de bases de datos y reduce de forma significativa el tiempo que normalmente se invierte en esta tarea manual. Además, mejora la calidad, la precisión y la accesibilidad de la documentación generada, lo que facilita su uso tanto para el análisis como para el mantenimiento de los esquemas de datos.

La arquitectura implementada demostró ser adecuada para los objetivos del proyecto. La combinación entre el análisis técnico local en Python y los módulos complementarios de procesamiento y generación de contenido permite obtener resultados más completos y útiles que los que se lograrían con un enfoque tradicional. Esto hace que el sistema no solo documente la estructura de la base de datos, sino que también apoye la comprensión del diseño y la detección de posibles mejoras.

El uso de tecnologías de código abierto permite mantener los costos del proyecto dentro de un rango accesible. Gracias a ello, se logró construir una solución con un nivel de funcionalidad alto sin requerir una inversión excesiva, lo que la vuelve viable dentro del contexto académico en el que fue desarrollado el proyecto.

Desde el punto de vista técnico, el sistema es sólido y cumple con los criterios de calidad establecidos. Su estructura modular, la comunicación entre componentes, la autenticación segura, el modo de solo lectura y la interacción en tiempo real contribuyen a que la solución sea confiable, segura y fácil de mantener.

Asimismo, el proyecto integra de manera satisfactoria conocimientos de varias áreas de la Ingeniería de Sistemas, como diseño de bases de datos, desarrollo web, análisis de sistemas y gestión de proyectos. Esto convierte al desarrollo en una experiencia formativa completa, que va más allá de los contenidos específicos del curso y fortalece la capacidad del equipo para enfrentar problemas reales.

Finalmente, la herramienta tiene un potencial importante tanto en el ámbito académico como en el profesional. Al tratarse de una aplicación web accesible, sin necesidad de instalación y basada en tecnologías de libre uso, puede ser adoptada por distintos equipos de desarrollo e instituciones que necesiten documentar sus bases de datos de manera más ordenada y eficiente.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# Recomendaciones

Para asegurar el correcto funcionamiento y evolución del sistema, se plantean las siguientes recomendaciones:

- Ampliar el soporte para más gestores de bases de datos, incorporando en futuras versiones motores como Oracle Database, Microsoft SQL Server, Cassandra y Redis, con el fin de aumentar el alcance del sistema en entornos empresariales.

- Implementar una conexión directa opcional a servidores de bases de datos, manteniendo el modo de solo lectura, para evitar la dependencia exclusiva de archivos exportados y facilitar el análisis de estructuras en tiempo real.

- Desarrollar un sistema de versionado de documentación que permita registrar y comparar cambios en el esquema a lo largo del tiempo, de manera que se pueda llevar un mejor control de la evolución de la base de datos.

- Incorporar pruebas automatizadas tanto unitarias como de integración, con el objetivo de asegurar la estabilidad del sistema, reducir errores y facilitar futuras mejoras o ampliaciones.

- Evaluar la posibilidad de adoptar un modelo freemium en caso de que el sistema se expanda fuera del ámbito académico, de modo que se pueda garantizar su sostenibilidad sin perder una versión gratuita para uso básico.

- Publicar el sistema en un repositorio público con documentación completa, para facilitar su consulta, reutilización y mejora por parte de la comunidad de desarrollo.

- Realizar pruebas de usabilidad con usuarios reales antes de una implementación formal, con la finalidad de validar la interfaz, detectar problemas de experiencia de uso y ajustar el sistema según la retroalimentación obtenida.

- Considerar la integración con herramientas de automatización y despliegue continuo, para que la documentación pueda actualizarse de forma más eficiente cuando existan cambios en los esquemas del proyecto.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# Bibliografía

- Brown, T. B., Mann, B., Ryder, N., Subbiah, M., Kaplan, J., Dhariwal, P., et al. (2020). Language models are few-shot learners. *Advances in Neural Information Processing Systems*, 33, 1877–1901.

- Date, C. J. (2004). *Introducción a los sistemas de bases de datos* (8.ª ed.). Pearson Education.

- Elmasri, R., & Navathe, S. B. (2016). *Sistemas de bases de datos* (7.ª ed.). Pearson Education.

- International Organization for Standardization. (2022). *ISO/IEC 27001:2022 — Information security, cybersecurity and privacy protection*. ISO/IEC.

- Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del software: Un enfoque práctico* (9.ª ed.). McGraw-Hill Education.

- Silberschatz, A., Korth, H. F., & Sudarshan, S. (2019). *Fundamentos de bases de datos* (7.ª ed.). McGraw-Hill Education.

- Sommerville, I. (2016). *Ingeniería del software* (10.ª ed.). Pearson Education.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# Anexos

Anexo 01 Informe de Factibilidad

Anexo 02 Documento de Visión

Anexo 03 Documento SRS

Anexo 04 Documento SAD

Anexo 05 Manuales y otros documentos
