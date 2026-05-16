📈 LinkedIn Growth Analytics: Implementación de Dogfooding mediante Python & Tableau

📖 1. Resumen del Proyecto
Este proyecto implementa la metodología de Dogfooding, aplicando Ciencia de Datos y Business Intelligence (BI) para optimizar y acelerar el crecimiento de mi propia cuenta profesional de LinkedIn. El análisis se enfoca en un nicho híbrido: Sports Analytics y Business Intelligence.

A través de un pipeline de datos End-to-End, transformo las métricas crudas de la plataforma en insights accionables para el calendario editorial, automatizando la toma de decisiones basada en datos (Data-Driven Decisions).

🎯 2. Objetivos de Negocio
Maximizar el Alcance: Identificar patrones temporales óptimos (días y horas) para publicar
Optimización de Contenido: Evaluar el rendimiento del contenido técnico (Python, SQL, Tableau) vs. estratégico
Gobierno de Datos (Data Governance): Corregir anomalías de origen en las métricas de la plataforma antes de su visualización

🛠️ 3. Stack Tecnológico
Python 3.10 (Anaconda): Entorno virtual e ingesta de datos
Pandas & OpenPyXL: Limpieza, transformación y tratamiento de datos desordenados
Tableau Public: Diseño del dashboard interactivo y análisis visual
Jupyter Notebooks (VS Code): Entorno de desarrollo e investigación

⚙️ 4. Arquitectura del Pipeline de Datos
[LinkedIn Data] ➔ [Python (Pandas/OpenPyXL)] ➔ [datos_linkedin_limpios.csv] ➔ [Tableau Dashboard]
Fase 1: Extracción y Limpieza (Python)
El reporte crudo de LinkedIn suele presentar problemas de formato y desfases temporales. Se implementó un script de limpieza en Python para:

Normalizar nombres de columnas y tipos de datos (Fechas, Enteros)
Clasificar los posts de forma automatizada mediante palabras clave en la columna Nicho (Sports Analytics, Business Intelligence, o General)

Fase 2: Reglas de Negocio y Control de Calidad
Durante el Diagnóstico de la Línea Base, se detectó una anomalía en los datos de origen: las impresiones igualaban exactamente a las interacciones en posts nuevos, arrojando un Engagement Rate artificial del 100%.

Acción de Data Governance: Se aplicó una corrección por software utilizando numpy.where() para mitigar el impacto de este desfase de la API en el dashboard final, asegurando la integridad de los reportes.

Fase 3: Modelado y Visualización (Tableau)
El dataset procesado se conectó a Tableau bajo el principio de Pirámide de Información:

Capa Directiva (KPIs): Tarjetas con Impresiones Totales, Interacciones Totales y Engagement Rate Global
Capa de Diagnóstico: Gráficos de barras para comparar el rendimiento por nicho y líneas de tiempo para identificar picos de tracción
⚠️ Regla de Negocio Crítica
El Engagement Rate Global de la cuenta no se calcula promediando los porcentajes de cada post (un error común). Se implementó el siguiente campo calculado de agregación:

( SUM([Interacciones]) / SUM([Impresiones])

💡 5. Próximos Pasos (Ciclo de Mejora Continua)
Inyección de Datos (Fase de BI): Publicar contenido estratégico enfocado en Business Intelligence para equilibrar el histórico de datos (actualmente dominado por Sports Analytics)
Actualización del Dashboard: Re-ejecutar el pipeline con el nuevo reporte de LinkedIn para evaluar el impacto de la nueva estrategia de contenido

📊 6. Resultados y Métricas Clave
Pipeline automatizado que reduce el tiempo de análisis de métricas de LinkedIn en un 80%
Identificación de patrones temporales óptimos para maximizar el alcance orgánico
Dashboard interactivo que permite monitoreo en tiempo real del rendimiento de contenido

🔗 7. Enlaces del Proyecto
Dashboard en Tableau Public:(https://public.tableau.com/views/DashboardLinkedIn-DogfoodingBISportsAnalytics_/Dashboard1?:language=es-ES&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
Código fuente: GitHub Repository
Dataset procesado: datos_linkedin_limpios.csv

📝 8. Aprendizajes Técnicos
Implementación de Data Governance para corregir anomalías en datos de origen
Aplicación de metodología Dogfooding en proyectos de analytics
Diseño de pipelines End-to-End escalables y reproducibles
Cálculo correcto de métricas agregadas en herramientas de BI

Tecnologías: Python Pandas Tableau Data Analytics Business Intelligence LinkedIn Analytics



