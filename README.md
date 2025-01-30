# Mercado Libre Product Clustering

Este proyecto implementa un pipeline de agrupación de productos similares en el marketplace de Mercado Libre.
Utiliza texto, imágenes y precios para detectar productos idénticos vendidos por distintos sellers.

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