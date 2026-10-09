# Predicción de Churn en Clientes de Telecomunicaciones

## 1. Descripción del proyecto

Este proyecto desarrolla un modelo de Machine Learning para predecir el abandono de clientes (*customer churn*) en una empresa de telecomunicaciones, utilizando el dataset Telco Customer Churn de Kaggle.

El objetivo es identificar patrones asociados al abandono y evaluar modelos predictivos que puedan contribuir al diseño de estrategias de retención de clientes.

## 2. Objetivo de negocio

Predecir qué clientes presentan mayor probabilidad de abandonar el servicio, con el fin de orientar acciones de retención, mejorar la experiencia del cliente y reducir potenciales pérdidas de ingresos.

Se trata de un problema de clasificación binaria cuya variable objetivo es `Churn`.

## 3. Dataset

- Fuente: Kaggle, Telco Customer Churn.
- Registros originales: 7.043.
- Variables originales: 21.
- Variable objetivo: `Churn` (`Yes` / `No`).
- Registros utilizados después de la limpieza: 7.032.

Se eliminaron 11 registros con valores faltantes en `TotalCharges`, luego de convertir esa variable a formato numérico.

## 4. Metodología

El proyecto incluye las siguientes etapas:

1. Análisis exploratorio de datos (EDA).
2. Limpieza y preprocesamiento.
3. Codificación de variables categóricas mediante OneHotEncoder.
4. Imputación de valores faltantes y escalado de variables numéricas.
5. División de los datos en entrenamiento y prueba, con estratificación.
6. Entrenamiento y comparación de modelos.
7. Optimización de hiperparámetros mediante GridSearchCV.
8. Evaluación con métricas de clasificación.
9. Interpretabilidad mediante SHAP.

## 5. Modelos evaluados

- Regresión Logística.
- Random Forest.
- XGBoost inicial.
- XGBoost optimizado mediante GridSearchCV.

La métrica ROC AUC se utilizó para comparar la capacidad de discriminación de los modelos. También se analizaron Accuracy, Precision, Recall, F1-score y matrices de confusión.

## 6. Resultados principales

La Regresión Logística obtuvo un Accuracy de aproximadamente 80,38 %, un ROC AUC de 0,8359 y un Recall de 0,57 para la clase de abandono.

XGBoost optimizado alcanzó un Accuracy de 79,67 %, un ROC AUC de 0,8388 y un Recall de 0,53 para la clase de abandono.

Los resultados muestran que la Regresión Logística mantiene un buen equilibrio entre las métricas evaluadas, mientras que XGBoost optimizado presenta un ROC AUC ligeramente superior en el conjunto de prueba.

## 7. Interpretabilidad con SHAP

Se utilizó SHAP para analizar la contribución de las variables a las predicciones de XGBoost.

Entre las variables con mayor importancia global se encuentran:

- Tipo de contrato mensual.
- Antigüedad del cliente (`tenure`).
- Cargos mensuales (`MonthlyCharges`).
- Ausencia de seguridad online.
- Ausencia de soporte técnico.

Estos resultados pueden ayudar a orientar futuras estrategias de retención. Las contribuciones del modelo no implican causalidad.

## 8. Tecnologías utilizadas

- Python.
- Google Colab.
- Pandas y NumPy.
- Matplotlib y Seaborn.
- Scikit-learn.
- XGBoost.
- SHAP.

## 9. Reproducción del proyecto

1. Abrir el notebook `.ipynb` publicado en este repositorio.
2. Abrirlo en Google Colab.
3. Ejecutar las celdas en orden.
4. Verificar la descarga del dataset de Kaggle y la disponibilidad de las librerías necesarias.
5. Ejecutar el entrenamiento, la evaluación y el análisis SHAP.

El notebook contiene el código, las visualizaciones y los resultados obtenidos durante el desarrollo.

## 10. Conclusiones

El análisis permitió identificar asociaciones entre el abandono y variables como el tipo de contrato, la antigüedad y los cargos mensuales.

Los modelos desarrollados constituyen una base para estudiar estrategias de retención basadas en datos. Antes de una implementación real, sería necesario evaluar umbrales de decisión, costos de errores de clasificación y resultados de acciones comerciales de retención.

---

Proyecto académico de Data Science II: Machine Learning para la Ciencia de Datos.
