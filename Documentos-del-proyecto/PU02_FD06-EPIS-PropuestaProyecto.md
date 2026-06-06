<center>

![./media/logo-upt.png](./media/logo-upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERÍA**

**Escuela Profesional de Ingeniería de Sistemas**

**Propuesta del Proyecto: Sistema de Documentación de Base de Datos**

Curso: Base de Datos II

Docente: Mag. Patrick Cuadros Quiroga

Integrantes:

***Andia Navarro, Diego Fabrizio (2022073906)***

***Quispe Chileno, Clara Briyith Mayra (2024080129)***

**Tacna – Perú**

**2026**

</center>

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

**Proyecto**

***Sistema de Documentación de Base de Datos, Tacna, 2026***

**Presentado por:**

***Andia Navarro, Diego Fabrizio***

***Quispe Chileno, Clara Briyith Mayra***

***2026***

| CONTROL DE VERSIONES | | | | | |
| :-: | :- | :- | :- | :- | :- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1.0 | DAN, CQC | DAN, CQC | DAN, CQC | 03/06/2020 | Versión Original |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **ÍNDICE GENERAL**

[Resumen Ejecutivo](#resumen-ejecutivo)

[I. Propuesta narrativa](#i-propuesta-narrativa)

- [Planteamiento del Problema](#planteamiento-del-problema)
- [Justificación del proyecto](#justificación-del-proyecto)
- [Objetivo general](#objetivo-general)
  - [3.1.- Objetivo General](#31--objetivo-general)
  - [3.2.- Objetivos Específicos](#32--objetivos-específicos)
- [Beneficios](#beneficios)
- [Alcance](#alcance)
- [Requerimientos del sistema](#requerimientos-del-sistema)
  - [6.1. Cuadro de Requerimientos Funcionales Inicial](#61-cuadro-de-requerimientos-funcionales-inicial)
  - [6.2. Cuadro de Requerimientos No Funcionales](#62-cuadro-de-requerimientos-no-funcionales)
  - [6.3. Cuadro de Requerimientos Funcionales Final](#63-cuadro-de-requerimientos-funcionales-final)
- [Restricciones](#restricciones)
- [Supuestos](#supuestos)
- [Resultados esperados](#resultados-esperados)
- [Metodología de implementación](#metodología-de-implementación)
- [Actores claves](#actores-claves)
- [Papel y responsabilidades del personal](#papel-y-responsabilidades-del-personal)
- [Plan de monitoreo y evaluación](#plan-de-monitoreo-y-evaluación)
- [Cronograma del proyecto](#cronograma-del-proyecto)
- [Hitos de entregables](#hitos-de-entregables)

[II. Presupuesto](#ii-presupuesto)

- [1. Planteamiento de aplicación del presupuesto](#1-planteamiento-de-aplicación-del-presupuesto)
- [2. Presupuesto](#2-presupuesto)
- [3. Análisis de Factibilidad](#3-análisis-de-factibilidad)
- [4. Evaluación Financiera](#4-evaluación-financiera)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **Resumen Ejecutivo**

| **Nombre del Proyecto propuesto**: *Sistema de Documentador de Base de datos, Tacna, 2026* |
| :- |
| **Propósito del Proyecto y Resultados esperados:** El propósito del proyecto es *desarrollar un sistema web que permita automatizar la documentación, análisis y exportación de esquemas de bases de datos, facilitando la comprensión de su estructura y reduciendo de manera significativa el tiempo dedicado a este proceso de forma manual.* Los resultados esperados son: *La implementación de una plataforma funcional capaz de cargar archivos de esquemas en distintos formatos, analizar automáticamente tablas, campos y relaciones, generar documentación técnica estructurada, visualizar diagramas Entidad–Relación, exportar reportes en PDF y brindar una experiencia de uso accesible, rápida y segura para distintos perfiles de usuario.* |
| **Población Objetivo:** *Desarrolladores de software, administradores de bases de datos, analistas de sistemas, equipos académicos y organizaciones que requieran documentar y analizar bases de datos de manera eficiente.* |
| **Monto de Inversión (En Soles):** ***S/. 3,925.00*** | **Duración del Proyecto (En Meses):** ***2*** |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## I. Propuesta narrativa

### Planteamiento del Problema

La gestión eficiente de sistemas de información depende en gran medida de la calidad y disponibilidad de la documentación de sus bases de datos. Sin embargo, en la práctica cotidiana del desarrollo de software se observa de manera recurrente una problemática central, la cual radica en la ausencia o deficiencia de documentación estructurada y actualizada de las bases de datos. Esta situación se manifiesta en las siguientes dimensiones concretas:

- Documentación inexistente o desactualizada: La mayoría de los proyectos de software priorizan el desarrollo funcional sobre la documentación técnica. Como resultado, las bases de datos crecen y evolucionan sin que su documentación sea actualizada de forma paralela, generando una brecha progresiva entre el estado real del sistema y la información disponible sobre él.

- Complejidad estructural no documentada: Los sistemas heredados o desarrollados por múltiples programadores a lo largo del tiempo presentan estructuras de bases de datos complejas, con relaciones implícitas entre tablas, convenciones de nomenclatura no documentadas y reglas de negocio implementadas a nivel de base de datos que no están registradas en ningún documento formal.

- Dependencia del conocimiento tácito: La falta de documentación genera una dependencia crítica del conocimiento individual de ciertos desarrolladores o administradores de bases de datos. Cuando estas personas no están disponibles, el equipo pierde acceso a información fundamental para el mantenimiento del sistema.

- Elevados costos de análisis y mantenimiento: Los desarrolladores que se incorporan a un proyecto deben invertir tiempo considerable en explorar y comprender la estructura de la base de datos antes de poder realizar cualquier modificación. Este retrabajo constante incrementa los costos de desarrollo y aumenta la probabilidad de cometer errores.

- Ausencia de herramientas inteligentes y accesibles: Las herramientas existentes para documentación de bases de datos son costosas, están vinculadas a gestores específicos, no ofrecen análisis crítico del diseño y no se benefician de las capacidades de la inteligencia artificial moderna.

### Justificación del proyecto

El proyecto propone una solución que combina un motor de análisis en Python con un módulo de inteligencia artificial para superar las limitaciones de las herramientas existentes. De esta manera, el sistema no solo permite realizar un análisis técnico preciso, con detección de claves, relaciones y métricas de normalización, sino que también ofrece una evaluación crítica del diseño, sugerencias de mejora y documentación descriptiva. Esta combinación de funciones no suele encontrarse de forma completa en herramientas gratuitas disponibles en el mercado.

Además, el sistema ha sido planteado utilizando herramientas de código abierto como Node.js, Python y librerías con licencias libres, junto con servicios que ofrecen planes gratuitos como Supabase y Vercel. Esto permite reducir considerablemente los costos de desarrollo e implementación, especialmente si se compara con soluciones comerciales de documentación que suelen requerir pagos anuales elevados por licencia.

Desde el punto de vista del uso práctico, el sistema reduce de manera significativa el tiempo dedicado a la documentación manual de bases de datos, permitiendo que los equipos de desarrollo enfoquen sus esfuerzos en actividades de mayor valor dentro del proceso de software. Esta automatización mejora la productividad y disminuye la carga repetitiva asociada a la elaboración de documentación técnica.

El proyecto también tiene un valor importante en el ámbito académico, ya que integra conocimientos de distintas áreas de la Ingeniería de Sistemas, como diseño de bases de datos, desarrollo web, análisis de sistemas y gestión de proyectos. Esto lo convierte en una experiencia aplicada que fortalece el aprendizaje y permite poner en práctica conceptos vistos en el curso.

Finalmente, al tratarse de una herramienta web accesible y basada en tecnologías de libre uso, el sistema puede ser adoptado por distintos equipos de desarrollo sin depender de grandes recursos económicos. Esto favorece el acceso a una solución profesional de documentación y contribuye a que más personas puedan organizar y comprender mejor sus bases de datos.

### Objetivo general

#### 3.1.- Objetivo General

Desarrollar un sistema web híbrido que combine inteligencia artificial y análisis técnico local para automatizar la documentación, auditoría y conversión de esquemas de bases de datos SQL y NoSQL, reduciendo el tiempo de documentación manual y mejorando la calidad, accesibilidad y comprensión de la información estructural de los sistemas de datos.

#### 3.2.- Objetivos Específicos

- Implementar un motor de análisis técnico en Python que extraiga automáticamente metadatos de bases de datos como tablas, campos, tipos de datos, claves primarias y foráneas, relaciones explícitas e implícitas, índices y métricas de normalización a partir de archivos de esquema en múltiples formatos.

- Desarrollar un módulo de visualización de diagramas Entidad–Relación interactivos, con controles de zoom, navegación y exportación en formato SVG, que faciliten la comprensión visual de la estructura y las relaciones de la base de datos.

- Construir un convertidor de esquemas profesional que permita transformar la estructura de la base de datos analizada a nueve formatos y tecnologías diferentes, facilitando procesos de migración y adopción de nuevas tecnologías.

- Desarrollar una interfaz web moderna e intuitiva que permita a usuarios de distintos perfiles técnicos realizar el flujo completo de documentación, desde la carga y análisis hasta la visualización y exportación, sin necesidad de instalación de software adicional ni conocimientos técnicos avanzados.

- Habilitar la exportación de reportes en formatos estándar, generando documentos completos y listos para presentación o archivo formal, que incluyan la documentación técnica, el análisis de auditoría y los diagramas ER.

### Beneficios

Los beneficios se calculan considerando el ahorro en tiempo, reducción de costos operativos y mejoras en la calidad y eficiencia de los procesos de desarrollo y gestión de bases de datos.

Beneficios tangibles:

- Reducción del tiempo de documentación manual (estimado 60% menos de horas invertidas).

- Disminución de errores en modificaciones de base de datos en un 50%.

- Reducción de costos de mantenimiento por mejor comprensión del sistema estimados en un 15%.

- Eliminación de costos de herramientas comerciales equivalentes.

Beneficios intangibles:

- Mejora significativa en la organización y calidad de la información técnica.

- Mayor eficiencia y productividad en el trabajo colaborativo de los equipos.

- Mejor toma de decisiones arquitectónicas basada en documentación actualizada.

- Incremento en la calidad del software desarrollado gracias a la mayor comprensión del modelo de datos.

- Reducción de la dependencia del conocimiento tácito de individuos específicos.

- Ventaja competitiva para organizaciones que adopten el sistema.

- Valor agregado como herramienta académica y de formación para estudiantes.

- Aumento en la confiabilidad de la información almacenada y gestionada.

- Cumplimiento de buenas prácticas de ingeniería de software en gestión de datos.

### Alcance

El Sistema de documentación de base de datos comprende varias funcionalidades dentro de su alcance, orientadas principalmente a facilitar la lectura, análisis, documentación y organización de esquemas de bases de datos. Entre las funciones incluidas se encuentra la carga de archivos de esquemas en formatos como .sql, .json, .xlsx, .yaml, .csv y .dbml, así como el análisis automático de su estructura para identificar tablas, campos, tipos de datos, claves primarias y claves foráneas, tanto explícitas como implícitas.

También forma parte del alcance la generación de documentación técnica estructurada, incluyendo diccionarios de datos, descripciones de tablas y relaciones, además de la creación de diagramas Entidad–Relación interactivos con opciones de zoom y exportación en formato SVG. El sistema igualmente permite detectar problemas estructurales como redundancias, relaciones poco definidas o ausencia de normalización, con el fin de ofrecer una visión más clara del estado del esquema analizado.

Dentro de las funcionalidades contempladas se encuentra además la generación de reportes de auditoría con observaciones y recomendaciones, apoyada por inteligencia artificial, así como la conversión de esquemas entre distintas tecnologías como MySQL, PostgreSQL, SQLite, MongoDB mediante Mongoose, Prisma, GraphQL, JSON Schema, CSV y YAML. A esto se suma la exportación de documentación en formatos PDF, la gestión de usuarios con autenticación, roles y compartición de documentación, la generación de datos de prueba sintéticos basados en el esquema analizado y el soporte para el análisis de bases de datos NoSQL, especialmente MongoDB.

Por otro lado, existen ciertas funcionalidades que no forman parte del alcance del proyecto. El sistema no realiza modificaciones directas sobre la base de datos ni ejecuta cambios automáticos en el esquema. Tampoco se conecta de manera directa y en tiempo real a servidores de producción, ni incorpora una versión avanzada de esquemas con comparación entre diferentes versiones.

### Requerimientos del sistema

#### 6.1. Cuadro de Requerimientos Funcionales Inicial

| **Código** | **Nombre** | **Descripción** | **Prioridad** |
| :- | :- | :- | :- |
| RF01 | Autenticar Usuario | Permitir el inicio de sesión de usuarios registrados mediante credenciales seguras como email y contraseña, gestionadas por Supabase con tokens JWT. | Alta |
| RF02 | Cargar Archivo de Esquema | Permitir la carga de archivos de esquemas de bases de datos en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml mediante arrastrar y soltar o selección manual. | Alta |
| RF03 | Analizar Estructura de BD | Procesar el archivo cargado y extraer automáticamente tablas, campos, tipos de datos, claves primarias y foráneas, relaciones e índices mediante el motor Python. | Alta |
| RF04 | Generar Documentación Técnica | Crear documentación estructurada de la base de datos, incluyendo diccionario de datos, descripción de tablas y relaciones, a partir del análisis realizado. | Alta |
| RF05 | Detectar Relaciones Implícitas | Identificar relaciones entre tablas no declaradas explícitamente mediante Fuzzy Matching de nombres de columnas, como user_id que referencia implícitamente a la tabla users. | Alta |

#### 6.2. Cuadro de Requerimientos No Funcionales

| **Código** | **Categoría** | **Descripción** | **Métrica** |
| :- | :- | :- | :- |
| RNF01 | Rendimiento | El sistema deberá procesar y mostrar resultados del análisis técnico Python para bases de datos de hasta 50 tablas en un tiempo máximo de 10 segundos. | <= 10 seg |
| RNF02 | Rendimiento | El análisis deberá completarse en un tiempo máximo de 30 segundos. | <= 30 seg |
| RNF03 | Disponibilidad | El sistema deberá estar disponible durante las horas de operación del proyecto con un tiempo de actividad mensual igual o superior al 99%. | >= 99% |
| RNF04 | Seguridad | Las credenciales de usuario deberán estar cifradas y gestionadas mediante tokens JWT, y las claves de API se administrarán mediante variables de entorno. | Cumplimiento obligatorio |
| RNF05 | Seguridad | El sistema operará en modo estricto de solo lectura sobre las bases de datos analizadas, sin ejecutar operaciones DML ni DDL. | Cumplimiento obligatorio |
| RNF06 | Usabilidad | La interfaz deberá ser responsiva y adaptable a distintas resoluciones de pantalla, incluyendo escritorio y tablets. | Responsive |
| RNF07 | Usabilidad | Un usuario nuevo deberá poder completar el flujo principal sin capacitación previa en un tiempo máximo de 5 minutos. | <= 5 min |
| RNF08 | Compatibilidad | El sistema deberá funcionar correctamente en Chrome, Firefox, Edge y Safari. | 4 navegadores verificados |
| RNF09 | Portabilidad | El sistema deberá poder ejecutarse en Windows 10/11 para desarrollo y Ubuntu Server 22.04 para producción sin modificaciones. | Multiplataforma |
| RNF10 | Mantenibilidad | El código deberá estar organizado de forma modular por capas, con documentación interna y una arquitectura bien definida. | Arquitectura por capas |
| RNF11 | Escalabilidad | El sistema deberá soportar múltiples usuarios simultáneos sin degradación significativa del rendimiento. | Arquitectura stateless |
| RNF12 | Privacidad | Los archivos de esquema cargados deberán eliminarse del servidor tras el procesamiento y no se persistirá información estructural sensible sin autorización. | Cumplimiento obligatorio |

#### 6.3. Cuadro de Requerimientos Funcionales Final

| **Código** | **Nombre** | **Descripción** | **Prioridad** |
| :- | :- | :- | :- |
| RF01 | Iniciar Sesión | Autenticación de usuarios mediante email y contraseña. | Alta |
| RF02 | Registrar Usuario | Crear nuevas cuentas de usuario en el sistema con validación de datos y asignación de rol, ya sea administrador o usuario estándar. | Alta |
| RF03 | Cargar Archivo de Esquema | Cargar archivos en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml mediante interfaz de arrastrar y soltar con validación de tipo y tamaño. | Alta |
| RF04 | Analizar BD con Python | Ejecutar el motor de análisis local Python para extraer tablas, campos, tipos de datos, claves PK y FK explícitas e implícitas, índices, restricciones y métricas de normalización. | Alta |
| RF05 | Generar Diagrama ER | Renderizar un diagrama Entidad–Relación interactivo con Mermaid.js a partir de las relaciones detectadas, con controles de zoom y exportación en formato SVG. | Alta |
| RF06 | Exportar a PDF | Generar y descargar un reporte completo de la documentación en formato PDF mediante jsPDF, incluyendo tablas, relaciones y resultados del análisis. | Alta |
| RF07 | Exportar a Word | Generar y descargar un reporte de documentación en formato Word en estructura formal. | Alta |
| RF08 | Convertir Esquema | Transformar el esquema analizado a uno de los nueve formatos disponibles: MySQL, PostgreSQL, SQLite, MongoDB mediante Mongoose, Prisma, GraphQL, JSON Schema, CSV y YAML. | Media |
| RF09 | Guardar Documentación | Almacenar en Supabase la documentación generada para su consulta posterior desde la sección "Mis documentaciones guardadas". | Media |
| RF10 | Compartir Documentación | Compartir una documentación guardada con otros usuarios registrados en la plataforma, accesible desde la sección "Documentaciones compartidas". | Media |
| RF11 | Gestionar Usuarios | Panel exclusivo para administradores que permite crear, editar, activar, desactivar y eliminar cuentas de usuario, y visualizar estadísticas de uso. | Media |
| RF12 | Generar Datos de Prueba | Crear datasets sintéticos y realistas basados en la estructura de la base de datos analizada utilizando las librerías de Python. | Baja |

### Restricciones

A continuación se presentan las limitaciones que delimitan el funcionamiento y el alcance del sistema.

- Solo lectura: El sistema se limita exclusivamente a la lectura e interpretación de esquemas de bases de datos. No tiene capacidad para modificar, editar, eliminar y administrar datos dentro de ninguna base de datos.

- Operación basada en archivos: El sistema trabaja únicamente con archivos de esquemas cargados por el usuario. No realiza conexiones directas en tiempo real a servidores de bases de datos en producción.

- Dependencia de la calidad del esquema: La precisión de la documentación generada depende directamente de la calidad, completitud y consistencia del archivo proporcionado. Si el esquema está incompleto o presenta sintaxis no estándar, los resultados pueden ser parciales o presentar omisiones.

- Restricción de tiempo de desarrollo: El proyecto se desarrolla en un periodo de 2 meses con un equipo de 2 personas, lo que limita la incorporación de funcionalidades más avanzadas en la primera versión del sistema.

- Limitaciones del plan gratuito: En su versión académica, el sistema opera bajo un plan gratuito, por lo que está sujeto a límites de almacenamiento, conexiones simultáneas y cantidad de filas en la base de datos.

- Navegadores compatibles: El sistema requiere navegadores modernos que soportan HTML5, CSS3, JavaScript. No se garantiza compatibilidad con versiones antiguas de navegadores como Internet Explorer.

- Tamaño máximo de archivo: Se establece un límite para los archivos de esquema cargados, ya que archivos mayores a 10 MB pueden generar tiempos de procesamiento elevados o incluso fallas durante el análisis.

- Conocimiento técnico mínimo requerido: Para interpretar correctamente la documentación generada, especialmente los diagramas Entidad–Relación y las métricas de normalización, se requiere una comprensión básica de conceptos de bases de datos relacionales.

### Supuestos

Los usuarios dispondrán de equipos de cómputo con navegadores web modernos y conexión estable a internet con un mínimo de 5 Mbps para el correcto funcionamiento del sistema.

Los archivos de esquema proporcionados al sistema contendrán información estructural válida y procesable por los analizadores del motor Python. Se asume que los usuarios exportarán sus esquemas desde gestores de bases de datos estándar siguiendo los formatos convencionales reconocidos por el sistema.

Los usuarios tendrán conocimientos básicos sobre bases de datos relacionales para interpretar correctamente la documentación y los diagramas Entidad-Relación generados por el sistema.

Las librerías de Python utilizadas, entre ellas sqlglot, pandas, networkx y Faker, mantendrán su compatibilidad y disponibilidad en los repositorios de instalación durante el período de desarrollo y uso del sistema.

El equipo de desarrollo contará con la disponibilidad de tiempo estimada de aproximadamente 72 horas por persona durante los 2 meses, suficiente para completar todas las funcionalidades planificadas dentro del cronograma establecido.

Los equipos de cómputo del equipo de desarrollo mantendrán su operatividad durante todo el período del proyecto sin necesidad de reemplazos o reparaciones mayores que afecten el cronograma.

Los servicios de despliegue utilizados para la puesta en producción del sistema permanecerán disponibles bajo sus planes gratuitos con las capacidades necesarias para ejecutar el backend del sistema durante la fase académica.

### Resultados esperados

- Sistema web funcional y desplegado: una aplicación web completamente operativa, accesible desde cualquier navegador moderno, que implemente todas las funcionalidades planificadas dentro de los parámetros de calidad establecidos por los requerimientos no funcionales.

- Motor de análisis Python integrado y validado: un motor de análisis técnico local capaz de procesar correctamente archivos de esquemas en todos los formatos soportados, extrayendo metadatos con una precisión igual o superior al 95% en la identificación de tablas, campos y relaciones explícitas.

- Reducción demostrable del tiempo de documentación: demostración práctica de que el sistema reduce el tiempo de documentación de bases de datos de un rango de 4 a 8 horas en el proceso manual a un rango de 2 a 5 minutos en el proceso automatizado, representando una reducción del 60-70%.

- Documentación técnica completa del proyecto: entrega de todos los documentos formales requeridos, incluyendo el Informe de Factibilidad, el Documento de Visión, la Especificación de Requerimientos, el Documento de Arquitectura e Informe General del Proyecto, alineados con los estándares de la Ingeniería de Software.

- Sistema seguro y conforme con normativas: implementación verificada de todas las medidas de seguridad establecidas, incluyendo autenticación con token, modo solo lectura, eliminación de archivos temporales y gestión de credenciales mediante variables de entorno, con cumplimiento demostrable de la Ley N° 29733 de Protección de Datos Personales del Perú.

- Módulo de conversión de esquemas operativo: módulo funcional capaz de transformar correctamente el esquema analizado a los distintos formatos tecnológicos soportados, verificado mediante pruebas con esquemas de referencia de distintos gestores de bases de datos.

- Validación de viabilidad financiera: confirmación de los indicadores financieros proyectados mediante el análisis de beneficios obtenidos durante la fase de pruebas con usuarios reales, verificando la relación Beneficio/Costo de 1.58, el Valor Actual Neto positivo y la Tasa Interna de Retorno del 54.5%.

### Metodología de implementación

Para el desarrollo del sistema se adoptó una metodología ágil incremental combinada con la elaboración de documentación formal alineada con los estándares de la Ingeniería de Software.

**Enfoque metodológico general:**

El proceso de desarrollo siguió un ciclo iterativo de cinco fases con revisiones al final de cada sprint semanal: Análisis, Diseño, Desarrollo, Pruebas y Documentación, volviendo a iterar en cada ciclo. Cada iteración produjo un incremento funcional del sistema, comenzando por las funcionalidades críticas como el motor de análisis Python, el servidor Node.js y la interfaz básica, avanzando progresivamente hacia características complementarias como el convertidor de esquemas y la gestión de usuarios.

**Artefactos de documentación formal producidos:**

Documento de Visión: define el alcance general del sistema, los interesados y usuarios, las necesidades identificadas, las características del producto, las restricciones y los criterios de calidad, estableciendo el panorama general del sistema desde una perspectiva de alto nivel.

Especificación de Requerimientos del Software: basado en el estándar IEEE 830, describe con precisión los requisitos funcionales y no funcionales del sistema, incluyendo casos de uso detallados con flujos normales y de excepción para cada funcionalidad principal.

Documento de Arquitectura del Software: define la arquitectura técnica del sistema, describiendo los componentes principales, sus interfaces, los patrones arquitectónicos aplicados como REST y cliente-servidor, y las decisiones de diseño que guiaron el desarrollo.

**Herramientas y tecnologías de implementación:**

El desarrollo utilizó el siguiente stack tecnológico: Node.js para el servidor backend; Python con sqlglot y pandas, para el motor de análisis; HTML5, CSS3 y JavaScript con Mermaid.js para el frontend; WebSockets para comunicación en tiempo real durante el procesamiento; y Git para el control de versiones del código fuente.

**Criterios de calidad aplicados:**

El desarrollo siguió el modelo de calidad ISO/IEC 25010:2011, evaluando los atributos de disponibilidad, rendimiento, usabilidad, precisión, fiabilidad, portabilidad, mantenibilidad y seguridad. Las metas específicas fueron: disponibilidad mensual igual o superior al 99%; tiempo de análisis igual o menor a 10 segundos para esquemas de hasta 50 tablas; flujo principal completable en menos de 5 minutos; precisión en la extracción de metadatos igual o superior al 95%; cero errores críticos no controlados en uso estándar; compatibilidad verificada en los principales navegadores modernos; y arquitectura modular por capas que facilite el mantenimiento y la extensión del sistema.

### Actores claves

- Equipo de Desarrollo: Es el grupo responsable del análisis, diseño, desarrollo, pruebas, documentación e implementación del sistema. Tiene el mayor nivel de participación en todas las fases del proyecto y ejecuta las actividades técnicas y funcionales necesarias para su construcción.

- Desarrolladores de Software: Profesionales y estudiantes que utilizarán el sistema para analizar y documentar bases de datos. Son usuarios frecuentes de la plataforma y requieren que la documentación generada sea clara, precisa y completa.

- Administradores de Bases de Datos: Profesionales encargados de la gestión, optimización y seguridad de las bases de datos. Utilizan el sistema para validar la consistencia del esquema y verificar la exactitud de la documentación generada.

- Analistas de Sistemas: Usuarios que emplean la documentación y los diagramas Entidad–Relación como apoyo en tareas de análisis, diseño y toma de decisiones técnicas.

- Administrador del Sistema: Usuario con acceso total a la plataforma, encargado de gestionar cuentas, permisos y configuraciones generales. Interactúa principalmente con el panel administrativo.

- Organización o Empresa Usuaria: Instituciones académicas y empresas de desarrollo de software que pueden adoptar el sistema para mejorar sus procesos de documentación y análisis de bases de datos.

### Papel y responsabilidades del personal

**Administrador**

- Función: Gestionar el acceso al sistema, controlar cuentas de usuario, supervisar el funcionamiento de la plataforma, configurar parámetros generales del sistema y garantizar la seguridad de la información procesada.

- Necesidades: Acceso completo al sistema, incluyendo panel de administración de usuarios, visualización de estadísticas de uso, monitoreo de procesos de análisis, y control sobre la documentación compartida entre usuarios.

- Privilegios: Acceso total a todas las funcionalidades del sistema, incluyendo las exclusivas del panel de administración.

- Conocimientos requeridos: Gestión de sistemas de información, administración de bases de datos, seguridad informática básica.

**Desarrollador**

- Función: Utilizar la herramienta para analizar bases de datos, generar documentación automática, visualizar estructuras y relaciones, y comprender el modelo de datos de los sistemas que desarrolla o mantiene.

- Necesidades: Acceso a las funcionalidades de carga de archivos de esquema, análisis técnico, auditoría, visualización de diagramas ER interactivos, conversión de esquemas entre tecnologías, y exportación de documentación.

- Privilegios: Acceso a todas las funcionalidades estándar del sistema.

- Conocimientos requeridos: Conocimientos básicos-intermedios de bases de datos relacionales y/o NoSQL, desarrollo de software.

**Analista**

- Función: interpretar la documentación e información estructural generada por el sistema para apoyar procesos de análisis funcional, modelado de sistemas, toma de decisiones arquitectónicas y elaboración de reportes técnicos.

- Necesidades: acceso a reportes claros y bien estructurados, documentación organizada del esquema, visualización comprensible de los diagramas ER, y facilidad para exportar y compartir la documentación generada con otros miembros del equipo.

- Privilegios: acceso a funcionalidades de análisis, visualización, exportación y compartición de documentación.

- Conocimientos requeridos: conocimientos intermedios de modelado de datos, análisis y diseño de sistemas de información.

### Plan de monitoreo y evaluación

El plan de monitoreo y evaluación del Sistema de documentación de base de datos establece los mecanismos, indicadores y frecuencias de seguimiento necesarios para asegurar que el proyecto se desarrolle según lo planificado y cumpla con los estándares de calidad definidos.

**Indicadores de Desempeño del Proyecto**

Avance del cronograma: porcentaje de tareas completadas respecto al total planificado para cada semana. Meta: 100% de cumplimiento semanal. Frecuencia de medición: semanal. Responsable: equipo de desarrollo.

Cobertura de requerimientos funcionales implementados: número de requerimientos funcionales completamente implementados y probados respecto al total. Meta: cumplimiento total al finalizar la fase de desarrollo. Frecuencia: al cierre de cada etapa. Responsable: equipo de desarrollo.

Calidad de la documentación entregada: evaluación de la completitud, coherencia y alineación con los estándares académicos de cada documento entregado. Meta: aprobación de todos los documentos sin observaciones críticas. Frecuencia: por hito de entrega. Responsable: docente supervisor.

Horas de trabajo registradas: seguimiento de las horas efectivas de desarrollo respecto a lo planificado. Meta: cumplimiento de la carga de trabajo establecida por integrante. Frecuencia: semanal. Responsable: equipo de desarrollo.

**Indicadores de Calidad del Sistema**

Precisión del motor de análisis: porcentaje de tablas, campos y relaciones identificadas correctamente en los esquemas de prueba respecto al total real. Meta: igual o superior al 95%. Medición: durante la fase de pruebas con esquemas de referencia. Responsable: equipo de desarrollo.

Tiempo de respuesta del análisis técnico: tiempo transcurrido desde la carga del archivo hasta la presentación de los resultados al usuario. Meta: igual o menor a 10 segundos para esquemas de hasta 50 tablas. Medición: mediante cronometraje en pruebas de distintos tamaños. Responsable: equipo de desarrollo.

Completitud del flujo principal para usuarios nuevos: tiempo que tarda un usuario sin experiencia previa en completar el flujo de carga, análisis, visualización y exportación. Meta: igual o menor a 5 minutos sin capacitación previa. Medición: sesiones de prueba de usabilidad con usuarios de distintos perfiles. Responsable: equipo de desarrollo.

Compatibilidad con navegadores: verificación del correcto funcionamiento del sistema en los navegadores definidos. Meta: funcionamiento completo sin errores críticos. Medición: pruebas manuales de cada funcionalidad al finalizar el desarrollo del frontend. Responsable: equipo de desarrollo.

Disponibilidad del sistema desplegado: porcentaje de tiempo en que el sistema permanece accesible sin interrupciones. Meta: igual o superior al 99% mensual. Medición: monitoreo continuo desde el despliegue. Responsable: equipo de desarrollo.

Tasa de errores críticos no controlados: número de errores no manejados que generen caída del sistema o pérdida de datos durante el uso estándar. Meta: cero errores críticos no controlados. Medición: revisión de registros del sistema durante las pruebas. Responsable: equipo de desarrollo.

**Indicadores de Impacto**

Reducción del tiempo de documentación: comparación entre el tiempo promedio del proceso manual y el tiempo del proceso automatizado en pruebas con usuarios reales. Meta: reducción demostrable del 60% al 70%. Medición: sesiones cronometradas con usuarios de prueba. Responsable: equipo de desarrollo.

Satisfacción de usuarios con la documentación generada: evaluación subjetiva de la precisión, claridad, utilidad y completitud de la documentación obtenida. Meta: calificación promedio igual o superior a 4 sobre 5. Medición: encuesta de satisfacción posterior a la prueba. Responsable: equipo de desarrollo.

**Mecanismos de Reporte y Seguimiento**

Reuniones de seguimiento semanal: el equipo de desarrollo realizará reuniones semanales para revisar el avance, identificar bloqueos técnicos, ajustar prioridades y actualizar el estado de las tareas.

Revisiones de hito con el docente supervisor: al finalizar cada fase principal del proyecto, se presentarán los avances para su revisión, retroalimentación y aprobación.

Control de versiones: el uso de Git permitirá registrar y dar seguimiento a los cambios realizados durante el desarrollo del sistema.

Registro de incidencias técnicas: se mantendrá un control de problemas encontrados y soluciones aplicadas, como parte de la documentación técnica del proyecto.

### Cronograma del proyecto

El desarrollo del proyecto se organiza en diferentes etapas que permiten avanzar de forma ordenada, asegurando que cada fase cumpla con sus objetivos antes de pasar a la siguiente. Este enfoque progresivo ayuda a reducir errores y facilita el control del avance del proyecto.

| **Fase** | **Actividad principal** | **Semanas** | **Descripción** |
| :- | :- | :- | :- |
| Fase 1 | Análisis del problema | Semana 1 | Identificación de necesidades, revisión del contexto, definición del problema y de los objetivos, y elaboración del Documento de Visión. |
| Fase 2 | Diseño del sistema | Semana 2 | Definición de la arquitectura del sistema, diseño de la API REST y los endpoints, elaboración del SRS y SAD, y diseño de la base de datos en Supabase. |
| Fase 3 | Desarrollo del prototipo: Módulo Core | Semanas 3 y 4 | Implementación del servidor Node.js con Express, desarrollo del motor de análisis en Python, creación del generador de diagramas e integración entre el servidor y el motor Python. |
| Fase 4 | Desarrollo del prototipo: Módulo Avanzado | Semanas 5 y 6 | Integración con la API, desarrollo del convertidor de esquemas, generación de datos de prueba, implementación del frontend, sistema de usuarios y exportación en PDF y Word. |
| Fase 5 | Pruebas del sistema | Semana 6 | Pruebas funcionales, pruebas de integración entre los módulos principales, pruebas con archivos reales y corrección de errores detectados. |
| Fase 6 | Despliegue y documentación final | Semana 7 | Despliegue en producción, elaboración del Informe de Factibilidad, elaboración del informe general, manuales de usuario y entrega final. |

Duración total: 7 semanas aproximadamente, equivalentes a 2 meses.

Fecha de inicio: Abril de 2026.

Fecha de entrega: Junio de 2026.

### Hitos de entregables

| **Hito** | **Semana** | **Entregable** | **Criterio de éxito** |
| :- | :- | :- | :- |
| Hito 1 | 1 | Documento de Visión versión 1.0 aprobado | Documento completo con las secciones de propósito, alcance, definiciones, posicionamiento, descripción de interesados, características del producto, restricciones y criterios de calidad. |
| Hito 2 | 2 | Especificación de Requerimientos versión 1.0 y Documento de Arquitectura versión 1.0 aprobados | Especificación con requerimientos funcionales y no funcionales documentados, además de casos de uso detallados; documento de arquitectura con la estructura técnica completa y las decisiones de diseño justificadas. |
| Hito 3 | 4 | Servidor Node.js funcional con motor Python integrado | Capacidad para procesar archivos .sql, .json y .yaml y retornar metadatos estructurados. |
| Hito 4 | 6 | Sistema web completamente funcional | Todas las funcionalidades de prioridad alta implementadas y las de prioridad media en estado básico operativo. |
| Hito 5 | 6 y 7 | Reporte de pruebas con criterios de aceptación verificados | Precisión del análisis igual o superior al 95%, tiempos de respuesta dentro de los límites establecidos, cero errores críticos no controlados y flujo principal completado en menos de 5 minutos. |
| Hito 6 | 7 | Sistema desplegado e informes finales aprobados | Sistema accesible en producción, documentos completos y aprobación final del proyecto. |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## II Presupuesto

### 1. Planteamiento de aplicación del presupuesto

El presupuesto del proyecto se ha definido tomando en cuenta las necesidades reales de desarrollo, prueba, despliegue y documentación de una solución web orientada a la automatización del análisis y documentación de bases de datos. Para ello, se ha considerado una distribución de costos en cuatro grandes grupos: costos generales, costos operativos, costos de ambiente y costos de personal. Esta clasificación permite organizar de manera más clara los recursos necesarios y estimar el esfuerzo global requerido para la ejecución del proyecto.

Los costos generales comprenden gastos menores vinculados con materiales de apoyo, insumos de oficina y otros recursos básicos que facilitan el trabajo diario durante el desarrollo. Aunque no representan una proporción elevada del total, sí son necesarios para sostener las actividades de planificación, control y elaboración de documentación. Por otro lado, los costos operativos incluyen los servicios indispensables para la continuidad del proyecto, como conectividad a internet, consumo eléctrico y desplazamientos para coordinación o revisión de avances. Estos gastos tienden a concentrarse durante las semanas de mayor actividad, especialmente en las fases de desarrollo e integración.

En cuanto a los costos de ambiente, estos abarcan la infraestructura tecnológica necesaria para construir, probar y desplegar el sistema. Dado que el proyecto aprovecha herramientas de código abierto y servicios con modalidades gratuitas o de bajo costo, esta categoría se mantiene dentro de un rango controlado. Esto permite reducir significativamente la inversión requerida sin comprometer la funcionalidad ni la calidad de la solución. Además, el uso de tecnologías web y servicios remotos evita la necesidad de adquirir equipamiento especializado adicional.

Finalmente, los costos de personal representan la valoración del tiempo y esfuerzo invertido por el equipo de desarrollo. Aunque el proyecto no implica necesariamente un desembolso monetario directo equivalente a ese valor, sí es importante considerarlo como parte del presupuesto global para reflejar el trabajo académico realizado. Esta estimación permite dimensionar el costo real de construir una solución de este tipo y sirve como referencia para evaluar su viabilidad económica. En conjunto, la distribución del presupuesto busca equilibrar funcionalidad, eficiencia de recursos y sostenibilidad durante las siete semanas previstas para el desarrollo del proyecto.

### 2. Presupuesto

**Costos Generales**

Corresponden a los materiales y recursos de uso cotidiano necesarios para el proyecto.

| **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- |
| Hojas bond A4 (Paquete 500 hojas) | 1 paquete | 25.00 | 25.00 |
| Lapiceros | 5 unidades | 2.00 | 10.00 |
| Folder y archivadores | 2 unidades | 5.00 | 10.00 |
| Impresión de documentos | 2 lote | 30.00 | 30.00 |
| **Total** | | | **75.00** |

**Costos operativos durante el desarrollo**

Gastos necesarios para mantener la operatividad del equipo durante los 2 meses de desarrollo.

| **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- |
| Internet (mensual) | 2 meses x 2 personas | 80.00 | 320.00 |
| Energía eléctrica | 2 meses x 2 personas | 30.00 | 120.00 |
| Transporte | 2 meses | 40.00 | 80.00 |
| Mantenimiento de equipos | 1 vez | 30.00 | 30.00 |
| **Total** | | | **550.00** |

**Costos del ambiente**

El proyecto utiliza infraestructura existente, por lo que no se requiere inversión significativa:

| **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- |
| Dominio web | Fase académica | 0.00 | 0.00 |
| BaaS | Plan gratuito | 0.00 | 0.00 |
| Hosting | Plan gratuito | 0.00 | 0.00 |
| Producción (Opcional) | Solo en despliegue permanente | 50.00 | 50.00 |
| **Total** | | | **50.00** |

**Costos de personal**

| **Rol** | **Cantidad** | **Duración** | **Pago mensual (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- | :- |
| Desarrollador Backend | 1 | 2 meses | 800.00 | 1600.00 |
| Desarrollador Frontend | 1 | 2 meses | 800.00 | 1600.00 |
| **Total** | | | | **3200.00** |

**Costos totales del desarrollo del sistema**

| **Tipo de costo** | **Monto (S/.)** |
| :- | :- |
| Costos generales | 75.00 |
| Costos operativos | 550.00 |
| Costos ambiente | 100.00 |
| Costos personal | 3200.00 |
| **Total** | **3925.00** |

### 3.   Análisis de Factibilidad

El estudio de factibilidad tiene como objetivo determinar si el proyecto planteado es viable en sus diferentes aspectos: técnico, económico, operativo, legal, social y ambiental. Con ello se busca comprobar no solo si el sistema puede construirse, sino también si realmente puede aportar una solución útil, ordenada y adecuada a la necesidad identificada.

Para elaborar este estudio, se realizaron varias actividades que permitieron analizar el proyecto desde una perspectiva más completa. Entre ellas se consideran el análisis de los requerimientos funcionales y no funcionales del sistema, la revisión de los recursos tecnológicos disponibles en el equipo de desarrollo, la selección de herramientas, frameworks y servicios de terceros que se ajusten al proyecto, la estimación de los costos de desarrollo e infraestructura, y el análisis del impacto social, legal y ambiental de la propuesta.

De esta manera, el estudio de factibilidad permite identificar si el sistema puede desarrollarse dentro de un contexto realista, con recursos alcanzables y con un beneficio claro para los usuarios. También ayuda a reducir riesgos y a definir con mayor seguridad el camino que seguirá el proyecto durante su desarrollo.

**Factibilidad Técnica**

Actualmente, el equipo de desarrollo está conformado por un pequeño grupo de personas, donde cada integrante dispone de su propia laptop o computadora personal.

- Procesador: Intel Core i3 o superior: Suficiente para desarrollo, pruebas locales y ejecución del servidor Node.js y Python.

- Memoria RAM de 8GB: Adecuada para ejecutar el entorno de desarrollo completo.

- Almacenamiento: 256GB SSD/HDD: Suficiente para el código fuente, dependencias y archivos temporales de prueba.

- Servidor de pruebas: Se utilizará un equipo local durante el desarrollo. Para producción, se evaluará el uso de un VPS o Vercel (plataforma serverless compatible con el stack del proyecto).

- Navegadores compatibles: Google Chrome, Mozilla Firefox, Microsoft Edge y otros navegadores modernos compatibles con tecnologías HTML5, CSS3 y JavaScript.

- Sistemas operativos compatibles:

    - Desarrollo: Windows 10/11 y Linux (Ubuntu).

    - Producción: Ubuntu Server o Debian.

**Factibilidad Económica**

El estudio de viabilidad económica permite determinar si el proyecto es rentable, comparando los beneficios esperados frente a los costos de desarrollo e implementación.

Se evalúa si el equipo cuenta con los recursos necesarios o si se requiere inversión adicional. En este caso, el proyecto presenta una inversión baja, ya que se utilizan herramientas de desarrollo gratuitas y equipos propios.

Definir los siguientes costos:

**Costos Generales**

Corresponden a los materiales y recursos de uso cotidiano necesarios para el proyecto.

| **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- |
| Hojas bond A4 (Paquete 500 hojas) | 1 paquete | 25.00 | 25.00 |
| Lapiceros | 5 unidades | 2.00 | 10.00 |
| Folder y archivadores | 2 unidades | 5.00 | 10.00 |
| Impresión de documentos | 2 lote | 30.00 | 30.00 |
| **Total** | | | **75.00** |

**Costos operativos durante el desarrollo**

Gastos necesarios para mantener la operatividad del equipo durante los 2 meses de desarrollo.

| **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- |
| Internet (mensual) | 2 meses x 2 personas | 80.00 | 320.00 |
| Energía eléctrica | 2 meses x 2 personas | 30.00 | 120.00 |
| Transporte | 2 meses | 40.00 | 80.00 |
| Mantenimiento de equipos | 1 vez | 30.00 | 30.00 |
| **Total** | | | **550.00** |

**Costos del ambiente**

El proyecto utiliza infraestructura existente, por lo que no se requiere inversión significativa:

| **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- |
| Dominio web | Fase académica | 0.00 | 0.00 |
| BaaS | Plan gratuito | 0.00 | 0.00 |
| Hosting | Plan gratuito | 0.00 | 0.00 |
| Producción (Opcional) | Solo en despliegue permanente | 50.00 | 50.00 |
| **Total** | | | **50.00** |

**Costos de personal**

| **Rol** | **Cantidad** | **Duración** | **Pago mensual (S/.)** | **Total (S/.)** |
| :- | :- | :- | :- | :- |
| Desarrollador Backend | 1 | 2 meses | 800.00 | 1600.00 |
| Desarrollador Frontend | 1 | 2 meses | 800.00 | 1600.00 |
| **Total** | | | | **3200.00** |

**Costos totales del desarrollo del sistema**

| **Tipo de costo** | **Monto (S/.)** |
| :- | :- |
| Costos generales | 75.00 |
| Costos operativos | 550.00 |
| Costos ambiente | 100.00 |
| Costos personal | 3200.00 |
| **Total** | **3925.00** |

**Factibilidad Operativa**

El sistema documentador de bases de datos ofrece importantes beneficios operativos para los equipos de desarrollo y gestión de sistemas de información. Este sistema permitirá automatizar la documentación de bases de datos, facilitando la visualización de estructuras, relaciones y atributos, lo que reduce significativamente los tiempos de análisis y comprensión.

Asimismo, optimiza el flujo de trabajo al disminuir la necesidad de documentar manualmente, reduciendo errores y mejorando la calidad de la información disponible. Esto permite que los procesos de mantenimiento, actualización y desarrollo de sistemas se realicen de manera más eficiente y organizada.

En cuanto a la capacidad operativa, el personal involucrado (desarrolladores, analistas y administradores de bases de datos) cuenta con los conocimientos necesarios para utilizar el sistema, ya que su diseño estará orientado a la facilidad de uso y no requerirá capacitación especializadas.

Beneficios Operativos:

- Automatización de la documentación: El sistema extrae automáticamente la estructura de la base de datos a partir del archivo cargado, eliminando el proceso manual y reduciendo el tiempo invertido en esta actividad en aproximadamente un 60-70%.

- Reducción de errores humanos: Al automatizar la extracción de metadatos, se elimina la posibilidad de errores de transcripción o inconsistencias entre la documentación y la realidad del sistema.

- Accesibilidad universal: Al ser una aplicación web, el sistema puede ser utilizado desde cualquier dispositivo con un navegador moderno, sin necesidad de instalación local de software especializado.

- Análisis inteligente: La integración de recursos adecuados para el análisis de base de datos, nos permite obtener auditorías críticas automáticas que van más allá de la simple documentación, ofreciendo recomendaciones de mejora, detección de problemas de diseño y análisis de normalización.

- Interoperabilidad: El convertidor de esquemas facilita la migración entre tecnologías de bases de datos, un proceso que normalmente requería experiencia técnica avanzada y horas de trabajo manual.

Lista de interesados:

- Desarrolladores de software: responsables de implementar y mantener los sistemas.

- Administradores de bases de datos: encargados de la gestión y optimización de la información.

- Analistas de sistemas: responsables del análisis y diseño de soluciones.

- Jefe de proyecto: supervisa el desarrollo y uso del sistema.

- Organización/empresa usuaria: beneficiaria directa del sistema.

- Usuarios finales (beneficiarios indirectos): reciben sistemas más estables y eficientes.

**Factibilidad Legal**

El proyecto cumple con las normativas legales vigentes relacionadas con el uso de software y manejo de información:

- Derechos de autor y licencias de software: Todas las herramientas y librerías utilizadas están licenciadas bajo licencias de código abierto (MIT, Apache 2.0, BSD), lo que permite su uso, modificación y distribución sin infringir derechos de propiedad intelectual. El sistema propio se distribuye bajo Licencia MIT.

- Protección de datos personales: El sistema no almacena información personal sensible más allá de las credenciales de acceso, gestionadas de forma segura por Supabase mediante cifrado. Los esquemas de bases de datos cargados para análisis son procesados temporalmente en el servidor y eliminados tras el análisis, sin persistir información sensible.

- Ley N° 29733 – Ley de Protección de Datos Personales: El sistema cumple con los principios establecidos en esta ley: finalidad, proporcionalidad, calidad de datos, seguridad y flujo transfronterizo controlado.

- Seguridad informática: El sistema implementa autenticación basada en tokens JWT mediante Supabase, control de acceso por roles y manejo seguro de archivos temporales, alineándose con las buenas prácticas establecidas por la ISO/IEC 27001.

- Uso académico: El sistema es desarrollado con fines académicos en el contexto del curso de Base de Datos II de la Universidad Privada de Tacna, no generando conflicto con ninguna regulación comercial o sectorial.

Por lo tanto, no existen restricciones legales que impidan su desarrollo.

**Factibilidad Social**

El sistema contribuye de manera positiva al entorno social y profesional en el que se desenvuelven los equipos de desarrollo de software:

- Mejora de la cultura de documentación: La implementación del sistema promueve una forma de trabajo más organizada y responsable, donde la documentación deja de ser una tarea postergada para convertirse en un proceso automático integrado al flujo de desarrollo, elevando la calidad general de los proyectos de software.

- Reducción de la brecha tecnológica: Al ofrecer análisis inteligente y diagramas visuales, el sistema facilita que usuarios con menor experiencia técnica puedan interpretar y trabajar con bases de datos complejas.

- Apoyo a la toma de decisiones: La disponibilidad de documentación estructurada, diagramas ER y auditorías críticas generadas automáticamente permite a los líderes de proyecto y arquitectos de sistemas tomar decisiones más informadas sobre la evolución de sus sistemas de información.

- Fomento del trabajo colaborativo: La funcionalidad de compartición de documentación entre usuarios facilita el trabajo en equipo distribuido, permitiendo que múltiples desarrolladores trabajen sobre la misma base documental de forma sincronizada.

- Impacto en la formación académica: El proyecto sirve como modelo de referencia para otros estudiantes de Ingeniería de Sistemas, demostrando la aplicación práctica de tecnologías modernas en la resolución de problemas reales del ámbito profesional.

**Factibilidad Ambiental**

El impacto ambiental del proyecto es mínimo, siendo consistente con los principios de desarrollo sostenible:

- Reducción del consumo de papel: Al generar documentación digital, el sistema elimina la necesidad de imprimir manuales técnicos y reportes de estructura de bases de datos.

- Uso eficiente de recursos energéticos existentes: El sistema utiliza equipos de cómputo ya disponibles en el equipo de desarrollo, sin requerir la adquisición de hardware adicional que implique consumo de recursos naturales en su fabricación.

- Infraestructura en la nube con enfoque verde: El uso de plataformas que han adoptado compromisos de eficiencia energética y uso de energías renovables en sus centros de datos, reduce la huella de carbono del proyecto en comparación con el mantenimiento de servidores físicos locales.

- Sin generación de residuos contaminantes: Al ser un proyecto de software puro, no genera desechos industriales, contaminantes químicos ni residuos electrónicos adicionales.

- Ciclo de vida extendido del conocimiento: Al documentar y preservar el conocimiento sobre la estructura de las bases de datos, el sistema contribuye a extender el ciclo de vida de los sistemas de información existentes, reduciendo la necesidad de reescritura completa por falta de documentación, lo que implicaría mayor consumo de recursos tecnológicos.

En consecuencia, el proyecto es amigable con el medio ambiente.

### 4.   Evaluación Financiera

La inversión total del proyecto asciende a S/ 3,925.00, distribuida principalmente en costos de personal y costos operativos. Dado que se utilizan herramientas de código abierto y servicios con planes gratuitos, la inversión en infraestructura es mínima.

La inversión se justifica debido a que el sistema permitirá optimizar procesos, reducir errores y mejorar la gestión de bases de datos, generando beneficios tanto económicos como operativos.

**Anexo 01 – Requerimientos del Sistema *Sistema de Documentación de Base de Datos***
