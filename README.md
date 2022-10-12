# Basic SALES data analysis.

## **Resumen**

- Se limpiaron los datos de la respectiva base de datos.
- Se realizó un análisis exploratorio.
- Se estimaron las ventas esperadas para el próximo periodo (siguiente año), de manera global y por territorio.
- Se estudio el comportamiento de las ventas por territorio y línea de producto.
- Se creo un modelo logístico para estimar la probabilidad de que un pedido fuera cancelado.

## **Recursos**

* Base de datos de ventas: "sales_data_sample.csv"


## **Ventas globales**

**Ventas globales (2004-2005):**

- imagen de la serie de tiempo global

Se ajusto un modelo **SARIMA(0,0,0)(0,1,0)[12]** con lo que se pudo estimar las ventas del próximo año.

Nota: Todos los supuestos del modelo se cumplieron, excepto el supuesto de Normalidad pero aún así se tomo como un modelo aceptable.

**Predicciones:**

- imagen de la serie de tiempo global con su forecast


## **Ventas por territorios**

### **EMEA**

**Ventas (2004-2005):**

- imagen de la serie de tiempo emea

**Predicciones:**

- imagen de la serie de tiempo emea con su forecast

### **NorthAmerica**

**Ventas (2004-2005):**

- imagen de la serie de tiempo northamerica

**Predicciones:**

- imagen de la serie de tiempo emea con su northamerica

**Nota:** Para los territorios de **Asia** y **Australia** no se tienen suficientes datos para ajustar un modelo SARIMA aceptable.

## **Línea de Producto por territorios: EMEA, NorthAmerica, Australia & Asia**

- imagen 1
- imagen 2
- imagen 3
- imagen 4

Un primer análisis que podríamos hacer, es destacar la gran cantidad de **autos clásicos** que se venden en todos los respectivos territorios. Además, 
las ventas relativas en Asia de los **camiones y autobuses** quedan en segundo lugar. Lo cúal podría indicar el alto desarrollo industrial que esa
zona tenía enntre los años 2004-2005, y que hoy en día aún tiene.


## **Modelo logístico**

Dentro de la variables **STATUS** existe un valor llamado **CANCELLED** lo que nos indica si un pedido fue cancelado. Por lo que en un intento de reducir costos, se
creo un modelo para predecir cuando es más probable que esto suceda. 

El modelo esta en: **logisticModel.py** 

La probabilidad de predecir correctamente si va a exitir
una cancelación del pedido es del 100%. Claramente existe overfitting, pero dados los pocos casos (60 observaciones) en los cuáles los pedidos fueron cancelados en esta base
de datos. Entonces podemos considerar a este modelo como acepatable.