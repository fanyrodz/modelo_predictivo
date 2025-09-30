# 📊 Modelo Predictivo

Este proyecto desarrolla un **modelo predictivo** utilizando datos de contratos, información personal, servicios de internet y telefonía. El objetivo es integrar y analizar los datos para entrenar modelos de Machine Learning capaces de predecir si un cliente continuará activo o no, generando información útil para estrategias de negocio.

---

## 📂 Archivos del proyecto

| Archivo | Descripción |
|---------|-------------|
| `modelo_predictivo.ipynb` | Notebook principal con el flujo completo: exploración, limpieza, ingeniería de características, entrenamiento de modelos y evaluación |
| `contract.csv` | Información de contratos |
| `personal.csv` | Datos personales de clientes |
| `internet.csv` | Detalles de servicios de internet |
| `phone.csv` | Detalles de servicios de telefonía |
| `README.md` | Documentación del proyecto |

---

## 🔄 Flujo de trabajo

1. **Unificación y exploración inicial**  
   - Cargar los 4 archivos (`contract.csv`, `personal.csv`, `internet.csv`, `phone.csv`) y unirlos por `customerID`.  
   - Verificar duplicados, registros sin correspondencia, tipos de datos y valores nulos.  

2. **Preprocesamiento**  
   - Limpiar valores nulos y ajustar tipos de datos.  
   - Convertir `EndDate` en variable binaria (1 = cancelado, 0 = activo).  
   - Codificar variables categóricas y escalar numéricas si el modelo lo requiere.  

3. **Feature Engineering**  
   - Calcular duración del contrato a partir de `BeginDate` y `EndDate`.  
   - Crear variables derivadas sobre servicios contratados (conteo total de servicios, combinaciones clave).  
   - Detectar y evitar *data leakage*.  

4. **Entrenamiento y validación de modelos**  
   - **Baseline**: Regresión Logística.  
   - **Modelos avanzados**: Random Forest, XGBoost, LightGBM.  
   - Ajuste de hiperparámetros.  
   - Validación con *stratified split* para mantener balance de clases.  

5. **Evaluación y conclusiones**  
   - Comparación de modelos según **AUC-ROC** (principal) y **Accuracy** (secundaria).  
   - Análisis de matriz de confusión y curvas ROC.  
   - Selección del mejor modelo y documentación de hallazgos para el equipo de negocio.  

---

## 📈 Resultados principales

- **Mejor modelo**: Random Forest con hiperparámetros ajustados.  
- **Rendimiento en conjunto de prueba**:  
  - AUC-ROC: **0.850**  
  - Accuracy: **0.791**  
- Buen equilibrio entre precisión y recall, especialmente en la clase de clientes cancelados.  

---

## 🛠️ Tecnologías utilizadas

- Python 3.x  
- pandas, numpy  
- scikit-learn  
- xgboost, lightgbm  
- matplotlib, seaborn  
- Jupyter Notebook  


