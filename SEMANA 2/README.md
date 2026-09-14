# SEMANA 2 — Clasificación IDS con Machine Learning

**Asignatura:** Inteligencia Artificial (PUCE)  
**Tema:** Clasificación inteligente de eventos de seguridad (IDS)  
**Dataset:** Subconjunto académico de CICIDS2017  

## Objetivo

Entrenar y evaluar modelos de ML (árbol de decisión, Random Forest, SVM) para clasificación binaria de flujos de red (benigno vs. ataque), con análisis de falsos negativos por familia de ataque.

## Contenido

| Ruta | Descripción |
|------|-------------|
| `notebooks/01_clasificacion_ids_cicids2017.ipynb` | Notebook principal |
| `data/` | `CICIDS2017_train.csv` y `CICIDS2017_test.csv` |
| `results/` | Estadísticas y artefactos |
| `reports/` | Informe (PDF/DOCX) |
| `requirements.txt` | Dependencias |

## Ejecución rápida

Desde esta carpeta (`SEMANA 2/`):

```bash
pip install -r requirements.txt
jupyter notebook notebooks/01_clasificacion_ids_cicids2017.ipynb
```