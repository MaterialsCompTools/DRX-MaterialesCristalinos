# DRX-MaterialesCristalinos
Manejo de softwares para datos de DRX<br>
![DRX- presentación-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/03bfc4cb-fb9a-429c-a7b8-94004ef78fe8)

## Objetivos del curso
Familiarizar al estudiante con las diferentes herramientas matemáticas y computacionales para el análisis de los datos de difracción de rayos de materiales. Esto, con el fin de que aprenda a extraer información valiosa como cantidad y tipos de fases cristalinas presentes en un material, así como calcular parámetros de red, tamaños de cristalito y microdeformaciones. Todos los ejemplos se harán con un patrón de difracción de rayos X que consta de dos fases cristalinas, aluminio y corindón.<br>

## Sección 1: Indexación de picos de patrones de difracción<br>

|    Microcontenidos     | Contenido |
|------------------------|:---------------------|
| [Qué es MATCH!](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#qu%C3%A9-es-match)| En este apartado aprenderás qué es MATCH!|
| [Tipos de archivos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#interfaz-de-match)| En este apartado aprenderás qué tipo de archivo puede utilizarse en MATCH!|
| [Interfaz](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#cargue-de-archivo)| En este apartado aprenderás cómo es la interfaz de MATCH!|
| [Cargue de archivo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#cargue-de-archivo)      | En este archivo aprenderás a cargar el archivo de trabajo, corroborar la longitud de onda de los rayos X utilizados, eliminar la difracción del kalfa-2 y definir el background de la medida.|
| [Indexación de picos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#indexaci%C3%B3n-de-picos)    | En este apartado aprenderás a hacer búsqueda y reconocimiento de picos, correr la identificación de picos, seleccionar las fases, revisar la información cristalográfica de la fase, e indexar los picos.|
| [Refinamiento automático](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n01/Readme.md#refinamiento-autom%C3%A1tico)| En este apartado aprenderás cómo usar el MATCH! para cuantificar las fases presentes en el material.|
| [Exportación de archivos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n01/Readme.md#resultados)| En este apartado aprenderás a exportar archivos dependiendo de la necesidad que se tenga.|

## Sección 2: Determinación de rasgos cristalográficos<br>

|    Microcontenidos          | Contenido |
|-------------------------------------|:---------------------|
| [Qué es Origin](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#qu%C3%A9-es-origin)                       | En este apartado aprenderás qué es Origin.|
| [Tipos de archivos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#extensiones-de-archivos-de-trabajo)                  | En este apartado aprenderás qué tipo de archivo puede utilizarse en Origin.|
| [Interfaz](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/Readme.md#interfaz-de-origin)                            | En este apartado aprenderás cómo es la interfaz de Origin.|
| [Importar archivo y reporte de patrón](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/Readme.md#importar-archivo-y-reportar-el-patr%C3%B3n-de-drx)          | En este apartado aprenderás a abrir los archivos de DRX del Match! y a reportar el difractograma.|
| Ajuste de picos                     | En este apartado aprenderás a hacer el ajuste de los picos de forma individual para extraer la información del ancho a la altura media del pico y la posición del mismo.|
| Cálculo de parámetros de red        | En este apartado aprenderás en qué consiste el método de las funciones de extrapolación y cómo se usa este para el cálculo de parámetros de red de estructuras cristalinas.|
| Williamson-Hall                     | En este apartado aprenderás a aplicar el método de Williamson-Hall para calcular las microdeformaciones y el tamaño de cristalito|
| Cálculo de densidad de dislocaciones| En este apartado aprenderás a calcular la densidad de dislocaciones.|

## Sección 3: Determinación de porcentajes de fases por refinamiento Rietveld<br>

|    Microcontenidos          | Contenido |
|-----------------------------|:---------------------|
| Qué es FullProf                             | En esta apartado aprenderás qué es FullProf|
| Refinamiento Rietveld                       | En este apartado aprenderás qué es el método Rietveld.|
| Preparación de archivos                     | En este apartado aprenderás a preparar los archivos para llevar a cabo el refinamiento con FullProf: .CIF, .DAT y .BGR.|
| Interfaz                                    |En este apartado aprenderás cómo es la interfaz del FullProf.|
| Creación del archivo .PCR de la primera fase| En este apartado aprenderás a crear el archivo .PCR de la primera fase|
| Cargue del archivo .BGR                     | En este apartado aprenderás a cargar el archivo .BGR|
| Refinamiento de la primera fase             | En este apartado aprenderás a cómo llevar a cabo el refinamiento paso a paso de la primera fase del material usando FullProf|
| Creación del archivo .PCR de la segunda fase| En este apartado aprenderás a crear el archivo .PCR de la segunda fase|
| Adición del archivo .PCR de la segunda fase al de la primera fase| En este apartado aprenderás a adicionar la información del archivo .PCR de la segunda fase en el archivo .PCR de la primera fase|
| Refinamiento de la segunda fase             | En este apartado aprenderás a cómo llevar a cabo el refinamiento paso a paso de la segunda fase del material usando FullProf|
| WinPlotr                                    | En este apartado aprenderás a usar WinPlotr para extraer información después del refinamiento.|
| Archivos de salida                          | En este apartado aprenderás a extraer la información después del proceso de refinamiento.|
