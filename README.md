# Análisis de Casos Positivos de COVID-19

## Descripción del proyecto
Este proyecto presenta un análisis exploratorio de los casos de COVID-19 en Colombia utilizando datos abiertos del gobierno.
El objetivo es identificar patrones clave en contagios, recuperación y mortalidad, apoyando la comprensión del impacto de la pandemia.

## Insights clave
* Alta concentración de casos en ciudades principales como Bogotá, Medellín y Cali
* **La tasa de mortalidad aumenta significativamente a partir de los 60 años**
* Mayor número de casos en mujeres, posiblemente asociado a factores de exposición
* Picos de contagio en periodos específicos, relacionados con dinámicas sociales y medidas sanitarias
* Alta tasa de recuperación en comparación con fallecimientos

## Visualizaciones
### Distribución geográfica de casos
<img width="424" height="237" alt="mapa" src="https://github.com/Juan-David-DA/casos_positivos_COVID/blob/main/imgs/imgs/mapa.png" />

### Evolución de casos en el tiempo
<img width="425" height="200" alt="evolucion" src="https://github.com/Juan-David-DA/casos_positivos_COVID/blob/main/imgs/imgs/evolucion.png" />

### Casos por género
<img width="337" height="138" alt="casos_por_genero" src="https://github.com/Juan-David-DA/casos_positivos_COVID/blob/main/imgs/imgs/casos_por_genero.jpg" />

### Recuperación vs. Fallecimientos
<img width="337" height="138" alt="casos_por_genero" src="https://github.com/Juan-David-DA/casos_positivos_COVID/blob/main/imgs/imgs/recuperacion.jpg" />

---

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
