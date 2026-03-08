# Telecom-X-Parte-2

# Predicción de Abandono de Clientes (Churn) - Telecom X

## Descripción del Proyecto
Este proyecto de Machine Learning tiene como objetivo predecir la tasa de cancelación (Churn) de los clientes de la empresa Telecom X. A través del análisis exploratorio, la ingeniería de características y el modelado predictivo, se identificaron los patrones de comportamiento que derivan en el abandono del servicio, permitiendo a la empresa tomar decisiones proactivas para la retención de usuarios.

## Tecnologías Utilizadas
* **Lenguaje:** Python
* **Manipulación y Análisis de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Logistic Regression, Random Forest, GridSearchCV)
* **Manejo de Datos Desbalanceados:** Imbalanced-Learn (SMOTE)
* **Entorno de Desarrollo:** Google Colab / Jupyter Notebook

## Fases del Proyecto

### 1. Preprocesamiento e Ingeniería de Variables
Se partió de un dataset previamente tratado. Se realizó la codificación de variables categóricas mediante One-Hot Encoding y mapeo binario. Las variables numéricas continuas fueron estandarizadas utilizando `StandardScaler` para optimizar el rendimiento de los modelos basados en distancia.

### 2. Balanceo de Datos
Al detectar un fuerte desbalanceo en la clase objetivo (solo un 25.7% de abandono), se implementó la técnica de sobremuestreo sintético **SMOTE** sobre el conjunto de entrenamiento, logrando una distribución 50/50 sin generar fuga de datos (Data Leakage) hacia el conjunto de prueba.

### 3. Entrenamiento y Evaluación de Modelos
Se entrenaron y compararon dos modelos de clasificación:
* **Regresión Logística:** Seleccionado por su interpretabilidad y alta capacidad de generalización.
* **Random Forest:** Utilizado para evaluar interacciones complejas, aunque requirió control de sobreajuste.

### 4. Optimización de Hiperparámetros (Tuning)
Se utilizó `GridSearchCV` con validación cruzada (5-folds) para encontrar los hiperparámetros óptimos de ambos modelos, priorizando la métrica **F1-Score** y el **Recall** para maximizar la detección de clientes en riesgo.

### 5. Conclusiones Estratégicas y Feature Importance
El análisis de los coeficientes del modelo ganador (Regresión Logística) reveló que:
* La **permanencia** (antigüedad del cliente) es el principal factor de retención.
* Los **contratos mensuales** y los **altos cargos mensuales** son los principales impulsores de la cancelación.
* Se propusieron estrategias de negocio accionables, como programas de fidelización temprana e incentivos de migración contractual.

## Cómo ejecutar este proyecto

1. Clonar el repositorio:
`git clone [URL_DE_TU_REPOSITORIO]`

2. Instalar las dependencias necesarias:
`pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn`

3. Ejecutar el notebook `Telecom_X_2.ipynb` en un entorno como Jupyter o Google Colab, asegurándose de tener el dataset en el directorio correspondiente.
