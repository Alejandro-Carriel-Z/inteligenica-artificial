# Clasificación inteligente de eventos de seguridad (IDS) con Machine Learning — Semana 2

**Autor:** Alejandro Carriel · PUCE · Ingeniería / Ciberseguridad · 5.º semestre  
**Asignatura:** Inteligencia Artificial  
**Institución:** Pontificia Universidad Católica del Ecuador (PUCE)

---

## Objetivo

Desarrollar y evaluar un pipeline de aprendizaje automático para la **clasificación binaria** de flujos de red (benigno vs. ataque) sobre un subconjunto académico del conjunto de datos **CICIDS2017**, con énfasis en métricas relevantes para un sistema de detección de intrusiones (IDS), en particular el análisis de **falsos negativos**.

## Conjunto de datos

Se utiliza un subconjunto de **CICIDS2017** (Canadian Institute for Cybersecurity) con etiqueta binaria:

| Archivo | Descripción |
|---------|-------------|
| `data/CICIDS2017_train.csv` | Conjunto de entrenamiento |
| `data/CICIDS2017_test.csv` | Conjunto de prueba |

- **Etiqueta objetivo:** `label_binary` (0 = benigno, 1 = ataque).
- **Columnas prohibidas como predictores** (no se usan en el entrenamiento):
  - `label_multiclass`
  - `attack_family`
  - `label_binary`
  - `source_file`

Las columnas `attack_family` y `label_multiclass` se emplean únicamente en el análisis posterior de falsos negativos, no como características del modelo.

## Metodología

1. Carga de datos de entrenamiento y prueba.
2. Análisis exploratorio de la distribución de `label_binary`.
3. Exclusión de columnas prohibidas y definición de predictores.
4. Estadísticas descriptivas y control de nulos, infinitos y duplicados.
5. Entrenamiento de tres modelos (solo sobre el conjunto de entrenamiento).
6. Evaluación en test: matriz de confusión, precision, recall, F1, ROC-AUC y curvas ROC.
7. Análisis de falsos negativos por `attack_family` / `label_multiclass`.

## Modelos

| Modelo | Configuración principal |
|--------|-------------------------|
| **Árbol de decisión** | `max_depth=12`, `min_samples_leaf=5`, `class_weight="balanced"`, `random_state=42` |
| **Random Forest** | `n_estimators=100`, `max_depth=18`, `min_samples_leaf=3`, `max_features="sqrt"`, `class_weight="balanced"`, `random_state=42` |
| **SVM (RBF)** | Pipeline con `StandardScaler` + `SVC(kernel="rbf", C=1.0, gamma="scale", class_weight="balanced", probability=True, random_state=42)` |

## Métricas de evaluación

Enfoque en métricas orientadas a IDS (clase positiva = ataque = 1):

- **Precision / Recall / F1**
- **ROC-AUC** y curvas ROC comparativas
- **Matriz de confusión** (TN, FP, FN, TP)
- **Análisis de FN:** un falso negativo es un ataque clasificado como benigno; en un IDS es el error más crítico

La *accuracy* se reporta solo como referencia y **no** debe usarse de forma aislada.

## Cómo ejecutar

Requisitos: Python 3.10+ recomendado.

```bash
# Crear y activar entorno virtual (Windows)
python -m venv .venv
.venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt

# Abrir el notebook
jupyter notebook notebooks/01_clasificacion_ids_cicids2017.ipynb
```

En Linux/macOS:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/01_clasificacion_ids_cicids2017.ipynb
```

Los datos deben estar en `data/` (ya incluidos en este repositorio académico). Las rutas del notebook son relativas a la carpeta `notebooks/` (`../data`, `../results`).

## Estructura del repositorio

```
semana2-clasificacion-ids/
├── README.md
├── INSTRUCCIONES_GITHUB.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── 01_clasificacion_ids_cicids2017.ipynb
├── data/
│   ├── README.md
│   ├── CICIDS2017_train.csv
│   └── CICIDS2017_test.csv
├── results/
│   └── estadisticas_descriptivas_train.csv
├── reports/
│   ├── Informe_Semana2_Clasificacion_IDS.pdf
│   └── Informe_Semana2_Clasificacion_IDS.docx
└── src/
    └── .gitkeep
```

## Nota ética

Este material se destina **exclusivamente a investigación educativa y defensiva** en detección de intrusiones. No debe utilizarse para actividades ofensivas, no autorizadas o maliciosas.

## Cita del conjunto de datos (CICIDS2017)

> Sharafaldin, I., Lashkari, A. H., & Ghorbani, A. A. (2018). *Toward Generating a New Intrusion Detection Dataset and Intrusion Traffic Characterization*. Proceedings of the 4th International Conference on Information Systems Security and Privacy (ICISSP).  
> Canadian Institute for Cybersecurity (CIC), University of New Brunswick.  
> Dataset: https://www.unb.ca/cic/datasets/ids-2017.html

## Licencia

Véase el archivo [LICENSE](LICENSE). El código y materiales académicos de este repositorio se publican bajo una licencia permisiva; el conjunto CICIDS2017 permanece sujeto a los términos de sus autores / CIC.
