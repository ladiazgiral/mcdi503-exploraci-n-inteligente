# MCDI503 · Exploración Inteligente de Datos

## Sumativa 2 · Avance del proyecto Fases 2 y 3

Repositorio desarrollado para la asignatura **MCDI503 – Exploración Inteligente de Datos**, correspondiente a la **Evaluación Sumativa 2**.

El proyecto utiliza el dataset **Titanic** y contiene un flujo reproducible de preparación de datos y análisis exploratorio inicial. El detalle metodológico, las decisiones técnicas, la evidencia y las interpretaciones se encuentran en el **Jupyter Notebook** y en el **informe PDF**. Este README se concentra en la organización del repositorio y en los pasos necesarios para reproducir la ejecución localmente.

**Integrantes:** Luis Díaz · Gonzalo Bouldres · Eduardo Contreras  
**Curso:** 202681.2538 · Exploración Inteligente de Datos  
**Dataset:** Titanic · Seaborn

---

## Objetivo del proyecto

Construir un flujo reproducible que permita diagnosticar la calidad del dataset, aplicar limpieza y transformaciones, preparar los datos para análisis, desarrollar exploraciones univariadas y bivariadas y generar salidas trazables en archivos de datos, tablas y visualizaciones.

El proyecto está preparado para ejecutarse de forma local con **Python y JupyterLab**, sin depender de Google Colab ni de descargas externas durante la ejecución del notebook.

---

## Estructura del repositorio

```text
.
├── data/
│   ├── input/
│   │   └── titanic.csv
│   └── process/
│       └── titanic_f23_prepared.csv
│
├── figures/
│   └── visualizaciones generadas por el notebook
│
├── notebooks/
│   └── mcdi503_f23_sumativo_grupo6.ipynb
│
├── outputs/
│   └── tablas y archivos de validación/resultados
│
├── Reports/
│   └── informe de la evaluación
│
├── requirements.txt
└── README.md
```

### Carpetas principales

- **`data/input/`**: dataset original utilizado por el proyecto.
- **`data/process/`**: dataset preparado generado durante la ejecución.
- **`notebooks/`**: notebook principal y evidencia técnica del proyecto.
- **`figures/`**: visualizaciones exportadas por el notebook.
- **`outputs/`**: tablas de diagnóstico, validación y resultados auxiliares.
- **`Reports/`**: informe final de la evaluación.

---

# Reproducir el proyecto desde cero

Los siguientes pasos permiten clonar el repositorio, crear un entorno aislado, instalar las dependencias y abrir Jupyter correctamente en el navegador.

## 1. Requisitos previos

Se recomienda disponer de:

- **Python 3.11 o superior**
- **Git**
- navegador web instalado

Puede verificar Python y Git con:

```powershell
python --version
git --version
```

---

## 2. Clonar el repositorio

Desde PowerShell o una terminal de Windows:

```powershell
git clone https://github.com/<usuario>/<repositorio>.git
```

> Reemplace `<usuario>/<repositorio>` por la URL real del repositorio en GitHub.

Luego ingrese a la carpeta clonada. Por ejemplo:

```powershell
cd mcdi503_f23_sumativo_grupo6
```

Todos los comandos siguientes deben ejecutarse desde la **raíz del repositorio**, donde se encuentran `requirements.txt`, `README.md`, `data/`, `notebooks/`, `figures/` y `outputs/`.

---

## 3. Crear el entorno virtual

```powershell
python -m venv .venv
```

Esto crea un entorno Python independiente dentro de la carpeta `.venv`.

---

## 4. Activar el entorno virtual

### Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

Cuando el entorno esté activo, normalmente aparecerá `(.venv)` al inicio de la línea de comandos.

### Windows CMD

```cmd
.venv\Scripts\activate.bat
```

### macOS / Linux

```bash
source .venv/bin/activate
```

---

## 5. Actualizar `pip`

Antes de instalar las dependencias se recomienda actualizar `pip` dentro del entorno virtual:

```powershell
python -m pip install --upgrade pip
```

El uso de `python -m pip` asegura que la instalación se realice con el mismo intérprete Python asociado al entorno virtual activo.

---

## 6. Instalar las dependencias

```powershell
python -m pip install -r requirements.txt
```

El archivo `requirements.txt` contiene las librerías necesarias para reproducir el proyecto, incluyendo `pandas`, `numpy`, `matplotlib`, `seaborn`, `notebook` y `jupyterlab`.

---

## 7. Abrir Jupyter correctamente en el navegador

Para este proyecto **no se recomienda iniciar solamente con `jupyter notebook`**, ya que en algunos entornos de Windows el servidor puede levantarse sin abrir correctamente la interfaz en el navegador o puede intentar utilizar un archivo de redirección local.

Utilice el siguiente comando desde la raíz del repositorio y con `.venv` activo:

```powershell
python -m jupyterlab --ServerApp.use_redirect_file=False --ServerApp.open_browser=True
```

Este comando:

- ejecuta JupyterLab utilizando el Python del entorno virtual;
- evita depender del ejecutable global `jupyter.exe`;
- desactiva el archivo local de redirección `jpserver-...-open.html`;
- solicita explícitamente la apertura automática del navegador;
- abre Jupyter mediante una dirección HTTP local, normalmente `http://localhost:8888/lab`.

De esta forma, Jupyter debería abrirse directamente en el navegador sin necesidad de copiar manualmente la URL o el token desde la consola.

---

## 8. Abrir el notebook

Una vez cargado JupyterLab en el navegador, navegue a:

```text
notebooks/
```

Abra:

```text
mcdi503_f23_sumativo_grupo6.ipynb
```

---

## 9. Ejecutar el notebook completo

Para comprobar la reproducibilidad del proyecto, ejecute el notebook desde el inicio y en orden.

En JupyterLab puede utilizar:

```text
Run → Run All Cells
```

Si desea garantizar una ejecución completamente limpia:

```text
Kernel → Restart Kernel and Run All Cells
```

El notebook utiliza **rutas relativas**, por lo que debe mantenerse la estructura original del repositorio y Jupyter debe iniciarse desde su carpeta raíz.

Al finalizar, el flujo vuelve a generar o actualizar los archivos correspondientes en:

```text
data/process/
figures/
outputs/
```

---

## Secuencia completa en Windows PowerShell

Ejemplo resumido de una instalación nueva:

```powershell
# 1. Clonar repositorio
git clone https://github.com/<usuario>/<repositorio>.git

# 2. Entrar al proyecto
cd mcdi503_f23_sumativo_grupo6

# 3. Crear entorno virtual
python -m venv .venv

# 4. Activar entorno virtual
.\.venv\Scripts\Activate.ps1

# 5. Actualizar pip
python -m pip install --upgrade pip

# 6. Instalar dependencias
python -m pip install -r requirements.txt

# 7. Iniciar JupyterLab y abrirlo automáticamente en el navegador
python -m jupyterlab --ServerApp.use_redirect_file=False --ServerApp.open_browser=True
```

Después de abrirse JupyterLab:

```text
notebooks → mcdi503_f23_sumativo_grupo6.ipynb
```

y ejecutar:

```text
Kernel → Restart Kernel and Run All Cells
```

---

## Configuración permanente de Jupyter en Windows

El comando anterior ya permite iniciar el proyecto correctamente. Si se desea dejar configurado Jupyter para futuras ejecuciones y evitar escribir los parámetros cada vez, puede generarse el archivo de configuración con:

```powershell
python -m jupyter server --generate-config
```

Luego edite:

```text
%USERPROFILE%\.jupyter\jupyter_server_config.py
```

Y asegúrese de incluir:

```python
c.ServerApp.use_redirect_file = False
c.ServerApp.open_browser = True
```

Después de guardar esa configuración, será suficiente iniciar Jupyter con:

```powershell
python -m jupyterlab
```

Para efectos de reproducibilidad del repositorio, la instrucción recomendada sigue siendo la versión explícita:

```powershell
python -m jupyterlab --ServerApp.use_redirect_file=False --ServerApp.open_browser=True
```

porque no depende de una configuración previa del equipo.

---

## Flujo general del proyecto

```text
Dataset original
      ↓
Diagnóstico de calidad
      ↓
Limpieza y validación
      ↓
Integración y transformaciones
      ↓
Dataset preparado
      ↓
Análisis univariado y bivariado
      ↓
Patrones, anomalías y hallazgos
      ↓
Figuras + tablas + salidas
```

El detalle de cada decisión, su justificación y la interpretación de los resultados se encuentra documentado directamente en el notebook y sintetizado en el informe.

---

## Archivos principales

### Notebook

```text
notebooks/mcdi503_f23_sumativo_grupo6.ipynb
```

Contiene el desarrollo técnico y reproducible del proyecto.

### Informe

El informe académico se encuentra en:

```text
Reports/
```

### Dataset original

```text
data/input/titanic.csv
```

### Dataset preparado

```text
data/process/titanic_f23_prepared.csv
```

---

## Reproducibilidad

El proyecto fue organizado para que otra persona pueda reconstruir el análisis a partir del repositorio. Para ello:

- el dataset original se conserva separado de los datos procesados;
- la estructura de carpetas es estable;
- las rutas utilizadas por el notebook son relativas;
- las transformaciones se ejecutan dentro del notebook;
- las dependencias están documentadas en `requirements.txt`;
- se utiliza un entorno virtual aislado;
- `pip` se actualiza antes de instalar dependencias;
- Jupyter se inicia mediante el mismo intérprete Python del entorno virtual;
- se fuerza la apertura correcta de Jupyter en el navegador sin depender del archivo de redirección local;
- las figuras y resultados se generan en carpetas específicas;
- el notebook puede ejecutarse completamente desde una sesión limpia.

Los archivos generados incluidos en el repositorio permiten revisar la entrega sin volver a ejecutar el análisis, mientras que el notebook permite reproducir el flujo completo cuando sea necesario.

---

## Alcance

Este repositorio corresponde al avance integrado de las **Fases 2 y 3** del proyecto de MCDI503. El README explica cómo instalar y ejecutar el proyecto; el desarrollo técnico, las decisiones metodológicas, los análisis y los hallazgos se encuentran en el notebook y en el informe final.
