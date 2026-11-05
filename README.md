# BERTopic Educativo: Think Tanks Chilenos

Material docente del curso **Modelado de tópicos con BERTopic: discurso experto de think tanks chilenos (2019–2024)**, Diploma de Postítulo en Inteligencia Artificial, Facultad de Ciencias Físicas y Matemáticas, Universidad de Chile.

## Contenido

- `bertopic_educativo_think_tanks.ipynb`: notebook principal, con explicaciones conceptuales y visualizaciones Plotly generadas en ejecución.
- `think_tanks_subset.parquet`: versión acotada del corpus (11.924 documentos, 2019–2024, sin universidades), expansión del corpus del artículo de González Hernando (2026), *Latin American Research Review*, https://doi.org/10.1017/lar.2026.10142.
- `requirements.txt`: dependencias.

## Estructura del notebook

1. Portada, objetivos de aprendizaje y contexto del corpus.
2. Ingesta, diccionario de variables y análisis descriptivo inicial.
3. Preprocesamiento: normalización, stopwords, chunking y límite de tokens.
4. BERTopic paso a paso: SBERT, UMAP, HDBSCAN, c-TF-IDF e integración.
5. Validación: Optuna, NLI, estabilidad entre semillas y top-N palabras.
6. Resultados: modelo base, modelo corregido, cinco visualizaciones interactivas (mapa semántico, heatmap tópico × think tank, evolución temporal, red de similitud y perfiles de diversidad) y un explorador de tópicos con serie de tiempo y tabla de publicaciones enlazadas.
7. Conclusiones y extensiones.

## Ejecución

1. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

2. Abre el notebook en Jupyter o JupyterLab y ejecuta las celdas en orden.

3. La primera ejecución descarga `paraphrase-multilingual-MiniLM-L12-v2` y calcula los embeddings (unos minutos en CPU). Se guardan en `think_tanks_subset_embeddings_384_v2.npy` y las ejecuciones posteriores los reutilizan.

4. El notebook ajusta dos modelos (base y corregido). La ejecución completa, incluyendo Optuna y el pipeline NLI, puede tardar entre 10 y 20 minutos en CPU. Las figuras usan Plotly y el explorador usa `ipywidgets`.

## Nota

El corpus debe estar en el mismo directorio que el notebook. No se incluyen imágenes estáticas: todas las figuras se computan al ejecutar las celdas. Si usas Google Colab, sube el `.parquet` y el notebook.
