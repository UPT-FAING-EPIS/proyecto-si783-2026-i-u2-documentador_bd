<center>

![./media/logo-upt.png](./media/logo-upt.png)

**UNIVERSIDAD PRIVADA DE TACNA**

**FACULTAD DE INGENIERÍA**

**Escuela Profesional de Ingeniería de Sistemas**

**Proyecto *Sistema de documentación de Base de Datos***

Curso: *Base de Datos II*

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

Sistema *de documentación de base de datos*

Informe de Factibilidad

Versión *{1.0}*

| CONTROL DE VERSIONES | | | | | |
| :-: | :- | :- | :- | :- | :- |
| Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| 1\.0 | DAN, CQC | DAN, CQC | DAN, CQC | 01/06/2026 | Versión Original |

<div style="page-break-after: always; visibility: hidden">\pagebreak</div>

# **ÍNDICE GENERAL**

[1. Descripción del Proyecto](#descripción-del-proyecto)

[2. Riesgos](#riesgos)

[3. Análisis de la Situación actual](#análisis-de-la-situación-actual)

[4. Estudio de Factibilidad](#estudio-de-factibilidad)

[4.1 Factibilidad Técnica](#factibilidad-técnica)

[4.2 Factibilidad Económica](#factibilidad-económica)

[4.3 Factibilidad Operativa](#factibilidad-operativa)

[4.4 Factibilidad Legal](#factibilidad-legal)

[4.5 Factibilidad Social](#factibilidad-social)

[4.6 Factibilidad Ambiental](#factibilidad-ambiental)

[5. Análisis Financiero](#análisis-financiero)

[6. Conclusiones](#conclusiones)



**<u>Informe de Factibilidad</u>**

1. <span id="descripción-del-proyecto" class="anchor"></span>**Descripción del Proyecto**

    1.1. Nombre del proyecto

    Sistema de documentación de base de datos

    1.2. Duración del proyecto

    2 meses

    1.3. Descripción

    El proyecto consiste en el desarrollo de un sistema híbrido de documentación y de bases de datos que combina la potencia de la Inteligencia Artificial con un motor de análisis local basado en Python, ofreciendo precisión técnica y visión crítica sobre la estructura de cualquier base de datos.

    El sistema permite a los usuarios cargar archivos de esquemas de bases de datos en múltiples formatos, y a partir de ellos genera automáticamente documentación estructurada, diagramas Entidad-Relación interactivos y reportes exportables en diferentes formatos.

    La importancia del proyecto surge debido a que muchas organizaciones y equipos de desarrollo carecen de documentación actualizada de sus bases de datos. Esta situación genera dificultades críticas en el mantenimiento, escalabilidad y comprensión de los sistemas de información. La solución propuesta centraliza y automatiza la documentación, reduce la dependencia del conocimiento tácito, mejora la trazabilidad de cambios y optimiza el trabajo colaborativo de desarrolladores, analistas y administradores de bases de datos.

    El sistema se despliega como una aplicación web accesible desde cualquier navegador moderno, con un servidor backend en Node.js y un módulo de análisis local en Python, integrado con Supabase para la gestión de usuarios y almacenamiento de documentación generada.

    1.4. Objetivos

        1.4.1 Objetivo general

        Desarrollar un sistema documentador de bases de datos que permita organizar, visualizar y gestionar la información estructural de bases de datos de manera eficiente.

        1.4.2 Objetivos Específicos

        - Implementar un motor de análisis para la extracción automática de la estructura de bases de datos SQL y NoSQL, detectando tablas, campos, claves primarias, claves foráneas, tipos de datos y métricas de normalización.

        - Desarrollar una interfaz web moderna e intuitiva que permita a los usuarios cargar archivos de esquemas, visualizar los resultados del análisis, navegar por las secciones de documentación y exportar reportes.

        - Integrar un modelo adecuado para generar auditorías críticas automáticas desde una perspectiva de arquitectura de datos y buenas prácticas de ingeniería, incluyendo sugerencias de mejora y análisis de normalización.

        - Generar diagramas Entidad-Relación interactivos, con controles de zoom y descarga en formato SVG, que permitan visualizar gráficamente las relaciones entre las entidades de la base de datos.

        - Implementar un convertidor de esquemas profesional que transforme la estructura de datos a múltiples formatos y tecnologías tales como MySQL, PostgreSQL, SQLite, MongoDB, Prisma, GraphQL, JSON Schema, CSV y YAML.

        - Habilitar la exportación de documentación en formatos accesibles como PDF, facilitando el almacenamiento, distribución y presentación formal de los resultados del análisis.



2. <span id="riesgos" class="anchor"></span>**Riesgos**

    El desarrollo del sistema puede verse afectado por diversos riesgos que podrían comprometer su éxito:

    - **Falta de experiencia técnica:** El equipo podría presentar dificultades en el uso de tecnologías como frameworks backend o conexión a múltiples bases de datos.

    - **Limitaciones de tiempo:** El proyecto tiene una duración corta (2 meses), lo que podría afectar la calidad si no se gestiona adecuadamente.

    - **Problemas de compatibilidad:** Posibles inconvenientes al conectar con diferentes gestores de bases de datos (MySQL, PostgreSQL, etc.).

    - **Errores en la extracción de datos:** Fallos en la automatización que generan documentación incompleta o incorrecta.

    - **Dependencia tecnológica:** Dependencia de herramientas externas o librerías que podrían cambiar o dejar de ser compatibles.

    - **Fallas en el servidor:** Problemas de disponibilidad o rendimiento en el entorno de despliegue.

    - **Riesgos de seguridad:** Acceso no autorizado a bases de datos durante la extracción de información.



3. <span id="análisis-de-la-situación-actual" class="anchor"></span>**Análisis de la Situación actual**

    3.1. Planteamiento del problema

    En la actualidad, muchas organizaciones y equipos de desarrollo de software presentan deficiencias críticas en la documentación de sus bases de datos, lo que genera dificultades significativas en la gestión, mantenimiento y evolución de los sistemas de información.

    Históricamente, la documentación de bases de datos se ha realizado de forma manual mediante archivos de texto, hojas de cálculo o diagramas elaborados sin una estandarización clara. Este enfoque no solo demanda tiempo considerable, sino que también incrementa la probabilidad de errores humanos, inconsistencias entre la documentación y la realidad del sistema, y pérdida de información relevante.

    Herramientas especializadas existentes en el mercado ofrecen funcionalidades parciales de documentación, pero generalmente están vinculadas a un gestor específico, requieren conexión directa a la base de datos, tienen costos de licencia elevados o no ofrecen análisis crítico impulsado por inteligencia artificial.

    La problemática actual se manifiesta en los siguientes aspectos:

    - **Alta dificultad de comprensión estructural:** Los sistemas heredados o desarrollados por múltiples programadores presentan estructuras de bases de datos complejas sin documentación clara, generando fuerte dependencia del conocimiento tácito de ciertos desarrolladores, lo que representa un riesgo operativo crítico.

    - **Documentación desactualizada:** La falta de documentación actualizada provoca errores frecuentes durante la modificación o ampliación de los sistemas, ya que no existe claridad sobre las relaciones entre tablas, restricciones o reglas de negocio implementadas a nivel de base de datos.

    - **Ausencia de herramientas automatizadas accesibles:** Las soluciones existentes no ofrecen análisis inteligente que combine la precisión técnica de un motor de análisis local con la capacidad interpretativa de la inteligencia artificial para generar auditorías críticas y sugerencias de mejora.

    - **Retrabajo constante:** Los desarrolladores invierten tiempo adicional en comprender estructuras existentes antes de realizar cualquier cambio, reduciendo la productividad y aumentando los costos de desarrollo y mantenimiento.

    - **Falta de interoperabilidad:** No existen herramientas variadas que permitan convertir esquemas entre múltiples tecnologías de bases de datos de manera ágil, dificultando la migración o la adopción de nuevas tecnologías.

    3.2. Consideraciones de hardware y software

    **Estaciones de trabajo (desarrolladores y usuarios técnicos)**

    Las estaciones de trabajo estarán destinadas a los desarrolladores y posibles usuarios técnicos del sistema, por lo que deben cumplir con las siguientes características mínimas:

    - Procesador: Intel Core i3 o equivalente
    - Memoria RAM: 4 GB mínimo
    - Almacenamiento: 256 GB HDD/SSD (preferiblemente SSD para mejor rendimiento)
    - Monitor: Resolución mínima de 1366x768
    - Conectividad: Acceso a red local e internet estable

    **Arquitectura del sistema**

    Para el correcto funcionamiento del sistema documentador, se consideran dos componentes principales:

    **Lado del servidor (Backend y Base de Datos)**

    En este componente se gestionará la lógica del sistema, la conexión a bases de datos externas y la generación de documentación.

    - Node.js >= 16.0.0
    - Express.js ^4.18.2
    - Multer ^1.4.5
    - Supabase JS ^105.3
    - WebSockets ^8.20.0
    - dotenv ^16.3.1
    - xlsx ^0.18.5

    **Lado del cliente (Frontend y acceso de usuario)**

    Este componente permitirá a los usuarios interactuar con el sistema, visualizar la estructura de las bases de datos y generar documentación.

    Navegadores compatibles:
    - Google Chrome
    - Mozilla Firefox
    - Microsoft Edge

    Tecnologías web:
    - HTML5
    - CSS3
    - Mermaid
    - jspDF



4. <span id="estudio-de-factibilidad" class="anchor"></span>**Estudio de Factibilidad**

    El estudio de factibilidad tiene como objetivo determinar si el proyecto planteado es viable en sus diferentes aspectos: técnico, económico, operativo, legal, social y ambiental. Con ello se busca comprobar no solo si el sistema puede construirse, sino también si realmente puede aportar una solución útil, ordenada y adecuada a la necesidad identificada.

    Para elaborar este estudio, se realizaron varias actividades que permitieron analizar el proyecto desde una perspectiva más completa. Entre ellas se consideran el análisis de los requerimientos funcionales y no funcionales del sistema, la revisión de los recursos tecnológicos disponibles en el equipo de desarrollo, la selección de herramientas, frameworks y servicios de terceros que se ajusten al proyecto, la estimación de los costos de desarrollo e infraestructura, y el análisis del impacto social, legal y ambiental de la propuesta.

    De esta manera, el estudio de factibilidad permite identificar si el sistema puede desarrollarse dentro de un contexto realista, con recursos alcanzables y con un beneficio claro para los usuarios. También ayuda a reducir riesgos y a definir con mayor seguridad el camino que seguirá el proyecto durante su desarrollo.

    4.1. <span id="factibilidad-técnica" class="anchor"></span>Factibilidad Técnica

    Actualmente, el equipo de desarrollo está conformado por un pequeño grupo de personas, donde cada integrante dispone de su propia laptop o computadora personal.

    - Procesador: Intel Core i3 o superior: Suficiente para desarrollo, pruebas locales y ejecución del servidor Node.js y Python.
    - Memoria RAM de 8GB: Adecuada para ejecutar el entorno de desarrollo completo.
    - Almacenamiento: 256GB SSD/HDD: Suficiente para el código fuente, dependencias y archivos temporales de prueba.
    - Servidor de pruebas: Se utilizará un equipo local durante el desarrollo. Para producción, se evaluará el uso de un VPS o Vercel (plataforma serverless compatible con el stack del proyecto).
    - Navegadores compatibles: Google Chrome, Mozilla Firefox, Microsoft Edge y otros navegadores modernos compatibles con tecnologías HTML5, CSS3 y JavaScript.
    - Sistemas operativos compatibles:
        - Desarrollo: Windows 10/11 y Linux (Ubuntu).
        - Producción: Ubuntu Server o Debian.

    4.2. <span id="factibilidad-económica" class="anchor"></span>Factibilidad Económica

    El estudio de viabilidad económica permite determinar si el proyecto es rentable, comparando los beneficios esperados frente a los costos de desarrollo e implementación.

    Se evalúa si el equipo cuenta con los recursos necesarios o si se requiere inversión adicional. En este caso, el proyecto presenta una inversión baja, ya que se utilizan herramientas de desarrollo gratuitas y equipos propios.

    Definir los siguientes costos:

    4.2.1. Costos Generales

    Corresponden a los materiales y recursos de uso cotidiano necesarios para el proyecto.

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Hojas bond A4 (Paquete 500 hojas) | 1 paquete | 25.00 | 25.00 |
    | Lapiceros | 5 unidades | 2.00 | 10.00 |
    | Folder y archivadores | 2 unidades | 5.00 | 10.00 |
    | Impresión de documentos | 2 lote | 30.00 | 30.00 |
    | **Total** | | | **75.00** |

    4.2.2. Costos operativos durante el desarrollo

    Gastos necesarios para mantener la operatividad del equipo durante los 2 meses de desarrollo.

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Internet (mensual) | 2 meses x 2 personas | 80.00 | 320.00 |
    | Energía eléctrica | 2 meses x 2 personas | 30.00 | 120.00 |
    | Transporte | 2 meses | 40.00 | 80.00 |
    | Mantenimiento de equipos | 1 vez | 30.00 | 30.00 |
    | **Total** | | | **550.00** |

    4.2.3. Costos del ambiente

    El proyecto utiliza infraestructura existente, por lo que no se requiere inversión significativa:

    | **Concepto** | **Cantidad** | **Costo Unitario (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- |
    | Dominio web | Fase académica | 0.00 | 0.00 |
    | BaaS | Plan gratuito | 0.00 | 0.00 |
    | Hosting | Plan gratuito | 0.00 | 0.00 |
    | Producción (Opcional) | Solo en despliegue permanente | 50.00 | 50.00 |
    | **Total** | | | **50.00** |

    4.2.4. Costos de personal

    | **Rol** | **Cantidad** | **Duración** | **Pago mensual (S/.)** | **Total (S/.)** |
    | :- | :- | :- | :- | :- |
    | Desarrollador Backend | 1 | 2 meses | 800.00 | 1600.00 |
    | Desarrollador Frontend | 1 | 2 meses | 800.00 | 1600.00 |
    | **Total** | | | | **3200.00** |

    4.2.5. Costos totales del desarrollo del sistema

    | **Tipo de costo** | **Monto (S/.)** |
    | :- | :- |
    | Costos generales | 75.00 |
    | Costos operativos | 550.00 |
    | Costos ambiente | 100.00 |
    | Costos personal | 3200.00 |
    | **Total** | **3925.00** |

    4.3. <span id="factibilidad-operativa" class="anchor"></span>Factibilidad Operativa

    El sistema documentador de bases de datos ofrece importantes beneficios operativos para los equipos de desarrollo y gestión de sistemas de información. Este sistema permitirá automatizar la documentación de bases de datos, facilitando la visualización de estructuras, relaciones y atributos, lo que reduce significativamente los tiempos de análisis y comprensión.

    Asimismo, optimiza el flujo de trabajo al disminuir la necesidad de documentar manualmente, reduciendo errores y mejorando la calidad de la información disponible. Esto permite que los procesos de mantenimiento, actualización y desarrollo de sistemas se realicen de manera más eficiente y organizada.

    En cuanto a la capacidad operativa, el personal involucrado (desarrolladores, analistas y administradores de bases de datos) cuenta con los conocimientos necesarios para utilizar el sistema, ya que su diseño estará orientado a la facilidad de uso y no requerirá capacitación especializadas.

    Beneficios Operativos:

    - **Automatización de la documentación:** El sistema extrae automáticamente la estructura de la base de datos a partir del archivo cargado, eliminando el proceso manual y reduciendo el tiempo invertido en esta actividad en aproximadamente un 60-70%.

    - **Reducción de errores humanos:** Al automatizar la extracción de metadatos, se elimina la posibilidad de errores de transcripción o inconsistencias entre la documentación y la realidad del sistema.

    - **Accesibilidad universal:** Al ser una aplicación web, el sistema puede ser utilizado desde cualquier dispositivo con un navegador moderno, sin necesidad de instalación local de software especializado.

    - **Análisis inteligente:** La integración de recursos adecuados para el análisis de base de datos, nos permite obtener auditorías críticas automáticas que van más allá de la simple documentación, ofreciendo recomendaciones de mejora, detección de problemas de diseño y análisis de normalización.

    - **Interoperabilidad:** El convertidor de esquemas facilita la migración entre tecnologías de bases de datos, un proceso que normalmente requería experiencia técnica avanzada y horas de trabajo manual.

    Lista de interesados:

    - Desarrolladores de software: responsables de implementar y mantener los sistemas.
    - Administradores de bases de datos: encargados de la gestión y optimización de la información.
    - Analistas de sistemas: responsables del análisis y diseño de soluciones.
    - Jefe de proyecto: supervisa el desarrollo y uso del sistema.
    - Organización/empresa usuaria: beneficiaria directa del sistema.
    - Usuarios finales (beneficiarios indirectos): reciben sistemas más estables y eficientes.

    4.4. <span id="factibilidad-legal" class="anchor"></span>Factibilidad Legal

    El proyecto cumple con las normativas legales vigentes relacionadas con el uso de software y manejo de información:

    - **Derechos de autor y licencias de software:** Todas las herramientas y librerías utilizadas están licenciadas bajo licencias de código abierto (MIT, Apache 2.0, BSD), lo que permite su uso, modificación y distribución sin infringir derechos de propiedad intelectual. El sistema propio se distribuye bajo Licencia MIT.

    - **Protección de datos personales:** El sistema no almacena información personal sensible más allá de las credenciales de acceso, gestionadas de forma segura por Supabase mediante cifrado. Los esquemas de bases de datos cargados para análisis son procesados temporalmente en el servidor y eliminados tras el análisis, sin persistir información sensible.

    - **Ley N° 29733 – Ley de Protección de Datos Personales:** El sistema cumple con los principios establecidos en esta ley: finalidad, proporcionalidad, calidad de datos, seguridad y flujo transfronterizo controlado.

    - **Seguridad informática:** El sistema implementa autenticación basada en tokens JWT mediante Supabase, control de acceso por roles y manejo seguro de archivos temporales, alineándose con las buenas prácticas establecidas por la ISO/IEC 27001.

    - **Uso académico:** El sistema es desarrollado con fines académicos en el contexto del curso de Base de Datos II de la Universidad Privada de Tacna, no generando conflicto con ninguna regulación comercial o sectorial.

    Por lo tanto, no existen restricciones legales que impidan su desarrollo.

    4.5. <span id="factibilidad-social" class="anchor"></span>Factibilidad Social

    El sistema contribuye de manera positiva al entorno social y profesional en el que se desenvuelven los equipos de desarrollo de software:

    - **Mejora de la cultura de documentación:** La implementación del sistema promueve una forma de trabajo más organizada y responsable, donde la documentación deja de ser una tarea postergada para convertirse en un proceso automático integrado al flujo de desarrollo, elevando la calidad general de los proyectos de software.

    - **Reducción de la brecha tecnológica:** Al ofrecer análisis inteligente y diagramas visuales, el sistema facilita que usuarios con menor experiencia técnica puedan interpretar y trabajar con bases de datos complejas.

    - **Apoyo a la toma de decisiones:** La disponibilidad de documentación estructurada, diagramas ER y auditorías críticas generadas automáticamente permite a los líderes de proyecto y arquitectos de sistemas tomar decisiones más informadas sobre la evolución de sus sistemas de información.

    - **Fomento del trabajo colaborativo:** La funcionalidad de compartición de documentación entre usuarios facilita el trabajo en equipo distribuido, permitiendo que múltiples desarrolladores trabajen sobre la misma base documental de forma sincronizada.

    - **Impacto en la formación académica:** El proyecto sirve como modelo de referencia para otros estudiantes de Ingeniería de Sistemas, demostrando la aplicación práctica de tecnologías modernas en la resolución de problemas reales del ámbito profesional.

    4.6. <span id="factibilidad-ambiental" class="anchor"></span>Factibilidad Ambiental

    El impacto ambiental del proyecto es mínimo, siendo consistente con los principios de desarrollo sostenible:

    - **Reducción del consumo de papel:** Al generar documentación digital, el sistema elimina la necesidad de imprimir manuales técnicos y reportes de estructura de bases de datos.

    - **Uso eficiente de recursos energéticos existentes:** El sistema utiliza equipos de cómputo ya disponibles en el equipo de desarrollo, sin requerir la adquisición de hardware adicional que implique consumo de recursos naturales en su fabricación.

    - **Infraestructura en la nube con enfoque verde:** El uso de plataformas que han adoptado compromisos de eficiencia energética y uso de energías renovables en sus centros de datos, reduce la huella de carbono del proyecto en comparación con el mantenimiento de servidores físicos locales.

    - **Sin generación de residuos contaminantes:** Al ser un proyecto de software puro, no genera desechos industriales, contaminantes químicos ni residuos electrónicos adicionales.

    - **Ciclo de vida extendido del conocimiento:** Al documentar y preservar el conocimiento sobre la estructura de las bases de datos, el sistema contribuye a extender el ciclo de vida de los sistemas de información existentes, reduciendo la necesidad de reescritura completa por falta de documentación, lo que implicaría mayor consumo de recursos tecnológicos.

    En consecuencia, el proyecto es amigable con el medio ambiente.



5. <span id="análisis-financiero" class="anchor"></span>**Análisis Financiero**

    La inversión total del proyecto asciende a S/ 3,925.00, distribuida principalmente en costos de personal y costos operativos. Dado que se utilizan herramientas de código abierto y servicios con planes gratuitos, la inversión en infraestructura es mínima.

    La inversión se justifica debido a que el sistema permitirá optimizar procesos, reducir errores y mejorar la gestión de bases de datos, generando beneficios tanto económicos como operativos.


    5.1. Justificación de la Inversión

        5.1.1. Beneficios del Proyecto

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

        5.1.2. Criterios de Inversión

            5.1.2.1. Relación Beneficio/Costo (B/C)

            La relación B/C compara los beneficios económicos estimados contra los costos totales de desarrollo, para ello se estima:

            - Beneficios: S/ 6060.00 (ahorro en tiempo y recursos)
            - Costos totales del desarrollo: S/ 3925.00
            - **B/C = 6060 / 3925 = 1.58**

            Interpretación: El resultado B/C = 1.58 es mayor a 1, por lo tanto el proyecto es económicamente viable y se acepta. Por cada sol invertido, el sistema genera S/ 1.58 en beneficios, representando un retorno positivo de S/ 0.58 por cada sol invertido.

            5.1.2.2. Valor Actual Neto (VAN)

            El VAN representa el valor actual de los beneficios netos que genera el proyecto, descontando el costo de oportunidad del capital. Se asume una tasa de descuento (COK) del 10% anual.

            Se estima un VAN positivo:

            | **Periodo** | **Flujo de Caja (S/.)** | **Factor de descuento (10%)** | **Valor actual (S/.)** |
            | :- | :- | :- | :- |
            | Año 0 (Inversión inicial) | -3925.00 | 1.0000 | -3925.00 |
            | Año 1 (Beneficios) | +6060.00 | 0.9091 | 5509.09 |
            | VAN | | | 1584.09 |

            Interpretación: El VAN = S/ +1,584.09 es mayor a 0, por lo tanto el proyecto genera valor económico neto y se acepta. El proyecto crea riqueza adicional de S/ 1,584.09 en términos actuales.

            5.1.2.3. Tasa Interna de Retorno (TIR)

            La TIR es la tasa de rentabilidad promedio que genera el capital invertido en el proyecto. Se calcula encontrando la tasa a la cual el VAN = 0.

            Se estima:

            - Inversión inicial: S/. 3925.00
            - Beneficios del primer año: S/. 6060.00
            - TIR estimada: 54.5%
            - Costo de oportunidad del capital (COK): 10%

            Interpretación: La TIR = 54.5% es mayor al COK = 10%, por lo tanto el proyecto es altamente rentable y se acepta. La rentabilidad del proyecto supera ampliamente el costo de oportunidad del capital, lo que indica que la inversión en el sistema es significativamente más beneficiosa que destinar los recursos a una inversión alternativa estándar.


6. <span id="conclusiones" class="anchor"></span>**Conclusiones**

El análisis de factibilidad realizado demuestra que el proyecto es viable, justificado y recomendable para su implementación desde todos los aspectos evaluados:

**Factibilidad Técnica:** El equipo de desarrollo cuenta con el hardware necesario en sus equipos personales, y todas las herramientas de software requeridas son de código abierto o disponen de planes gratuitos adecuados para el ámbito académico. El stack tecnológico seleccionado es moderno, robusto y ampliamente documentado.

**Factibilidad Económica:** La inversión total del proyecto asciende a S/ 3,925.00, mayormente concentrada en costos de personal. Los indicadores financieros confirman la viabilidad económica: B/C = 1.58 (> 1), VAN = S/ +1,584.09 (> 0) y TIR = 54.5% (> COK del 10%), siendo todos favorables para la aceptación del proyecto.

**Factibilidad Operativa:** El sistema automatiza procesos de documentación que actualmente se realizan de forma manual e ineficiente, ofreciendo beneficios tangibles a todos los interesados. No se requiere capacitación especializada para su uso, garantizando una adopción ágil por parte de los usuarios finales.

**Factibilidad Legal:** El proyecto utiliza exclusivamente herramientas de código abierto, cumple con la Ley N° 29733 de Protección de Datos Personales del Perú y con los principios de la ISO/IEC 27001 en materia de seguridad de la información. No existe ningún conflicto legal que impida su desarrollo.

**Factibilidad Social:** El sistema contribuye a democratizar el conocimiento técnico, mejorar la cultura de documentación en los equipos de desarrollo y fomentar la colaboración entre profesionales de distintos niveles de experiencia.

**Factibilidad Ambiental:** El impacto ambiental del proyecto es mínimo y favorable, dado que promueve la reducción del uso de papel, aprovecha la infraestructura existente y utiliza plataformas en la nube con compromisos de sostenibilidad energética.

En conclusión, el proyecto es factible en todos sus aspectos y se recomienda firmemente su implementación. El sistema propuesto no solo resuelve una problemática real y frecuente en el desarrollo de software, sino que lo hace de manera inteligente, accesible y con un retorno de inversión claramente positivo, aportando valor tanto al equipo de desarrollo como a las organizaciones que lo adopten.
