# LinkedIn Growth Analytics: Implementación de Dogfooding mediante Python & Tableau

## 🎯 Propósito del Proyecto
Este proyecto implementa la metodología de **Dogfooding** (usar las herramientas que domino para optimizar mi propio producto) con el fin de acelerar el crecimiento de mi marca personal en LinkedIn. El análisis se enfoca en un nicho híbrido estratégico: **Sports Analytics** y **Business Intelligence**. 

A través de un pipeline automatizado de datos, transformo texto plano e históricos aislados de métricas en un motor de decisiones de Business Intelligence que dicta qué contenido, qué día y a qué hora genera el mayor impacto.

---

## 🛠️ Arquitectura del Pipeline de Datos (ETL)

El backend de LinkedIn exporta datos fragmentados, con tablas espejo mal estructuradas (Interacciones e Impresiones separadas lateralmente) y URLs codificadas en formato web (`%3A`). Diseñé un proceso ETL robusto en Python para solucionar este reto de ingeniería de datos:

```text
[LinkedIn Privacy: Shares.csv]  ───(URL Decode + Regex)───┐
                                                          ├──> [Post_ID Join] ──> [linkedin_data_final.csv] ──> [Tableau Web Dashboard]
[LinkedIn Analytics: .xlsx]     ───(iloc Split Lateral)───┘
```

### Componentes Técnicos:
1. **Ingestión e Ingeniería de Características (Python & Pandas):** 
   * Separación de bloques paralelos mediante posicionamiento puro (`.iloc`).
   * Decodificación web (`urllib.parse.unquote`) y expresiones regulares (`re.search`) para extraer un identificador único numérico (`Post_ID`) infalible, resolviendo el conflicto de enlaces que bloqueaba el cruce de datos.
2. **Clasificación Automatizada de Texto (Regex & Numpy):**
   * Implementación de un categorizador semántico con `np.select` para escanear y etiquetar automáticamente el histórico de publicaciones en 4 nichos clave.
3. **Capa de Visualización (Tableau Public):**
   * Consolidación de un archivo óptimo unificado (`linkedin_data_final.csv`) conectado a un cuadro de mando interactivo bajo el principio de *Pirámide de Información*.

---

## 📈 Distribución del Contenido por Nicho Temático

El proceso de clasificación de texto analizó el histórico completo de publicaciones, segmentándolo de la siguiente manera para la auditoría de marca:

*   **Otros / General:** 53 posts (Gestión de comunidad y contenido transversal).
*   **Data & Business Intelligence:** 12 posts (Contenido técnico puro).
*   **Sports Analytics (Híbrido):** 11 posts (Estrategia central de atracción).
*   **Fútbol / Deportes:** 4 posts (Análisis de actualidad de la industria).

---

## 📊 Insights Senior de Negocio & Growth

### 🎯 1. El Océano Azul del Nicho Híbrido (Sports Analytics)
Aunque la cantidad de publicaciones entre Data pura y Sports Analytics es equilibrada (12 vs 11), el contenido híbrido actúa como el principal reductor de fricción para la audiencia. Al combinar la pasión masiva del fútbol (ej. Analizar las tácticas de Carlo Ancelotti) con el tecnicismo de Tableau o Python, se logra retener la atención de perfiles técnicos y no técnicos simultáneamente.

### ⏰ 2. Ventanas de Lanzamiento vs. Saturación Algorítmica
El análisis de frecuencia revela que el volumen de publicaciones se concentra fuertemente los **Martes (27 posts)** en bloques de **06:00 - 07:00 hrs** y **19:00 hrs**. Si bien publicar temprano activa el *Day-Start Analytics*, los martes representan el día con mayor saturación de creadores en la plataforma. La analítica basada en promedios del pipeline permite identificar qué días de menor volumen (ej. Miércoles o Jueves) otorgan un alcance neto más alto por publicación.

### 📉 3. Ciclo de Vida del Contenido & Estrategia de Repurposing
El proceso de cruce de datos (`LEFT JOIN`) identificó que solo 24 de las publicaciones históricas mantienen métricas activas en los reportes de rendimiento recientes de LinkedIn. Esto demuestra de forma científica que el 70% del contenido técnico "muere" para el algoritmo después de unos meses. Como acción estratégica de Dogfooding, el pipeline identifica las publicaciones con alto engagement histórico para ser reescritas y relanzadas, maximizando el ROI del esfuerzo de desarrollo de contenido anterior.

---

## 🚀 Conclusión del Portafolio
Este proyecto demuestra que la analítica de datos es una herramienta de ejecución inmediata. Al procesar mi propia actividad, transformé datos crudos en una ventaja competitiva. El resultado no es solo un tablero estético, sino un marco de trabajo de Business Intelligence real para la toma de decisiones estratégicas de marca.

