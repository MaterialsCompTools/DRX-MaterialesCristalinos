<div align="center"> 

# Determinación de porcentajes de fases por refinamiento Rietveld. 

![FullProf logo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/aa82ea0c-a328-46fa-aaf3-bc19419ba279)

</div> 

## Objetivos

* Conocer qué es el método Rietveld
* Conocer para qué sirve el _software_ FullProf
* Conocer los archivos de trabajo del software
* Utilizar FullProf para llevar a cabo el refinamiento Rietveld de un patrón de DRX
* Conocer los archivas de salida del _software_

## Requerimientos

* Descargar la versión del software que más le convenga: [FullProf Suite](https://www.ill.eu/sites/fullprof/php/downloads.html)

## Qué es FullProf

FullProf es una herramienta para el refinamiento rietveld de forma automatizada.

## Refinamiento Rietveld

Es una técnica de refinamiento con precisión alta que se usa para determinar los parámetros estructurales de una muestra de análisis. Esto se hace a partir de la construcción de un modelo teórico que se ajuste al patrón de difracción experimental, usando el métodod de mínimos cuadrados.

Para esto, lo primero que se hace es calcular la intensidad total en cada uno de los puntos del difractograma. La intensidad a calcular en un punto _i_ está dada por la siguiente ecuación:

<div align="center">

$y_{ci} = {(𝜇_{m})^{-1}} [(Φ_{rsi}) \displaystyle\sum_{Φ}^{} S_Φ \displaystyle\sum_{hΦ}^{} J_{hΦ} Lp_{hΦ} {\lvert F_{hΦ} \rvert^2} G_{hΦi} P_{h}] + y_{bi}$

</div>

A continuación se muestra qué significa cada término:

$𝜇_{m}$ es el Coeficiente de absorción de la mezcla<br>
$Φ_{rsi}$ es la corrección por rugosidad superficial en el punto _i_ <br>
$S_Φ$ es el factor de escala de la fase<br>
$J_{hΦ}$ es la multiplicidad del plano _(hkl)_ de la fase Φ<br>
$Lp_{hΦ}$ es el factor de polarización de Lorentz de la fase Φ (La radiación dispersada se polariza parcialmente, creando una anisotropía con relación a la dirección de vibración del electrón, y una reducción de la intensidad dispersada.)<br>
$F_{hΦ}$ es el factor de estructura asociado con al plano _(hkl)_ de la fase Φ (Efecto de interferencia interna debido a las relaciones de fase geométrica entre todos los átomos incluidos en la celdilla unidad.)<br>
$G_{hΦi}$ es la función del perfil de las líneas de difracción asociadas a los planos _(hkl)_ de la fase φ<br>
$P_{h}$ es el valor de la función de corrección por orientación preferencial del plano _(hkl)_ <br>
$y_{bi}$ es la contribución de la radiación de fondo (_background_) <br>

Como puede verse, la ecuación tiene en cuenta la contribución de todas las fases<br>

Los patrones experimental y teórico se comparan por medio del método de mínimos cuadrados:

<div align="center">

$M = \displaystyle\sum_{j}^{} {\frac{{(y_{0j}-y_{cj})^2}}{{y_{0j}}}}$

</div>

Esa función se minimiza con relación a los M parámetros de refinamiento, así: $\frac{{𝜕M}}{{𝜕p_i}}$

Los parámetros de refinamiento son:<br>
* Coeficientes de la expansión en series de la función que describe el background (línea base)
* El factor de escala
* Los parámetros de red
* Los coeficientes en la función del perfil

Ya veíamos las funciones más utilizadas para simular los [Picos difractados](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#ajuste-de-picos)<br>
También veíamos las causas del [ensanchamiento de los picos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#ensanchamiento-de-picos)

El ancho para una curva Gaussiana puede escribirse así:

<div align="center">

$Γ_G= U tan^2 (θ) + V tan(θ) +W + \frac{{V}}{{cos^2 (θ)}}$

</div>

El ancho para una curva Lorentziana puede escribirse así:

<div align="center">

$Γ_L= Y tan (θ) + \frac{{X}}{{cos (θ)}}$

</div>

U y Y corresponden a la contribución al ensanchamiento por las microdeformaciones<br>
X y P corresponden a la contribución al ensanchamiento por el tamaño de cristalito<br>
V y W corresponden al ensanchamiento instrumental<br>

## Preparación de archivos

Para trabajar con esta herramienta se requieren 3 archivos de entradas con las siguientes extensiones:

* **.CIF** es el archivo que contienen la información cristalográfica de la fase que se va a refinar
*  **.DAT** es el archivo que se exporta de MATCH!, que contiene la información experimental del patrón a refinar
*  **.BGR** es el archivo que contiene los puntos del _background_ o radiación de fondo

### Archivos .CIF

El archivo con extensión .CIF puede descargarse de MATCH! Es el archivo que usamos para llevar a cabo la indexación. Para ello, abrimos nuestro archivo en **MATCH!** y abrimos el <kbd>DATA SHEET</kbd> de nuestra fase. Haciendo click en el número al lado de <kbd>Link to orig. entry</kbd> podemos descargar el archivo.

![Figura 115](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/baadf049-19aa-45f2-a13c-f6ee4a558234)

Esto automáticamente descarga el archivo, que queda con el nombre según el número:

<div align="center">

![Figura 116](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/6faa544e-f815-47ce-95ec-da947538362a)

</div>

Se recomienda cambiarle al nombre según la fase de trabajo.

Otra opción para descargar un archivo con extensión **.CIF** sin acceder al MATCH!, es yendo directamente a la **base de datos** [Crystallography Open Database](http://www.crystallography.net/cod/)


<div align="center">

![Imagen1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/f32b19c5-9657-44f4-aaa6-2254bc7ba4ae)

</div>

Damos _click_ en <kbd>SEARCH</kbd>, en el menú de la parte izquierda:

![Imagen2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/7150132d-d5b2-4db2-a7e0-e912e6934c10)

Inmediatamente se abre una nueva página, que nos pide información sobre la fase de la que necesitamos el archivo **.CIF**. Escribimos el nombre o fórmula química de la fase. Para efectos de este ejercicio práctico empezaremos con la fase 1, que es la de aluminio.

![Imagen3](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/3013dd04-757e-4b19-9f7b-452414ad5735)

Esto nos despliega una lista de todos los archivos relacionados.

![Imagen4](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/ccd76213-61fc-4a9b-8dad-03f0a1e37d4b)

Damos _click_ en aquel que corresponda químicamente a nuestro material. Inmediatamente el archivo se descarga.

![Imagen5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8d0bf813-8828-449b-8a36-86ef41b8bec0)

De nuevo, se recomienda cambiarle al nombre según la fase de trabajo.

**NOTA**: lo más adecuado es descargar el archivo de MATCH! porque será el de mejor coincidencia con nuestro patrón experimental. Esto facilitará las cosas a la hora del refinamiento Rietveld.

Guardamos los archivos con extensión **.CIF** de las fases que vamos a refinar. En nuestro caso, alumunio y alúmina ($Al_2O_3$)

![Imagen6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/66b553db-bd99-44ab-85a4-4df655dc4b7f)

### Archivos .DAT

El archivo de nuestro patrón de difracción con extensión .DAT que usa FullProf tiene algunas algunas características: En la primera fila deben ir el ángulo 2Theta de inicio de los datos; el paso (que es la diferencia que hay de un punto a otro); y el ángulo 2 Theta de finalización de los datos. Después tenemos columnas de datos con la información de las intensidades.

![Imagen7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1d46d055-c4dd-4013-8847-36d79fbad6ab)

Para descargar este archivo de MATCH! vamos a <kbd>File</kbd>, <kbd>Export</kbd> y <kbd>Profile data</kbd>. 

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/973dccd4-1fe1-45f0-8848-59b3405766f7)

Al dar _click_ se nos abre una ventana que nos pregunta la ruta para guardar el archivo (la seleccionamos o buscamos), el nombre del archivo (lo cambiamos si es necesario) y el **tipo de archivo**. Desplegamos la ventana y escogemos <kbd>Profile (start,step,end, intensities)(*dat)</kbd>.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/97dfbd39-abeb-4ba7-8636-9342ad891802)

Al dar _click_ se nos genera el archivo:

![Imagen9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1e51604f-ed7d-42e6-a580-909c6766d7a1)

### Archivo .BGR

Para crear el archivo con extensión **.BGR** abrimos el FullProf. De la barra de tareas clickeamos en el botón que se muestra a continuación. 

![Imagen11](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1120204b-b01d-480f-a4cd-3cfcdb6108aa)

Esto abre la ventana de **WinPLOTR**. Ahí damos _click_ en <kbd>File</kbd>

![Imagen14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/7d7aef94-f2a9-4610-bb79-4a6557125572)

Damos _click_ en <kbd>Open pattern file </kbd>

![Imagen15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/c9f724c8-b66e-4429-858f-adb05a76b0ed)

Seleccionamos la segunda opción y damos <kbd>OK</kbd>.

![Imagen16](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8a973a09-2e71-4a3b-ba58-c6ac9d701d92)

Abrimos el archivo **.DAT** que habíamos guardado:

<div align="center">

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/2b525664-c467-4cde-8cab-9cd592acfa05)

</div>

Esta acción abre el archivo

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/c18ded0b-4909-44e3-a129-5c22e5e724fb)

En <kbd>Points Selection</kbd> escogemos <kbd>Automatic Background<7kbd>

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/84cfe6c7-406f-4070-a8ec-3d4f43a63292)

Eso nos abre una ventana que nos pide información.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/445697b8-07c5-46f0-ad6c-064a3bf98380)

En <kbd>Background threshold</kbd> un valor entre 0.05 y 0.07 funciona bien. Esto está relacionado con la cantidad de puntos que tendrá el archivo del background.

La cantidad de puntos generada fue de 68. Podemos cerrar la ventanita.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/fd1a476c-7bc1-471b-a15b-a257ec6e3603)

Puede verse que en azul está representado nuestro patrón experimental, y en verde aparecen los puntos del _background_.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/2e5d8a81-1a2b-4c68-b6d1-c007c5fefe2d)

Para guardar los datos vamos a <kbd>Points Selection</kbd>  y escogemos <kbd>SaVe background points</kbd>. Nospregunta, y le decimos que <kbd>sí</kbd>.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/81b02afe-f2ac-4d6b-8838-9c563a16f630)

Nombramos el archivo, cuidando de que la extensión sea **.BGR**.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/40d3e82e-a97d-47a2-a8ca-9b022bbf62d5)

Se nos confirma que se ha creado el archivo con la cantidad de puntos correspondiente.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/3a9e60c0-ac85-4cbd-9f1f-adcaadf5e782)

Si se desea, podemos editar el archivo. Yo diré que no.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/eab694f6-8003-427a-9e5f-a2eab524f6a3)

Ya tenemos listos los 4 archivos

* 2 archivos **.CIF** con la información cristalográfica de las fases <br>
* 1 archivo **.DAT** con la información experimental del patrón DRX que vamos a refinar<br>
* 1 archivo **.BGR** con la información del background o radiación de fondo<br>

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/804fed5b-cbf6-4df9-b285-c95ae419a00c)

## Creación de archivo .PCR de la primera fase

Abrimos el _software_ FullProf. Esto abre la barra de tareas.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/db4576d4-6005-4c8b-b070-817ebe05249c)

Abrimos <kbd>ED PCR</kbd>. Eso hace que se abra una ventana, como se ve abajo, que es el **editor de archivos PCR**. Usamos el ícono de CIF $\rightarrow$ Pcr.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/dc5941fb-0348-4ff1-afa2-d3c12dab3e02)

Damos doble _click_ al archivo de la fase con la que vamos a trabajar. En este caso, **Al.cif**. Esto abre una ventana con la información cristalográfica de la fase, como los parámetros de red y el grupo espacial. Verificamos que la información corresponda a la de nuestra fase y damos <kbd>OK</kbd>.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/109d7ddb-a8d0-45f4-8259-28a98ab0c0bf)

Con esta acción volvemos a quedar en el editor de archivos PCR. Aquí podemos observar 7 botones. Vamos a trabajar sobre los 3 primeros: <kbd>General</kbd>, <kbd>Patterns</kbd> y <kbd>Phases</kbd>.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b5da99f2-b80e-4452-a34a-186909c6521d)

Primero damos _click_ en <kbd>General</kbd>
