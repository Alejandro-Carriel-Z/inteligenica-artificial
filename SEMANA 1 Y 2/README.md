# Semana 1 y 2 — Clasificación IDS con Machine Learning

Material académico de **Inteligencia Artificial** (PUCE): clasificación inteligente de eventos de seguridad sobre **CICIDS2017** (etiqueta binaria).

## Contenido

- `notebooks/` — análisis y modelos (Árbol, Random Forest, SVM)
- `data/` — train/test CICIDS2017 (subconjunto de la tarea)
- `reports/` — informe en DOCX/PDF
- `results/` — estadísticas descriptivas
- `requirements.txt` — dependencias Python

## Cómo ejecutar

```bash
cd "SEMANA 1 Y 2"
python -m venv .venv
# Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/01_clasificacion_ids_cicids2017.ipynb
```
