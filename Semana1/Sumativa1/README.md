# MCDI503 — Exploración Inteligente de Datos

## Evaluación Sumativa 1 · Fase 1

Repositorio del proyecto desarrollado para la asignatura **MCDI503 — Exploración Inteligente de Datos** de la Universidad Andrés Bello.

Esta entrega da continuidad directa a la **Evaluación Formativa 1**. En la formativa se definieron el proyecto, el dataset, las cinco preguntas exploratorias, la organización prevista del EDA y los criterios iniciales de reproducibilidad. En la **Sumativa S01** esa planificación se **ejecuta de principio a fin en Jupyter**, dejando evidencia técnica, gráfica y narrativa de la primera implementación del EDA reproducible.

### Integrantes

- Luis Díaz
- Gonzalo Bouldres
- Eduardo Contreras

---

## 1. Continuidad con la Formativa 1

La Sumativa S01 **no inicia un proyecto nuevo**. Mantiene lo definido en la entrega formativa y avanza desde la planificación hacia la ejecución.

| Elemento | Formativa 1 | Sumativa S01 |
|---|---|---|
| Título del proyecto | **Supervivencia en el Titanic: exploración de factores asociados a datos** | Se conserva el mismo proyecto; “Implementación inicial del EDA reproducible” identifica el avance sumativo |
| Dataset | `Titanic.csv`, 891 registros y 12 variables | Se utiliza el mismo archivo como entrada inmutable |
| Calidad | Se diagnosticaron nulos, duplicados y distribuciones iniciales | Se cuantifica y documenta la calidad antes de interpretar |
| Preguntas | Se formularon **5 preguntas exploratorias** | Se ejecutan las mismas 5 preguntas mediante código, tablas y gráficos |
| `Fare` | Se planificó analizar respecto de **clase y supervivencia** | Se ejecutan comparaciones por `Pclass`, `Survived` y el cruce `Pclass × Survived` |
| Transformación | Se planificó `FamilySize = SibSp + Parch + 1` | Se implementa `FamilySize`; `IsAlone` se usa solo como extensión secundaria documentada |
| Outliers | Se planificó revisión sin eliminación automática | Se usa IQR para marcar `Fare`; los casos no se eliminan sin evidencia de error |
| Reproducibilidad | Se definieron rutas, carpetas, datos originales/procesados, figuras y outputs | Se agregan SHA-256, versiones del entorno, manifiesto y resultados exportados |
| Notebook | Base de trabajo | Evidencia principal ejecutada: **pregunta → acción → resultado** |
| Informe | Plan del proyecto | Síntesis técnica de la ejecución, decisiones y hallazgos con referencias al notebook |

La secuencia de la Formativa 1 también se conserva: **contexto/carga → estructura/tipos → calidad mínima → descriptivos → distribuciones → relaciones simples → FamilySize → outliers → síntesis**.

---

## 2. Proyecto

### SUPERVIVENCIA EN EL TITANIC: EXPLORACIÓN DE FACTORES ASOCIADOS A DATOS

El proyecto utiliza el dataset **Titanic** proporcionado por la asignatura. Cada fila representa un pasajero e incluye variables demográficas y asociadas al viaje como `Survived`, `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Cabin` y `Embarked`.

El objetivo de la Sumativa S01 es **ejecutar el EDA planificado en la Formativa 1**, describiendo la supervivencia y los patrones iniciales asociados con sexo, clase, edad, tarifa y tamaño del grupo familiar, mientras se documentan la calidad del dato, las decisiones exploratorias, las transformaciones, los resultados intermedios, los supuestos y las limitaciones.

El alcance es **descriptivo y exploratorio**: no se realizan pruebas inferenciales ni modelos predictivos y las asociaciones observadas no se interpretan como relaciones causales.

---

## 3. Preguntas exploratorias

La Sumativa conserva **exactamente las cinco preguntas** formuladas en el informe de la Formativa 1:

1. ¿Cuál es la proporción de supervivencia y cómo cambia según sexo?
2. ¿Existen diferencias de supervivencia entre las clases de pasajero?
3. ¿Cómo se distribuye `Age` y qué diferencias descriptivas aparecen entre sobrevivientes y no sobrevivientes, considerando sus valores faltantes?
4. ¿Cómo se comporta `Fare` y qué patrones preliminares presenta respecto de **clase y supervivencia**?
5. ¿El tamaño del grupo familiar, derivado de `SibSp` y `Parch`, muestra patrones que convenga profundizar?

La **calidad del dato no se agrega como una sexta pregunta**: se mantiene como una etapa transversal y previa a la interpretación, tal como quedó planificado en la Formativa 1.

---

## 4. Estructura del repositorio

```text
.
├── data/
│   ├── input/
│   │   └── Titanic.csv
│   └── process/
│       └── titanic_eda_process.csv
├── figures/
│   ├── 01_diagnostico_calidad_distribuciones.png
│   ├── 02_relaciones_preguntas_ejecutadas.png
│   └── 03_fare_clase_supervivencia.png
├── notebooks/
│   └── mcdi503_s01_g6.ipynb
├── outputs/
│   ├── *.csv
│   ├── resumen_eda.md
│   └── manifest_ejecucion.txt
├── Reports/
│   ├── mcdi503_s01_g6.pdf
├── requirements.txt
└── README.md
```

### Uso de las carpetas

| Carpeta | Propósito |
|---|---|
| `data/input/` | Datos originales. **No se modifican ni sobrescriben.** |
| `data/process/` | Datos derivados mediante código. |
| `figures/` | Visualizaciones generadas por el notebook. |
| `notebooks/` | Notebook principal ejecutado. |
| `outputs/` | Tablas, resúmenes y archivos de trazabilidad. |
| `Reports/` | Informe institucional en PDF y versión editable. |

---

## 5. Requisitos

- Python 3.10 o superior recomendado.
- Jupyter Notebook 7 o JupyterLab 4.
- Dependencias definidas en `requirements.txt`.

---

## 6. Instalación en Jupyter

### Windows (PowerShell)

Desde la raíz del repositorio:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python -m ipykernel install --user --name mcdi503-s01 --display-name "Python (MCDI503 S01)"
jupyter notebook
```

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
python -m ipykernel install --user --name mcdi503-s01 --display-name "Python (MCDI503 S01)"
jupyter notebook
```

Jupyter debería abrir el navegador automáticamente. Luego abra:

```text
notebooks/mcdi503_s01_g6.ipynb
```

Seleccione el kernel **Python (MCDI503 S01)** si no queda seleccionado automáticamente.

---

## 7. Ejecución reproducible

Antes de ejecutar, verifique que exista:

```text
data/input/Titanic.csv
```

En Jupyter utilice:

```text
Kernel / Restart Kernel and Run All Cells
```

o la opción equivalente **Run All**.

La ejecución no requiere modificar rutas dentro del notebook: el código detecta automáticamente la raíz del proyecto tanto si Jupyter se inicia desde la raíz como si el kernel trabaja desde `notebooks/`.

---

## 8. Flujo del notebook

El notebook respeta los ocho apartados exigidos para la Sumativa S01:

1. **Identificación del proyecto** — mantiene el título y el foco de la Formativa 1.
2. **Contexto y objetivo exploratorio** — conserva las cinco preguntas iniciales.
3. **Carga y revisión inicial de datos** — archivo, dimensiones, tipos, nulos y duplicados.
4. **Exploración preliminar** — ejecución de preguntas 1 a 4 con descriptivos y relaciones.
5. **Decisiones y transformaciones iniciales** — `FamilySize`, extensión `IsAlone`, decisiones de nulos y outliers.
6. **Resultados e interpretación inicial** — matriz explícita pregunta → acción → resultado.
7. **Supuestos y limitaciones** — condiciones de interpretación y restricciones del dataset.
8. **Cierre del avance** — síntesis y continuidad hacia fases posteriores.

---

## 9. Transformaciones

### Transformación principal planificada

```python
FamilySize = SibSp + Parch + 1
```

`FamilySize` es la variable derivada definida en la Formativa 1 y se implementa por código en la Sumativa.

### Extensión secundaria surgida durante la ejecución

```python
IsAlone = 1 if FamilySize == 1 else 0
```

`IsAlone` se utiliza únicamente para resumir viajar solo vs. acompañado. **No reemplaza ni modifica la pregunta original sobre `FamilySize`**.

No se imputan nulos ni se eliminan outliers automáticamente.

---

## 10. Figuras generadas

### `01_diagnostico_calidad_distribuciones.png`

Ejecuta el diagnóstico inicial planificado en la Formativa 1:

- valores faltantes;
- supervivencia global;
- distribución de `Age`;
- distribución de `Fare`.

### `02_relaciones_preguntas_ejecutadas.png`

Ejecuta las relaciones asociadas a las preguntas 1, 2, 3 y 5:

- supervivencia por sexo;
- supervivencia por clase;
- `Age` según supervivencia;
- supervivencia por `FamilySize`, mostrando también el tamaño (`n`) de cada grupo.

### `03_fare_clase_supervivencia.png`

Completa la pregunta 4, que en la Formativa 1 exigía analizar `Fare` respecto de **clase y supervivencia**:

- distribución de `Fare`;
- `Fare` según supervivencia;
- `Fare` según `Pclass`;
- mediana de `Fare` por cruce `Pclass × Survived`.

Todas las figuras se generan automáticamente al ejecutar el notebook.

En el **informe complementario**, cada figura se acompaña de una **bajada interpretativa breve**. La bajada no repite el gráfico: resume qué muestra, qué hallazgo aporta y cómo se conecta con la pregunta exploratoria correspondiente. En el notebook, la misma lógica queda registrada después de cada bloque como **Resultado e interpretación**.

---

## 11. Outputs generados

La ejecución produce archivos tabulares y de trazabilidad en `outputs/`, entre ellos:

- `resumen_calidad.csv`;
- `supervivencia_por_sexo.csv`;
- `supervivencia_por_clase.csv`;
- `supervivencia_sexo_clase.csv`;
- `age_por_supervivencia.csv`;
- `fare_por_supervivencia.csv`;
- `fare_por_clase.csv`;
- `fare_por_clase_y_supervivencia.csv`;
- `revision_outliers_fare_iqr.csv`;
- `supervivencia_por_tamano_familiar.csv`;
- `supervivencia_solo_vs_acompanado.csv`;
- `tabla_pregunta_accion_resultado.csv`;
- `resumen_eda.md`;
- `manifest_ejecucion.txt`.

El manifiesto registra la ruta de la entrada, su **hash SHA-256**, dimensiones y las versiones de Python, pandas, NumPy y Matplotlib utilizadas.

---

## 12. Hallazgos exploratorios iniciales

1. **Supervivencia global:** 38,4 % (342 de 891 pasajeros).
2. **Sexo:** 74,2 % de supervivencia en mujeres frente a 18,9 % en hombres.
3. **Clase:** 63,0 % en primera clase, 47,3 % en segunda y 24,2 % en tercera.
4. **Edad:** 177 valores faltantes; mediana de 28 años tanto en sobrevivientes como no sobrevivientes en este primer corte.
5. **Tarifa y clase:** mediana de `Fare` de 60,29 en primera clase, 14,25 en segunda y 8,05 en tercera.
6. **Tarifa y supervivencia:** mediana de 26,0 entre sobrevivientes frente a 10,5 entre no sobrevivientes; el patrón debe interpretarse junto con `Pclass`.
7. **Outliers de Fare:** 116 observaciones quedan fuera de los límites IQR; se documentan y conservan.
8. **Tamaño familiar:** patrón no lineal; los grupos intermedios presentan tasas más altas, mientras los grupos grandes tienen pocos registros.
9. **Calidad:** `Cabin` queda fuera del foco inicial por su 77,1 % de ausencia; `Age` se analiza sin imputación.

Los hallazgos son **exploratorios y descriptivos**, no evidencia causal.

---

## 13. Reproducibilidad y trazabilidad

La Sumativa consolida los criterios definidos previamente:

- separación entre datos originales y procesados;
- fuente original inmutable;
- rutas relativas al repositorio;
- transformaciones realizadas mediante código;
- variables derivadas documentadas;
- figuras y tablas generadas automáticamente;
- hash SHA-256 de la entrada;
- versiones del entorno;
- decisiones exploratorias registradas con motivo y resultado intermedio;
- supuestos y limitaciones explícitos;
- correspondencia entre preguntas, acciones, resultados y figuras;
- ejecución completa en Jupyter sin pasos manuales ocultos.

---

## 14. Archivos para la entrega

Según las instrucciones de la Sumativa S01, los dos archivos principales para Canvas son:

```text
Reports/mcdi503_f1_sumativo_grupo6.pdf
notebooks/mcdi503_f1s_eda_titanic.ipynb
```

El informe PDF funciona como **síntesis técnica** y el notebook ejecutado constituye la **evidencia técnica principal**.

---

## 15. Diferencia entre la Formativa 1 y la Sumativa S01

La diferencia metodológica central es:

```text
FORMativa 1                           SUMATIVA S01
-----------                           -------------
define el proyecto          →         conserva el mismo proyecto
formula 5 preguntas         →         ejecuta las mismas 5 preguntas
planifica la calidad        →         cuantifica y documenta calidad
planifica FamilySize        →         implementa FamilySize por código
planifica Fare vs clase     →         ejecuta Fare vs Pclass y supervivencia
prevé visualizaciones       →         genera figuras reproducibles
establece criterios         →         registra hash, versiones y outputs
planifica el EDA            →         ejecuta el EDA y sintetiza hallazgos
```

La Sumativa S01 es, por tanto, **la ejecución documentada y reproducible del EDA que quedó planificado en la Formativa 1**.
