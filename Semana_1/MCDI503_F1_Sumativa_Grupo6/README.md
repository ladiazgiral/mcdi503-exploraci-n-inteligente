# MCDI503 - Evaluación Sumativa 1 - Grupo 6

## Proyecto

**Supervivencia en el Titanic: exploración de factores asociados a la supervivencia**  
Asignatura: **MCDI503 - Exploración Inteligente de Datos**  
Integrantes: **Luis Díaz, Gonzalo Bouldres y Eduardo Contreras**  
Fase: **Implementación inicial de un análisis exploratorio de datos (EDA) reproducible**

Este repositorio contiene la ejecución definitiva del primer ciclo de EDA sobre el dataset `titanic` distribuido por Seaborn. El flujo integra verificación de integridad del insumo, diagnóstico de calidad, análisis descriptivo univariado y bivariado, transformaciones derivadas, visualizaciones, documentación de decisiones, síntesis de hallazgos y controles automáticos de coherencia.

## Estado de la ejecución

La ejecución definitiva fue completada el **06-09-2026 a las 12:59:21 (UTC-03:00)** y finalizó sin errores. La última validación del notebook registró:

```text
estado_global=OK
VALIDACIÓN FINAL: OK
```

La identidad de la corrida, las versiones del entorno y las comprobaciones de coherencia se conservan en:

- `outputs/manifest_ejecucion.txt`
- `outputs/validacion_final.txt`

## Dataset e integridad

- Fuente: copia local auditada del dataset `titanic` distribuido por Seaborn.
- Archivo: `data/input/titanic_seaborn.csv`
- Dimensiones de entrada: **891 filas x 15 columnas**.
- SHA-256: `43af81a01f25a7771c9a42809a31625f4d0de3f335cdf29961f9ba179a86c13d`.

El notebook verifica el hash y las dimensiones antes de iniciar el análisis. El archivo original no se modifica; las transformaciones se escriben en `data/process/`.

## Preguntas exploratorias

1. ¿Cuál es la proporción de supervivencia y cómo cambia según sexo?
2. ¿Existen diferencias de supervivencia entre las clases de pasajero?
3. ¿Cómo se distribuye `age` y qué diferencias descriptivas aparecen según supervivencia?
4. ¿Cómo se comporta `fare` respecto de clase y supervivencia?
5. ¿El tamaño del grupo familiar presenta diferencias descriptivas de supervivencia?

El análisis se limita a una exploración descriptiva. No se realizan imputaciones, pruebas inferenciales ni modelos predictivos, y las asociaciones observadas no se interpretan causalmente.

## Estructura del repositorio

```text
MCDI503_F1_Sumativa_Grupo6/
├── .gitattributes
├── .gitignore
├── README.md
├── SHA256_INPUT.txt
├── environment.yml
├── requirements.txt
├── data/
│   ├── input/
│   │   └── titanic_seaborn.csv
│   └── process/
│       └── titanic_eda_process.csv
├── notebooks/
│   └── mcdi503_f1_sumativo_grupo6.ipynb
├── figures/
│   ├── 01_diagnostico_calidad_distribuciones.png
│   ├── 02_relaciones_preguntas_ejecutadas.png
│   └── 03_fare_clase_supervivencia.png
├── outputs/
│   ├── tablas y resultados del EDA
│   ├── decisiones_exploratorias.csv
│   ├── tabla_pregunta_accion_resultado.csv
│   ├── manifest_ejecucion.txt
│   ├── validacion_final.txt
│   └── resúmenes técnicos generados por el notebook
└── Reports/
    └── mcdi503_f1_sumativo_grupo6.pdf
```

## Resultados principales de la corrida definitiva

- Supervivencia global: **38,4 %**.
- Supervivencia por sexo: **74,2 % en mujeres** y **18,9 % en hombres**.
- Supervivencia por clase: **63,0 % (1.ª)**, **47,3 % (2.ª)** y **24,2 % (3.ª)**.
- `age`: **177 valores faltantes (19,9 %)**; mediana de **28 años** en ambos grupos de supervivencia.
- `deck`: **688 valores faltantes (77,2 %)**.
- `fare`: mediana global de **14,45**; **116** observaciones identificadas por la regla IQR y conservadas para la exploración.
- Supervivencia viajando solo: **30,4 %**; con familiares registrados: **50,6 %**.

Los resultados completos se encuentran en `outputs/` y en las salidas visibles del notebook.

## Decisiones metodológicas principales

- Se utiliza exclusivamente la copia local auditada del dataset.
- No se imputan valores faltantes en esta fase.
- `pclass` se trata como variable ordinal categórica.
- Se deriva `FamilySize = sibsp + parch + 1` mediante código. `IsAlone` se recalcula desde `FamilySize` para dejar la transformación explícita y auditable desde `sibsp` y `parch`, aun cuando el dataset de Seaborn ya contiene la variable derivada `alone`.
- Los valores extremos de `fare` se identifican mediante IQR, pero no se eliminan automáticamente.
- Las 107 filas completamente coincidentes se documentan y conservan porque el dataset de Seaborn no aporta un identificador individual único que permita confirmar duplicidad de pasajeros.

## Entorno reproducible

La corrida definitiva utilizó:

| Componente | Versión |
|---|---:|
| Python | 3.12.4 |
| NumPy | 1.26.4 |
| pandas | 2.2.2 |
| Seaborn | 0.13.2 |
| Matplotlib | 3.8.4 |
| ipykernel | 6.28.0 |
| notebook | 7.0.8 |
| JupyterLab | 4.0.11 |

### Conda

```bash
conda env create -f environment.yml
conda activate mcdi503_f1_g6
jupyter lab
```

### pip

En un entorno con Python 3.12.4:

```bash
pip install -r requirements.txt
jupyter lab
```

## Reproducción

1. Iniciar Jupyter desde la raíz del proyecto.
2. Abrir `notebooks/mcdi503_f1_sumativo_grupo6.ipynb`.
3. Seleccionar el kernel del entorno reproducible.
4. Ejecutar **Restart Kernel and Run All Cells**.
5. Comprobar que la última celda muestre `VALIDACIÓN FINAL: OK`.
6. Guardar el notebook con sus salidas visibles.

Al comenzar una corrida, el notebook limpia únicamente los productos derivados de `data/process/`, `figures/` y `outputs/`. El dataset auditado y el informe en `Reports/` permanecen intactos.

## Productos de entrega

Los dos productos académicos principales son:

- `Reports/mcdi503_f1_sumativo_grupo6.pdf`
- `notebooks/mcdi503_f1_sumativo_grupo6.ipynb`

El resto del repositorio conserva los insumos, resultados y evidencias necesarios para reproducir y auditar el flujo analítico.
