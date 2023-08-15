# Proyecto de Machine Learning (Soy Henry): [Criptomonedas]


## Descripción

  Este proyecto tiene como objetivo sugerir un listado de 10 criptomonedas para un grupo de inversores. La finalidad de esto es estrictamente pedagógica, por lo que no es una sugerencia real de inversión. 


### KPI's

Presentación: La presentación está compuesta por 10 pestañas, cada una corresponde al análisis de un criptoactivo. En cada una se observan 3 KPI's los cuales actúan EN CONJUNTO para un objetivo en común: Se compra dicho activo o no se compra, y en caso de realizar una compra, si es conveniente mantener dicha compra en el tiempo.

 -KPI 1: El objetivo de este indicador es detectar en un mismo gráfico de líneas, el cruce del precio con el de tres métricas: La media móvil, del promedio y moda históricos. La forma en que se deben cruzar debe ser de tal manera que el precio atraviese desde abajo hacia arriba a la media móvil, y además, este debe superar el precio y moda históricos. De ser así, esta sería una posible señal de compra. 

-KPI 2: La alta volatilidad puede significar que el precio tiene la capacidad de moverse significativamente en un corto período de tiempo. Por lo tanto, este indicador tiene como objetivo determinar si el criptoactivo se encuentra en un período de volatilidad baja, para reducir el riesgo de compra.
Para tal fin, se utilizan dos métricas en un mismo gráfico: La representación de la varianza histórica en función del tiempo, y el valor de su mediana histórica, de tal manera que, si su línea esté por debajo de la mediana histórica, se asume que no hay riesgo de compra. Se utilizó esta métrica ( tanto la estática como la dinámica ) dado que esta presenta mayor sensibilidad a los cambios del precio, por sus características matemáticas.

-KPI 3: El desvío estándar en este contexto, da una idea de la dispersión de los datos respecto al promedio del mismo. Sería deseable que este valor, a nivel mensual, se encuentre por debajo del desvío estándar anual para continuar con la operatoria. Por tal motivo, el objetivo de este kpi es el de dar un indicador de si se puede continuar o no con dicha operatoria. Para esto, se utiliza un gráfico que muestra dos métricas: desvío estándar a través del tiempo y media móvil del desvío estándar. Si dichos gráficos están cerca, y si el desvío estándar mensual se encuentra por debajo del desvío estándar correspondiente a el año de la compra, se puede continuar en la operatoria, de lo contrario, sería conveniente vender.

Desde como fueron planteadas, dichas métricas actúan de manera independiente una de la otra, pero se complementan entre sí con el objetivo de reducir los riesgos de la compra del inversor.

### Presentación del dashboard y conclusiones

### Desarrollo del análisis exploratorio y conclusiones

- Análisis exploratorio de los datos: Previo al desarrollo de los dashboards, hubo un proceso de filtrado de datos. Dado que la cantidad de estos era excesiva, se decidió hacer un primer filtro determinado por su capitalización, es decir, se consideraron los 10 criptoactivos con mayor capitalización que figuraban en la base de datos de la API, y esto aceleró el tiempo de recolección de los mismos. Otro aspecto importante del análisis exploratorio fue considerar el uso de medias móviles, que sirvieron para comprender mejor el comportamiento de las tendencias de dichos criptoactivos. Por último, se crearon gráficos de volúmen de compras para corroborar si actualmente había o no mucha demanda de compra, en comparación con los datos históricos.

- Conclusiones del análisis exploratorio: 

Se pudo observar que todos los criptoactivos filtrados actualmente se encuentran en un período bajo de volúmen de compras bajo en comparación con los datos históricos.

Se han detectado dos criptoactivos que no varían con el precio del tiempo. Se pudo constatar que estas criptomonedas están dentro de una categoría llamada "stable-coins", su característica es que están hechas con la intención de que su precio se mantenga igual el precio del dolar. 

Se pudo constatar también que la mayoría de los precios de los criptoactivos estaban fuertemente correlacionados. Sin embargo, es necasario aclarar que esto no es evidencia suficiente para concluir que todos los criptoactivos seleccionados tengan las mismas señales de compra y venta y optar por un grupo reducido de ellos.

- Respecto al uso de las medias móviles, se pudo detectar que existe un patrón que podría servir como métrica para utilizar en los dashboards, y consiste en ver los cruces de estas con el precio en un mismo gráfico podría sugerir la compra o venta del criptoactivo. Sin embargo, esto no es evidencia suficiente para determinar tal acción.

### Archivos

1. .
2. .
3. .
4. .
5. .
6. .
7. . 
