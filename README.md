# Análisis de Casos Positivos de COVID-19

## Descripción del proyecto
Este proyecto presenta un análisis exploratorio de datos (EDA) y un proceso de limpieza y transformación sobre casos positivos de COVID-19 en Colombia.

El objetivo principal es preparar un dataset limpio, consistente y estructurado que permita realizar análisis posteriores y visualizaciones en herramientas como Power BI.

El archivo principal es:

- `Casos_positivos_COVID.ipynb`: Notebook con el análisis, limpieza y transformación de los datos.
- Acceder a los datasets y al tablero de Power BI: [Drive](https://drive.google.com/file/d/1h7dFzPYGxl9f46B32VI2OiwYtJbxK_eS/view?usp=drive_link)

---

## Contenido del notebook

### 1. Análisis Exploratorio (EDA)
Se realiza una revisión inicial del dataset para identificar:

- Valores nulos
- Variables irrelevantes
- Calidad general de los datos

#### Hallazgos clave:
Se detectaron columnas con más del **95% de valores nulos**, entre ellas:

- Código ISO del país  
- Nombre del país  
- Nombre del grupo étnico  
- Fecha de muerte  

Decisión:
- Se eliminan las tres primeras columnas por su irrelevancia.
- Se conserva **Fecha de muerte** por su valor analítico (relación con fallecimientos).

---

### 2. Limpieza de Datos

#### Imputación de valores
Se encontró que cuando ciertas columnas tienen valores nulos, la columna *Fecha de muerte* sí tiene datos.

Columnas afectadas:
- Ubicación del caso  
- Estado  
- Recuperado  
- Tipo de recuperación  

Acción:
- Se imputa el valor **"Fallecido"** en estos campos cuando corresponde.

---

#### Eliminación de columnas
Se eliminan columnas con alta proporción de datos faltantes y bajo valor analítico.

---

### 3. Guardado de datos
El dataset limpio se exporta para su uso posterior.

Nota:
Se dejan algunos aspectos pendientes intencionalmente para procesamiento adicional en Power Query para práctica de limpieza con esta herramienta:

- Valores vacíos en "fecha de inicio de síntomas"
- Valores nulos en "Tipo de recuperación"

---

### 4. Revisión previa a Power Query
Se analiza la viabilidad de eliminar registros incompletos.

Conclusión:
- No se eliminan filas con fecha de inicio de síntomas nula
- Esto evita pérdida de información importante en otras variables como:
  - Ubicación
  - Estado

---

## Objetivo final

Obtener un dataset:

- Limpio  
- Consistente  
- Listo para análisis o visualización  
- Compatible con herramientas externas como Power Query  

---

## Notas adicionales

- El enfoque del notebook es principalmente de **preprocesamiento de datos**
- Algunas decisiones de limpieza están orientadas a mantener la mayor cantidad de información posible
- Se prioriza la integridad del dataset sobre la eliminación agresiva de registros
