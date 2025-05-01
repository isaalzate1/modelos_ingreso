
# Clasificación de Ingresos a partir de Datos Sociodemográficos

## 🎯 Objetivo del proyecto

El objetivo de este proyecto es construir modelos de clasificación supervisada que permitan predecir el ingreso (`Income`) de una persona a partir de un conjunto de características sociodemográficas. Se utilizan tres enfoques: K-Nearest Neighbors (KNN), RMS y Árbol de Decisión. Este análisis busca no solo evaluar el desempeño predictivo de los modelos, sino también interpretar sus limitaciones frente a un conjunto de datos.

---

## 📋 Descripción de los datos

La base de datos incluye las siguientes variables:

- `Sex`: Codificado como 0 (Femenino) y 1 (Masculino)
- `Age`: Edad
- `Marital status`: Estado civil
- `Education`: Nivel educativo
- `Occupation`: Tipo de ocupación
- `Settlement size`: Tamaño del lugar de residencia
- `Income`: Variable objetivo, ingreso reportado
---

## 🧪 Modelos aplicados

Se entrenaron y evaluaron los siguientes modelos:

### 1. K-Nearest Neighbors (KNN)
- Accuracy (test): 60.6%
- Validación cruzada (media): 57.3%
- AUC macro: 0.387
- Observaciones:
  - Mejor rendimiento entre los tres modelos.

### 2. RMS
- Accuracy (test): 59.6%
- Validación cruzada (media): 57.5%
- AUC macro: 0.375
- Observaciones:
  - Se comportó de forma competitiva respecto a KNN, aunque su capacidad de generalización es ligeramente inferior.

### 3. Árbol de Decisión
- Accuracy (test): 59.2%
- Validación cruzada (media): 56.7%
- AUC macro: 0.388
- Observaciones:
  - Aunque su AUC fue la más alta, su exactitud general fue la más baja.
---

## 📉 Análisis de desempeño

- La variable `Income` tiene **1982 clases distintas** con muy pocas observaciones por clase (algunas con 1 solo registro).
- Esto impide que los modelos generalicen adecuadamente y provoca un fuerte desbalance de clases.
- Las matrices de confusión muestran muchos errores de clasificación en clases poco representadas.
- Las correlaciones entre predicción y realidad son bajas, lo que refuerza la dificultad del problema.

---

## 📌 Conclusiones

1. **Dificultad del problema**: predecir ingresos exactos a partir de características sociales básicas es un problema complejo, especialmente con alta cardinalidad y desbalance.
2. **Importancia de redefinir el problema**:
   - Sería más útil convertir el ingreso en rangos o percentiles.
   - Esto permitiría una clasificación más razonable (por ejemplo: bajo, medio, alto).
3. **Recomendaciones futuras**:
   - Aplicar reducción de clases.
   - Analizar la variable `Income` como regresión en lugar de clasificación.

---

## 📊 Visualizaciones

Se incluyeron:
- Gráficas de distribución para variables como estado civil.
- Matrices de confusión para cada modelo.
- Comparación de AUC y Accuracy entre modelos.