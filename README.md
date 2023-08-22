# Proyecto de Data Analytics (Soy Henry): [Criptomonedas]

## Descripción

Este proyecto tiene como propósito sugerir un conjunto de 10 criptoactivos para un grupo de inversores. A través de la creación de tres KPIs, se buscará determinar si es un momento adecuado para realizar una compra. Es importante aclarar que esta iniciativa tiene un enfoque estrictamente pedagógico.

Para facilitar la comprensión del proyecto se introducen dos conceptos necesarios:

- **Capitalización:**

  El concepto de capitalización de mercado es una herramienta financiera empleada para medir el tamaño relativo de una criptomoneda, empresa u otro activo financiero en el mercado. En el contexto de las criptomonedas, este término se refiere al valor total de todas las unidades de una criptomoneda en circulación, multiplicado por su precio actual en el mercado. En forma más intuitiva, se podría decir que la capitalización de mercado refleja la valoración global de una criptomoneda en base a su precio y su cantidad de unidades en circulación.

  La fórmula para calcular la Capitalización de Mercado es la siguiente:

  Capitalización = Suma Total de Unidades en Circulación x Precio Actual.

- **Volumen:**

  En este contexto, el volumen representa cantidad total de activos (en este caso criptomonedas) que se han comprado o vendido en un período de tiempo determinado.

- **Media móvil:**

  La media móvil es un valor promedio calculado para un subconjunto de datos consecutivos en una serie temporal, donde el subconjunto "se desliza" a lo largo de la serie un paso a la vez, calculando el promedio en cada posición.

  Ejemplo:

  A continuación se detalla un ejemplo del uso de la media móvil para un conjunto de precios en dólares

  Día 1: 100 usd . No hay suficientes datos anteriores para calcular la media móvil.

  Día 2: (100 usd + 150 usd ) / 2 = 125 usd

  Día 3: (100 usd + 150 usd + 120 usd) / 3 = 123.33 usd

  Día 4: (150 usd + 120 usd + 180 usd) / 3 = 150 usd

  Día 5: (120 usd + 180 usd + 200 usd) / 3 = 166.67 usd

  Día 6: (180 usd + 200 usd + 160 usd) / 3 = 180 usd

  Día 7: (200 usd + 160 usd + 220 usd) / 3 = 193.33 usd

  En este ejemplo, la media móvil de 3 días ayuda a suavizar las fluctuaciones diarias y resalta la tendencia general en las ventas a lo largo de la semana. Cada valor de la media móvil es el promedio de los tres días anteriores, y el agrupamiento de tres días consecutivos se desplaza un día a la vez para calcular la media móvil en cada posición. 

  Se podría decir de forma intuitiva que la media móvil tiene la propiedad de "recordar" información, por lo que se consideró sumamente útil para el análisis de las tendencias de los criptoactivos en este proyecto.

## Resumen el trabajo realizado

En la etapa de análisis exploratorio se inició aplicando un filtro para identificar las 10 criptomonedas con la mayor capitalización desde el año 2017 hasta la fecha actual. Basándose en esta selección, se determinó cuáles de estas criptomonedas serían recomendables adquirir y para cuáles sería más aconsejable esperar antes de realizar una compra. Estas decisiones se respaldaron mediante la creación de tres KPIs, los cuales se utilizaron para evaluar conjuntamente la viabilidad de adquirir estos criptoactivos y, en caso de haber realizado una compra, si resulta conveniente mantener dicha posición.

### Archivos

1. **etl-eda**: se encuentra el desarrollo en código del etl y análisis exploratirio.
   
3. **top_10_ultim.csv**: archivo csv obtenido en la finalización del proceso de etl y eda.
   
5. **top_10**: archivo de la base de datos filtrada luego del eda, en power BI. Se mdificó el formato de las columnas numéricas, se intercambiaron "." por "," y se cambió la columna "timestamp" a formato fecha.
   
7. **Dashboard**: archivo en formato pbix, corresponde a la presentación hecha en power BI.

### Presentación en Power BI

La presentación consta de 10 pestañas, cada una dedicada al análisis de un criptoactivo en particular. Cada pestaña contiene tres indicadores clave de desempeño (KPIs) relacionados con ese criptoactivo.

### Explicación de las KPI's

- **KPI 1 - Indicador de Volatilidad:** 

  Este indicador evalúa la volatilidad del criptoactivo. La alta volatilidad puede significar que el precio tiene la capacidad de moverse significativamente en un corto período de tiempo. Por lo tanto, este indicador tiene como objetivo determinar si el criptoactivo se encuentra en un período de volatilidad baja, lo que podría reducir el riesgo de compra. Para tal fin, se utilizan tres métricas en un mismo gráfico: La representación de la varianza histórica en función del tiempo, y el valor de su mediana y media históricas. Si el valor de la varianza está por debajo de estas métricas, se asume que la volatilidad es relativamente baja y no hay un riesgo significativo de compra.

- **KPI 2 - Indicador de Entrada:**

  El objetivo de este indicador es detectar el momento adecuado para comprar. Para ello, se evalúa si el precio del criptoactivo cruza la media móvil desde abajo hacia arriba. Se considera tanto la temporalidad histórica como la anual. Las situaciones que se consideran para tomar una decisión de compra son:

  - En caso de que el precio se encuentre debajo de la media móvil con tendencia a atravesarlo y en temporalidad anual ya lo haya hecho, se considera una señal positiva y podría ser un momento para comprar.
  - Si el precio ha atravesado la media móvil desde abajo hacia arriba tanto en temporalidad histórica como anual, también se considera una señal positiva, aunque no tan fuerte como la primera. 
  - Si el precio no atraviesa la media móvil, no se recomienda comprar en ese momento.

- **KPI 3 - Indicador de Dispersión:**

  Este indicador utiliza el desvío estándar para evaluar la dispersión de los datos en relación con el promedio. Se espera que el desvío estándar anual esté por debajo del desvío estándar histórico para considerar la continuidad de la compra después de haberla realizado. Si el desvío estándar anual es menor que el histórico, esto sugiere que los datos están más cerca del promedio y, por lo tanto, la inversión podría mantenerse.

Las KPIs se desarrollan de manera independiente pero se complementan entre sí para reducir los riesgos en la elección de compra del inversor.

### Conclusiones desarrolladas con los indicadores:

- **Dogecoin:**

  - **KPI 1:** El indicador de volatilidad muestra que la varianza, tanto históricamente como en la temporalidad anual, está por debajo de su mediana y media históricas, lo que sugiere una volatilidad relativamente baja. 
  - **KPI 2:** En el gráfico de temporalidad histórica, el precio del Dogecoin ha atravesado la media móvil recientemente, pero aún está por debajo de su media y mediana históricas. En temporalidad anual, el precio ha atravesado la media móvil de abajo hacia arriba y está cerca del promedio anual. Se recomienda esperar para comprar.
  - **KPI 3:** El desvío estándar anual está por debajo del histórico. En caso de haber realizado una compra, podría mantenerse.

- **Cardano:**

  - **KPI 1:** El indicador de volatilidad muestra que la varianza está por debajo de los valores de la media y mediana históricas, lo que sugiere una volatilidad relativamente baja.
  - **KPI 2:** El precio no ha atravesado la media móvil ni en temporalidad histórica ni anual, y no ha superado los valores de mediana y promedio. Se recomienda esperar para comprar.
  - **KPI 3:** El desvío estándar anual está por debajo del histórico. Si se ha realizado una compra, podría mantenerse.

[... Repite el análisis para los otros criptoactivos ...]

### Lectura optativa: Desarrollo del análisis exploratorio

- **Análisis exploratorio de los datos:** Antes de desarrollar los dashboards, se realizó un proceso de filtrado para identificar las 10 criptomonedas con mayor capitalización desde 2017 hasta la fecha actual. Se consideraron las medias móviles para comprender mejor las tendencias. Además, se crearon gráficos de volumen de compras para evaluar la demanda actual en comparación con los datos históricos.

- **Conclusiones del análisis exploratorio:** Se observó que los criptoactivos filtrados actualmente tienen un volumen de compras bajo en comparación con los datos históricos. Se detectaron stablecoins que mantienen su precio estable en relación con el dólar. La correlación entre los precios de los criptoactivos fue notable. Sin embargo, esto no garantiza señales de compra y venta similares. Se observó que las medias móviles podrían indicar puntos de entrada, pero esto necesita más validación.

## Tecnología Utilizada

- ![Python Logo](https://www.python.org/static/community_logos/python-logo.png =50x)
- ![Power BI Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Power_bi_logo_black.svg/100px-Power_bi_logo_black.svg.png =50x)
- ![Colab Logo](https://colab.research.google.com/img/colab_favicon.ico =50x)

