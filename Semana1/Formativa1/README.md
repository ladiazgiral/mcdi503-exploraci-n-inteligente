# MCDI503 — Exploración Inteligente de Datos

## Evaluación Formativa 1 · Fase 1

Repositorio del proyecto desarrollado para la asignatura **MCDI503 — Exploración Inteligente de Datos** de la Universidad Andrés Bello.

El objetivo de esta primera fase es definir el foco del proyecto, caracterizar el conjunto de datos y organizar un **Análisis Exploratorio de Datos (EDA) inicial, trazable y reproducible**, utilizando **Jupyter Notebook/JupyterLab**.

### Integrantes

- Luis Díaz
- Gonzalo Bouldres
- Eduardo Contreras

---

## 1. Proyecto

### Análisis exploratorio de los factores asociados a la supervivencia en el Titanic

El proyecto utiliza el dataset **Titanic** proporcionado para las actividades de la asignatura. Cada registro representa a un pasajero e incluye variables demográficas y asociadas al viaje, tales como `Survived`, `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare` y `Embarked`.

El análisis busca comprender la estructura y calidad de los datos e identificar patrones exploratorios relacionados con la supervivencia. Los resultados de esta fase son **descriptivos** y no deben interpretarse como relaciones causales.

---

## 2. Preguntas exploratorias

El notebook se organiza principalmente en torno a las siguientes preguntas:

1. ¿Cuál es la proporción general de supervivencia?
2. ¿Existen diferencias descriptivas de supervivencia según sexo?
3. ¿Cómo cambia la supervivencia entre las clases de pasajeros?
4. ¿Qué diferencias de edad se observan entre pasajeros sobrevivientes y no sobrevivientes?
5. ¿El tamaño del grupo familiar presenta algún patrón respecto de la supervivencia?
6. ¿Qué problemas de calidad, valores faltantes o posibles valores atípicos deben considerarse antes de continuar el análisis?

---

## 3. Estructura del repositorio

```text
.
├── data/
│   ├── input/
│   │   └── Titanic.csv
│   └── process/
│       └── titanic_eda_process.csv
├── figures/
│   └── *.png
├── notebooks/
│   └── mcdi503_f01_g6.ipynb
├── outputs/
│   ├── *.csv
│   ├── resumen_eda.md
│   └── manifest_ejecucion.txt
├── Reports/
│   ├── mcdi503_f01_g6.pdf
├── requirements.txt
└── README.md
```

### Uso de las carpetas

| Carpeta | Propósito |
|---|---|
| `data/input/` | Datos originales. El notebook no modifica estos archivos. |
| `data/process/` | Datos transformados o derivados mediante código. |
| `figures/` | Visualizaciones generadas por el notebook. |
| `notebooks/` | Notebook principal del análisis. |
| `outputs/` | Tablas, resúmenes y archivos de trazabilidad generados. |
| `Reports/` | Informe institucional en PDF y su versión editable. |

La separación permite mantener la secuencia **entrada → transformación → análisis → figuras/resultados → reporte**.

---

## 4. Requisitos

Se recomienda utilizar **Python 3.10 o superior**.

Las dependencias necesarias se encuentran en:

```text
requirements.txt
```

El archivo incluye Jupyter Notebook/JupyterLab y las librerías utilizadas en el análisis:

- NumPy
- pandas
- Matplotlib
- IPython kernel

---

## 5. Preparación del entorno Jupyter

### 5.1 Clonar o descargar el repositorio

Ubíquese en una carpeta de trabajo y descargue el proyecto.

### 5.2 Crear un entorno virtual

#### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 5.3 Instalar las dependencias

Desde la **raíz del repositorio**:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5.4 Verificar el archivo de entrada

Antes de ejecutar el notebook debe existir:

```text
data/input/Titanic.csv
```

El notebook **no descarga ni reemplaza automáticamente** el dataset. Si el archivo no existe, la ejecución se detendrá con un mensaje indicando la ruta esperada. Esto evita utilizar accidentalmente una fuente distinta.

---

## 6. Ejecutar el notebook en Jupyter

Desde la **raíz del repositorio**, puede iniciar cualquiera de las dos interfaces.

### JupyterLab

```bash
python -m jupyterlab --ServerApp.use_redirect_file=False
```

### Jupyter Notebook

```bash
jupyter notebook
```

Luego abra:

```text
notebooks/mcdi503_f1f_eda_titanic.ipynb
```

Para comprobar la reproducibilidad del análisis, utilice la opción **Restart Kernel and Run All Cells** o su equivalente en la interfaz utilizada.

El notebook está preparado para localizar la raíz del proyecto aunque el kernel se inicie desde la carpeta `notebooks/`. Por ello, todas las rutas utilizadas son relativas a la estructura del repositorio y no dependen de rutas absolutas de un computador específico.

---

## 7. Flujo del notebook

El análisis sigue esta secuencia:

1. Definición del contexto, alcance y preguntas exploratorias.
2. Configuración del entorno y rutas del proyecto.
3. Carga controlada de `data/input/Titanic.csv`.
4. Identificación de la unidad de análisis y tipos de variables.
5. Revisión de calidad mínima:
   - valores faltantes;
   - duplicados;
   - rangos;
   - categorías.
6. Estadísticas descriptivas.
7. Visualizaciones univariadas.
8. Relaciones simples entre supervivencia y otras variables.
9. Creación documentada de `FamilySize`.
10. Revisión exploratoria de posibles outliers mediante IQR.
11. Generación de figuras de síntesis utilizadas en el informe.
12. Exportación de resultados.
13. Síntesis de hallazgos, decisiones y limitaciones.
14. Checklist de reproducibilidad.

Las celdas Markdown documentan **qué se hace, por qué se hace y qué se observa**, manteniendo trazabilidad del razonamiento analítico.

---

## 8. Archivos generados al ejecutar

### `data/process/`

Se genera:

```text
titanic_eda_process.csv
```

Este archivo conserva los datos utilizados durante el análisis e incorpora la variable derivada:

```text
FamilySize = SibSp + Parch + 1
```

El archivo original `data/input/Titanic.csv` permanece intacto.

### `figures/`

El notebook genera las visualizaciones utilizadas durante el EDA, entre ellas:

- distribución de supervivencia;
- distribución de edad;
- distribución de tarifa;
- supervivencia por sexo;
- supervivencia por clase;
- edad según supervivencia;
- supervivencia por tamaño familiar;
- figuras de síntesis para el informe.

### `outputs/`

Se generan tablas y archivos de apoyo, por ejemplo:

- diagnóstico de calidad;
- descriptivos numéricos;
- diccionario de variables;
- frecuencias de variables categóricas;
- tablas de supervivencia por grupos;
- revisión de posibles outliers;
- `resumen_eda.md`;
- `manifest_ejecucion.txt`.

El manifiesto registra información del archivo de entrada y del entorno de ejecución, incluyendo el **hash SHA-256** de `Titanic.csv`.

---

## 9. Reproducibilidad y trazabilidad

El proyecto aplica los siguientes criterios:

- separación entre datos originales y datos procesados;
- uso de rutas relativas al repositorio;
- transformaciones realizadas únicamente mediante código;
- variables derivadas documentadas;
- figuras generadas automáticamente desde el notebook;
- resultados tabulares exportados a una carpeta independiente;
- registro del hash del archivo de entrada;
- registro de versiones del entorno;
- documentación narrativa de decisiones, hallazgos y limitaciones;
- posibilidad de ejecutar el notebook completo desde el dataset original mediante Jupyter.

---

## 10. Alcance

Este trabajo corresponde a una **exploración inicial**. No se realizan pruebas inferenciales ni modelos predictivos.

Los patrones encontrados:

- son descriptivos;
- sirven para orientar análisis posteriores;
- pueden estar condicionados por valores faltantes u otras características del dataset;
- no implican causalidad.

---

## 11. Informe

Los documentos de entrega se almacenan en:

```text
Reports/
```

El archivo PDF corresponde al informe institucional de la Evaluación Formativa 1 y el DOCX se conserva como versión editable.

---

## 12. Referencias principales

- Bruce, P., Bruce, A., & Gedeck, P. (2020). *Practical statistics for data scientists: 50+ essential concepts using R and Python* (2nd ed.). O'Reilly Media.
- Paraíso, S. (2026). *Resumen aplicado del libro: EDA mínimo viable*. Universidad Andrés Bello.
- Paraíso, S. (2026). *Tres errores típicos en EDA*. Universidad Andrés Bello.
- Paraíso, S. (2026). *Checklist notebook reproducible*. Universidad Andrés Bello.
- Tukey, J. W. (1977). *Exploratory data analysis*. Addison-Wesley.
- VanderPlas, J. (2016). *Python data science handbook: Essential tools for working with data*. O'Reilly Media.

---

**Universidad Andrés Bello — UNAB Online**  
**MCDI503 — Exploración Inteligente de Datos**  
**Avance del Proyecto — Fase 1**  
**2026**
