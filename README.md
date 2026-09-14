# Inteligencia Artificial · PUCE

**Estudiante:** Alejandro Carriel  
**Institución:** Pontificia Universidad Católica del Ecuador (PUCE)  
**Asignatura:** Inteligencia Artificial  
**Semestre:** 5.º  

---

## Sobre este repositorio

Portafolio académico del curso **Inteligencia Artificial**. El material se organiza por semanas (prácticas, notebooks y reportes).

## Estructura

| Carpeta | Contenido |
|---------|-----------|
| [`SEMANA 2/`](SEMANA%202/) | Clasificación inteligente de eventos de seguridad (IDS) con Machine Learning — CICIDS2017 |
| `SEMANA 1/`, `SEMANA 3/` … | Otras semanas (se irán agregando) |

### SEMANA 2 — Clasificación IDS (CICIDS2017)

Pipeline de ML para clasificación binaria (benigno vs. ataque) sobre un subconjunto académico de **CICIDS2017**, con énfasis en métricas relevantes para IDS (precision, recall, F1, ROC-AUC y análisis de falsos negativos).

Incluye:

- `notebooks/` — notebook principal de clasificación
- `data/` — CSV de entrenamiento y prueba
- `results/` — salidas intermedias
- `reports/` — informe de la semana
- `src/` — código auxiliar
- `requirements.txt` — dependencias Python

## Cómo empezar (SEMANA 2)

```bash
cd "SEMANA 2"
python -m venv .venv
# Windows:
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/01_clasificacion_ids_cicids2017.ipynb
```

Las rutas del notebook son relativas a `notebooks/` (`../data`, `../results`).

## Nota ética

Material destinado **exclusivamente a investigación educativa y defensiva** en detección de intrusiones. No debe usarse para actividades ofensivas, no autorizadas o maliciosas.

## Licencia

Véase [LICENSE](LICENSE). El dataset CICIDS2017 permanece sujeto a los términos de sus autores / CIC.