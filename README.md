# Proyecto de Data Analytics (Soy Henry): [Criptomonedas]


## Descripción

Este proyecto tiene como propósito sugerir un conjunto de 10 criptoactivos para un grupo de inversores. A través de la creación de tres KPIs, se buscará determinar si es un momento adecuado para realizar una compra. Es importante aclarar que esta iniciativa tiene un enfoque estrictamente pedagógico.


Para facilitar la comprensión del proyecto se introducen dos conceptos necesarios:

- Capitalización:
  
El concepto de capitalización de mercado es una herramienta financiera empleada para medir el tamaño relativo de una criptomoneda, empresa u otro activo financiero en el mercado. En el contexto de las criptomonedas, este término se refiere al valor total de todas las unidades de una criptomoneda en circulación, multiplicado por su precio actual en el mercado.

de forma más intuitiva, se podría decir que la capitalización de mercado refleja la valoración global de una criptomoneda en base a su precio y su cantidad de unidades en circulación.

La fórmula para calcular la Capitalización de Mercado es la siguiente:

Capitalización = Suma Total de Unidades en Circulación x Precio Actual.

- Volumen:

En este contexto, el volumen representa cantidad total de activos (en este caso criptomonedas) que se han comprado o vendido en un período de tiempo determinado.

- Media móvil:

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

### Resumen el trabajo realizado

En la etapa de análisis exploratorio se inició aplicando un filtro para identificar las 10 criptomonedas con la mayor capitalización desde el año 2017 hasta la fecha actual. Basándose en esta selección, se determinó cuáles de estas criptomonedas serían recomendables adquirir y para cuáles sería más aconsejable esperar antes de realizar una compra. Estas decisiones se respaldaron mediante la creación de tres KPIs, los cuales se utilizaron para evaluar conjuntamente la viabilidad de adquirir estos criptoactivos y, en caso de haber realizado una compra, si resulta conveniente mantener dicha posición.

### Archivos

1. etl-eda: se encuentra el desarrollo en código del etl y análisis exploratirio.
   
3. top_10_ultim.csv: archivo csv obtenido en la finalización del proceso de etl y eda.
   
5. top_10 : archivo de la base de datos filtrada luego del eda, en power BI. Se mdificó el formato de las columnas numéricas, se intercambiaron "." por "," y se cambió la columna "timestamp" a formato fecha.
   
7. Dashboard: archivo en formato pbix, corresponde a la presentación hecha en power BI. 

### Presentación en Power BI

La presentación consta de 10 pestañas, cada una dedicada al análisis de un criptoactivo en particular. Cada pestaña contiene tres indicadores clave de desempeño (KPIs) relacionados con ese criptoactivo.


### Explicación de las KPI's

- KPI 1: La alta volatilidad puede significar que el precio tiene la capacidad de moverse significativamente en un corto período de tiempo. Por lo tanto, este indicador tiene como objetivo determinar si el criptoactivo se encuentra en un período de volatilidad baja, para reducir el riesgo de compra.
Para tal fin, se utilizan tres métricas en un mismo gráfico: La representación de la varianza histórica en función del tiempo, y el valor de su mediana y media históricas, de tal manera que, si su valor está por debajo de estas, se asume que la volatilidad es relativamente baja y no hay riesgo de compra, en caso contrario, se podría considerar riesgo leve o alto. El motivo por el cual se utilizó la varianza es porque presenta una gran sensibilidad a los cambios del precio, por sus características matemáticas.

- KPI 2: El objetivo de este indicador es detectar en un mismo gráfico de líneas el cruce del precio con el de tres métricas: La media móvil, el promedio y moda históricas.
Media móvil:
La forma en que se debe cruzar el precio con la media móvil, debe ser de tal manera que el precio la atraviese desde abajo hacia arriba. Por otro lado, se debe cumplir lo mismo en temporalidad anual actual. Es decir, en el lapso del inicio del año 2023 hasta el día 17 de agosto de 2023. A continuación se especifican los casos que se tendrán a consideración:

#### - En caso de que el precio se encuentre debajo de la media móvil con tendencia a atravesarlo y en temporalidad anual ya lo haya hecho, se considera una señal positiva. De ser así, esta sería una posible señal de compra.
#### - En el caso de que en temporalidad histórica, el precio haya atravesado a la media móvil desde abajo hacia arriba, y también lo haya hecho en temporalidad anual, también se considera una señal positiva, aunque no tan buena como la presentada en el caso anterior.
#### - Si el precio no atraviesa la media móvil, el indicador queda automáticamente descartado de momento.
  
- KPI 3: El desvío estándar en este contexto, da una idea de la dispersión de los datos respecto al promedio del mismo. Sería deseable que este valor, a nivel anual, se encuentre por debajo del desvío estándar histórico para continuar con la operatoria. Por tal motivo, el objetivo de este kpi es el de dar un seguimiento una vez realizada la compra, 

Desde como fueron planteadas, estas KPIs actúan de manera independiente una de la otra, pero se complementan entre sí con el objetivo de reducir los riesgos de la elección de compra del inversor.

### Presentación del dashboard
#### Términos utilizados:

###### Temporalidad histórica: Corresponde al período transcurrido desde el año 2017 hasta la actualidad.
###### Temporalidad anual: Corresponde al período transcurrido desde comienzos del año 2023 hasta la actualidad ( 17 de aosto de 2023 ).
###### Indicador de Volatilidad: Corresponde al KPI 1.
###### Indicador de Entrada: Corresponde al KPI 2.
###### Indicador de dispersión: Corresponde al KPI 3 ( si bien la varianza es también un inicador de dispersión, esta terminología se utiliza en este caso para referirse a esta KPI ).

### Conclusiones desarrolladas con los indicadores:

- Dogecoin:
  
KPI 1: El indicador de volatilidad muestra que la varianza, desde la temporalidad histórica, se encuentra por debajo de su mediana y media históricas, por lo que se concluye que la volatilidad es relativamente baja. En temporalidad anual correspondiente al período 2023, se puede apreciar que dicha tendencia continúa.

KPI 2: En el gráfico de temporalidad histórica se observa que el precio del dogecoin atravesó la media móvil recientemente, pero esta aún se encuentra debajo de su media y mediana histórica, por lo que aún no es señal de cómpra. Sin embargo, en temporalidad anual, el precio atravesó la media móvil de abajo hacia arriba, pasó el precio de 0,075 usd de la mediana anual, y está por llegar al promedio anual de 0,076 usd. Se concluye que es conveniente esperar un poco más para realizar la compra de este criptoactivo.

KPI 3: El desvío estándar anual se encuentra en un valor de 0,008797 usd, lo cual es inferior al valor anual de 0,01 usd. De realizarse la compra de este criptoactivo se podría mantener la operatoria. 

- Cardano:

KPI 1: El indicador de volatilidad muestra que el valor de la varianza está por debajo de los valores de la media y mediana histórica. Se puede afirmar que la volatilidad es relativamente baja.

KPI 2: El indicador histórico muestra que el precio ha superado el valor de 0,226 usd, pero aún no ha llegado a superar el precio de 0,451 usd. Por otro lado, se observa que el precio aún no ha atravesado la media móvil. También se observa que en el transcurso del año el precio no ha sobrepasado la media y mediana anual, por lo que se espera prudencia a la hora de realizar la compra.

KPI 3: El indicador anual muestra que el valor del desvío estándar es de 0,046 usd, por debajo del valor histórico de 0,587 usd. Se aconcluye que es posible mantener la operatoria en caso de haber realizado una compra.

- Ripple:
   
KPI 1: El indicador de volatilidad histórico y anual muestran que la varianza se encuentra sobre el valor 0,001. Se recomienda esperar a que baje un poco más la volatilidad.

KPI 2: El precio ya tocó y pasó la media móvil el 1 de Febrero de este año. Por otro lado, éste ya ha superado los valores de 0,0393 usd y 0,500 usd, valores de media y mediana histórica. En temporalidad anual sucede lo mismo, por lo que sería oportuno efectuar en este momento la compra.

KPI 3: El desvío estándar histórico está en el valor 0,346 usd, siendo el anual de 0,106 usd. Se aconcluye que es posible mantener la operatoria en caso de haber realizado una compra.

- Solana:
 
KPI 1: El indicador de volatilidad muestra una varianza inferior al valor de la mediana y del promedio, cuyos valores son de 11,28 y de 100,73 respectivamente. Se cumple el objetivo de esta KPI en temporalidad histórica y anual. Se asume entonces que la volatilidad es relativamente baja.

KPI 2: El precio se encuentra por encima de la media móvil histórica, y a su vez está por debajo de los valores de 30,42 usd y 49,74 usd, valores de la mediana y media histórica. Sin embargo, en temporalidad anual se han cumplido los objetivos de la KPI, por lo que se recomienda la compra del criptoactivo. 

KPI 3: El desvío estándar anual está muy por debajo del histórico. Se aconcluye que es posible mantener la operatoria en caso de haber realizado una compra.

- Binancecoin:
  
KPI 1: El indicador de volatilidad muestra que la varianza está por debajo de los valores históricos, y a su vez, en temporalidad anual, por debajo de los valores de la media y mediana ( debajo de 108,29 usd  y 232,58 usd ). Se cumple el objetivo de este KPI y se considera que la volatilidad es relativamente baja.

KPI 2: El indicador histórico muestra que, si bien el precio está por encima de los valores de 28,67 usd y de 158 usd correspondientes a la mediana y al promedio, aún este no atravesó la media móvil. En temporalidad anual, se observa que el precio no ha superado ninguno de las métricas, por lo que se recomienda esperar un poco más para concretar la operatoria de la compra.

KPI 3: El desvío estándar anual se encuentra en 34,84 usd muy por debajo del histórico que es de 177,98 usd. Se aconcluye que es posible mantener la operatoria en caso de haber realizado una compra.

- Staked-ether:
  
KPI 1: El indicador de volatilidad evidencia que la varianza está por debajo de los valores de 29.335,09 y de 51.347,92 que corresponden a los valores de la media y mediana históricas. Por otro lado, en temporalidad anual, se evidencia la misma característica, en este caso está por debajo de los valores de 4.329,78 y 7.671,53. Se cumple el objetivo del KPI y se considera que la varianza se encuentra relativamente baja.

KPI 2: El indicador de entrada para la compra muestra que tanto el precio, así como también la media móvil y el promedio y la mediana histórica se encuentran muy cercanos. En temporalidad anual se observa que el precio está por debajo de la media móvil, la tendencia se observa bajista, aunque aún no está por debajo de la media y mediana anual. Se recomienda no comprar aún.

KPI 3: El valor del desvío estándar anual es de 180 usd, el cual está por debajo del valor histórico de 1.120 usd. Se concluye con este indicador que de realizar compra, esta se puede mantener sin salir de la operatoria.

- Bitcoin:
  
KPI 1: El indicador de volatilidad muestra que el precio de la varianza se encuentra por debajo de los valores históricos de 97.1293,78 y 5.816.999,57 correspondientes a la media y mediana de la varianza. Esto también sucede en temporalidad anual. Se concluye que, según este indicador, la volatilidad es relativamente baja.

KPI 2: El indicador de entrada evidencia que el precio está por encima de los valores 11.630,12 usd y 20.092,37 usd correspondientes a la mediana y promedio histórico. Sin embargo el precio aún se encuentra por debajo de la media móvil. En temporalidad anual, el precio supera los valores de la mediana y el promedio anual, aunque aún no ha superado el valor de la media móvil anual. Se recomienda esperar un poco más para comprar.

KPI 3: El desvío estándar anual se encuentra en 3.670 usd, y su valor histórico es de 16.080 usd, por lo que se considera que de realizar una compra, esta se puede mantener. 

- Ethereum:

KPI 1: El indicador de volatilidad muestra que la varianza se encuentra por debajo de los valores históricos de media y mediana, cuyos valores son de 3198,19 y 30.235,28. En temporalidad anual esta tendencia se mantiene, la varianza está por debajo de los valores 4.439,51 y 7.453,11 correspondientes a la media y promedio anual. Se considera entonces, que la volatilidad es relativamente baja.

KPI 2: El indicador de entrada muestra que el precio se encuentra atravesando la media móvil hacia abajo, por lo que no se recomienda realizar compra por el momento.

KPI 3: El desvío estándar histórico es de 1.130 usd, y el anual de 180 usd, por lo que, en caso de realizar compra o haberlo hecho, esta se puede mantener.

- Tether:

KPI 1: El indicador de volatilidad muestra que actualmente la criptomoneda se encuentra estable, no es necesario utilizar más métricas teniendo en cuenta que ésta es una stable coin.

KPI 2: El indicador de entrada muestra que a nivel histórico la criptomoneda sufrió fuertes caídas, sin embargo esta no ha desaparecido y desde el año 2020 en adelante no ha sufrido caídas del precio, por lo que se recomienda comprar para los perfiles que quieren asumir menor riesgo. No se utilizaron medias ni medianas para esta cripomoneda por su característica de ser stablecoin.

KPI 3: El desvío estándar de este criptoactivo se encuentra en 0,07791 usd a nivel histórico. Su valor anual es de 0,00196 usd. En caso de realizar compra, esta posición se puede sostener.

- Usd-Coin: 

KPI 1: El índice de volatilidad para este criptoactivo se encuentra bajo. Sin embargo esta criptomoneda ha sufrido mucha volatilidad en temporalidad histórica. Se recomienda esperar un poco más y esperar que esta volatilidad baja se mantenga en el tiempo.

KPI 2: El indicador de entrada muestra que este criptoactivo ha sufrido muchos cambios en su precio, dado que este criptoactivo entra en la categoría de stable coin, no se recomienda de momento realizar una compra, sería aconsejable esperar a ver que este precio continúe con la tendencia actual hasta el año que viene por lo menos. No se han utilizado recursos de métricas del pki para esta criptomoneda.

KPI 3: El desvío estándar histórico de este criptoactivo se encuentra en un valor de 0,00313 usd, mientras que el anual es de 0,00258 usd. De realizar una compra, esta operación se puede mantener.

### Lectura optativa: Desarrollo del análisis exploratorio

- Análisis exploratorio de los datos: Previo al desarrollo de los dashboards, hubo un proceso de filtrado de datos. Dado que la cantidad de estos era excesiva, se decidió hacer un primer filtro determinado por su capitalización, es decir, se consideraron los 10 criptoactivos con mayor capitalización que figuraban en la base de datos de la API, y esto aceleró el tiempo de recolección de los mismos. Otro aspecto importante del análisis exploratorio fue considerar el uso de medias móviles, que sirvieron para comprender mejor el comportamiento de las tendencias de dichos criptoactivos. Por último, se crearon gráficos de volúmen de compras para corroborar si actualmente había o no mucha demanda de compra, en comparación con los datos históricos.

- Conclusiones del análisis exploratorio: 

Se pudo observar que todos los criptoactivos filtrados actualmente se encuentran en un período bajo de volúmen de compras bajo en comparación con los datos históricos.

Se han detectado dos criptoactivos que no varían con el precio del tiempo. Se pudo constatar que estas criptomonedas están dentro de una categoría llamada "stable-coins", su característica es que están hechas con la intención de que su precio se mantenga igual el precio del dolar. 

Se pudo constatar también que la mayoría de los precios de los criptoactivos estaban fuertemente correlacionados. Sin embargo, es necasario aclarar que esto no es evidencia suficiente para concluir que todos los criptoactivos seleccionados tengan las mismas señales de compra y venta y optar por un grupo reducido de ellos.

- Respecto al uso de las medias móviles, se pudo detectar que existe un patrón que podría servir como métrica para utilizar en los dashboards, y consiste en ver los cruces de estas con el precio en un mismo gráfico podría sugerir la compra o venta del criptoactivo. Sin embargo, esto no es evidencia suficiente para determinar tal acción.

## Tecnología Utilizada

![Python Logo](https://www.python.org/static/community_logos/python-logo.png)
![Power BI Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Power_bi_logo_black.svg/100px-Power_bi_logo_black.svg.png)
![Colab Logo]([https://jupyter.org/assets/main-logo.svg](https://colab.research.google.com/img/colab_favicon.ico)https://colab.research.google.com/img/colab_favicon.ico)


