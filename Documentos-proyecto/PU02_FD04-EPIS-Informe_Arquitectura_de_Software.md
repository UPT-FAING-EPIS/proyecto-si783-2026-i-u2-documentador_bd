<div align="center">

![Logo UPT](./media/logo-upt.png)

<br>

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERÍA**

**Escuela Profesional de Ingeniería de Sistemas**

**Proyecto *Sistema de Documentación de Base de Datos***

Curso: *Base de Datos II*

Docente: *Mag. Patrick Cuadros Quiroga*

Integrantes:

***Andia Navarro, Diego Fabrizio (2022073906)***

***Quispe Chileno, Clara Briyith Mayra (2024080129)***

**Tacna – Perú**

***2026***

</div>

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

Sistema *de documentación de base de datos*

Documento de Arquitectura de Software

Versión *{1.0}*

| CONTROL DE VERSIONES | | | | | |
| :-: | :- | :- | :- | :- | :- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1.0 | DAN, CQC | DAN, CQC | DAN CQC | 04/06/2026 | Versión Original |

| CONTROL DE VERSIONES | | | | | |
| :-: | :- | :- | :- | :- | :- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1.0 | MPV | ELV | ARV | 10/10/2020 | Versión Original |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# ÍNDICE GENERAL

[1. INTRODUCCIÓN](#introducción)

[1.1. Propósito (Diagrama 4+1)](#propósito-diagrama-41)

[1.2. Alcance](#alcance)

[1.3. Definición, siglas y abreviaturas](#definición-siglas-y-abreviaturas)

[1.4. Organización del documento](#organización-del-documento)

[2. OBJETIVOS Y RESTRICCIONES ARQUITECTÓNICAS](#objetivos-y-restricciones-arquitectónicas)

[2.1. Requerimientos Funcionales](#requerimientos-funcionales)

[2.2. Requerimientos No Funcionales – Atributos de Calidad](#requerimientos-no-funcionales--atributos-de-calidad)

[3. REPRESENTACIÓN DE LA ARQUITECTURA DEL SISTEMA](#representación-de-la-arquitectura-del-sistema)

[3.1. Vista de Caso de uso](#vista-de-caso-de-uso)

[3.1.1. Diagramas de Casos de uso](#diagramas-de-casos-de-uso)

[3.2. Vista Lógica](#vista-lógica)

[3.2.1. Diagrama de Subsistemas (paquetes)](#diagrama-de-subsistemas-paquetes)

[3.2.2. Diagrama de Secuencia (vista de diseño)](#diagrama-de-secuencia-vista-de-diseño)

[3.2.3. Diagrama de Colaboración (vista de diseño)](#diagrama-de-colaboración-vista-de-diseño)

[3.2.4. Diagrama de Objetos](#diagrama-de-objetos)

[3.2.5. Diagrama de Clases](#diagrama-de-clases)

[3.2.6. Diagrama de Base de datos (relacional o no relacional)](#diagrama-de-base-de-datos-relacional-o-no-relacional)

[3.3. Vista de Implementación (vista de desarrollo)](#vista-de-implementación-vista-de-desarrollo)

[3.3.1. Diagrama de arquitectura software (paquetes)](#diagrama-de-arquitectura-software-paquetes)

[3.3.2. Diagrama de arquitectura del sistema (Diagrama de componentes)](#diagrama-de-arquitectura-del-sistema-diagrama-de-componentes)

[3.4. Vista de procesos](#vista-de-procesos)

[3.4.1. Diagrama de Procesos del sistema (diagrama de actividad)](#diagrama-de-procesos-del-sistema-diagrama-de-actividad)

[3.5. Vista de Despliegue (vista física)](#vista-de-despliegue-vista-física)

[3.5.1. Diagrama de despliegue](#diagrama-de-despliegue)

[4. ATRIBUTOS DE CALIDAD DEL SOFTWARE](#atributos-de-calidad-del-software)

[4.1. Escenario de Funcionalidad](#escenario-de-funcionalidad)

[4.2. Escenario de Usabilidad](#escenario-de-usabilidad)

[4.3. Escenario de confiabilidad](#escenario-de-confiabilidad)

[4.4. Escenario de rendimiento](#escenario-de-rendimiento)

[4.5. Escenario de mantenibilidad](#escenario-de-mantenibilidad)

[4.6. Otros Escenarios](#otros-escenarios)

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **1.** INTRODUCCIÓN

## **1.1.** Propósito (Diagrama 4+1)

El presente documento constituye el Documento de Arquitectura de Software del Sistema de Documentación de Base de Datos, desarrollado por DB Smart Solutions S.A.C. Su propósito es describir de manera formal, precisa y completa la arquitectura del sistema desde múltiples perspectivas complementarias, facilitando la comprensión, mantenimiento y evolución del mismo.

Este documento adopta el modelo de vistas arquitectónicas propuesto por Philippe Kruchten, que organiza la descripción de la arquitectura en cinco vistas. La Vista de Casos de Uso describe los escenarios de uso que guían y validan las decisiones arquitectónicas, siendo su audiencia principal todos los interesados. La Vista Lógica describe la descomposición del sistema en subsistemas, clases y sus relaciones, orientada a diseñadores y desarrolladores. La Vista de Implementación describe la organización del software en módulos, paquetes y componentes, dirigida al equipo de desarrollo. La Vista de Procesos describe el comportamiento dinámico del sistema en tiempo de ejecución, orientada a arquitectos e integradores. La Vista de Despliegue describe la topología física donde se despliega el sistema, dirigida a administradores e infraestructura.

## **1.2.** Alcance

Este documento describe la arquitectura del Sistema de Documentación de Base de Datos en su versión 1.0, un sistema web que integra los siguientes componentes: un servidor backend en Node.js con Express como orquestador central; un motor de análisis local en Python con las librerías sqlglot, pandas, networkx y Faker; un servicio de análisis en la nube para la generación de documentación descriptiva; un sistema de gestión de usuarios, autenticación y almacenamiento de documentación en la nube; y un frontend web desarrollado en HTML5, CSS3 y JavaScript con Mermaid.js para la renderización de diagramas Entidad-Relación.

## **1.3.** Definición, siglas y abreviaturas

- SAD: Software Architecture Document, Documento de Arquitectura de Software.

- API: Application Programming Interface, Interfaz de Programación de Aplicaciones.

- REST: Representational State Transfer, estilo arquitectónico para servicios web.

- JWT: JSON Web Token, estándar de tokens para autenticación segura.

- RLS: Row Level Security, seguridad a nivel de fila en bases de datos relacionales.

- ORM: Object-Relational Mapping, mapeo objeto-relacional.

- ER: Entidad-Relación, modelo de representación de bases de datos.

- BaaS: Backend as a Service, backend como servicio en la nube.

- CORS: Cross-Origin Resource Sharing, política de intercambio de recursos entre orígenes.

- RBAC: Role-Based Access Control, control de acceso basado en roles.

- SVG: Scalable Vector Graphics, formato de imagen vectorial.

- FK: Foreign Key, clave foránea en bases de datos relacionales.

- PK: Primary Key, clave primaria en bases de datos relacionales.

- UUID: Universally Unique Identifier, identificador único universal.

- JSONB: JSON Binary, formato binario de almacenamiento JSON en bases de datos relacionales.

## **1.4.** Organización del documento

El documento está organizado siguiendo el modelo 4+1. La Sección 2 define los objetivos y restricciones que condicionan las decisiones arquitectónicas. La Sección 3 presenta las cinco vistas arquitectónicas del sistema con sus respectivos diagramas. La Sección 4 describe los atributos de calidad mediante escenarios de calidad concretos alineados con la norma ISO/IEC 25010:2011.

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **2.** OBJETIVOS Y RESTRICCIONES ARQUITECTÓNICAS

## **2.1.** Requerimientos Funcionales

| **Código** | **Requerimiento** | **Decisión arquitectónica** |
| :- | :- | :- |
| RF-01 | Autenticación de usuarios con roles | Uso de autenticación basada en tokens JWT con control de acceso RBAC implementado en el servidor Node.js mediante verificación del identificador de administrador en la cabecera de cada solicitud. |
| RF-02 | Carga de archivos de esquemas en múltiples formatos | Uso de Multer en Node.js con almacenamiento en el directorio temporal del sistema operativo. |
| RF-03 | Análisis técnico local de la estructura de la base de datos | Implementación de un motor Python independiente en main.py, invocado como proceso hijo desde Node.js mediante spawn, con comunicación JSON por la salida estándar del proceso. |
| RF-04 | Generación de documentación descriptiva del esquema | Invocación asíncrona de un servicio externo de análisis desde el servidor Node.js, gestionando la clave de acceso en variables de entorno para evitar su exposición al cliente. |
| RF-05 | Generación de diagramas Entidad-Relación interactivos | El motor Python genera el código Mermaid a partir del esquema analizado, y el frontend lo renderiza con la librería Mermaid.js directamente en el navegador del usuario. |
| RF-06 | Exportación de documentación en PDF y Word | Generación del documento PDF en el lado del cliente mediante jsPDF, servido por Node.js desde las dependencias del proyecto. |
| RF-07 | Almacenamiento de documentación en la nube | Uso de una tabla de documentos en la base de datos en la nube con campos de contenido en formato JSONB para almacenar el análisis completo de cada esquema procesado. |
| RF-08 | Compartición de documentación entre usuarios | Uso de una tabla de elementos compartidos con claves foráneas a las tablas de documentos y usuarios, con políticas de seguridad a nivel de fila para el control de acceso por usuario. |
| RF-09 | Panel de administración de usuarios | Implementación de endpoints REST exclusivos bajo la ruta /api/admin con verificación del rol de administrador en la tabla de perfiles de la base de datos. |
| RF-10 | Registro de logs de actividad | Uso de una tabla de logs en la base de datos con políticas de seguridad que solo permiten lectura a usuarios con rol de administrador. |
| RF-11 | Conversión de esquemas a múltiples formatos | Implementación de un módulo en Python, cuyos resultados se incluyen en la respuesta JSON del análisis devuelta al servidor. |
| RF-12 | Generación de datos de prueba | Implementación la librería Faker, invocado con un indicador especial y recibiendo la entrada mediante JSON por la entrada estándar del proceso. |

## **2.2.** Requerimientos No Funcionales – Atributos de Calidad

| **Código** | **Requerimiento** | **Decisión arquitectónica** |
| :- | :- | :- |
| RNF-01 | Rendimiento: Análisis Python igual o menor a 10 segundos para esquemas de hasta 50 tablas | Ejecución del motor Python como proceso local sin latencia de red, con comunicación directa por entrada y salida estándar. |
| RNF-02 | Rendimiento: Análisis con servicio externo igual o menor a 30 segundos | Invocación asíncrona con async/await y timeout configurado en el cliente. |
| RNF-03 | Disponibilidad igual o superior al 99% mensual | Despliegue en una plataforma de distribución global con acuerdos de nivel de servicio superiores al 99.9%. |
| RNF-04 | Seguridad: Credenciales nunca expuestas al cliente | Uso de variables de entorno mediante dotenv, actuando el servidor como proxy para todas las llamadas a servicios externos. |
| RNF-05 | Seguridad: Solo lectura sobre bases de datos analizadas | El sistema únicamente procesa archivos de esquema sin que ningún endpoint ejecute operaciones de modificación sobre bases externas. |
| RNF-06 | Seguridad: Archivos temporales eliminados tras el procesamiento | Uso de os.tmpdir para el almacenamiento temporal, con eliminación del archivo inmediatamente después de invocar el motor Python. |
| RNF-07 | Privacidad: Políticas de seguridad en todas las tablas | Definición de políticas Row Level Security para cada tabla de la base de datos. |
| RNF-08 | Compatibilidad con Chrome, Firefox, Edge y Safari | Desarrollo del frontend con HTML5, CSS3 y JavaScript estándar, sin dependencias de tecnologías propietarias del navegador. |
| RNF-09 | Portabilidad en Windows y Linux | Uso de Node.js y Python como plataformas multiplataforma, con os.tmpdir y path.join para independencia del sistema operativo. |
| RNF-10 | Escalabilidad para múltiples usuarios simultáneos | Diseño de un servidor stateless sin estado de sesión local, con sesiones gestionadas por el servicio de autenticación en la nube. |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **3.** REPRESENTACIÓN DE LA ARQUITECTURA DEL SISTEMA

## **3.1.** Vista de Caso de uso

La vista de casos de uso identifica los escenarios de mayor impacto arquitectónico que guían las decisiones de diseño del sistema.

### **3.1.1.** Diagramas de Casos de uso

## **3.2.** Vista Lógica

La vista lógica describe la descomposición del sistema en subsistemas, paquetes y clases, mostrando las responsabilidades y relaciones entre los principales elementos de diseño.

### **3.2.1.** Diagrama de Subsistemas (paquetes)

### **3.2.2.** Diagrama de Secuencia (vista de diseño)

### **3.2.3.** Diagrama de Colaboración (vista de diseño)

### **3.2.4.** Diagrama de Objetos

### **3.2.5.** Diagrama de Clases

### **3.2.6.** Diagrama de Base de datos (relacional o no relacional)

## **3.3.** Vista de Implementación (vista de desarrollo)

### **3.3.1.** Diagrama de arquitectura software (paquetes)

### **3.3.2.** Diagrama de arquitectura del sistema (Diagrama de componentes)

## **3.4.** Vista de procesos

### **3.4.1.** Diagrama de Procesos del sistema (diagrama de actividad)

## **3.5.** Vista de Despliegue (vista física)

### **3.5.1.** Diagrama de despliegue

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **4.** ATRIBUTOS DE CALIDAD DEL SOFTWARE

## **4.1. Escenario de Funcionalidad**

- Fuente del estímulo: Usuario desarrollador.

- Estímulo: Carga un archivo .sql con 20 tablas, incluyendo claves foráneas explícitas e implícitas detectables por similitud de nombres de columna como user_id.

- Entorno: Sistema en operación normal con usuario autenticado en rol estándar.

- Artefacto: Motor Python en sql_analyzer.py.

- Respuesta: El sistema extrae correctamente las 20 tablas, detecta las claves foráneas explícitas mediante sentencias FOREIGN KEY con REFERENCES y las implícitas mediante coincidencia difusa de nombres de columnas, genera el código Mermaid del diagrama Entidad–Relación y retorna el JSON completo al frontend.

- Medida de respuesta: Igual o superior al 95% de precisión en la identificación de tablas, campos, claves primarias y foráneas explícitas; e igual o superior al 80% de precisión en claves foráneas implícitas mediante coincidencia difusa.

- Decisión arquitectónica: El motor Python utiliza múltiples estrategias combinadas, como expresiones regulares sobre CREATE TABLE y ALTER TABLE con FOREIGN KEY, claves foráneas en línea con REFERENCES y coincidencia difusa de nombres de columna.

## **4.2. Escenario de Usabilidad**

- Fuente del estímulo: Usuario analista de sistemas sin experiencia previa con la herramienta.

- Estímulo: Primer uso del sistema, iniciando sesión, cargando un archivo de esquema .json y solicitando la generación de documentación.

- Entorno: Sistema en producción accedido desde Google Chrome en Windows 10.

- Respuesta: El sistema guía al usuario visualmente mediante una interfaz de arrastrar y soltar, indicadores de progreso y mensajes de estado claros en español. El resultado se muestra de forma organizada en pestañas diferenciadas para el análisis técnico, el diagrama Entidad–Relación, el convertidor de esquemas y las opciones de exportación.

- Medida de respuesta: El usuario completa el flujo completo desde el inicio de sesión hasta la exportación del PDF en un tiempo igual o menor a 5 minutos sin asistencia externa.

- Decisión arquitectónica: Interfaz de página única con retroalimentación en tiempo real mediante WebSockets, completamente en español y con mensajes de error descriptivos en lenguaje natural.

## **4.3. Escenario de confiabilidad**

- Fuente del estímulo: Servicio externo de análisis descriptivo.

- Estímulo: El servicio externo no está disponible temporalmente por timeout, error 503 o créditos agotados durante una solicitud de documentación.

- Entorno: Sistema en operación normal.

- Respuesta: El sistema captura el error mediante bloques de control, retorna un mensaje descriptivo al frontend y permite al usuario continuar con el análisis del motor local como alternativa, el cual opera de forma independiente sin requerir servicios externos.

- Medida de respuesta: El fallo del servicio externo no provoca la caída del servidor; el sistema retorna un código HTTP 500 con un mensaje JSON descriptivo en un tiempo igual o menor a 3 segundos; el motor local sigue operando con normalidad.

- Decisión arquitectónica: Arquitectura de dos motores independientes, uno local y otro externo; si uno falla, el otro continúa disponible, con manejo explícito de errores en todas las funciones asíncronas del servidor.

## **4.4. Escenario de rendimiento**

- Fuente del estímulo: Usuario desarrollador.

- Estímulo: Carga un archivo .sql de 16 kilobytes con 20 tablas y 15 relaciones de clave foránea.

- Entorno: Sistema en producción con carga normal de 1 a 5 usuarios simultáneos.

- Respuesta: El servidor recibe el archivo, invoca el proceso Python, el analizador procesa el SQL, extrae los metadatos, genera el diagrama Mermaid y las conversiones correspondientes, y retorna el JSON completo al cliente.

- Medida de respuesta: Tiempo total de procesamiento igual o menor a 10 segundos para archivos de hasta 50 tablas; e igual o menor a 5 segundos para esquemas de hasta 20 tablas como el archivo de prueba real del proyecto.

- Decisión arquitectónica: Motor Python como proceso local sin latencia de red, comunicación directa por salida estándar y uso de os.tmpdir en disco rápido para archivos temporales.

## **4.5. Escenario de mantenibilidad**

- Fuente del estímulo: Desarrollador del equipo DB Smart Solutions S.A.C.

- Estímulo: Se requiere agregar soporte para un nuevo formato de archivo de esquema, como .prisma del ORM Prisma.

- Entorno: Entorno de desarrollo local.

- Respuesta: El desarrollador crea un nuevo método, registra la extensión (.prisma) en el bloque condicional de analyze_file, agrega .prisma a la lista de extensiones permitidas en Multer dentro de server.js y actualiza validateDatabaseContent. El cambio queda localizado y no afecta a los demás módulos.

- Medida de respuesta: El cambio requiere modificaciones en tres archivos como máximo, sin necesidad de refactorizar la arquitectura existente; tiempo estimado de implementación igual o menor a 4 horas.

- Decisión arquitectónica: Patrón de diseño Strategy, donde cada formato de archivo tiene su propio método analizador aislado en DatabaseAnalyzer, respetando el principio abierto/cerrado.

## **4.6. Otros Escenarios**

**Escenario de Escalabilidad**

- Atributo: Escalabilidad.

- Fuente del estímulo: Crecimiento del uso del sistema.

- Estímulo: El número de usuarios simultáneos crece de 5 a 50 usuarios activos.

- Entorno: Sistema desplegado en una plataforma de distribución global.

- Respuesta: La plataforma escala automáticamente las instancias del servidor Node.js mediante funciones serverless. El servicio de base de datos en la nube gestiona el pool de conexiones a PostgreSQL. El servidor es completamente stateless, permitiendo múltiples instancias paralelas sin conflictos ni inconsistencias.

- Medida de respuesta: El tiempo de respuesta se mantiene dentro de los límites definidos de 10 segundos para el análisis local y 30 segundos para el análisis externo, incluso con hasta 50 usuarios simultáneos bajo el plan gratuito de la plataforma.

- Decisión arquitectónica: Servidor stateless en el que las sesiones se validan contra la base de datos en cada solicitud sin almacenamiento local, con despliegue en plataforma serverless que escala horizontalmente de forma automática según la demanda.
