Proyecto de Data Analytics: Criptomonedas (Soy Henry)
Descripción
Este proyecto tiene como propósito sugerir un conjunto de 10 criptoactivos para un grupo de inversores. Se crearon tres KPIs para determinar si es un momento adecuado para comprar. Este proyecto tiene un enfoque pedagógico.

Conceptos Clave
Capitalización: Medida del tamaño relativo de una criptomoneda en el mercado basada en su valor total en circulación.

Volumen: Cantidad total de activos (criptomonedas) comprados o vendidos en un período de tiempo.

Media Móvil: Valor promedio calculado para un subconjunto de datos consecutivos en una serie temporal.

Resumen del Trabajo
Análisis Exploratorio: Filtrado de las 10 criptomonedas con mayor capitalización desde 2017. Creación de KPIs para evaluar su compra.

Archivos:

etl-eda: Código para ETL y análisis exploratorio.
top_10_ultim.csv: CSV resultante del ETL y EDA.
top_10: Base de datos filtrada en Power BI.
Dashboard.pbix: Presentación en Power BI.
Presentación en Power BI: 10 pestañas, cada una con KPIs para un criptoactivo específico.

Explicación de los KPIs
KPI 1 - Volatilidad: Evalúa si el criptoactivo tiene volatilidad baja. Utiliza la varianza histórica y comparación con mediana y media.

KPI 2 - Entrada: Detecta si el precio cruza la media móvil desde abajo hacia arriba. Evalúa temporalidad histórica y anual.

KPI 3 - Dispersión: Mide dispersión de datos respecto al promedio. Compara desvío estándar anual con histórico.

Conclusiones de los KPIs
Dogecoin: Volatilidad baja, posible compra en temporalidad anual.
Cardano: Volatilidad baja, precaución en la compra.
Ripple: Alta volatilidad, esperar.
Solana: Volatilidad baja, compra sugerida en temporalidad anual.
Binancecoin: Volatilidad baja, esperar.
Staked-ether: Volatilidad baja, precaución en la compra.
Bitcoin: Volatilidad baja, esperar.
Ethereum: Volatilidad baja, no es momento de compra.
Tether: Volatilidad estable (stablecoin), esperar.
Usd-Coin: Volatilidad estable (stablecoin), precaución en la compra.
Tecnología Utilizada
Python Logo
Power BI Logo
Colab Logo


