# Desafio_Telecom_Parte_II
Desafio Telecom Parte II
# 📊 Telecom X – Parte 2  
## Predicción de Cancelación de Clientes (Churn)



## 🎯 Propósito del Proyecto

El objetivo principal de este análisis es **predecir la cancelación (churn) de clientes** utilizando técnicas de Machine Learning.

A partir de variables demográficas, contractuales y de consumo, se desarrollaron modelos predictivos capaces de identificar qué clientes tienen mayor probabilidad de cancelar el servicio, permitiendo a la empresa anticiparse y aplicar estrategias de retención.

---

## 📂 Estructura del Proyecto
```
TelecomX_Parte2/
│
├── img/
├── TelecomX_Modelado.ipynb
├── telecom_tratado.csv
└── README.md
```

---

## 🛠 Preparación de los Datos

### 1️⃣ Clasificación de Variables

- **Variables Numéricas**
  - `Tenure`
  - `ChargesMonthly`
  - `ChargesTotal`
  - `Churn` (variable objetivo)

- **Variables Categóricas**
  - `Contract`
  - `PaymentMethod`
  - `InternetService`
  - `OnlineSecurity`
  - `TechSupport`
  - Entre otras.

---

### 2️⃣ Codificación

Se aplicó **One-Hot Encoding** para transformar las variables categóricas en formato numérico.

Justificación:
- Los algoritmos de Machine Learning requieren datos numéricos.
- One-Hot evita introducir relaciones ordinales artificiales.

---

### 3️⃣ Normalización

Se utilizó **StandardScaler** únicamente para la Regresión Logística.

Justificación:
- Modelos como Regresión Logística y KNN son sensibles a la escala.
- La normalización evita que variables con mayor magnitud influyan desproporcionadamente en el modelo.
- Random Forest no requiere normalización porque no depende de distancias ni magnitudes.

---

### 4️⃣ Separación de Datos

Se dividió el dataset en:

- 70% Entrenamiento  
- 30% Prueba  

Utilizando `train_test_split` con `stratify=y` para mantener la proporción de churn en ambos conjuntos.

---

## 🔎 Análisis Exploratorio (EDA)

Durante el análisis se realizaron:
- Visualización de desbalance de clases.

![alt text](img/image-9.png)


- Matriz de correlación entre variables numéricas.

![alt text](img/descarga.png)
![alt text](img/image-2.png)


- Análisis dirigido:

![alt text](img/image-3.png)![alt text](img/image-4.png)



### 📈 Principales Insights

- Clientes con contrato **Month-to-Month** presentan mayor tasa de cancelación.
- Clientes con menor **Tenure** tienen mayor probabilidad de churn.
- El método de pago **Electronic Check** está asociado a mayor cancelación.
- Servicios adicionales como **TechSupport y OnlineSecurity** reducen la probabilidad de churn.

---

## 🤖 Modelos Implementados

Se entrenaron dos modelos principales:

### 1️⃣ Regresión Logística
- Requiere normalización.
- Permite interpretar coeficientes.
- Buen desempeño base.
![alt text](img/image-7.png)

### 2️⃣ Random Forest
- No requiere normalización.
- Captura relaciones no lineales.
- Mejor desempeño general en F1-score.
![alt text](img/image-8.png)
---

## 📊 Evaluación de Modelos

Se utilizaron las siguientes métricas:

- Exactitud (Accuracy)
- Precisión
- Recall
- F1-score
- Matriz de Confusión

![alt text](img/image-5.png)
![alt text](img/image-6.png)

### 🔍 Observaciones

- Random Forest mostró mejor capacidad predictiva general.
- No se detectó overfitting severo.
- Regresión Logística permitió mejor interpretabilidad.


---

## 🚀 Estrategias Propuestas

- Incentivar contratos a largo plazo.
- Promover métodos de pago automáticos.
- Implementar programas de fidelización temprana.
- Ofrecer paquetes con servicios de valor agregado.
- Aplicar el modelo predictivo para alertas tempranas de churn.

---

## ▶️ Cómo Ejecutar el Proyecto

### 1️⃣ Requisitos

Instalar las siguientes librerías:

```

pip install pandas numpy matplotlib seaborn scikit-learn

```

### 2️⃣ Ejecutar el Notebook

1. Colocar `telecom_tratado.csv` en el mismo directorio del notebook.
2. Abrir `TelecomX_Modelado.ipynb`.
3. Ejecutar las celdas en orden.

---

## 📌 Conclusión

Este proyecto integra análisis exploratorio, modelado predictivo y estrategias de negocio para abordar el problema de cancelación de clientes.

El modelo desarrollado permite identificar clientes en riesgo y proporciona información estratégica clave para mejorar la retención y reducir pérdidas.

### 🔰Del Proyecto
**Factores que mas influyen en la cancelación (de acuerdo a los modelos y analisis de correlación)**


| Variable                                                          | Observación                                                             |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Contract (Month-to-Month)**                                     | Clientes con contratos mensuales tienen mayor probabilidad de cancelar. |
| **PaymentMethod (Electronic Check)**                              | Clientes que pagan con cheque electrónico muestran tendencia a churn.   |
| **Tenure**                                                        | Menor tiempo como cliente → mayor probabilidad de cancelar.             |
| **ChargesMonthly**                                                | Facturación alta o irregular puede aumentar la cancelación.             |
| **Servicios opcionales (TechSupport, Streaming, OnlineSecurity)** | La ausencia de servicios de valor agregado incrementa churn.            |




---

📍 Proyecto desarrollado como parte del desafío **Telecom X – Machine Learning**.
