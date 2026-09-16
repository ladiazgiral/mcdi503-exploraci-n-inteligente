# MCDI503 - Evaluación Formativa 1 - Grupo 6

## Proyecto

**Análisis exploratorio de variables asociadas a la supervivencia de pasajeros del Titanic**

Este repositorio documenta la definición inicial del proyecto, la caracterización técnica del dataset y la planificación del análisis exploratorio de datos reproducible correspondiente a la Fase 1 Formativa.

## Estado técnico

El notebook `notebooks/mcdi503_f1f_plan_eda_grupo6.ipynb` fue ejecutado de principio a fin con ocho celdas de código consecutivas y sin errores. La validación técnica final se encuentra en `outputs/validacion_formativa.txt` y registra `estado_global=OK`.

## Dataset

- Fuente técnica: Seaborn `titanic`.
- Unidad de análisis: registro de pasajero.
- Dimensiones: 891 registros x 15 variables.
- SHA-256: `43af81a01f25a7771c9a42809a31625f4d0de3f335cdf29961f9ba179a86c13d`.
- Variables con valores faltantes: `age`, `deck`, `embarked` y `embark_town`.
- Las filas completamente coincidentes se documentan como coincidencias de registro y no se eliminan automáticamente debido a la ausencia de un identificador individual único.

## Preguntas exploratorias planificadas

- **P1:** supervivencia general y según `sex`.
- **P2:** supervivencia según `pclass` y cruce `sex x pclass`.
- **P3:** distribución de `age` y comparación según `survived`.
- **P4:** comportamiento de `fare` respecto de `pclass` y `survived`.
- **P5:** tamaño familiar construido desde `sibsp` y `parch` y su relación descriptiva con la supervivencia.

## Reproducibilidad

La ejecución utiliza una copia local del dataset, rutas relativas, verificación SHA-256, dependencias documentadas y exportación separada de productos derivados. Las versiones efectivamente utilizadas se registran en `outputs/manifest_formativa.csv`.

## Estructura

```text
.
├── data/
│   └── input/
│       └── titanic_seaborn.csv
├── notebooks/
│   └── mcdi503_f1f_plan_eda_grupo6.ipynb
├── outputs/
│   ├── caracterizacion_dataset.csv
│   ├── categorias_iniciales.csv
│   ├── manifest_formativa.csv
│   ├── plan_eda.csv
│   ├── rangos_iniciales.csv
│   ├── resumen_para_ficha.md
│   └── validacion_formativa.txt
├── Reports/
│   └── mcdi503_f1f_grupo6.pdf
├── .gitattributes
├── .gitignore
├── environment.yml
├── requirements.txt
└── SHA256_INPUT.txt
```

## Reproducción

1. Crear o activar un entorno compatible con `environment.yml` o `requirements.txt`.
2. Abrir `notebooks/mcdi503_f1f_plan_eda_grupo6.ipynb`.
3. Reiniciar el kernel y ejecutar todas las celdas en orden.
4. Confirmar que la validación final muestre `VALIDACIÓN FORMATIVA: OK`.
5. Guardar el notebook ejecutado.

## Entregable académico

El informe formativo se encuentra en `Reports/mcdi503_f1f_grupo6.pdf`.
