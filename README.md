# Mercado Libre Product Clustering

Este proyecto implementa un pipeline de agrupación de productos similares en el marketplace de Mercado Libre.
Utiliza texto, imágenes y precios para detectar productos idénticos vendidos por distintos sellers.


La idea principal detrás de definir un producto similar como aquel que tiene el mismo título, imagen y precio es capturar las tres dimensiones clave que los usuarios consideran al comparar productos en un marketplace:

- Título (texto): El título del producto suele ser la primera información que ven los usuarios y les da una idea general del producto. Si dos productos tienen títulos muy similares, es probable que sean el mismo producto o al menos muy similares.

- Imagen: La imagen del producto es otro factor importante que los usuarios consideran. Si dos productos tienen la misma imagen, es muy probable que sean el mismo producto.

- Precio: El precio del producto es un indicador de su valor. Si dos productos tienen un precio similar, es más probable que sean el mismo producto.

Al combinar estas tres dimensiones, podemos identificar productos que son muy probablemente el mismo, incluso si están listados por diferentes vendedores o en diferentes categorías.

Si bien hay otras características que podrían considerarse, como las especificaciones técnicas o la marca, estas tres dimensiones (título, imagen y precio) son las más relevantes para la mayoría de los usuarios. Además, estas son las características que suelen estar disponibles para todos los productos en un marketplace.

## Cómo ejecutar el pipeline

### 1. Procesar datos para un país específico
```python
df_procesado = procesar_datos_pais(lista_paises_ml, pais_index=17)
```
Esto ejecuta todo el pipeline de preprocesamiento y clustering hasta la fase de exportación.

### 2. Guardar resultados en CSV
```python
guardar_csv_por_pais(df=df_procesado)
```
Esto genera un archivo CSV con los productos agrupados para su análisis posterior.

## Metodología
- **Texto:** TF-IDF + DBSCAN + BERT para similitud semántica.
- **Imágenes:** Embeddings con CLIP y similitud coseno.
- **Precios:** Segmentación por coeficiente de variación.
