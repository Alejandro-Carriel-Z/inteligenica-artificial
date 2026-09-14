# Datos — CICIDS2017 (subconjunto académico)

## Archivos

| Archivo | Descripción |
|---------|-------------|
| `CICIDS2017_train.csv` | Conjunto de entrenamiento (flujos de red etiquetados) |
| `CICIDS2017_test.csv` | Conjunto de prueba |

## Etiqueta y columnas especiales

- **Objetivo:** `label_binary` (0 = benigno, 1 = ataque).
- **No usar como predictores:** `label_multiclass`, `attack_family`, `label_binary`, `source_file`.
- `attack_family` / `label_multiclass` pueden usarse solo para análisis de errores (p. ej. falsos negativos).

## Cómo colocar los archivos

Si clonas el repositorio sin datos, copia los CSV en esta carpeta (`data/`) con exactamente estos nombres:

```
data/CICIDS2017_train.csv
data/CICIDS2017_test.csv
```

El notebook en `notebooks/` carga los datos con rutas relativas: `Path("../data")`.

## Cita

Sharafaldin, I., Lashkari, A. H., & Ghorbani, A. A. (2018). *Toward Generating a New Intrusion Detection Dataset and Intrusion Traffic Characterization*. ICISSP.  
Canadian Institute for Cybersecurity — https://www.unb.ca/cic/datasets/ids-2017.html

Uso exclusivamente educativo y defensivo.
