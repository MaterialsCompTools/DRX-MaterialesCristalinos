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

