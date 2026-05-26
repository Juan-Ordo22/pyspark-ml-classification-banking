# PySpark ML Classification — Banking Dataset
### Taller de Clasificación con Apache Spark MLlib y Hadoop HDFS

---

## Descripción

Este repositorio contiene el desarrollo de un taller académico de **Machine Learning supervisado aplicado a un dataset bancario**, implementado íntegramente sobre el ecosistema de Big Data: **Apache Spark (PySpark)**, **Spark MLlib** y **Hadoop HDFS**.

El objetivo principal es construir, evaluar y comparar múltiples modelos de clasificación binaria para predecir un comportamiento bancario, siguiendo un flujo de trabajo completo que abarca desde la ingesta de datos en HDFS hasta la comparación final de métricas entre modelos.

---

## Estructura del repositorio

```
pyspark-ml-classification-banking/
│
├── TallerOrdonezClasification.ipynb   # Cuaderno principal desarrollado
└── README.md
```

---

## Contenido del cuaderno principal

El cuaderno sigue un flujo de trabajo estructurado en 11 secciones:

| # | Sección | Descripción |
|---|---------|-------------|
| 1 | Importación de Bibliotecas y Sesión Spark | Configuración del entorno PySpark y carga de librerías |
| 2 | Hadoop HDFS: carga de ficheros | Ingesta del dataset bancario desde HDFS |
| 3 | Descripción y análisis del Dataset | Exploración inicial, estadísticas descriptivas y visualizaciones |
| 4 | Verificación de la calidad de los Datos | Detección de nulos, duplicados e inconsistencias |
| 5 | Preparación de los Datos | Selección de variables y estructuración del dataset |
| 6 | Limpieza de los Datos | Tratamiento de valores faltantes y atípicos |
| 7 | Formato de los Datos | Conversión y estandarización de tipos de datos |
| 8 | Codificación y Vector Assembler | Encoding de variables categóricas y ensamblado de features |
| 9 | Modelización | Entrenamiento de 5 modelos de clasificación |
| 10 | Evaluación de los Modelos | Métricas individuales y tabla comparativa final |
| 11 | Conclusiones | Análisis de resultados y recomendaciones |

---

## Modelos de clasificación implementados

Todos los modelos fueron construidos utilizando **Spark MLlib** (`pyspark.ml.classification`):

- Logistic Regression
- Random Forest Classifier
- Decision Tree Classifier
- Gradient Boosted Tree (GBT)
- Support Vector Machine (SVM — LinearSVC)

La división del dataset utilizada es **80% entrenamiento / 20% prueba** (`randomSplit`).

---

## Métricas de evaluación

Cada modelo fue evaluado con las siguientes métricas, usando
`pyspark.mllib.evaluation.MulticlassMetrics` y `pyspark.ml.evaluation.BinaryClassificationEvaluator`:

| Métrica | Descripción |
|---------|-------------|
| Confusion Matrix | Tabla de verdaderos/falsos positivos y negativos |
| Accuracy | Proporción de predicciones correctas sobre el total |
| Precision | Proporción de verdaderos positivos sobre los predichos positivos |
| Recall | Proporción de verdaderos positivos sobre los positivos reales |
| F1-score | Media armónica entre Precision y Recall |
| AUC-ROC | Área bajo la curva ROC — capacidad discriminativa del modelo |

Los resultados se consolidan en una tabla comparativa final con visualización gráfica.

---

## Tecnologías utilizadas

| Tecnología | Uso |
|------------|-----|
| Python 3.x | Lenguaje de programación base |
| Apache Spark / PySpark | Procesamiento distribuido de datos |
| Spark MLlib | Implementación de modelos de Machine Learning |
| Hadoop HDFS | Almacenamiento y carga distribuida del dataset |
| Jupyter Notebook | Entorno de desarrollo interactivo |
| Matplotlib / Seaborn | Visualizaciones y gráficas exploratorias |
| Pandas | Consolidación de métricas comparativas |

---

## Requisitos y ejecución

### Prerrequisitos

- Apache Spark 3.x con PySpark
- Hadoop configurado con HDFS activo
- Python 3.8+
- Jupyter Notebook o JupyterLab

### Ejecución

```bash
jupyter notebook TallerOrdonezClasification.ipynb
```

> Asegúrate de que la sesión Spark esté correctamente configurada
> y que el dataset bancario esté disponible en la ruta HDFS indicada
> en la sección 2 del cuaderno.

---

## Dataset

El dataset utilizado corresponde a datos bancarios cargados desde **Hadoop HDFS**.
Contiene variables demográficas, financieras y de comportamiento del cliente,
con una variable objetivo binaria de clasificación.

---

## Autor

**Juan David Ordoñez**
Materia: Procesamiento de Alto Volúmenes de Datos
Pontificia Universidad Javeriana

---

## Licencia

Repositorio de uso académico. Todos los derechos reservados al autor.
