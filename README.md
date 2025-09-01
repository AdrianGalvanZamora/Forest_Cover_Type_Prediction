# Predicción de Tipos de Cobertura Forestal

## Descripción del Proyecto
Este proyecto utiliza el **Forest Cover Type Dataset** del UCI Machine Learning Repository para predecir tipos de cobertura forestal basados en variables cartográficas como elevación, pendiente y tipos de suelo. El enfoque es ambiental y científico, ideal para empresas verdes, biotech o conservación de biodiversidad, ya que ayuda en el monitoreo forestal y toma de decisiones para sostenibilidad.

- **Dataset:** Forest Cover Type (581,012 instancias, 54 features, 7 clases de cobertura).
- **Fuente:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/31/covertype).
- **Herramientas:** Python con Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn y SciPy.
- **Objetivos:**
  - Realizar análisis exploratorio de datos (EDA) para entender distribuciones y correlaciones.
  - Limpiar y preparar datos (sin valores faltantes, escalado de variables cuantitativas).
  - Pruebas de hipótesis (ANOVA para elevación vs. tipos de cobertura).
  - Modelado de clasificación multi-clase con Random Forest.
  - Evaluación con métricas como accuracy (~88.9%), F1-score y matriz de confusión.
  - Visualizaciones: histogramas, boxplots, mapa de calor de correlaciones, importancia de variables.

Este proyecto demuestra habilidades en análisis de datos con enfoque biológico/ambiental, alineado con sectores como salud pública, biotech y empresas ecológicas.

## Requisitos
- Python 3.8+.
- Bibliotecas: Instala con `pip install pandas numpy matplotlib seaborn scikit-learn scipy`.
- Dataset: Descarga de [aquí](https://archive.ics.uci.edu/static/public/31/covertype.zip) y coloca `covtype.data` en la carpeta del notebook.

## Metodología
1. **Carga y Limpieza:** Dataset cargado sin headers, nombres asignados manualmente. Verificado: 581,012 instancias, 0 valores faltantes.
2. **EDA:**
   - Distribución del target: Clases 1 (36.46%) y 2 (48.76%) dominan ~85%, indicando desbalance.
   - Histogramas de variables cuantitativas (e.g., Slope sesgada).
   - Boxplots: Elevación varía significativamente entre clases.
   - Correlaciones: Altas entre Hillshade variables (e.g., Hillshade_9am y Hillshade_3pm: r=-0.78).
3. **Pruebas de Hipótesis:** ANOVA para Elevation vs. Cover_Type (F-statistic: 155,307, p-value: 0.00) rechaza H0, confirmando diferencias significativas.
4. **Preparación:** Split 80/20 con estratificación (X_train: 464,809; X_test: 116,203). Escalado de 10 variables cuantitativas.
5. **Modelado:** Random Forest (100 árboles, profundidad 20). Accuracy: 88.91%.
6. **Evaluación:** 
   - F1-scores: Clase 1 (0.88), Clase 2 (0.90), pero bajo en Clase 5 (0.56) debido a desbalance.
   - Importancia de variables: Elevation (0.289) lidera, seguido de distancias a carreteras y fuego.
7. **Visualizaciones:** Matriz de confusión, gráfico de importancia de features.

## Resultados Clave
- **Accuracy:** 88.91%.
- **Mejor rendimiento:** Clases mayoritarias (1: Spruce/Fir, 2: Lodgepole Pine).
- **Insights:** Elevación es el predictor principal, útil para estrategias de conservación en empresas verdes.
- **Limitaciones:** Desbalance afecta clases minoritarias (e.g., Clase 5: recall 0.39).

## Cómo Ejecutar
1. Descarga el dataset y coloca `covtype.data` en la carpeta.
2. Abre `Proyecto8_CoberturaForestal.ipynb` en Jupyter Notebook.
3. Ejecuta las celdas en orden.
4. Nota: El entrenamiento puede tomar ~5-10 minutos debido al tamaño del dataset.

## Mejoras Futuras
- Aplicar SMOTE para balancear clases minoritarias.
- Probar XGBoost o redes neuronales para mejorar F1-score en clases raras.
- Integrar datos geoespaciales para mapas interactivos.

## Licencia
MIT License. Cita el dataset original si usas este proyecto.

Autor: [Tu Nombre/Usuario de LinkedIn]  
Fecha: Septiembre 2024  
Enlace al repositorio: [Inserta enlace de GitHub aquí]
