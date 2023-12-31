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

## Análisis de posibles operaciones de compra con los indicadores:

### Dogecoin:

**KPI 1:** El indicador de volatilidad muestra que la varianza, desde la temporalidad histórica, se encuentra por debajo de su mediana y media históricas, por lo que se concluye que la volatilidad es relativamente baja. En temporalidad anual correspondiente al período 2023, se puede apreciar que dicha tendencia continúa.

**KPI 2:** En el gráfico de temporalidad histórica se observa que el precio del dogecoin atravesó la media móvil recientemente, pero esta aún se encuentra debajo de su media y mediana histórica, por lo que aún no es señal de compra. Sin embargo, en temporalidad anual, el precio atravesó la media móvil de abajo hacia arriba, pasó el precio de 0,075 USD de la mediana anual y está por llegar al promedio anual de 0,076 USD. Se concluye que es conveniente esperar un poco más para realizar la compra de este criptoactivo.

**KPI 3:** El desvío estándar anual se encuentra en un valor de 0,008797 USD, lo cual es inferior al valor anual de 0,01 USD. De realizarse la compra de este criptoactivo se podría mantener la operatoria.

### Cardano:

**KPI 1:** El indicador de volatilidad muestra que el valor de la varianza está por debajo de los valores de la media y mediana histórica. Se puede afirmar que la volatilidad es relativamente baja.

**KPI 2:** El indicador histórico muestra que el precio ha superado el valor de 0,226 USD, pero aún no ha llegado a superar el precio de 0,451 USD. Por otro lado, se observa que el precio aún no ha atravesado la media móvil. También se observa que en el transcurso del año el precio no ha sobrepasado la media y mediana anual, por lo que se espera prudencia a la hora de realizar la compra.

**KPI 3:** El indicador anual muestra que el valor del desvío estándar es de 0,046 USD, por debajo del valor histórico de 0,587 USD. Se concluye que es posible mantener la operatoria en caso de haber realizado una compra.

### Ripple:

**KPI 1:** El indicador de volatilidad histórico y anual muestran que la varianza se encuentra sobre el valor 0,001. Se recomienda esperar a que baje un poco más la volatilidad.

**KPI 2:** El precio ya tocó y pasó la media móvil el 1 de Febrero de este año. Por otro lado, éste ya ha superado los valores de 0,0393 USD y 0,500 USD, valores de media y mediana histórica. En temporalidad anual sucede lo mismo, por lo que sería oportuno efectuar en este momento la compra.

**KPI 3:** El desvío estándar histórico está en el valor 0,346 USD, siendo el anual de 0,106 USD. Se concluye que es posible mantener la operatoria en caso de haber realizado una compra.

### Solana:

**KPI 1:** El indicador de volatilidad muestra una varianza inferior al valor de la mediana y del promedio, cuyos valores son de 11,28 y de 100,73 respectivamente. Se cumple el objetivo de esta KPI en temporalidad histórica y anual. Se asume entonces que la volatilidad es relativamente baja.

**KPI 2:** El precio se encuentra por encima de la media móvil histórica, y a su vez está por debajo de los valores de 30,42 USD y 49,74 USD, valores de la mediana y media histórica. Sin embargo, en temporalidad anual se han cumplido los objetivos de la KPI, por lo que se recomienda la compra del criptoactivo.

**KPI 3:** El desvío estándar anual está muy por debajo del histórico. Se concluye que es posible mantener la operatoria en caso de haber realizado una compra.

### Binancecoin:

**KPI 1:** El indicador de volatilidad muestra que la varianza está por debajo de los valores históricos, y a su vez, en temporalidad anual, por debajo de los valores de la media y mediana (debajo de 108,29 USD y 232,58 USD). Se cumple el objetivo de este KPI y se considera que la volatilidad es relativamente baja.

**KPI 2:** El indicador histórico muestra que, si bien el precio está por encima de los valores de 28,67 USD y de 158 USD correspondientes a la mediana y al promedio, aún este no atravesó la media móvil. En temporalidad anual, se observa que el precio no ha superado ninguno de las métricas, por lo que se recomienda esperar un poco más para concretar la operatoria de la compra.

**KPI 3:** El desvío estándar anual se encuentra en 34,84 USD muy por debajo del histórico que es de 177,98 USD. Se concluye que es posible mantener la operatoria en caso de haber realizado una compra.

### Staked-ether:

**KPI 1:** El indicador de volatilidad evidencia que la varianza está por debajo de los valores de 29.335,09 y 51.347,92 que corresponden a los valores de la media y mediana históricas. Por otro lado, en temporalidad anual, se evidencia la misma característica, en este caso está por debajo de los valores de 4.329,78 y 7.671,53. Se cumple el objetivo del KPI y se considera que la varianza se encuentra relativamente baja.

**KPI 2:** El indicador de entrada para la compra muestra que tanto el precio, así como también la media móvil y el promedio y la mediana histórica se encuentran muy cercanos. En temporalidad anual se observa que el precio está por debajo de la media móvil, la tendencia se observa bajista, aunque aún no está por debajo de la media y mediana anual. Se recomienda no comprar aún.

**KPI 3:** El valor del desvío estándar anual es de 180 USD, el cual está por debajo del valor histórico de 1.120 USD. Se concluye con este indicador que de realizar compra, esta se puede mantener sin salir de la operatoria.

### Bitcoin:

**KPI 1:** El indicador de volatilidad muestra que el precio de la varianza se encuentra por debajo de los valores históricos de 97.1293,78 y 5.816.999,57 correspondientes a la media y mediana de la varianza. Esto también sucede en temporalidad anual. Se concluye que, según este indicador, la volatilidad es relativamente baja.

**KPI 2:** El indicador de entrada evidencia que el precio está por encima de los valores 11.630,12 USD y 20.092,37 USD correspondientes a la mediana y promedio histórico. Sin embargo el precio aún se encuentra por debajo de la media móvil. En temporalidad anual, el precio supera los valores de la mediana y el promedio anual, aunque aún no ha superado el valor de la media móvil anual. Se recomienda no realizar una compra en este momento, y esperar a ver si el precio supera la media movil en temporalidad anual.

**KPI 3:** El desvío estándar anual se encuentra en 3.670 USD, y su valor histórico es de 16.080 USD, por lo que se considera que de realizar una compra, esta se puede mantener.

### Ethereum:

**KPI 1:** El indicador de volatilidad muestra que la varianza se encuentra por debajo de los valores históricos de media y mediana, cuyos valores son de 3198,19 y 30.235,28. En temporalidad anual esta tendencia se mantiene, la varianza está por debajo de los valores 4.439,51 y 7.453,11 correspondientes a la media y promedio anual. Se considera entonces, que la volatilidad es relativamente baja.

**KPI 2:** El indicador de entrada muestra que el precio se encuentra atravesando la media móvil hacia abajo, por lo que no se recomienda realizar compra por el momento.

**KPI 3:** El desvío estándar histórico es de 1.130 USD, y el anual de 180 USD, por lo que, en caso de realizar compra o haberlo hecho, esta se puede mantener.

### Tether:

**KPI 1:** El indicador de volatilidad muestra que actualmente la criptomoneda se encuentra estable, no es necesario utilizar más métricas teniendo en cuenta que ésta es una stable coin.

**KPI 2:** El indicador de entrada muestra que a nivel histórico la criptomoneda sufrió fuertes caídas, sin embargo esta no ha desaparecido y desde el año 2020 en adelante no ha sufrido caídas del precio, por lo que se recomienda comprar para los perfiles que quieren asumir menor riesgo. No se utilizaron medias ni medianas para esta criptomoneda por su característica de ser stablecoin.

**KPI 3:** El desvío estándar de este criptoactivo se encuentra en 0,07791 USD a nivel histórico. Su valor anual es de 0,00196 USD. En caso de realizar compra, esta posición se puede sostener.

### Usd-Coin: 

**KPI 1:** El índice de volatilidad para este criptoactivo se encuentra bajo. Sin embargo esta criptomoneda ha sufrido mucha volatilidad en temporalidad histórica. Se recomienda esperar un poco más y esperar que esta volatilidad baja se mantenga en el tiempo.

**KPI 2:** El indicador de entrada muestra que este criptoactivo ha sufrido muchos cambios en su precio, dado que este criptoactivo entra en la categoría de stable coin, no se recomienda de momento realizar una compra, sería aconsejable esperar a ver que este precio continúe con la tendencia actual hasta el año que viene por lo menos. No se han utilizado recursos de métricas del pki para esta criptomoneda.

**KPI 3:** El desvío estándar histórico de este criptoactivo se encuentra en un valor de 0,00313 USD, mientras que el anual es de 0,00258 USD. De realizar una compra, esta operación se puede mantener.

### Lectura optativa: Desarrollo del análisis exploratorio

- **Análisis exploratorio de los datos:** Antes de desarrollar los dashboards, se realizó un proceso de filtrado para identificar las 10 criptomonedas con mayor capitalización desde 2017 hasta la fecha actual. Se consideraron las medias móviles para comprender mejor las tendencias. Además, se crearon gráficos de volumen de compras para evaluar la demanda actual en comparación con los datos históricos.

- **Conclusiones del análisis exploratorio:** Se observó que los criptoactivos filtrados actualmente tienen un volumen de compras bajo en comparación con los datos históricos. Se detectaron stablecoins que mantienen su precio estable en relación con el dólar. La correlación entre los precios de los criptoactivos fue notable. Sin embargo, esto no garantiza señales de compra y venta similares. Se observó que las medias móviles podrían indicar puntos de entrada, pero esto necesita más validación.

## Tecnología Utilizada

- <img src="https://www.python.org/static/community_logos/python-logo.png" alt="Python Logo" width="50"/>
- <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Power_bi_logo_black.svg/100px-Power_bi_logo_black.svg.png" alt="Power BI Logo" width="50"/>
- <img src="https://colab.research.google.com/img/colab_favicon.ico" alt="Colab Logo" width="50"/>

