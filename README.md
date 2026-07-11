# 📊 Proyecto TelecomX – Parte 2: Predicción de Evasión de Clientes (Churn)

Este proyecto forma parte del reto de análisis avanzado de datos de TelecomX. Luego de haber destacado en la etapa de análisis exploratorio, ahora se busca construir modelos predictivos que anticipen qué clientes están en riesgo de cancelar sus servicios.

## 🧠 Objetivo

Desarrollar un pipeline robusto de machine learning que permita:
- Preparar los datos para modelado.
- Analizar correlaciones y seleccionar variables relevantes.
- Entrenar múltiples modelos de clasificación.
- Evaluar su rendimiento.
- Interpretar resultados y entregar insights estratégicos.

---

## 🔧 Etapas del Proyecto

### 1. Carga y Exploración de Datos
- Se cargó el archivo `TelecomX_Data.json` desde el entorno de Google Colab.
- Se aplicó `pd.json_normalize()` para aplanar estructuras anidadas.

### 2. Transformación de Variables
- Renombrado de columnas (`customer.` → `cust_`, `account.` → `acct_`, etc.).
- Conversión de columnas de texto (`Yes`/`No`) a binario (1/0).
- Transformación de `charges_Total` a tipo numérico.

### 3. Limpieza y Enriquecimiento
- Eliminación de columnas irrelevantes como `customerID`.
- Creación de la variable derivada `Cuentas_Diarias` (`charges_Monthly / 30`).

### 4. Codificación y Preparación
- Aplicación de `pd.get_dummies()` para codificar variables categóricas.
- Revisión de nulos y depuración final para modelado.

### 5. Balanceo de Clases (Opcional)
- Se aplicó SMOTE para balancear las clases y evitar sesgo hacia clase mayoritaria.

### 6. Normalización (Opcional)
- Se utilizó `StandardScaler` para estandarizar variables sensibles a escala (Regresión Logística, KNN).

---

## 📈 Análisis Exploratorio

### Distribución del Churn
- Aproximadamente el 26% de los clientes cancelan el servicio.
- Visualizaciones con gráficos de barras y pie chart.

### Segmentación por Variables Categóricas
- Contrato mensual → mayor churn.
- Método de pago “Electronic check” → mayor churn.
- Clientes sin pareja o mayores → mayor riesgo.

### Segmentación por Variables Numéricas
- Menor tenure, menor gasto total y mayor gasto mensual → mayor tendencia a cancelar.

### Correlaciones
- `cust_tenure` y `charges_Total` presentan correlación negativa con churn.
- `charges_Monthly` y `Cuentas_Diarias` correlacionan positivamente.

---

## 🤖 Modelos Construidos

### 1. Regresión Logística (con normalización)
- Mejores resultados en precisión.
- Interpretación mediante coeficientes.

### 2. Random Forest (sin normalización)
- F1-score superior.
- Menor riesgo de overfitting.
- Análisis de importancia de variables por impureza.

---

## 🧮 Evaluación de Modelos

Se aplicaron las siguientes métricas:
- Accuracy
- Precision
- Recall
- F1-Score
- Matriz de Confusión

### Comparación
- **Random Forest** obtuvo el mejor equilibrio entre recall y F1-score.
- **Regresión Logística** útil por su interpretabilidad, aunque menos eficaz para recall.

---

## 🧠 Variables Más Relevantes

- `acct_Contract` → tipo de contrato.
- `cust_tenure` → antigüedad del cliente.
- `charges_Total` → gasto total acumulado.
- `acct_PaymentMethod` → método de pago.
- `Total_Servicios` → cantidad de servicios contratados.

---

## 📝 Conclusiones Estratégicas

- Clientes nuevos con contrato mensual y bajo gasto total tienen mayor riesgo de churn.
- El método de pago “Electronic check” es una señal de riesgo.
- Retener clientes nuevos y aumentar la cantidad de servicios contratados mejora la permanencia.
  
### 💡 Recomendaciones
- Programa de retención para contratos mensuales.
- Incentivar métodos de pago automáticos.
- Alertas tempranas basadas en comportamiento.
- Beneficios escalonados por número de servicios contratados.

---

## 🚀 Tecnologías Utilizadas

- Python 3.11
- Google Colab
- Pandas, NumPy, Seaborn, Matplotlib
- Scikit-learn, Imbalanced-learn (SMOTE)

---

## 📂 Estructura del Repositorio

TelecomX_Parte2/ │ ├── TelecomX_Data.json # Archivo de entrada tratado ├── TelecomX_Modelos.ipynb # Notebook completo con el pipeline └── README.md # Documento de resumen del proyecto


---

## 🎓 Autor

**Cesar Constantino**  
Analista Junior de Machine Learning en TelecomX  
Apasionado por el análisis de datos, automatización y estrategia de retención

---



> Actualización de prueba para practicar flujo de PR con n8n.

## Dashboard desarrolladores MxXSKwAW
Actualizacion para ejercicio de Pull Request.

PR ejercicio MxXSKwAW v2
