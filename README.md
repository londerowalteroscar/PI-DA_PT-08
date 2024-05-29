# PROYECTO INDIVIDUAL Nº2 - Siniestros Viales

## Descripción del Problema
Los siniestros viales son eventos que involucran vehículos en las vías públicas y pueden tener graves consecuencias. En Buenos Aires, estos incidentes son una preocupación debido al alto volumen de tráfico y densidad poblacional. Reducir las tasas de mortalidad por siniestros viales es crucial para mejorar la seguridad vial. En Argentina, los siniestros viales causan alrededor de 4.000 muertes al año, siendo una de las principales causas de muertes violentas. El Observatorio de Movilidad y Seguridad Vial solicita un proyecto de análisis de datos para ayudar a reducir las víctimas fatales de siniestros viales en Buenos Aires, proporcionando un dataset sobre homicidios en siniestros viales ocurridos entre 2016-2021.

El dataset se encuentra en: [https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales)

## Contexto
En Argentina, los siniestros viales causan un alto número de muertes cada año, superando incluso a otras causas de muerte violenta. El Observatorio de Movilidad y Seguridad Vial de Buenos Aires busca reducir estas cifras proporcionando información para tomar medidas efectivas.

## Rol a Desarrollar
El proyecto implica el análisis de datos sobre homicidios en siniestros viales en Buenos Aires entre 2016 y 2021. El objetivo es proporcionar información que permita a las autoridades locales tomar medidas para reducir la cantidad de víctimas fatales.

## ETL (Extracción, Transformación y Carga)

### Extracción
Se utilizan las siguientes librerías:

(Contenido de requirements.txt)

Los datos se extraen de un archivo de Google Sheets:

[https://docs.google.com/spreadsheets/d/1nq00jGIZHQ1RLSET43zKnUsMsoFb-pBg/export?format=xlsx](https://docs.google.com/spreadsheets/d/1nq00jGIZHQ1RLSET43zKnUsMsoFb-pBg/export?format=xlsx)

### Transformación

#### Explorar y Limpiar Datos:
- Se carga la información de cada hoja del archivo en un DataFrame diferente.
- Se reemplazan valores nulos y se unifican formatos.
- Se eliminan columnas con demasiados datos faltantes y duplicados.
- Se renombran columnas para facilitar el merge.

#### Explorar y Transformar Datos:
- Se corrigen mayúsculas y minúsculas en los nombres de las columnas.

#### Unificar Datasets:
- Se eliminan columnas repetidas en uno de los DataFrames.
- Se fusionan los DataFrames utilizando la columna "ID".

### Carga
Se guarda el DataFrame resultante en un archivo CSV llamado `viales_clean.csv`.

## EDA (Análisis Exploratorio de Datos)

### Exploración
Se importan las librerías necesarias y se carga el archivo `viales_clean.csv`.

### Variables Categóricas
Se analizan las siguientes variables categóricas:
- ROL
- SEXO
- LUGAR_DEL_HECHO
- TIPO_DE_CALLE
- CALLE
- CRUCE
- DIRECCIÓN_NORMALIZADA
- PARTICIPANTES
- VICTIMA
- ACUSADO

### Variables Numéricas
Se utilizan mapas de boxplot para detectar outliers en las variables:
- EDAD
- N_VICTIMAS
- AAAA
- MM
- DD
- HH
- COMUNA

Se genera un mapa de correlación para analizar las relaciones entre las variables numéricas seleccionadas.

### Análisis de la Variable de Interés: N_VICTIMAS
Se realizan los siguientes análisis:
- Histograma de frecuencias.
- Gráfico de barras de víctimas.
- Evolución anual de víctimas.
- Evolución mensual promedio de víctimas.
- Evolución promedio de víctimas por hora del día.
- Evolución promedio por día del mes de víctimas.
- Promedio de edad de víctimas.
- Relación entre rol y sexo de la víctima.
- Relación entre sexo y acusado.
- Frecuencia según el sexo tanto para rol como para acusado.

### Mapa de Distribución Espacial de Siniestros
Se genera un mapa que muestra la distribución geográfica de los siniestros viales en las diferentes comunas de Buenos Aires.

## Nota
Este README proporciona una descripción general del proyecto y su contenido. Para obtener más detalles, consulta los Jupyter Notebooks `ETL.ipynb` y `EDA.ipynb`.

