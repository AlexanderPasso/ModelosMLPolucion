# ModelosMLPolucion

# 🌫️ Predicción de Polución con Machine Learning

Proyecto de **Machine Learning aplicado a la predicción de niveles de contaminación atmosférica**, utilizando modelos de **XGBoost** y **LSTM (Long Short-Term Memory)**.

El objetivo es analizar el comportamiento histórico de la concentración de **PM2.5** y desarrollar modelos capaces de predecir sus valores a partir de variables meteorológicas y temporales.

---

## 📌 Descripción del proyecto

La contaminación atmosférica presenta un comportamiento dinámico influenciado por diferentes factores ambientales y meteorológicos.

En este proyecto se implementan dos enfoques de Machine Learning para predecir la concentración de **PM2.5**:

- **XGBoost:** modelo de Gradient Boosting basado en árboles de decisión.
- **LSTM:** red neuronal recurrente especializada en el procesamiento de datos secuenciales y series temporales.

La comparación permite analizar el comportamiento de un modelo de Machine Learning basado en árboles frente a un modelo de Deep Learning diseñado para capturar dependencias temporales.

---

## 📊 Dataset

El conjunto de datos contiene registros históricos de contaminación atmosférica y variables meteorológicas.

La variable objetivo utilizada en el proyecto es:

**PM2.5:** concentración de material particulado con diámetro inferior a 2.5 micrómetros.

### Variables utilizadas

| Variable | Descripción |
|---|---|
| `pm2.5` | Concentración de PM2.5 |
| `DEWP` | Punto de rocío |
| `TEMP` | Temperatura |
| `PRES` | Presión atmosférica |
| `cbwd` | Dirección combinada del viento |
| `Iws` | Velocidad acumulada del viento |
| `Is` | Horas acumuladas de nieve |
| `Ir` | Horas acumuladas de lluvia |

El conjunto de datos contiene aproximadamente **41.733 registros**.

---

## 🔎 Análisis exploratorio

Antes del entrenamiento de los modelos se realizó un proceso de exploración y preparación de los datos que incluyó:

- Análisis de valores faltantes.
- Análisis estadístico de las variables.
- Análisis de correlaciones.
- Visualización de la distribución de PM2.5.
- Análisis del comportamiento temporal de la contaminación.
- Transformación de variables categóricas.
- Preparación de las variables para los modelos.

---

# 🤖 Modelos implementados

## 1. XGBoost

Se implementó **XGBoost Regressor**, un algoritmo de Gradient Boosting basado en árboles de decisión.

El modelo permite capturar relaciones no lineales entre las variables de entrada y la concentración de PM2.5.

### Ventajas de XGBoost

- Buen desempeño en problemas de regresión.
- Capacidad para modelar relaciones no lineales.
- Entrenamiento eficiente.
- Permite trabajar con diferentes tipos de variables.
- Permite analizar la importancia de las características.

---

## 2. LSTM

Se implementó una arquitectura basada en **Long Short-Term Memory (LSTM)**.

Las redes LSTM pertenecen a la familia de redes neuronales recurrentes y están diseñadas para trabajar con datos secuenciales, permitiendo aprender relaciones temporales presentes en una serie de datos.

Para este proyecto, los datos históricos fueron organizados en **secuencias temporales**, permitiendo utilizar información de períodos anteriores para realizar las predicciones.

### Arquitectura utilizada

La configuración final del modelo LSTM fue:

- Primera capa LSTM: **64 unidades**
- Segunda capa LSTM: **32 unidades**
- Ventana temporal: **168 pasos**
- Épocas de entrenamiento: **5**

La ventana temporal de **168 pasos** corresponde aproximadamente a una semana de información horaria.

---

# 📏 Métricas de evaluación

Para evaluar el desempeño de los modelos se utilizaron las siguientes métricas:

### MAE — Mean Absolute Error

Representa el error absoluto promedio entre los valores reales y las predicciones.

Un valor menor indica un menor error promedio.

### MSE — Mean Squared Error

Calcula el promedio de los errores al cuadrado, dando mayor importancia a los errores grandes.

### RMSE — Root Mean Squared Error

Es la raíz cuadrada del MSE y permite interpretar el error aproximadamente en las mismas unidades de la variable objetivo.

### R² — Coeficiente de determinación

Indica la proporción de la variabilidad de la variable objetivo que puede ser explicada por el modelo.

---

# 📈 Resultados

Los resultados obtenidos sobre el conjunto de evaluación fueron:

| Modelo | MAE | RMSE | R² |
|---|---:|---:|---:|
| **XGBoost** | **10.5411** | **17.8105** | **0.9493** |
| **LSTM** | 11.77 | 18.35 | 0.9463 |

### XGBoost

```text
MAE  : 10.5411
RMSE : 17.8105
R²   : 0.9493
```

# ⚙️ Tecnologías utilizadas
```
Python
Pandas
NumPy
Matplotlib
Scikit-learn
XGBoost
Jupyter 
Notebook
```


# 📂Estructura del proyecto
```
ModelosMLPolucion/
│
├── data/
│   └── Dataset de contaminación
│
├── notebooks/
│   ├── Exploracion_Datos.ipynb
│   ├── XGBoost.ipynb
│   └── LSTM.ipynb
│
├── README.md
```
