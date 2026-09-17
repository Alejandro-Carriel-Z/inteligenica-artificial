# Cambios y mejoras — Semana 3 vs Semanas 1 y 2

**Proyecto:** Inteligencia Artificial · PUCE  
**Autor:** Alejandro Carriel Zambrano  

## Enfoque de cada bloque

| Bloque | Tema | Técnicas |
|--------|------|----------|
| Semanas 1 y 2 | Clasificación supervisada IDS (CICIDS2017) | Árbol de decisión, Random Forest, SVM |
| Semana 3 | Detección de anomalías / alertas | **Isolation Forest** (no supervisado / semi-supervisado según diseño del lab) |

## Qué aporta Semana 3 respecto al trabajo anterior

1. **Cambio de paradigma:** de clasificación supervisada (etiquetas ataque/benigno) a **detección de anomalías** con Isolation Forest.
2. **Hiperparámetro clave `contamination`:** se evalúa cómo el porcentaje esperado de anomalías afecta precision, recall, F1 y el volumen de alertas.
3. **Trade-off operativo:** contamination baja → menos alertas y recall incompleto; contamination alta → más alertas y posible caída de precision (más falsos positivos).
4. **Evidencia reproducible:** CSV de comparación y resultados + notebook + PDF de tarea.

## Continuidad académica

- Semanas 1–2 construyen el pipeline de ML para IDS con modelos clásicos y métricas de clasificación.
- Semana 3 amplía el portafolio hacia **anomaly detection**, útil cuando las etiquetas son escasas o el objetivo es priorizar alertas.

## Cómo interpretar `comparacion_contamination.csv`

Columnas típicas: `contamination`, `precision`, `recall`, `f1_score`, `alertas_generadas`.  
Sirve para elegir un punto de operación (equilibrio entre detectar ataques y no saturar al analista).