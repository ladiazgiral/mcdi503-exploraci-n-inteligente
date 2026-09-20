# MCDI503 - Evaluación Sumativa 3 - Fase 4 - Grupo 6

**Asignatura:** MCDI503 - Exploración Inteligente de Datos  
**Integrantes:** Luis Díaz, Gonzalo Bouldres y Eduardo Contreras  
**Fecha de entrega:** miércoles 23 de septiembre de 2026

## Propósito

Cierre técnico del proyecto Titanic mediante un pipeline exploratorio reproducible que integra transformaciones y normalizaciones, creación de variables derivadas, selección preliminar de características, codificación categórica y validaciones de trazabilidad.

## Estructura del repositorio

```text
MCDI503_F4_Sumativa_Grupo6/
├── README.md
├── requirements.txt
├── data/
│   ├── input/
│   │   ├── titanic.csv
│   │   └── titanic_f23_prepared.csv
│   └── process/
│       ├── titanic_f4_matriz_caracteristicas.csv
│       ├── titanic_f4_pipeline_final.csv
│       └── titanic_f4_target.csv
├── notebooks/
│   └── mcdi503_f4_sumativa3_grupo6.ipynb
├── outputs/
│   ├── 00_entorno_ejecucion.csv
│   ├── ...
│   ├── 16_inventario_artefactos.csv
│   └── manifest_pipeline.json
├── figures/
│   ├── 01_transformacion_fare.png
│   ├── 02_variables_normalizadas.png
│   ├── 03_family_size_supervivencia.png
│   └── 04_interaccion_sex_pclass.png
├── reports/
│   └── mcdi503_f4_sumativa3_grupo6.pdf
└── presentation/
    └── mcdi503_f4_presentacion_grupo6.pptx
```

## Evidencia técnica

El notebook incluido corresponde a la ejecución final validada del pipeline. La corrida conserva 891 registros, genera un dataset enriquecido y una matriz candidata de 10 características sin valores faltantes, y deja registradas las auditorías de transformaciones, variables derivadas, selección preliminar, codificación y validación final.

Los archivos de `outputs/`, `figures/` y `data/process/` son productos reproducibles de esa misma ejecución y respaldan la trazabilidad del análisis.

## Reproducción del pipeline

1. Instalar las dependencias declaradas en `requirements.txt`.
2. Abrir `notebooks/mcdi503_f4_sumativa3_grupo6.ipynb`.
3. Ejecutar el notebook completo en orden (`Restart Kernel` + `Run All`).
4. Verificar que el cierre indique que las validaciones del pipeline fueron superadas.
5. Los artefactos se regeneran en `data/process/`, `outputs/` y `figures/`.

El notebook localiza automáticamente la raíz del proyecto mientras se conserve esta estructura de carpetas. Las versiones exactas usadas en la ejecución final quedan registradas en `outputs/00_entorno_ejecucion.csv`.

## Entrega en Canvas

La entrega oficial contempla el informe final en PDF, el notebook ejecutado y una presentación final en formato video. El archivo PPTX de `presentation/` corresponde al material base para la grabación. El producto oficial de presentación en Canvas debe exportarse y entregarse en formato video, según la pauta.
