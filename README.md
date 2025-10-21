# 🌲 Predicción de Tipos de Cobertura Forestal  
[English version below ⬇️]  

**Sector:** Medio Ambiente, Biotecnología, Sostenibilidad  
**Herramientas:** Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy)  

---

## 📋 Descripción General  
Este proyecto utiliza el dataset *Forest Cover Type* del **UCI Machine Learning Repository** para **predecir tipos de cobertura forestal** basados en variables cartográficas como elevación, pendiente, tipo de suelo y distancia a carreteras o fuentes de agua.  

El objetivo es **mejorar el monitoreo ambiental y la toma de decisiones en conservación forestal**, apoyando estrategias de sostenibilidad y gestión territorial en empresas ecológicas y organizaciones ambientales.  

---

## 📊 Dataset  
- **Fuente:** [UCI Machine Learning Repository – Forest Cover Type Dataset](https://archive.ics.uci.edu/ml/datasets/Covertype)  
- **Tamaño:** 581,012 instancias, 54 características, 7 clases  
- **Archivo:** `covtype.data`  

---

## 🔍 Metodología  
1. **Carga y Limpieza de Datos**  
   - Dataset cargado sin encabezados; se asignaron nombres manualmente.  
   - Verificación de 0 valores faltantes.  

2. **Análisis Exploratorio (EDA)**  
   - Las clases 1 y 2 representan el 85% del total, indicando desbalance.  
   - Histogramas muestran sesgo en *Slope* y otras variables cuantitativas.  
   - Boxplots revelan diferencias significativas de elevación entre tipos de cobertura.  
   - Correlaciones altas entre variables de sombreado (p. ej. *Hillshade_9am* y *Hillshade_3pm*: r = -0.78).  

3. **Pruebas de Hipótesis**  
   - ANOVA entre *Elevation* y *Cover_Type*: F = 155,307, p ≈ 0.00 → diferencias significativas entre grupos.  

4. **Preparación y Modelado**  
   - Split 80/20 (train/test) con estratificación.  
   - Escalado de 10 variables cuantitativas.  
   - Modelo: *Random Forest Classifier* (100 árboles, profundidad = 20).  

5. **Evaluación del Modelo**  
   - Accuracy: **88.91%**  
   - F1-scores: Clase 1 (0.88), Clase 2 (0.90), Clase 5 (0.56).  
   - Variable más importante: **Elevation (importancia = 0.289)**.  

6. **Visualizaciones Clave**  
   - Matriz de confusión.  
   - Gráfico de importancia de variables.  

---

## 🌎 Principales Hallazgos  
- **Elevación** es el factor más relevante para clasificar tipos de bosque.  
- Clases dominantes (Spruce/Fir y Lodgepole Pine) muestran alto rendimiento (>88% F1).  
- Las variables de distancia a carreteras y fuego también contribuyen significativamente.  

---

## 🧠 Aplicaciones en el Mundo Real  
- Modelos predictivos para monitoreo de biodiversidad.  
- Optimización de zonas de conservación.  
- Integración con sistemas GIS para análisis geoespacial y mapas interactivos.  

---

## ⚙️ Requisitos de Ejecución  
- Python 3.8+  
- Librerías: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`  
- Archivo: `covtype.data`  

Instalación rápida:
- pip install pandas numpy matplotlib seaborn scikit-learn scipy


---

## 🚀 Cómo Ejecutar  
1. Descarga el dataset y colócalo en la carpeta del notebook.  
2. Abre `Prediccion_cobertura_forestal.ipynb` en Jupyter Notebook.  
3. Ejecuta las celdas en orden (tiempo de entrenamiento: ~5–10 min).  

---

## 🔧 Mejoras Futuras  
- Aplicar **SMOTE** para balancear clases minoritarias.  
- Probar **XGBoost** o **redes neuronales** para mejorar el rendimiento.  
- Integrar datos geoespaciales para visualizaciones interactivas.  

---

## 👤 Autor  
**Adrián Galván**  
**Fecha:** Septiembre 2025  

---

# 🌲 Forest Cover Type Prediction  

**Sector:** Environmental Science, Biotechnology, Sustainability  
**Tools:** Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy)  

---

## 📋 Overview  
This project uses the *Forest Cover Type* dataset from the **UCI Machine Learning Repository** to **predict forest cover types** based on cartographic variables such as elevation, slope, soil type, and distances to roads or water sources.  

The goal is to **enhance environmental monitoring and conservation decision-making**, supporting sustainability initiatives and biodiversity management.  

---

## 📊 Dataset  
- **Source:** [UCI Machine Learning Repository – Forest Cover Type Dataset](https://archive.ics.uci.edu/ml/datasets/Covertype)  
- **Size:** 581,012 instances, 54 features, 7 classes  
- **File:** `covtype.data`  

---

## 🔍 Methodology  
1. **Data Cleaning**  
   - Dataset loaded without headers; feature names assigned manually.  
   - Confirmed 0 missing values.  

2. **Exploratory Data Analysis (EDA)**  
   - Classes 1 and 2 dominate (~85% total), showing class imbalance.  
   - Skewed distributions in *Slope* and other numeric features.  
   - Boxplots show significant elevation differences across classes.  
   - Strong correlations among hillshade variables (*Hillshade_9am* vs *Hillshade_3pm*: r = -0.78).  

3. **Hypothesis Testing**  
   - ANOVA for *Elevation* vs *Cover_Type*: F = 155,307, p ≈ 0.00 → significant differences confirmed.  

4. **Modeling**  
   - 80/20 stratified split (train/test).  
   - Scaled numeric variables.  
   - Model: *Random Forest Classifier* (100 trees, depth = 20).  

5. **Model Evaluation**  
   - Accuracy: **88.91%**  
   - F1-scores: Class 1 (0.88), Class 2 (0.90), Class 5 (0.56).  
   - Top predictor: **Elevation (importance = 0.289)**.  

6. **Visualizations**  
   - Confusion matrix.  
   - Feature importance chart.  

---

## 🌎 Key Findings  
- **Elevation** is the strongest predictor of forest cover type.  
- Major classes (Spruce/Fir and Lodgepole Pine) achieve high F1-scores (>88%).  
- Road and fire distance features also contribute meaningfully.  

---

## 🧠 Real-World Applications  
- Predictive tools for forest and biodiversity management.  
- Conservation planning and land-use optimization.  
- Integration with **GIS platforms** for geospatial analysis and mapping.  

---

## ⚙️ Execution Requirements  
- Python 3.8+  
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`  
- File: `covtype.data`  

Quick install:
- pip install pandas numpy matplotlib seaborn scikit-learn scipy


---

## 🚀 How to Run  
1. Download the dataset and place it in the project directory.  
2. Open `Prediccion_cobertura_forestal.ipynb` in Jupyter Notebook.  
3. Run all cells sequentially (training time: ~5–10 min).  

---

## 🔧 Future Improvements  
- Apply **SMOTE** to handle class imbalance.  
- Experiment with **XGBoost** or **neural networks** to boost performance.  
- Integrate **geospatial data** for interactive map visualizations.  

---

## 👤 Author  
**Adrián Galván**  
**Date:** September 2025  
