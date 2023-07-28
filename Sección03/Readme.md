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

Ya veíamos las funciones más utilizadas para simular los picos difractados, en el apartado de [Picos difractados](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#ajuste-de-picos)


