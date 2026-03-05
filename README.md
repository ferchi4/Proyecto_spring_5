# Análisis de Rentabilidad: Planes de Prepago Megaline

Este proyecto analiza el comportamiento de los clientes de los planes de prepago "Surf" y "Ultimate" de la empresa de telecomunicaciones Megaline. El objetivo principal es determinar cuál de las dos tarifas genera más ingresos para la empresa y cómo los usuarios utilizan los servicios de llamadas, mensajes e internet. Este análisis servirá para ajustar el presupuesto de publicidad de la compañía.

## Objetivo

Comparar los dos planes de prepago para determinar cuál genera más ingresos, analizando cómo los clientes consumen los servicios de llamadas, mensajes e internet a lo largo del año.

## 🛠️ Tecnologías Utilizadas

*   **Python:** Lenguaje de programación principal.
*   **Pandas:** Para la manipulación, limpieza y agregación de datos.
*   **NumPy:** Para operaciones numéricas y cálculos de redondeo.
*   **Matplotlib / Seaborn:** Para la visualización de datos y la creación de gráficos (histogramas, diagramas de caja, etc.).
*   **SciPy:** Para la realización de pruebas de hipótesis estadísticas (prueba t de Student).
*   **Jupyter Notebook:** Entorno interactivo para el desarrollo del análisis.

## Dataset

Se utilizaron cinco archivos CSV que contienen información detallada de 500 clientes de Megaline durante el año 2018:
*   `megaline_calls.csv`: Información sobre las llamadas (duración, fecha).
*   `megaline_internet.csv`: Información sobre el consumo de internet (MB usados por sesión).
*   `megaline_messages.csv`: Información sobre los mensajes de texto enviados.
*   `megaline_plans.csv`: Descripción de las tarifas de los planes "Surf" y "Ultimate".
*   `megaline_users.csv`: Datos demográficos de los clientes y el plan que utilizan.

## Pasos Clave del Análisis

1.  **Descripción y Preparación de los Datos:**
    *   Se realizó una exploración inicial de cada DataFrame para evaluar su estructura, tipos de datos y valores ausentes.
    *   Se corrigieron los nombres de las columnas para mayor consistencia.
    *   Se manejaron los valores ausentes (`NaN`), rellenándolos según el contexto (ej: `churn_date` con 'active').
    *   Se eliminaron filas duplicadas en todos los conjuntos de datos.
    *   Se convirtieron las columnas de fecha al formato `datetime` para facilitar su manejo y se creó una columna `month` para análisis mensual.

2.  **Agregación de Datos por Usuario:**
    *   Se calcularon métricas mensuales por usuario: número de llamadas, minutos totales hablados, número de mensajes y total de MB usados.
    *   Se fusionaron todos los datos de consumo con la información del usuario y las tarifas en un único DataFrame (`datos_usuarios`) para facilitar el análisis.

3.  **Cálculo de Ingresos Mensuales:**
    *   Se implementó la lógica de facturación de Megaline, que redondea la duración de las llamadas hacia arriba (por minuto) y el uso de internet hacia arriba (por GB).
    *   Se calculó el ingreso mensual para cada usuario sumando la cuota fija del plan y los cargos por exceder los límites de minutos, mensajes y datos.

4.  **Estudio del Comportamiento del Usuario:**
    *   Se analizó y visualizó el consumo mensual promedio de minutos, mensajes y GB de datos para ambos planes a lo largo del año.
    *   Se compararon las distribuciones de consumo mediante histogramas y diagramas de caja, y se calcularon estadísticas descriptivas (media, varianza).

5.  **Análisis de Ingresos:**
    *   Se compararon los ingresos mensuales generados por los usuarios de cada plan, tanto en promedios como en su distribución general.
    *   Se utilizaron diagramas de caja para visualizar la dispersión y los valores atípicos en los ingresos de cada plan.

6.  **Prueba de Hipótesis Estadísticas:**
    *   **Hipótesis 1:** Se utilizó una prueba t de Student para determinar si existía una diferencia significativa en el ingreso promedio entre los usuarios de los planes "Ultimate" y "Surf". La prueba confirmó que la diferencia es estadísticamente significativa.
    *   **Hipótesis 2:** Se realizó otra prueba t de Student para comparar el ingreso promedio de los usuarios del área NY-NJ contra el de otras regiones, encontrando también una diferencia significativa.

## Resultados y Conclusiones

*   **Comportamiento de Uso:** Aunque los promedios de consumo (minutos, mensajes, datos) son similares entre ambos planes, los usuarios de "Surf" presentan una **mayor variabilidad** y casos de consumo extremo, a diferencia de los usuarios de "Ultimate" que tienen un patrón de uso más estable.
*   **Rentabilidad de los Planes:** Se confirmó estadísticamente que los usuarios del plan **"Ultimate" generan un ingreso promedio significativamente mayor** para la empresa. Este resultado es clave para la estrategia comercial.
*   **Estrategia Recomendada:** Incentivar a los usuarios del plan "Surf", especialmente aquellos con patrones de alto consumo, a migrar al plan "Ultimate" podría ser una táctica efectiva para aumentar los ingresos totales de Megaline.

##  Cómo Ejecutar el Proyecto

Clona este repositorio :
(https://github.com/ferchi4/Proyecto_spring_5)
