# MCDI503 - Exploración Inteligente para la Ciencia de Datos

## Proyecto integrado · Grupo 6

Repositorio académico desarrollado para la asignatura **MCDI503 - Exploración Inteligente para la Ciencia de Datos**. El proyecto mantiene continuidad sobre el dataset **Titanic** y documenta, de forma progresiva y reproducible, el proceso de exploración, preparación, transformación e ingeniería preliminar de características desarrollado durante las Semanas 1, 2 y 3.

### Integrantes

- Luis Díaz
- Gonzalo Bouldres
- Eduardo Contreras

**Docente:** Sergio Paraíso

---

## Propósito del repositorio

El repositorio conserva la trazabilidad completa del proyecto desde la definición inicial del problema hasta el cierre técnico de la Fase 4. Cada semana mantiene sus propios entregables académicos y, cuando corresponde, notebooks ejecutados, datos de entrada y proceso, figuras, salidas de auditoría y archivos de dependencias.

El flujo general del proyecto es:

```text
Titanic · 891 registros × 15 variables
                │
                ▼
Semana 1 · Fase 1
Definición del proyecto y EDA reproducible
                │
                ▼
Semana 2 · Fases 2 y 3
Calidad, limpieza, integración, preparación y EDA
                │
                ▼
titanic_f23_prepared.csv · 891 × 29
                │
                ▼
Semana 3 · Fase 4
Ingeniería de variables y selección preliminar
                │
                ├── Dataset enriquecido · 891 × 36
                └── Matriz candidata · 891 × 10 + target
```

---

## Estructura general

```text
.
├── README.md
├── Semana_1/
│   ├── MCDI503_F1_Formativa_Grupo6/
│   └── MCDI503_F1_Sumativa_Grupo6/
│
├── Semana_2/
│   ├── MCDI503_F2_Formativa_Grupo6/
│   └── MCDI503_F2_Sumativa_Grupo6/
│
└── Semana_3/
    ├── README.md
    ├── Formativa/
    │   └── MCDI503_F4_Formativa_Grupo6/
    └── Sumativa/
        └── MCDI503_F4_Sumativa_Grupo6/
```

Cada subcarpeta incluye su propio `README.md` cuando corresponde, con el alcance, los archivos de entrega y las instrucciones específicas de reproducción.

---

## Semana 1 · Fase 1

### Evaluación Formativa 1

Corresponde a la definición inicial del proyecto y a la planificación del análisis exploratorio. Incluye:

- caracterización del dataset;
- identificación de variables, tipos y valores faltantes;
- formulación de preguntas exploratorias;
- supuestos y limitaciones iniciales;
- planificación reproducible del EDA;
- notebook ejecutado e informe formativo en PDF.

Ruta:

```text
Semana_1/MCDI503_F1_Formativa_Grupo6/
```

### Evaluación Sumativa 1

Implementa el primer EDA reproducible sobre Titanic. Incluye:

- diagnóstico de calidad;
- análisis univariado y bivariado;
- variables derivadas iniciales;
- visualizaciones generadas mediante código;
- documentación de decisiones;
- controles de integridad y validación;
- notebook ejecutado e informe sumativo.

Ruta:

```text
Semana_1/MCDI503_F1_Sumativa_Grupo6/
```

---

## Semana 2 · Fases 2 y 3

### Evaluación Formativa 2

Planifica la preparación e integración de datos y la continuación del análisis exploratorio. El producto académico corresponde a un informe formativo en PDF.

Ruta:

```text
Semana_2/MCDI503_F2_Formativa_Grupo6/
```

### Evaluación Sumativa 2

Implementa el flujo reproducible de calidad, limpieza, integración y preparación del dataset, junto con análisis exploratorio complementario.

Entre sus principales productos se encuentra:

```text
data/process/titanic_f23_prepared.csv
```

Este archivo conserva **891 registros** y amplía la representación preparada a **29 variables**, constituyendo la entrada técnica de continuidad para la Fase 4.

Ruta:

```text
Semana_2/MCDI503_F2_Sumativa_Grupo6/
```

---

## Semana 3 · Fase 4

La Semana 3 separa explícitamente la actividad formativa de la evaluación sumativa.

### Evaluación Formativa Fase 4

Presenta el plan de ingeniería de variables y selección preliminar de características que posteriormente se implementa en el cierre sumativo.

Ruta:

```text
Semana_3/Formativa/MCDI503_F4_Formativa_Grupo6/
```

Producto principal:

```text
Reports/mcdi503_f4_formativo_grupo6.pdf
```

### Evaluación Sumativa Fase 4

Corresponde al cierre técnico del proyecto mediante un pipeline exploratorio reproducible que integra:

- transformaciones y normalizaciones;
- creación de variables derivadas;
- codificación de variables categóricas;
- selección preliminar de características;
- auditorías de decisiones y efectos;
- validaciones de integridad y trazabilidad;
- dataset enriquecido;
- matriz candidata y target separados;
- informe final y material de presentación.

Ruta:

```text
Semana_3/Sumativa/MCDI503_F4_Sumativa_Grupo6/
```

Resultados estructurales del cierre:

- registros preservados: **891**;
- variables originales conservadas: **15**;
- dataset preparado de entrada: **891 × 29**;
- dataset enriquecido final: **891 × 36**;
- matriz candidata de características: **891 × 10**;
- matriz candidata sin valores faltantes;
- target separado de la matriz de características;
- validaciones finales del pipeline superadas.

---

## Continuidad y trazabilidad de los datos

El proyecto mantiene el mismo conjunto de observaciones de Titanic durante las distintas fases.

La continuidad entre las Semanas 2 y 3 se conserva mediante el archivo:

```text
titanic_f23_prepared.csv
```

La copia generada en la Sumativa de Semana 2 y la utilizada como entrada en la Sumativa de Semana 3 corresponden al mismo artefacto preparado, permitiendo mantener trazabilidad entre preparación, ingeniería de variables y selección preliminar.

Los archivos originales se conservan separados de los productos derivados mediante las carpetas `data/input/` y `data/process/`.

---

## Reproducibilidad

Las dependencias se documentan **por entrega técnica**, ya que los entornos utilizados en las distintas fases no son idénticos. Por esta razón, el repositorio no utiliza un `requirements.txt` global.

Los proyectos que contienen notebooks reproducibles incorporan su propio archivo de dependencias:

```text
Semana_1/MCDI503_F1_Formativa_Grupo6/requirements.txt
Semana_1/MCDI503_F1_Sumativa_Grupo6/requirements.txt
Semana_2/MCDI503_F2_Sumativa_Grupo6/requirements.txt
Semana_3/Sumativa/MCDI503_F4_Sumativa_Grupo6/requirements.txt
```

La Semana 1 incorpora adicionalmente archivos `environment.yml` y controles SHA-256. Las fases posteriores mantienen trazabilidad mediante manifiestos, registros del entorno, controles de entrada y archivos de auditoría generados por los propios notebooks.

Los notebooks se encuentran ejecutados y conservan código, narrativa y resultados de la corrida correspondiente a cada entrega.

### Reproducción de una entrega técnica

Desde la raíz del subproyecto que se desea reproducir:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Luego debe abrirse el notebook indicado en el `README.md` de esa entrega y ejecutarse desde el inicio, manteniendo la estructura original de carpetas para preservar las rutas relativas.

---

## Entregables académicos principales

| Semana | Evaluación | Producto principal |
|---|---|---|
| 1 | Formativa 1 | `Semana_1/MCDI503_F1_Formativa_Grupo6/Reports/mcdi503_f1f_grupo6.pdf` |
| 1 | Sumativa 1 | `Semana_1/MCDI503_F1_Sumativa_Grupo6/Reports/mcdi503_f1_sumativo_grupo6.pdf` |
| 2 | Formativa 2 | `Semana_2/MCDI503_F2_Formativa_Grupo6/mcdi503_f23f_grupo6.pdf` |
| 2 | Sumativa 2 | `Semana_2/MCDI503_F2_Sumativa_Grupo6/Reports/mcdi503_f23_sumativo_grupo6.pdf` |
| 3 | Formativa Fase 4 | `Semana_3/Formativa/MCDI503_F4_Formativa_Grupo6/Reports/mcdi503_f4_formativo_grupo6.pdf` |
| 3 | Sumativa Fase 4 | `Semana_3/Sumativa/MCDI503_F4_Sumativa_Grupo6/reports/mcdi503_f4_sumativa3_grupo6.pdf` |

El notebook ejecutado y los artefactos técnicos correspondientes permanecen dentro de cada subproyecto.

---

## Alcance metodológico

El trabajo desarrollado es de carácter exploratorio y de preparación analítica. Las asociaciones observadas en el dataset no se interpretan como relaciones causales. La selección de características de la Fase 4 es **preliminar** y deja una base reproducible preparada para una eventual etapa posterior de modelamiento y validación predictiva.

---

## Estado del proyecto

Las Semanas 1, 2 y 3 se encuentran organizadas como una secuencia continua del mismo proyecto sobre Titanic. La estructura del repositorio separa claramente entregas formativas, sumativas, datos originales, productos procesados, notebooks, salidas, figuras e informes, manteniendo trazabilidad entre fases y evitando sobrescribir los insumos originales.
