Análisis de Ventas y Datos de Tiendas
Este repositorio contiene un análisis de datos de ventas de diferentes tiendas basado en una serie de ejercicios realizados utilizando Python y la librería Pandas para el procesamiento de datos, junto con Matplotlib para la visualización.

Descripción
El análisis abarca cuatro tiendas diferentes, y se enfoca en realizar los siguientes pasos:

Cálculo de Ingreso Total por Tienda: Se calcula el ingreso total generado por cada tienda.

Cálculo del Costo de Envío Promedio por Tienda: Se obtiene el costo de envío promedio para cada tienda, lo que permite entender cuánto se gasta, en promedio, por tienda.

Análisis de Categorías de Productos Vendidos: Se determina la cantidad de productos vendidos por categoría en cada tienda.

Análisis de Calificaciones Promedio de Clientes: Se calcula la calificación promedio otorgada por los clientes en cada tienda, proporcionando una visión de la satisfacción general.

Identificación de los Productos Más y Menos Vendidos: Se analiza cuáles fueron los productos más y menos vendidos en cada tienda.

Visualización Gráfica de los Resultados: Se crean varios gráficos para presentar las conclusiones de los análisis de manera visual.

Requisitos
Python 3.x

Pandas

Matplotlib

Puedes instalar las dependencias utilizando pip:

bash
Copy
Edit
pip install pandas matplotlib
Datos
Los datos utilizados provienen de archivos CSV alojados en GitHub. Estos archivos contienen información sobre los productos vendidos en las tiendas, como el precio, la categoría, las calificaciones de los clientes, entre otros.

URLs de los datos:

Tienda 1

Tienda 2

Tienda 3

Tienda 4

Análisis Realizado
1. Ingreso Total por Tienda
Se calcula el ingreso total de cada tienda sumando el precio de todos los productos vendidos.

python
Copy
Edit
ingresos_tienda = {
    "Tienda 1": round(tienda["Precio"].sum(), 2),
    "Tienda 2": round(tienda2["Precio"].sum(), 2),
    "Tienda 3": round(tienda3["Precio"].sum(), 2),
    "Tienda 4": round(tienda4["Precio"].sum(), 2),
}
2. Costo de Envío Promedio por Tienda
Se calcula el costo de envío promedio por cada tienda, redondeado a pesos colombianos.

python
Copy
Edit
costo_envio_promedio = {
    "Tienda 1": round(tienda["Costo de envío"].mean(), 0),
    "Tienda 2": round(tienda2["Costo de envío"].mean(), 0),
    "Tienda 3": round(tienda3["Costo de envío"].mean(), 0),
    "Tienda 4": round(tienda4["Costo de envío"].mean(), 0),
}
3. Distribución de Categorías de Productos Vendidos
Se analiza la cantidad de productos vendidos por categoría en cada tienda, mostrando cuáles son las categorías más populares.

python
Copy
Edit
categorias_tienda1 = tienda["Categoría del Producto"].value_counts()
categorias_tienda2 = tienda2["Categoría del Producto"].value_counts()
categorias_tienda3 = tienda3["Categoría del Producto"].value_counts()
categorias_tienda4 = tienda4["Categoría del Producto"].value_counts()
4. Calificación Promedio de los Clientes por Tienda
Se calcula la calificación promedio de los clientes para cada tienda.

python
Copy
Edit
calificacion_promedio = {
    "Tienda 1": round(tienda["Calificación"].mean(), 2),
    "Tienda 2": round(tienda2["Calificación"].mean(), 2),
    "Tienda 3": round(tienda3["Calificación"].mean(), 2),
    "Tienda 4": round(tienda4["Calificación"].mean(), 2),
}
5. Productos Más y Menos Vendidos en Cada Tienda
Se identifican los productos más vendidos y menos vendidos en cada tienda.

python
Copy
Edit
productos_mas_vendidos_tienda1 = tienda.groupby("Producto")["Cantidad de cuotas"].sum().sort_values(ascending=False)
productos_menos_vendidos_tienda1 = tienda.groupby("Producto")["Cantidad de cuotas"].sum().sort_values(ascending=True)
6. Gráficos Generados
Gráfico de barras mostrando el Ingreso Total por Tienda.

Gráfico de barras mostrando la Distribución de Categorías de Productos más vendidas en Tienda 1.

Gráfico de dispersión mostrando la relación entre la Calificación Promedio de Clientes y los Ingresos Totales de las tiendas.

Cómo Ejecutar el Análisis
Clona este repositorio o descarga el archivo Python en tu máquina.

Instala las dependencias mencionadas en los requisitos.

Ejecuta el archivo Python para ver el análisis y los gráficos generados.

bash
Copy
Edit
python análisis_tiendas.py
