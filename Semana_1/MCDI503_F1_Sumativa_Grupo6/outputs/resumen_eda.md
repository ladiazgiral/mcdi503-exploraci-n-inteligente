# Resumen EDA - Sumativa S01

## Identidad de la ejecución
- Fuente: dataset `titanic` de Seaborn mediante copia local auditada.
- SHA-256: `43af81a01f25a7771c9a42809a31625f4d0de3f335cdf29961f9ba179a86c13d`.
- Entrada: 891 filas × 15 columnas.
- Procesado: 891 filas × 17 columnas.

## Resultados principales
- Supervivencia global: 38.4%.
- Mujeres: 74.2%.
- Hombres: 18.9%.
- pclass 1/2/3: 63.0% / 47.3% / 24.2%.
- `age` faltantes: 177 (19.9%).
- `deck` faltantes: 688 (77.2%).
- Mediana de `age`: 28 años en no sobrevivientes y 28 años en sobrevivientes.
- Mediana global de `fare`: 14.45.
- Límite superior IQR de `fare`: 65.63.
- `fare` fuera de límites IQR: 116 observaciones.
- Mediana de `fare` por pclass 1/2/3: 60.29 / 14.25 / 8.05.
- Supervivencia viajando solo: 30.4%.
- Supervivencia con familiares: 50.6%.

## Decisiones metodológicas
- No se imputan faltantes en S01.
- No se eliminan automáticamente valores extremos de `fare`.
- No se eliminan automáticamente las 107 filas completamente coincidentes por ausencia de un identificador individual único.
- Las asociaciones son descriptivas y no se interpretan causalmente.
