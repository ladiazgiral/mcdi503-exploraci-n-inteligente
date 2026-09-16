# MCDI503 - Exploración Inteligente para la Ciencia de Datos

## Proyecto Fase 1 - Grupo 6

Repositorio académico correspondiente a la **Fase 1** de la asignatura **MCDI503 - Exploración Inteligente para la Ciencia de Datos**.

El proyecto desarrolla una primera aproximación reproducible al análisis exploratorio de datos utilizando el conjunto **Titanic** distribuido mediante Seaborn. La Fase 1 se organiza en dos entregas complementarias: una **evaluación formativa**, orientada a la definición del proyecto, caracterización inicial del dataset y planificación del EDA; y una **evaluación sumativa**, centrada en la implementación reproducible del análisis, documentación de decisiones, transformaciones y resultados exploratorios.

## Integrantes

- Luis Díaz
- Gonzalo Bouldres
- Eduardo Contreras

**Docente:** Sergio Paraíso

## Estructura del repositorio

```text
Semana_1/
├── MCDI503_F1_Formativa_Grupo6/
│   ├── data/
│   ├── notebooks/
│   ├── outputs/
│   ├── Reports/
│   ├── README.md
│   ├── SHA256_INPUT.txt
│   ├── environment.yml
│   └── requirements.txt
│
└── MCDI503_F1_Sumativa_Grupo6/
    ├── data/
    ├── figures/
    ├── notebooks/
    ├── outputs/
    ├── Reports/
    ├── README.md
    ├── SHA256_INPUT.txt
    ├── environment.yml
    └── requirements.txt
```

## Fase 1 Formativa

La carpeta `MCDI503_F1_Formativa_Grupo6` contiene la definición inicial del proyecto y la evidencia técnica utilizada para caracterizar el conjunto de datos y planificar el análisis exploratorio.

Incluye:

- caracterización inicial del dataset;
- identificación de variables, tipos y valores faltantes;
- preguntas exploratorias P1-P5;
- supuestos y limitaciones preliminares;
- organización prevista del EDA;
- criterios iniciales de reproducibilidad;
- notebook ejecutado de planificación y caracterización;
- informe formativo en PDF.

## Fase 1 Sumativa

La carpeta `MCDI503_F1_Sumativa_Grupo6` contiene la implementación reproducible del EDA planificado.

Incluye:

- notebook ejecutado de principio a fin;
- diagnóstico de calidad de datos;
- análisis univariado y bivariado;
- transformaciones derivadas (`FamilySize` e `IsAlone`);
- documentación trazable de decisiones exploratorias;
- tablas y figuras generadas mediante código;
- manifiesto del entorno de ejecución;
- validación técnica de coherencia;
- informe sumativo en PDF.

## Dataset

Se utiliza el conjunto `titanic` distribuido mediante Seaborn.

Archivo de entrada:

```text
titanic_seaborn.csv
```

Dimensiones:

```text
891 registros × 15 variables
```

SHA-256:

```text
43af81a01f25a7771c9a42809a31625f4d0de3f335cdf29961f9ba179a86c13d
```

El archivo original se conserva sin sobrescritura y las transformaciones se realizan mediante código reproducible.

## Reproducibilidad

Cada entrega mantiene de forma independiente:

- `requirements.txt`, con las dependencias utilizadas;
- `environment.yml`, con la definición del entorno;
- `SHA256_INPUT.txt`, para verificar la integridad del dataset;
- rutas relativas dentro del proyecto;
- separación entre datos de entrada, productos derivados, notebooks, figuras y reportes;
- archivos `.gitignore` y `.gitattributes` para evitar artefactos temporales y preservar la integridad del archivo de entrada.

Los notebooks incluyen celdas narrativas y código ejecutable con trazabilidad entre datos, decisiones, transformaciones y resultados.

## Entregables

### Formativa
- `Semana_1/MCDI503_F1_Formativa_Grupo6/Reports/mcdi503_f1f_grupo6.pdf`

### Sumativa
- `Semana_1/MCDI503_F1_Sumativa_Grupo6/Reports/mcdi503_f1_sumativo_grupo6.pdf`
- `Semana_1/MCDI503_F1_Sumativa_Grupo6/notebooks/mcdi503_f1_sumativo_grupo6.ipynb`

## Alcance

El análisis desarrollado en la Fase 1 es de carácter exploratorio y descriptivo. Los resultados permiten caracterizar el comportamiento de las variables disponibles y documentar asociaciones observadas dentro del conjunto de datos, sin establecer relaciones causales.
