<center>

![./media/logo-upt.png](./media/logo-upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERÍA**

**Escuela Profesional de Ingeniería de Sistemas**

**Proyecto: *Sistema de Documentación de Base de Datos***

Curso: *Base Datos II*

Docente: *Mag. Patrick Cuadros Quiroga*

Integrantes:

***Andia Navarro, Diego Fabrizio (2022073906)***

***Quispe Chileno, Clara Briyith Mayra (2024080129)***

**Tacna – Perú**

***2026***

**  
**
</center>

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

Sistema *de Documentación de Base de Datos*

Documento de Especificación de Requerimientos de Software

Versión *{1.0}*

| CONTROL DE VERSIONES | | | | | |
| :-: | :- | :- | :- | :- | :- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1\.0 | DAN, CQC | DAN, CQC | DAN, CQC | 04/06/2026 | Versión Original |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **ÍNDICE GENERAL**

[I. Introducción](#introducción)

[1. Generalidades de la Empresa](#generalidades-de-la-empresa)

[1.1. Nombre de la Empresa](#nombre-de-la-empresa)

[1.2. Visión](#visión)

[1.3. Misión](#misión)

[1.4. Organigrama](#organigrama)

[2. Visionamiento de la Empresa](#visionamiento-de-la-empresa)

[2.1. Descripción del Problema](#descripción-del-problema)

[2.2. Objetivos de Negocio](#objetivos-de-negocio)

[2.3. Objetivos de Diseño](#objetivos-de-diseño)

[2.4. Alcance del Proyecto](#alcance-del-proyecto)

[2.5. Viabilidad del Sistema](#viabilidad-del-sistema)

[2.6. Información obtenida del levantamiento de Información](#información-obtenida-del-levantamiento-de-información)

[3. Análisis de Procesos](#análisis-de-procesos)

[3.1. Diagrama del Proceso Actual](#diagrama-del-proceso-actual)

[3.2. Diagrama del Proceso Propuesto](#diagrama-del-proceso-propuesto)

[4. Especificación de Requerimientos de Software](#especificación-de-requerimientos-de-software)

[4.1. Cuadro de Requerimientos Funcionales Inicial](#cuadro-de-requerimientos-funcionales-inicial)

[4.2. Cuadro de Requerimientos No Funcionales](#cuadro-de-requerimientos-no-funcionales)

[4.3. Cuadro de Requerimientos Funcionales Final](#cuadro-de-requerimientos-funcionales-final)

[4.4. Reglas de Negocio](#reglas-de-negocio)

[5. Fase de Desarrollo](#fase-de-desarrollo)

[5.1. Perfiles de Usuario](#perfiles-de-usuario)

[5.2. Modelo Conceptual](#modelo-conceptual)

[5.3. Modelo Lógico](#modelo-lógico)

[II. Conclusiones](#conclusiones)

[III. Recomendaciones](#recomendaciones)

[IV. Bibliografía](#bibliografía)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **I. Introducción**

## 1. Generalidades de la Empresa

### 1.1. Nombre de la Empresa

DB Smart Solutions S.A.C.

### 1.2. Visión

Ser la empresa líder en soluciones tecnológicas orientadas a la automatización, análisis y documentación inteligente de bases de datos a nivel nacional e internacional, consolidándose como un referente en la aplicación de inteligencia artificial para la gestión del conocimiento técnico en sistemas de información.

### 1.3. Misión

Brindar herramientas innovadoras que faciliten la gestión, comprensión y mantenimiento de bases de datos mediante soluciones eficientes, seguras y accesibles, contribuyendo a la mejora continua de la calidad del software y la productividad de los equipos de desarrollo a través de la automatización inteligente.

### 1.4. Organigrama

La estructura organizacional de DB Smart Solutions S.A.C. está diseñada de forma jerárquica, lo que permite definir con claridad las funciones y responsabilidades de cada área dentro de la empresa. En la parte superior se encuentra la Gerencia General, que actúa como máxima autoridad y se encarga de la toma de decisiones estratégicas, la supervisión general de las operaciones y la coordinación entre las distintas áreas de trabajo.

De la Gerencia General dependen tres áreas principales. La primera es el Área de Desarrollo de Software, encargada de la construcción, mantenimiento y mejora de las soluciones tecnológicas que ofrece la empresa. Dentro de esta área se encuentran el Desarrollador Backend/Python, responsable de la lógica de negocio, el procesamiento de datos y la integración de servicios, y el Desarrollador Frontend (UX/UI), quien se enfoca en la interfaz visual, la experiencia de usuario y la interacción entre el sistema y los usuarios finales.

La segunda área es el Área Soporte, que tiene como objetivo garantizar el correcto funcionamiento técnico de los sistemas, servidores, bases de datos y entornos de despliegue. En esta área se ubica el Administrador de Base de Datos (DBA), quien se encarga de la administración, seguridad, disponibilidad y organización de la información almacenada.

La tercera área es el Área Comercial, que se ocupa de la gestión económica, administrativa y de apoyo general a la empresa. Esta área permite mantener el control de los recursos, los gastos y la planificación interna, asegurando que las operaciones de la organización se desarrollen de manera ordenada y sostenible.

En conjunto, esta estructura permite una distribución clara de tareas, mejora la coordinación entre equipos y facilita el desarrollo eficiente de los proyectos de la empresa.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 2. Visionamiento de la Empresa

### 2.1. Descripción del Problema

Muchas bases de datos no cuentan con documentación actualizada, completa ni estructurada. Esta situación genera una cadena de consecuencias negativas que afectan directamente la calidad, eficiencia y continuidad de los sistemas de información en las organizaciones.

**Dependencia del conocimiento individual:** La ausencia de documentación formalizada genera una dependencia crítica del conocimiento tácito de ciertos desarrolladores o administradores. Cuando estas personas no están disponibles, el equipo pierde acceso a información esencial para el mantenimiento y evolución del sistema, incrementando el riesgo operativo.

**Incremento de errores en modificaciones:** La falta de documentación estructurada que describa tablas, relaciones, restricciones y reglas de negocio implementadas a nivel de base de datos provoca que los desarrolladores realicen cambios sin una comprensión completa del sistema, aumentando la probabilidad de introducir errores, inconsistencias o rupturas en la integridad referencial.

**Retrasos en el mantenimiento:** Los procesos de análisis, desarrollo y actualización se vuelven más lentos cuando no existe una referencia documental clara. Los desarrolladores deben invertir horas explorando el esquema directamente en el gestor de base de datos antes de poder realizar cualquier modificación, lo que reduce la productividad del equipo.

**Dificultades de integración y trazabilidad:** La ausencia de documentación estructurada complica la integración de la base de datos con otros sistemas y limita la trazabilidad de los cambios realizados, dificultando las auditorías técnicas y el control de versiones del esquema.

**Impacto en la incorporación de nuevos desarrolladores:** Los nuevos miembros del equipo deben invertir tiempo considerable en comprender el funcionamiento del sistema sin contar con una referencia clara, lo que prolonga su curva de aprendizaje y retrasa su contribución efectiva al proyecto.

En este contexto, se hace necesario contar con una solución que automatice la generación y mantenimiento de la documentación de bases de datos, facilitando su comprensión, reduciendo errores y mejorando los procesos de mantenimiento y evolución del sistema.

### 2.2. Objetivos de Negocio

- **Reducir tiempos de análisis de bases de datos.** Permitir a los equipos técnicos comprender de manera más rápida la estructura y funcionamiento de las bases de datos, optimizando los procesos de desarrollo, mantenimiento y toma de decisiones. Se estima una reducción del 60-70% en el tiempo de documentación manual.

- **Mejorar la mantenibilidad de sistemas.** Facilitar la actualización, modificación y evolución de los sistemas mediante documentación clara, automatizada y siempre disponible, reduciendo la dependencia del conocimiento individual y minimizando errores derivados de la falta de información estructural.

- **Ofrecer una solución web escalable y accesible.** Diseñar la solución como una aplicación web que se adapte al crecimiento de usuarios y volumen de datos, permitiendo su implementación en diferentes entornos organizacionales sin requerir instalación de software adicional en los dispositivos de los usuarios.

- **Generar valor mediante automatización documental.** Mejorar la eficiencia operativa de los equipos de desarrollo a través de la automatización de la documentación, reduciendo costos asociados a errores, retrabajos y tiempos prolongados de análisis, y aportando mayor valor a los procesos tecnológicos de la organización.

- **Incorporar inteligencia artificial como diferenciador competitivo.** Integrar capacidades de análisis crítico mediante IA que permitan no solo documentar, sino también auditar el diseño de la base de datos, detectar problemas de normalización y proporcionar recomendaciones de mejora automatizadas.

### 2.3. Objetivos de Diseño

- **Diseñar una interfaz amigable e intuitiva.** Desarrollar una interfaz web moderna que permita a los usuarios interactuar con el sistema sin necesidad de conocimientos técnicos avanzados, con navegación clara entre módulos y retroalimentación visual en tiempo real.

- **Automatizar la extracción de metadatos.** Implementar un motor de análisis en Python capaz de obtener automáticamente información completa de la base de datos: tablas, atributos, tipos de datos, claves primarias y foráneas, índices y métricas de normalización.

- **Visualizar relaciones entre tablas mediante diagramas ER interactivos.** Implementar representaciones gráficas Entidad-Relación renderizadas con Mermaid.js, con controles de zoom y exportación en formato SVG, que permitan entender de manera clara la estructura y conexiones dentro de la base de datos.

- **Exportar reportes en múltiples formatos.** Permitir la generación de documentación exportable en formatos PDF, facilitando su almacenamiento, distribución y uso en distintos contextos tanto técnicos como administrativos.

- **Implementar conversión de esquemas multi-tecnología.** Desarrollar un convertidor profesional que transforme el esquema analizado a nueve tecnologías diferentes: MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, JSON Schema, CSV y YAML.

- **Garantizar seguridad mediante autenticación y control de acceso.** Implementar un sistema de autenticación basado en JWT mediante Supabase, con diferenciación de roles, garantizando que solo usuarios autorizados accedan al sistema y a la información procesada.

### 2.4. Alcance del Proyecto

El sistema de documentador de base de datos abarca las siguientes funcionalidades:

- Carga de archivos de esquemas en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml.
- Análisis técnico automático mediante motor Python.
- Auditoría crítica del diseño mediante IA con análisis descriptivo.
- Detección de problemas y recomendaciones.
- Generación y visualización de diagramas Entidad-Relación interactivos con controles de zoom y exportación SVG.
- Conversión de esquemas a nueve formatos tecnológicos.
- Exportación de documentación en PDF.
- Generación de datos de prueba sintéticos.
- Sistema de gestión de usuarios con autenticación, roles, almacenamiento y compartición de documentación.
- Panel de administración de usuarios.

### 2.5. Viabilidad del Sistema

El proyecto es viable técnicamente, económicamente y operativamente, debido al uso de tecnologías open source y recursos disponibles.

Desde el punto de vista técnico, el sistema es implementable con tecnologías maduras y bien documentadas: Node.js para el servidor backend, Python para el motor de análisis, las librerías sqlglot y pandas para el procesamiento de esquemas, y Mermaid.js para la visualización. Todas las herramientas son de código abierto con planes gratuitos suficientes para el alcance del proyecto.

En el aspecto económico, la inversión total del proyecto asciende a S/ 3,925.00, con una relación Beneficio/Costo de 1.58, un Valor Actual Neto de S/ +1,584.09 y una Tasa Interna de Retorno del 54.5%, superando ampliamente el costo de oportunidad del 10%. La mayor parte de la inversión corresponde a la valoración del esfuerzo académico del equipo de desarrollo.

En cuanto a la viabilidad operativa, el sistema opera como aplicación web sin requerimientos de instalación. La interfaz está diseñada para que un usuario nuevo pueda completar el flujo principal en menos de 5 minutos, sin necesidad de capacitación especializada.

### 2.6. Información obtenida del levantamiento de Información

Durante el proceso de levantamiento de información se realizó un análisis de necesidades en entornos de desarrollo de software, identificando las siguientes problemáticas y requerimientos principales:

- Documentación automatizada de bases de datos: frecuencia muy alta, impacto alto.
- Compatibilidad con múltiples SGBD: frecuencia alta, impacto alto.
- Acceso web desde navegadores sin instalación local: frecuencia alta, impacto medio.
- Exportación de documentación en formatos estándar: frecuencia alta, impacto medio.
- Visualización gráfica de relaciones entre tablas: frecuencia alta, impacto alto.
- Análisis crítico del diseño con recomendaciones de mejora: frecuencia media, impacto alto.
- Conversión de esquemas entre tecnologías de bases de datos: frecuencia media, impacto medio.
- Gestión de usuarios con control de acceso y roles: frecuencia alta, impacto alto.
- Almacenamiento y compartición de documentación generada: frecuencia media, impacto medio.
- Generación de datos de prueba basados en el esquema real: frecuencia baja, impacto bajo.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 3. Análisis de Procesos

### 3.1. Diagrama del Proceso Actual

### 3.2. Diagrama del Proceso Propuesto

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 4. Especificación de Requerimientos de Software

### 4.1. Cuadro de Requerimientos Funcionales Inicial

| **Código** | **Nombre** | **Descripción** | **Prioridad** |
| :- | :- | :- | :- |
| RF01 | Autenticar Usuario | Permitir el inicio de sesión de usuarios registrados mediante credenciales seguras como email y contraseña, gestionadas por Supabase con tokens JWT. | Alta |
| RF02 | Cargar Archivo de Esquema | Permitir la carga de archivos de esquemas de bases de datos en formatos .sql, .json, .xlsx, .yaml, .csv y .dbml mediante arrastrar y soltar o selección manual. | Alta |
| RF03 | Analizar Estructura de BD | Procesar el archivo cargado y extraer automáticamente tablas, campos, tipos de datos, claves primarias y foráneas, relaciones e índices mediante el motor Python. | Alta |
| RF04 | Generar Documentación Técnica | Crear documentación estructurada de la base de datos, incluyendo diccionario de datos, descripción de tablas y relaciones, a partir del análisis realizado. | Alta |
| RF05 | Detectar Relaciones Implícitas | Identificar relaciones entre tablas no declaradas explícitamente mediante Fuzzy Matching de nombres de columnas, como user_id que referencia implícitamente a la tabla users. | Alta |

### 4.2. Cuadro de Requerimientos No Funcionales

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

### 4.3. Cuadro de Requerimientos Funcionales Final

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

### 4.4. Reglas de Negocio

| **Código** | **Regla de negocio** | **Descripción** |
| :- | :- | :- |
| RN-01 | Solo lectura sobre las bases de datos analizadas | El sistema tendrá permisos exclusivamente de lectura sobre los archivos de esquema y bases de datos procesadas. No se ejecutarán operaciones de inserción, actualización, eliminación ni modificación de estructura. |
| RN-02 | Acceso restringido a usuarios autenticados | Todas las funcionalidades estarán restringidas a usuarios previamente autenticados mediante credenciales válidas. El acceso a rutas protegidas sin token válido será rechazado con el código HTTP 401. |
| RN-03 | Toda documentación debe generarse desde una fuente válida | La documentación, diagramas y reportes solo podrán generarse cuando se haya completado con éxito el análisis de un archivo válido. El sistema verificará formato, tamaño y estructura antes de procesarlo. |
| RN-04 | No se modificará la información de la base de datos origen | El sistema no altera la estructura ni los datos almacenados en la base de datos original. Su función se limita al análisis, auditoría y documentación del esquema. |
| RN-05 | Los archivos temporales deben eliminarse tras el procesamiento | Los archivos cargados serán eliminados del servidor al finalizar el procesamiento. Solo los resultados del análisis serán devueltos al cliente y, si el usuario lo autoriza, almacenados en Supabase. |
| RN-06 | Control de acceso basado en roles | El sistema diferenciará dos niveles de acceso, usuario estándar y administrador, cada uno con permisos específicos según sus funciones. |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

## 5. Fase de Desarrollo

### 5.1. Perfiles de Usuario

**Administrador**

- **Función:** Gestionar el acceso al sistema, controlar cuentas de usuario, supervisar el funcionamiento de la plataforma, configurar parámetros generales del sistema y garantizar la seguridad de la información procesada.
- **Necesidades:** Acceso completo al sistema, incluyendo panel de administración de usuarios, visualización de estadísticas de uso, monitoreo de procesos de análisis, y control sobre la documentación compartida entre usuarios.
- **Privilegios:** Acceso total a todas las funcionalidades del sistema, incluyendo las exclusivas del panel de administración.
- **Conocimientos requeridos:** Gestión de sistemas de información, administración de bases de datos, seguridad informática básica.

**Desarrollador**

- **Función:** Utilizar la herramienta para analizar bases de datos, generar documentación automática, visualizar estructuras y relaciones, y comprender el modelo de datos de los sistemas que desarrolla o mantiene.
- **Necesidades:** Acceso a las funcionalidades de carga de archivos de esquema, análisis técnico, auditoría, visualización de diagramas ER interactivos, conversión de esquemas entre tecnologías, y exportación de documentación.
- **Privilegios:** Acceso a todas las funcionalidades estándar del sistema.
- **Conocimientos requeridos:** Conocimientos básicos-intermedios de bases de datos relacionales y/o NoSQL, desarrollo de software.

**Analista**

- **Función:** Interpretar la documentación e información estructural generada por el sistema para apoyar procesos de análisis funcional, modelado de sistemas, toma de decisiones arquitectónicas y elaboración de reportes técnicos.
- **Necesidades:** Acceso a reportes claros y bien estructurados, documentación organizada del esquema, visualización comprensible de los diagramas ER, y facilidad para exportar y compartir la documentación generada con otros miembros del equipo.
- **Privilegios:** Acceso a funcionalidades de análisis, visualización, exportación y compartición de documentación.
- **Conocimientos requeridos:** Conocimientos intermedios de modelado de datos, análisis y diseño de sistemas de información.

### 5.2. Modelo Conceptual

#### Diagrama de Paquetes

#### Diagrama de Casos de Uso

#### Escenarios de Caso de Uso (Narrativa)

**Caso de uso: Iniciar Sesión**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-01 |
| Nombre | Iniciar Sesión |
| Tipo | Obligatorio |
| Requisito ID | RF-01 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Usuario, Administrador, Desarrollador, Analista |
| Interacción | Fase de Autenticación |
| Descripción | Permite al usuario autenticarse en el sistema mediante sus credenciales para acceder a las funcionalidades disponibles según su rol. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El usuario debe estar previamente registrado en el sistema con credenciales válidas. |
| PostCondiciones | El usuario accede al panel principal del sistema con los permisos correspondientes a su rol. |
| Flujo Normal | 1. El usuario accede a la página de inicio de sesión. 2. Ingresa sus credenciales. 3. El sistema valida la información. 4. El sistema permite el ingreso al panel principal. |
| Flujo de Excepción E001 | Credenciales incorrectas. El sistema muestra un mensaje de autenticación inválida y permite reintentar. |
| Flujo de Excepción E002 | Usuario inactivo. La cuenta ha sido desactivada y el sistema muestra un mensaje indicando que debe contactar al administrador. |
| Flujo de Excepción E003 | Error de conexión. El sistema no puede validar el acceso y muestra un mensaje de error temporal. |

**Caso de Uso: Registrar Usuario**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-02 |
| Nombre | Registrar Usuario |
| Tipo | Obligatorio |
| Requisito ID | RF-02 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Administrador |
| Interacción | Fase de Administración de Usuarios |
| Descripción | Permite crear nuevas cuentas de usuario en el sistema con datos válidos y asignación de rol. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El administrador debe haber iniciado sesión en el sistema. |
| PostCondiciones | El nuevo usuario queda registrado y disponible para acceder al sistema según su rol. |
| Flujo Normal | 1. El administrador accede al módulo de usuarios. 2. Ingresa los datos del nuevo usuario. 3. El sistema valida la información. 4. El sistema registra la cuenta. 5. El usuario queda habilitado. |
| Flujo de Excepción E001 | Datos inválidos. El sistema muestra un mensaje indicando que revise la información ingresada. |
| Flujo de Excepción E002 | Usuario ya registrado. El sistema informa que la cuenta ya existe. |

**Caso de Uso: Cargar Archivo de Esquema**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-03 |
| Nombre | Cargar Archivo de Esquema |
| Tipo | Obligatorio |
| Requisito ID | RF-03 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Carga y Procesamiento |
| Descripción | Permite cargar archivos de esquemas de bases de datos en distintos formatos para su posterior análisis. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El usuario debe estar autenticado y contar con un archivo de esquema válido. |
| PostCondiciones | El archivo queda cargado y listo para ser procesado por el sistema. |
| Flujo Normal | 1. El usuario selecciona o arrastra el archivo. 2. El sistema valida el formato y tamaño. 3. El archivo se envía al servidor. 4. El sistema confirma la carga exitosa. |
| Flujo de Excepción E001 | Formato no soportado. El sistema informa que el archivo no es compatible. |
| Flujo de Excepción E002 | Archivo demasiado grande. El sistema informa que supera el tamaño permitido. |

**Caso de Uso: Analizar Base de Datos**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-04 |
| Nombre | Analizar Base de Datos |
| Tipo | Obligatorio |
| Requisito ID | RF-04 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Procesamiento |
| Descripción | Permite procesar el archivo cargado para extraer tablas, campos, tipos de datos, claves y relaciones. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El usuario debe estar autenticado y haber cargado previamente un archivo válido. |
| PostCondiciones | La estructura de la base de datos queda analizada y disponible para visualización. |
| Flujo Normal | 1. El usuario solicita el análisis. 2. El sistema procesa la estructura. 3. Se identifican tablas y relaciones. 4. El sistema muestra los resultados. |
| Flujo de Excepción E001 | Error de análisis. El sistema no puede procesar los datos y muestra un mensaje de error. |

**Caso de Uso: Detectar Relaciones Implícitas**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-05 |
| Nombre | Detectar Relaciones Implícitas |
| Tipo | Obligatorio |
| Requisito ID | RF-05 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Análisis |
| Descripción | Permite identificar relaciones entre tablas que no están declaradas de forma explícita en el esquema. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El análisis de la base de datos debe haberse completado correctamente. |
| PostCondiciones | Las relaciones implícitas detectadas quedan incluidas en la documentación generada. |
| Flujo Normal | 1. El sistema revisa los nombres de columnas y tablas. 2. Compara patrones de coincidencia. 3. Detecta relaciones probables. 4. Muestra las relaciones encontradas. |
| Flujo de Excepción E001 | No se detectan coincidencias suficientes. El sistema informa que no fue posible identificar relaciones implícitas. |

**Caso de Uso: Generar Documentación Técnica**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-06 |
| Nombre | Generar Documentación Técnica |
| Tipo | Obligatorio |
| Requisito ID | RF-06 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Generación de Documentación |
| Descripción | Permite generar documentación estructurada de la base de datos analizada, incluyendo diccionario de datos, descripción de tablas y relaciones. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El análisis de la base de datos debe estar completado. |
| PostCondiciones | La documentación técnica queda generada y disponible para revisión o exportación. |
| Flujo Normal | 1. El usuario solicita la generación de documentación. 2. El sistema organiza la información analizada. 3. Se crea la documentación estructurada. 4. El sistema muestra el resultado. |
| Flujo de Excepción E001 | Error de generación. El sistema muestra un mensaje indicando que no fue posible crear la documentación. |

**Caso de Uso: Generar Diagrama ER**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-07 |
| Nombre | Generar Diagrama Entidad-Relación |
| Tipo | Obligatorio |
| Requisito ID | RF-07 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Visualización |
| Descripción | Permite visualizar el diagrama Entidad–Relación de la base de datos analizada, con opciones de zoom, navegación y exportación. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El análisis de la base de datos debe haber sido completado con éxito. |
| PostCondiciones | El diagrama queda visible en pantalla y disponible para descarga. |
| Flujo Normal | 1. El usuario selecciona la vista del diagrama. 2. El sistema genera la representación gráfica. 3. El diagrama se muestra en pantalla. 4. El usuario navega o descarga el archivo. |
| Flujo de Excepción E001 | Sin análisis previo. El sistema informa que primero debe cargarse y analizarse un esquema. |

**Caso de Uso: Exportar Reporte en PDF**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-08 |
| Nombre | Exportar Reporte en PDF |
| Tipo | Obligatorio |
| Requisito ID | RF-08 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista, Administrador |
| Interacción | Fase de Exportación |
| Descripción | Permite generar y descargar la documentación de la base de datos en formato PDF. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | La documentación técnica debe estar generada previamente. |
| PostCondiciones | El archivo PDF queda disponible para descarga. |
| Flujo Normal | 1. El usuario selecciona exportar en PDF. 2. El sistema recopila la documentación. 3. Se genera el archivo. 4. El archivo se descarga automáticamente. |
| Flujo de Excepción E001 | Error en generación. El sistema informa que no pudo crear el archivo PDF. |

**Caso de Uso: Convertir Esquema**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-10 |
| Nombre | Convertir Esquema |
| Tipo | Opcional |
| Requisito ID | RF-10 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Conversión |
| Descripción | Permite transformar el esquema analizado a diferentes formatos y tecnologías de base de datos. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El esquema debe haber sido analizado previamente. |
| PostCondiciones | El esquema convertido queda disponible para revisión o descarga. |
| Flujo Normal | 1. El usuario selecciona el formato de destino. 2. El sistema procesa la estructura. 3. Se genera la conversión. 4. Se muestra el resultado. |
| Flujo de Excepción E001 | Formato no soportado. El sistema informa que el destino seleccionado no está disponible. |

**Caso de Uso: Guardar Documentación**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-11 |
| Nombre | Guardar Documentación |
| Tipo | Opcional |
| Requisito ID | RF-11 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Usuario |
| Interacción | Fase de Almacenamiento |
| Descripción | Permite almacenar la documentación generada para su consulta posterior. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El usuario debe estar autenticado y contar con documentación generada. |
| PostCondiciones | La documentación queda almacenada y disponible en el historial del usuario. |
| Flujo Normal | 1. El usuario selecciona guardar. 2. El sistema registra la documentación. 3. Se confirma el almacenamiento. |
| Flujo de Excepción E001 | Error al guardar. El sistema informa que no fue posible almacenar la documentación. |

**Caso de Uso: Compartir Documentación**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-12 |
| Nombre | Compartir Documentación |
| Tipo | Opcional |
| Requisito ID | RF-12 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Usuario |
| Interacción | Fase de Colaboración |
| Descripción | Permite compartir una documentación guardada con otros usuarios registrados en la plataforma. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El usuario debe estar autenticado y disponer de documentación guardada. |
| PostCondiciones | La documentación compartida queda accesible para los usuarios autorizados. |
| Flujo Normal | 1. El usuario selecciona una documentación. 2. Indica con quién desea compartirla. 3. El sistema registra el acceso compartido. 4. El destinatario puede visualizarla. |
| Flujo de Excepción E001 | Usuario no autorizado. El sistema informa que no tiene permisos para compartir la documentación. |

**Caso de Uso: Gestionar Usuarios**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-13 |
| Nombre | Gestionar Usuarios |
| Tipo | Opcional |
| Requisito ID | RF-13 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Administrador |
| Interacción | Fase de Administración |
| Descripción | Permite administrar las cuentas de usuario del sistema y visualizar información general de uso. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | El administrador debe haber iniciado sesión en el sistema. |
| PostCondiciones | Las cuentas de usuario quedan actualizadas según la acción ejecutada. |
| Flujo Normal | 1. El administrador accede al panel de usuarios. 2. Selecciona una cuenta. 3. Realiza la acción requerida. 4. El sistema guarda los cambios. |
| Flujo de Excepción E001 | Error de permisos. El sistema informa que no tiene autorización para ejecutar la acción. |

**Caso de Uso: Generar Datos de Prueba**

| **Campo** | **Descripción** |
| :- | :- |
| Id Caso de Uso | RF-14 |
| Nombre | Generar Datos de Prueba |
| Tipo | Opcional |
| Requisito ID | RF-14 |
| Versión | 1.0 |
| Autor | Equipo de Desarrollo — DB Smart Solutions S.A.C. |
| Actores | Desarrollador, Analista |
| Interacción | Fase de Generación de Datos |
| Descripción | Permite crear datasets sintéticos y realistas basados en la estructura de la base de datos analizada. |
| Referencias | Ninguna |
| Anexos | Ninguno |
| Precondiciones | La base de datos debe haber sido analizada previamente. |
| PostCondiciones | Los datos de prueba quedan generados y disponibles para uso interno. |
| Flujo Normal | 1. El usuario solicita la generación. 2. El sistema toma la estructura analizada. 3. Se crean los datos sintéticos. 4. El sistema muestra o exporta el resultado. |
| Flujo de Excepción E001 | Error de generación. El sistema informa que no fue posible crear los datos de prueba. |

### 5.3. Modelo Lógico

#### Análisis de Objetos

- **Usuario:** representa a la persona que interactúa con el sistema. Puede desempeñar distintos roles, como administrador, desarrollador o analista, y es quien accede a las funciones disponibles según sus permisos.

- **Sesión:** gestiona el acceso del usuario dentro del sistema, manteniendo la autenticación activa durante su uso y controlando el tiempo de validez del ingreso.

- **Archivo de esquema:** corresponde al archivo cargado por el usuario para su análisis. Se mantiene de forma temporal mientras se procesa la información y luego se elimina del servidor.

- **Analizador de base de datos:** es el componente encargado de procesar el archivo de esquema y extraer la información estructural necesaria para la documentación.

- **Módulo de auditoría:** se encarga de generar observaciones y recomendaciones sobre la estructura analizada, aportando un análisis complementario del esquema.

- **Documentación:** reúne de forma consolidada los resultados obtenidos del análisis, incluyendo tablas, campos, relaciones, métricas y observaciones. Esta información puede guardarse y compartirse dentro del sistema.

- **Diagrama Entidad–Relación:** representa visualmente las entidades y relaciones detectadas durante el análisis, permitiendo una mejor comprensión de la estructura de la base de datos.

- **Conversión de esquema:** corresponde al resultado de transformar el esquema analizado a otro formato tecnológico, según la necesidad del usuario.

- **Reporte:** es el documento final que se genera con toda la documentación del análisis y se exporta en formato PDF para su descarga o archivo.

- **Proyecto:** agrupa el conjunto de documentaciones generadas por un usuario, permitiendo organizarlas y consultarlas posteriormente de manera ordenada.

#### Diagrama de Actividades con Objetos

#### Diagrama de Secuencia

#### Diagrama de Clases

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **II. Conclusiones**

La automatización del proceso de documentación de bases de datos resulta técnicamente viable y aporta un valor inmediato al usuario. El sistema desarrollado demuestra que es posible reemplazar un proceso manual que puede tomar varias horas por un flujo automatizado de pocos minutos, manteniendo un nivel alto de calidad en la documentación obtenida gracias al motor de análisis local y a los módulos complementarios de evaluación y generación de contenido.

La arquitectura híbrida basada en análisis técnico local y apoyo inteligente constituye una propuesta diferenciadora frente a otras herramientas. Por un lado, el motor local garantiza precisión en la extracción de metadatos, incluyendo la detección de relaciones implícitas mediante coincidencia de nombres, lo cual es un aspecto importante que no siempre está presente en soluciones similares. Por otro lado, el módulo de evaluación complementa el análisis con observaciones de nivel más alto sobre el diseño del esquema.

La especificación de requerimientos cubre de manera adecuada el ciclo completo de documentación. Los requerimientos funcionales y no funcionales definidos permiten estructurar un sistema integral que incluye autenticación, carga de archivos, análisis, visualización de diagramas ER, exportación de documentación, conversión de esquemas y gestión colaborativa de la información generada.

Las reglas de negocio establecidas ayudan a garantizar la seguridad e integridad del sistema. El principio de solo lectura, la autenticación obligatoria, la eliminación de archivos temporales y el control de acceso por roles conforman un marco de seguridad sólido que protege tanto la información procesada como la privacidad de los usuarios.

El modelo lógico refleja de forma coherente la arquitectura real del sistema. Las clases identificadas y sus relaciones corresponden directamente a los módulos implementados, lo que demuestra consistencia entre el diseño conceptual y la solución desarrollada.

Finalmente, el sistema posiciona a DB Smart Solutions S.A.C. como una propuesta innovadora dentro del ámbito de las herramientas de documentación de bases de datos. Al integrar tecnologías modernas en una solución web accesible, el proyecto demuestra el potencial de estas herramientas para resolver problemas reales del desarrollo de software y establece una base sólida para futuras mejoras y expansiones.

# **III. Recomendaciones**

- Ampliar la compatibilidad con más sistemas gestores de bases de datos, incorporando soporte para plataformas como Oracle Database, Microsoft SQL Server, MariaDB y Cassandra, con el fin de aumentar el alcance del sistema en entornos empresariales.

- Implementar una conexión directa opcional a servidores de bases de datos, manteniendo el modo de solo lectura y los estándares de seguridad establecidos, para facilitar el análisis sin depender exclusivamente de archivos exportados.

- Robustecer los mecanismos de seguridad para entornos de producción, incorporando cifrado de datos, registro de actividad por usuario, limitación de intentos de acceso y políticas de expiración de sesiones más estrictas.

- Optimizar el rendimiento para esquemas de gran escala mediante procesamiento por bloques, ejecución asíncrona y caché de resultados, evitando reprocesamientos innecesarios y mejorando los tiempos de respuesta.

- Desarrollar un sistema de versionado de documentación que permita comparar cambios en el esquema a lo largo del tiempo y conservar un historial de la evolución de la base de datos.

- Incorporar pruebas automatizadas unitarias e integrales para asegurar la estabilidad del sistema y facilitar la detección temprana de errores en futuras ampliaciones.

- Evaluar la integración con herramientas de automatización y despliegue continuo para que la documentación pueda actualizarse de forma más eficiente ante cambios en los esquemas del proyecto.

- Publicar el sistema como un proyecto de código abierto para facilitar su adopción, permitir su mejora por parte de la comunidad y acompañarlo con documentación completa de instalación, configuración y uso.

# **IV. Bibliografía**

- Brown, T. B., Mann, B., Ryder, N., Subbiah, M., Kaplan, J., Dhariwal, P., et al. (2020). Language models are few-shot learners. *Advances in Neural Information Processing Systems*, 33, 1877–1901. <https://arxiv.org/abs/2005.14165>

- Date, C. J. (2004). *Introducción a los sistemas de bases de datos* (8.ª ed.). Pearson Education.

- Elmasri, R., & Navathe, S. B. (2016). *Sistemas de bases de datos* (7.ª ed.). Pearson Education.

- IEEE Computer Society. (1998). *IEEE Std 830-1998: Recommended Practice for Software Requirements Specifications*. Institute of Electrical and Electronics Engineers.

- International Organization for Standardization. (2011). *ISO/IEC 25010:2011 — Systems and software quality models*. ISO/IEC.

- Ministerio de Justicia del Perú. (2011). *Ley N° 29733 — Ley de Protección de Datos Personales*. Diario Oficial El Peruano. <https://www.minjus.gob.pe/>

- MySQL Documentation. (2024). MySQL 8.0 Reference Manual. <https://dev.mysql.com/doc/>

- NetworkX Developers. (2024). NetworkX documentation. <https://networkx.org/documentation/stable/>

- Node.js Foundation. (2024). Node.js documentation. <https://nodejs.org/en/docs/>

- PostgreSQL Global Development Group. (2024). PostgreSQL 16 documentation. <https://www.postgresql.org/docs/>
