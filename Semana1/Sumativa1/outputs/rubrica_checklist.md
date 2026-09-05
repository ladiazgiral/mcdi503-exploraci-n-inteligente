# Validación interna - Rúbrica Sumativa S01

Esta matriz se utiliza como control previo de la entrega. No sustituye la calificación docente.

| Criterio | Evidencia en la entrega |
|---|---|
| Portada e índice / organización del PDF | PDF institucional, portada con curso, título, integrantes, docente, fecha e índice visible; apartados II-IX identificables. |
| Introducción y contextualización | PDF II: contexto, problema, propósito, valor del EDA y vínculo con Titanic. |
| Objetivo, decisiones y alcance | PDF III + V-VII; notebook II, V y VII. Mantiene exactamente las cinco preguntas de la Formativa 1. |
| Notebook ejecutado y flujo del EDA | Notebook ejecutado de principio a fin; 13 celdas de código con ejecución 1-13; secuencia pregunta → acción → resultado. |
| Documentación trazable | Notebook V incluye decisiones D1-D6 con motivo y resultado intermedio. |
| Reproducibilidad y coherencia | Rutas relativas, entrada inmutable, data/process, figures, outputs, SHA-256, versiones y manifiesto. |
| Registro del proceso, supuestos y limitaciones | Notebook VII y PDF VII. |
| Síntesis de hallazgos + referencias | PDF VIII incluye resultados cuantificados y referencias a secciones/figuras del notebook. |
| Aspectos formales | PDF de 3 páginas tamaño carta, formato institucional, bibliografía APA 7 y gráficos generados por el notebook. |

## Continuidad Formativa 1 → Sumativa S01

- Mismo proyecto y dataset.
- Mismas cinco preguntas exploratorias.
- Misma secuencia de EDA planificada.
- `FamilySize` se implementa como transformación principal planificada.
- `Fare` se analiza explícitamente respecto de **Pclass y Survived**, cerrando la pregunta 4 de la Formativa.
- La calidad del dato se mantiene como etapa transversal, no como una sexta pregunta.
- `IsAlone` queda documentada solo como extensión secundaria surgida durante la ejecución.
