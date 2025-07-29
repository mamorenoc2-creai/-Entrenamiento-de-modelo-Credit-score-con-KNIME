# 🔍 Credit Score Prediction Project - KNIME

Este proyecto utiliza la plataforma **KNIME** para desarrollar un modelo de predicción del **score crediticio** basado en el conjunto de datos *German Credit Data*. A diferencia de un flujo tradicional programado en Python, KNIME permite acelerar el desarrollo, visualizar fácilmente cada etapa del flujo, y exportar modelos reutilizables en otros entornos (como PMML o ONNX).

---

## 🧠 Objetivo

Construir un modelo de clasificación que permita identificar si un solicitante de crédito representa un **riesgo alto o bajo** para una entidad financiera, optimizando la toma de decisiones crediticias.

---

## 🛠️ Herramientas utilizadas

- [KNIME Analytics Platform](https://www.knime.com/knime-analytics-platform)  
- Conjunto de datos: *German Credit Data* (1000 registros, 20 atributos)
- Algoritmo principal: **Random Forest Classifier**
- Exportación del modelo: **PMML**

---

## ⚙️ Estructura del flujo en KNIME

1. **Importación de datos**  
   - Lectura del conjunto de datos desde archivo `.csv`.

2. **Preprocesamiento**
   - Conversión de variables categóricas codificadas (A11, A12...) mediante:
     - One Hot Encoding / Ordinal Encoding.
   - Revisión y tratamiento de valores nulos (si existen).

3. **Partición de datos**
   - 80% entrenamiento / 20% prueba
   - Sampling estratificado para mantener proporción de clases.

4. **Entrenamiento del modelo**
   - Modelo: `Random Forest Learner`
   - Parámetros clave:
     - Número de árboles: `100`
     - Criterio de partición: `Gini Index`
     - Profundidad máxima: sin límite (por defecto)
     - Random seed: `1234`

5. **Evaluación del modelo**
   - Métricas generadas:
     - Curva ROC y AUC
     - Precisión, Recall, F1-Score
     - Matriz de confusión

6. **Exportación del modelo**
   - Exportado en formato **PMML**
   - Prepara
