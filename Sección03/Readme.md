<div align="center">
   
<div align="center"><a href="https://www.escuelaing.edu.co/es/investigacion-e-innovacion/centro-de-estudios-de-gestion-de-tecnologia-e-innovacion/" target="_blank"><img src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20CGTEI%20png.png" alt="R.LTWB" width="80%" border="0" /></a></div>

</div><br>

<div align="center"> 

# Determinación de porcentajes de fases por refinamiento Rietveld

![FullProf logo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/FullProf%20logo%20PNG.png)

</div> 

## Objetivos

* Conocer qué es el método Rietveld
* Conocer para qué sirve el _software_ FullProf
* Conocer los archivos de trabajo del _software_
* Utilizar FullProf para llevar a cabo el refinamiento Rietveld de un patrón de DRX
* Conocer los archivos de salida del _software_

## Requerimientos

* Descargar la versión del _software_ que más le convenga: [FullProf Suite](https://www.ill.eu/sites/fullprof/php/downloads.html)

## Qué es FullProf

FullProf es una herramienta para el refinamiento rietveld de forma automatizada.

## Refinamiento Rietveld

<div align="justify">

Es una técnica de refinamiento con precisión alta que se usa para determinar los parámetros estructurales de una muestra de análisis. Esto se hace a partir de la construcción de un modelo teórico que se ajuste al patrón de difracción experimental, usando el método de mínimos cuadrados.

Para esto, lo primero que se hace es calcular la intensidad total en cada uno de los puntos del difractograma. La intensidad a calcular en un punto _i_ está dada por la siguiente ecuación:

</div>

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
* Coeficientes de la expansión en series de la función que describe el _background_ (línea base)
* El factor de escala
* Los parámetros de red
* Los coeficientes en la función del perfil

Ya veíamos las funciones más utilizadas para [ajustar los picos difractados](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#ajuste-de-picos)<br>
También veíamos las causas del [ensanchamiento de los picos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#ensanchamiento-de-picos)

El ancho para una curva Gaussiana puede escribirse así:

<div align="center">

$Γ_G= U tan^2 (θ) + V tan(θ) +W + \frac{{P}}{{cos^2 (θ)}}$

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

<div align="justify">

El archivo con extensión .CIF puede descargarse de MATCH! Es el archivo que usamos para llevar a cabo la indexación. Para ello, abrimos nuestro archivo en **MATCH!** y abrimos el <kbd>DATA SHEET</kbd> de nuestra fase. Haciendo click en el número al lado de <kbd>Link to orig. entry</kbd> podemos descargar el archivo.

</div>

![Descarga CIF Match](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Descargar%20Match.png)

Esto automáticamente descarga el archivo, que queda con el nombre según el número:

<div align="center">

![Figura 116](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Descargar%20Match-2.png)

</div>

Se recomienda cambiarle al nombre según la fase de trabajo.

<div align="justify">

Otra opción para descargar un archivo con extensión **.CIF** sin acceder al MATCH!, es yendo directamente a la **base de datos** [Crystallography Open Database](http://www.crystallography.net/cod/) Damos _click_ en <kbd>SEARCH</kbd>, en el menú de la parte izquierda:

</div>

<div align="center">

![Diapositiva1-1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva1-1.PNG)

</div>

<div align="justify">

Inmediatamente se abre una nueva página, que nos pide información sobre la fase de la que necesitamos el archivo **.CIF**. Escribimos el nombre o fórmula química de la fase. Para efectos de este ejercicio práctico empezaremos con la fase 1, que es la de aluminio.

</div>

![Diapositiva2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva2.PNG)

Esto nos despliega una lista de todos los archivos relacionados.

![Diapositiva3](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva3.PNG)

Damos _click_ en aquel que corresponda químicamente a nuestro material. Inmediatamente el archivo se descarga.

![Diapositiva4](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva4.PNG)

De nuevo, se recomienda cambiarle al nombre según la fase de trabajo.

**NOTA**: lo más adecuado es descargar el archivo de MATCH! porque será el de mejor coincidencia con nuestro patrón experimental. Esto facilitará las cosas a la hora del refinamiento Rietveld.

Guardamos los archivos con extensión **.CIF** de las fases que vamos a refinar. En nuestro caso, alumunio y alúmina ($Al_2O_3$)

![Diapositiva5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva5.PNG)

### Archivos .DAT

<div align="justify">

El archivo de nuestro patrón de difracción con extensión *.DAT que usa FullProf tiene algunas algunas características: En la primera fila deben ir el ángulo 2Theta de inicio de los datos; el paso (que es la diferencia que hay de un punto a otro); y el ángulo 2 Theta de finalización de los datos. Después tenemos columnas de datos con la información de las intensidades.

</div>

![Diapositiva6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva6.PNG)

Para descargar este archivo de MATCH! vamos a <kbd>File</kbd>, <kbd>Export</kbd> y <kbd>Profile data</kbd>. 

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/MatchDAT-1.png)

<div align="justify">

Al dar _click_ se nos abre una ventana que nos pregunta la ruta para guardar el archivo (la seleccionamos o buscamos), el nombre del archivo (lo cambiamos si es necesario) y el **tipo de archivo**. Desplegamos la ventana y escogemos <kbd>Profile (start,step,end, intensities)(*dat)</kbd>.

</div>

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/MatchDAT-2.png)

Al dar _click_ en <kbd>GUARDAR</kbd> se nos genera el archivo:

![Imagen9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/MatchDAT-3.png)

### Archivo .BGR

<div align="justify">

Para crear el archivo con extensión **.BGR** abrimos el FullProf. De la barra de tareas clickeamos en el botón que se muestra a continuación. Esto abre la ventana de **WinPLOTR**. Ahí damos _click_ en <kbd>File</kbd>

</div>

![Diapositiva7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva7.PNG)

Damos _click_ en <kbd>Open pattern file </kbd>

![Diapositiva8](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva8.PNG)

Seleccionamos la segunda opción y damos <kbd>OK</kbd>.

![Diapositiva9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva9.PNG)

Abrimos el archivo **.DAT** que habíamos guardado:

<div align="center">

![Diapositiva10](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen1.png)

</div>

Esta acción abre el archivo

![Diapositiva11](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen2.png)

En <kbd>Points Selection</kbd> escogemos <kbd>Automatic Background</kbd>

![Diapositiva12](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen3.png)

Eso nos abre una ventana que nos pide información.

![Diapositiva13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva%20de%20correcci%C3%B3n-2.png)

<div align="justify">

En <kbd>Background threshold</kbd> un valor entre 0.05 y 0.07 funciona bien. Esto está relacionado con la cantidad de puntos que tendrá el archivo del _background_.

La cantidad de puntos generada fue de 68. Podemos cerrar la ventanita. Puede verse que en azul está representado nuestro patrón experimental, y en verde aparecen los puntos del _background_.

</div>

![Diapositiva13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen4.png)

![Diapositiva14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen5.png)

Para guardar los datos vamos a <kbd>Points Selection</kbd>  y escogemos <kbd>SaVe background points</kbd>.

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen6.png)

Se nos pregunta si queremos guardar el archivo. Decimos que <kbd>sí</kbd>.

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen7.png)

Nombramos el archivo, cuidando que la extensión sea **.BGR**.

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen8.png)

Se nos confirma que se ha creado el archivo con la cantidad de puntos correspondiente.

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen9.png)

Si se desea, podemos editar el archivo. Yo diré que no. Listo esto, cerramos la ventana azul.

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen10.png)

Ya tenemos listos los 4 archivos

* 2 archivos **.CIF** con la información cristalográfica de las fases <br>
* 1 archivo **.DAT** con la información experimental del patrón DRX que vamos a refinar<br>
* 1 archivo **.BGR** con la información del background o radiación de fondo<br>

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph3/Imagen11.png)

## Creación de archivo .PCR de la primera fase

<div align="justify">

Ahora vamos a crear el archivo con extensión **.PCR**. Para ello abrimos el _software_ FullProf. Esto abre la barra de tareas. Posteriormente abrimos <kbd>ED PCR</kbd>. Eso hace que se abra una ventana, como se ve abajo, que es el **editor de archivos PCR**. Usamos el ícono de CIF $\rightarrow$ Pcr.

![Diapositiva21](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva21.PNG)

Damos doble _click_ al archivo de la fase con la que vamos a trabajar. En este caso, **Al.cif**. Esto abre una ventana con la información cristalográfica de la fase, como los parámetros de red y el grupo espacial. Verificamos que la información corresponda a la de nuestra fase y damos <kbd>OK</kbd>.

![Diapositiva22](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva22.PNG)

Con esta acción volvemos a quedar en el editor de archivos PCR. Aquí podemos observar 7 botones. Vamos a trabajar sobre los 3 primeros: <kbd>General</kbd>, <kbd>Patterns</kbd> y <kbd>Phases</kbd>. Primero damos _click_ en <kbd>General</kbd>. Eso abre otra ventana. En <kbd>Title</kbd> ponemos el título de la fase. En <kbd>Calculations</kbd> marcamos <kbd>Refinement/Calculation of a Powder Diffraction Profile</kbd>. Finalizamos con <kbd>OK</kbd>.

![Diapositiva23](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva23.PNG)

Con esa acción volvemos al editor de archivos PCR. Clickeamos en el botón de <kbd>Patterns</kbd>. En la ventana que se abre clickeamos en <kbd>Data file/Peak shape</kbd>. Esto nos abre una ventana que se denomina **Profile data information: Pattern 1**. En la parte de **Data File Format** clickeamos en <kbd>Free Format (2ThetaI, step, 2ThetaF)</kbd>, que es el formato de nuestro archivo **.DAT**

![Diapositiva24](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva24.PNG)

Luego pasamos a la pestaña de **Refinement/Simulation**, donde marcamos en <kbd>X-Ray</kbd>, ya que nuestros datos son de difracción de rayos X. En <kbd>Wavelenght</kbd> escogemos el tipo de fuente de nuestros rayos X. Recordemos que esto podemos consultarlo en el MATCH! En nuestro caso la fuente fue de cobre. Damos <kbd>OK</kbd>. Luego, clickeamos en la pestaña de kbd>Pattern Calculation/Peak Shape</kbd> de la ventana de **Profile data information: Pattern 1**. En la ventana que se despliega, en la parte de **Peak Shape** escogemos la curva que escogeremos para simular nuestros picos. Lo haremos con una **pseudo-voigt**. En la parte de abajo, de **Range** colocamos los valores de <kbd>Theta_min</kbd>, que es el valor inicial del ángulo 2Theta; de <kbd>Theta_max</kbd> que es el valor final del ángulo 2Theta; y ponemos el valor del paso <kbd>Step</kbd>. Finalizamos con <kbd>OK</kbd>.

![Diapositiva25](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva25.PNG)

Ahora, siguiendo en la ventana de **Patterns**, damos _click_ en <kbd>Background Type</kbd>. En la ventana que se abre señalamos <kbd>Linear interpolation between a set background points with refinable heights</kbd> y damos <kbd>OK</kbd>. Ahí quedamos en la ventana de **Patterns Information** y volvemos a dar <kbd>OK</kbd>.

![Diapositiva26](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva26.PNG)

Con esta acción volvemos a quedar en el editor de archivos PCR. Ahora damos _click_ en <kbd>Phases</kbd>. Al hacerlo se abre otra ventana que se llama **Phase Information: Phase 1**. Aquí vamos a colocar la información general de la fase, empezando por el nombre en <kbd>Name of Phase</kbd>. Posteriormente damos _click_ en el botón <kbd>Contribution to Patterns</kbd>.

![Diapositiva27](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva27.PNG)

En la ventana que se abre vamos a marcar <kbd>X-ray</kbd> en la parte de **Type of Pattern**. En la parte de **Peak Shape** vamos a seleccionar <kbd>Pseudo-voigt</kbd> y damos <kbd>OK</kbd>. Con esto volvemos a la ventana de **Phase Information: Phase 1**. Ahora damos _click_ en <kbd>Symmetry</kbd> En la ventana que se despliega vamos a corroborar la información del grupo espacial, que podemos verificar en el <kbd>DATA SHEET</kbd> de MATCH! Finalizamos con <kbd>OK</kbd>. Y nuevamente <kbd>OK</kbd> en **Phase Information: Phase 1**.

![Diapositiva28](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva28.PNG)

Cargamos el archivo **.BGR**. Para esto, vamos al Editor de archivos PCR y damos _click_ en el botón de <kbd>Refinement</kbd>.

<div align="center">

![Diapositiva32](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva32.PNG)

</div>

Esto nos abre una ventana que se denomina **Refinement Information**. En la parte de <kbd>Cycles of Refinement</kbd> colocamos **40**, que es un valor adecuado. Abajo al lado derecho clickeamos en <kbd>Background</kbd>. Eso nos abre la ventana de **Linear interpolation between a set of Background Points**. Clickeamos en <kbd>Import from Background File</kbd>. Eso nos abre una ventana para buscar nuestro archivo con extensión **.BGR**. Lo cargamos. Al cargar el archivo, la ventanita de **Number of Points** debe actualizarse, y debe aparecer ahí el número de puntos de nuestro archivo de _Backgroound_. Damos <kbd>OK</kbd> y <kbd>OK</kbd>.

![Diapositiva33](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva33.PNG)

Con esta acción queda cargado nuestro archivo **.BGR**. Damos _click_ en _Ok_.

Con esto quedamos de nuevo en el Editor de archivos PCR. Ahora damos _click_ en el botón de los 3 discos en azul, como se ve a continuación. 

<div align="center">

![Diapositiva29](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva%20de%20correcci%C3%B3n-3.png)

</div>

Esto nos crea el archivo con extensión **.PCR**. Lo nombramos con el nombre de la fase o el material y finalizamos poniendo .PCR para que quede creado con la extensión adecuada..

</div>

<div align="center">

![Diapositiva30-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva30-2.PNG)

</div>

## Refinamiento de la primera fase

<div align="justify">

El refinamiento Rietveld con el FullProf consta de una serie de pasos, en los que se señalan ciertas casillas (lo que significa que ese parámetro se libera para la iteración del _software_, por lo que se espera que su valor cambie después de correr el programa) y otras no (cuando una casilla no está señalada, significa que su valor queda fijo durante la corrida del _software_). En este ejemplo trabajaremos usando la **_psudo-voigt_** que, como veíamos, ajusta muy bien para nuestro material.

 </div>

Para el refinamiento usamos la casilla de Refinement del Editor de archivos PCR.  Hay cuatro botones con los que trabajaremos: <kbd>Background</kbd> <kbd>Instrumental</kbd> <kbd>Profile</kbd> y <kbd>Atoms</kbd>

![FP-1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/FP-1.png)

 Con <kbd>Background</kbd> refinamos los puntos de intensidad del perfil de la radiación de fondo.

 <div align="center">

 ![FP-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/FP-2.png)

 </div>

 Con <kbd>Instrumental</kbd> refinamos el el punto cero del detector

 ![FP-3](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/FP-3.png)

 <div align="justify">

En <kbd>Profile</kbd> refinamos varios factores. Uno de ellos es _Scale Factor_, que ajusta la intensidad neta del patrón, multiplicando cada punto de datos por el factor de escala. También están los parámetros de red: _a_, _b_, _c_ y los ángulos _alfa_, _beta_ y _gamma_. Los **parámetros de forma del perfil**, que son de dos tipos: los del ancho a la altura media del pico (FWHM) y otros parámetros. Los relacionados con FWHM son <kbd>U</kbd>, <kbd>V</kbd> y <kbd>W</kbd>, que son parámetros de la parte gaussiana de la pseudo-voigt. <kbd>V</kbd> y <kbd>W</kbd> relacionados con el ensanchamiento instrumental y <kbd>U</kbd> con las microdeformaciones. Los otros parámetros de forma son <kbd>Eta_0</kbd> y <kbd>X</kbd>, siendo <kbd>X</kbd> un parámetro de la curva lorentziana, relacionada con el tamaño de cristalito, y <kbd>Eta_0</kbd> (η) es la razón entre gaussiana y lorentziana, como veíamos en [Ajuste de Picos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#ajuste-de-picos). Dentro de los parámetros del perfil también tenemos el de **orientación preferencial**, <kbd>G1</kbd>.

 </div>

 ![FP-4](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/FP-4.png)

 ![FP-5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/FP-5.png)

 Y, por último, en <kbd>Atoms</kbd> se refinan las posiciones atómicas y el factor de ocupación de los átomos.

 ![FP-6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/FP-6.png)

La rutina recomendada usando la **pseudo-voigt** como curva de ajuste y la **interpolación lineal** para el _background_ es el siguiente:
* **1.**	Refinar el factor de escala
* **2.**	Refinar el background
* **3.**	Refinar los parámetros de red
* **4.**	Fijar los parámetros de red y el background
* **5.**	Refinar el punto cero del detector en Instrumental
* **6.**	Refinar el factor de escala
* **7.**	Refinar el factor de escala y los parámetros U y V
* **8.**	Refinar el factor de escala y los parámetros U y W
* **9.**	Refinar el factor de escala y los parámetros V y W
* **10.**	Refinar el factor de escala, los parámetros U y V y el factor X
* **11.**	Refinar el factor de escala, los parámetros U y V y el factor Eta_0
* **12.**	Refinar el factor de escala, los parámetros U y V, el factor Eta_0 y las posiciones atómicas
* **13.**	Refinar el factor de escala, los parámetros U y V, el factor Eta_0 y el factor de ocupación
* **14.**	Refinar el factor de escala, los parámetros U y V y el factor Eta_0 
* **15.**	Refinar el factor de escala, los parámetros U y V, el factor Eta_0 y el factor orientación preferencia G1
 
<div align="justify">

Estando en el Editor de archivos PCR, clickeamos en el botón de <kbd>Refinement</kbd>. La ventana que se abre consta de 5 zonas. Nos dirigimos a <kbd>Profile</kbd> y clickeamos ahí. Eso nos abre una nueva ventana (**Profile Parameters: Phase 1**). Señalamos la casilla de <kbd>Scale</kbd> de la parte de <kbd>Coefficients</kbd>. Al señalar una casilla lo que hacemos es decirle al sistema que haga iteraciones no dejándola fija. Es decir, puede variar su valor. Lo que no se señala queda fijo para el programa. Señalamos y damos _click_ en <kbd>OK</kbd> y <kbd>OK</kbd>. 

</div>

![Diapositiva3](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva3.PNG)

Posteriormente guardamos cambios con el botón del disco azul. Para pedirle al _software_ que lleve a cabo las iteraciones de refinamiento damos _click_ en el logo que se muestra a continuación del Editor de archivos PCR. 

![Diapositiva4](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva4.PNG)

Cuando hago eso, él me pide confirmación del archivo con el que estamos trabajando. Lo seleccionamos para confirmar.

![Diapositiva5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva5.PNG)

<div align="justify">

El software hace las iteraciones sobre la ventana que se abre, y al terminar queda como se muestra a continuación. Podemos ver, en rojo, el patrón experimental. En negro, sobre la curva roja, aparece una negra, que corresponde al patrón teórico o refinado. Lo que esperamos al final es que ambas curvas coincidan. En azul aparece el background, que irá cambiando a medida que se lleva a cabo el refinamiento. Al final esperamos que quede plano, sin mucho ruido.

Encontramos 2 valores importantes que nos indicarán que tan bien está quedando el refinamiento. Uno de ellos es el **factor de Bragg** que indica qué tan diferentes son las intensidades de las curvas experimental y teórica. Mientras más alto el valor, más diferencias entre ellas. Un valor por debajo de 10 es adecuado para que un refinamiento sea aceptable. El otro es el **chi-cuadrado reducido**, que relaciona el factor del perfil con el factor del perfil ponderado. Un valor adecuado de Chi-2 es menor a 5. Si desea profundizar en estos conocimientos, puede dirigirse a la página del [FullProf-Tutoriales](https://www.ill.eu/sites/fullprof/php/tutorials.html)

</div>

En este caso el **Factor de Bragg = 83** y el **Chi-2 = 12.8**. Como recién empezamos el proceso estos valores son altos.

![Diapositiva6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva6.PNG)

Al cerrar esta ventana se abre una pequeña que nos pregunta si cargamos nuevamente el archivo PCR. Le decimos que sí.

![Diapositiva7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva7.PNG)

De nuevo vamos a <kbd>Refinement</kbd> y clickeamos en <kbd>Background</kbd>.

![Diapositiva8](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva8.PNG)

Clickeamos en <kbd>Refine All</kbd>, con el fin de seleccionar todos los puntos del _background_. Clickeamos en <kbd>Ok</kbd>.

![Diapositiva9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva9.PNG)

Guardamos cambios en el archivo con el ícono del disco azul, y damos _click_ en el botón de refinar.

![Diapositiva10](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva10.PNG)

Es hace correr la iteración mostrando la ventana que vemos a continuación. Podemos ver que tanto el factor de Bragg como el Chi-2 bajaron.

![Diapositiva11](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva11.PNG)

De nuevo, cerramos esta ventana y decimos que sí a la nueva que aparece.

![Diapositiva12](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva12.PNG)

**NOTA:** se recomienda guardar un soporte de los archivos del refinamiento actual en otra carpeta cada que consideremos que vamos bien con el proceso, por si con alguna orden que le damos al _software_ se 'enloquece' (nos muestra parámetros de valor absurdo).

Vamos de nuevo a <kbd>Refinement</kbd> y damos _click_ en botón de <kbd>Profile</kbd>. Seleccionamos las casillas de los parámetros de red. Aprobamos la acción con <kbd>OK</kbd> y <kbd>OK</kbd>.

![Diapositiva13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva13.PNG)

Guardamos los cambios y refinamos:

![Diapositiva14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva14.PNG)

Al hacer esto el **chi-2** se mantuvo igual, pero el **Factor de Bragg** bajó levemente:

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva15.PNG)

De nuevo, cerramos y damos <kbd>Sí</kbd> en la nueva ventana.

![Diapositiva16](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva16.PNG)

Revisamos en <kbd>Profile</kbd> el resultado, y vemos que los valores de los parámetros de red han cambiado.

![Diapositiva17](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva17.PNG)

Ahora fijamos todo en esta ventana:

![Diapositiva18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva18.PNG)

Vamos a <kbd>Background</kbd>

![Diapositiva19](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva19.PNG)

Y también fijamos todo:

![Diapositiva20](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva20.PNG)

Guardamos y corremos el _software_:

![Diapositiva21](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva21.PNG)

Confirmamos el archivo y se abre la ventana de resultado. EL hacer esto hace que el **chi-2** baje un poco.

![Diapositiva23](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva23.PNG)

Ahora vamos a <kbd>Background</kbd> <kbd>Instrumental</kbd> y seleccionamos la casilla de <kbd>Zero</kbd>

![Diapositiva24](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva24.PNG)

Guardamos cambios y corremos el programa. El resultado muestra un **chi-2 = 6.10** y un **Factor de Bragg = 36.05**.

![Diapositiva25](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva25.PNG)

Sin embargo, si acercamos uno de los picos (arrstrando el _click_ izquierdo en el área) vemos que la coincidencia entre curva teórica y experimental aún no es buena.

![Diapositiva26](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva26.PNG)

Ahora volvemos a marcar el factor de escala y corremos: <kbd>Refinement</kbd> <kbd>Profile</kbd> <kbd>Scale</kbd>.

![Diapositiva27](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva27.PNG)

Ahora volvemos a <kbd>Refinement</kbd> <kbd>Profile</kbd> y marcamos las casillas de <kbd>U</kbd> y <kbd>V</kbd>. 

![Diapositiva28](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva28.PNG)

Guardamos cambios y corremos el refinamiento. El resultado es un **chi-2 = 3.67**  y un **Factor de Bragg = 7.506**. Ambos valores muy adecuados.

![Diapositiva29](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva29.PNG)

Ahora volvemos a <kbd>Refinement</kbd> <kbd>Profile</kbd> y marcamos las casillas de <kbd>U</kbd> y <kbd>W</kbd>. 

![Diapositiva30](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva30.PNG)

Al correr el resultado es un incremento grande en el **Factor de Bragg** y leve en el **Chi-2**

![Diapositiva31](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva31.PNG)

Ahora dejamos marcados <kbd>V</kbd> y <kbd>W</kbd> y corremos.

![Diapositiva32](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva32.PNG)

Después marcamos la casilla de X <kbd>X</kbd>

![Diapositiva33](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva33.PNG)

El resultado es un **Chi-2** más bajo, pero un **Factor de Bragg** levemente mayor:

![Diapositiva34](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva34.PNG)

Ahora desmarcamos <kbd>X</kbd> y marcamos <kbd>Eta_0</kbd>

![Diapositiva35](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva35.PNG)

Guardamos y corremos. Esta acción elevó mucho el **Factor de Bragg**, aunque disminuyó el **Chi-2**. 

![Diapositiva36](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva36.PNG)

Sin embargo, vemos que la coincidencia entre curvas teórica y experimental va bien:

![Diapositiva37](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva37.PNG)

Cerramos la ventana y, como hemos venido haciendo, cargamos el archivo PCR. Ahora nos dirigimos a <kbd>Refinement</kbd> <kbd>Atoms</kbd> y marcamos las casillas de las posiciones atómicas.

![Diapositiva38](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva38.PNG)

Guardamos cambios y corremos el programa. Esta acción vuelve a bajar el valor del **Factor de Bragg**.

![Diapositiva39](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva39.PNG)

Volvemos a <kbd>Refinement</kbd> <kbd>Atoms</kbd> y marcamos la casilla del factor de ocupación.

![Diapositiva40](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva40.PNG)

Esta acción también baja el **Factor de Bragg**.

![Diapositiva41](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva41.PNG)

Volvemos a <kbd>Refinement</kbd> <kbd>Atoms</kbd> y fijamos todo (desmarcamos todas las casillas).

![Diapositiva42](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva42.PNG)

Esta acción incrementa de nuevo el **Factor de Bragg**

![Diapositiva43](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva43.PNG)

Ahora vamos a <kbd>Refinement</kbd> <kbd>Profile</kbd> <kbd>Preferred Orientation</kbd> y marcamos <kbd>G1</kbd>.

![Diapositiva44](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva44.PNG)

Esto reduce el tanto el **Factor de Bragg** como el **chi-2**

![Diapositiva45](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva45.PNG)

Hasta este punto hemos terminado la rutina de refinamiento. Como el **Factor de Bragg** no está en un valor adecuado, vamos a repetir todo el proceso, paso a paso. Deben fijarse todos los parámetros nuevamente:

![Diapositiva47](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva47.PNG)

Fijamos todo, guardamos, y volvemos a correr el refinamiento.

![Diapositiva48](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva48.PNG)

Volvemos a empezar, clickeando en el factor de escala:

![Diapositiva49](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva49.PNG)

Al correr nuevamente el programa tenemos:

![Diapositiva50](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva50.PNG)

Ahora refinamos el background:

![Diapositiva51](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva51.PNG)

Vemos un resultado positivo, ya que **chi-2 = 2.97**  y un **Factor de Bragg = 7.557**

![Diapositiva52](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva52.PNG)

Vemos una mayor aproximación entre las curvas teórica y experimental:

![Diapositiva53](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva53.PNG)

Ahora marcamos las casillas de los parámetros de red en <kbd>Profile</kbd>

![Diapositiva54](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva54.PNG)

Esto hace que suba un poco el **Factor de Bragg**

![Diapositiva55](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva55.PNG)

Volvemos a dejar todo fijo en <kbd>Profile</kbd> y <kbd>Background</kbd>

![Diapositiva56](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva56.PNG)

Y corremos:

![Diapositiva57](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva57.PNG)

Fijando nuevamente el factor de escala tenemos:

![Diapositiva59](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva59.PNG)

Ahora vamos a <kbd>Instrumental</kbd> y marcamos <kbd>Zero</kbd>

![Diapositiva60](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva60.PNG)

![Diapositiva61](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva61.PNG)

Ahora, parámetros <kbd>U</kbd> y <kbd>V</kbd>

![Diapositiva62](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva62.PNG)

**Factor de Bragg** y **Chi-2** siguen bajando.

![Diapositiva63](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva63.PNG)

 Ahora, parámetros <kbd>V</kbd> y <kbd>W</kbd>

![Diapositiva64](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva64.PNG)

![Diapositiva65](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva65.PNG)

 Con <kbd>U</kbd> y <kbd>W</kbd> tenemos

![Diapositiva67](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva67.PNG)

Con <kbd>X</kbd>

![Diapositiva68](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva68.PNG)

![Diapositiva69](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva69.PNG)

Con <kbd>Eta_0</kbd>

![Diapositiva70](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva70.PNG)

![Diapositiva71](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva71.PNG)

Ahora en <kbd>Instrumental</kbd> marcamos las posiciones atómicas:

![Diapositiva72](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva72.PNG)

El resultado del refinamiento:

![Diapositiva73](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva73.PNG)

Con el factor de ocupación en <kbd>OCC</kbd> tenemos:

![Diapositiva75](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva75.PNG)

Ahora con <kbd>Profile</kbd> <kbd>Preferred Orientation</kbd> <kbd>G1</kbd> nos queda:

![Diapositiva79](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva79.PNG)

<div align="justify">

Aunque el resultado podría ser mejor -para ello puede repetirse toda la rutina de refinamiento-, vemos que los valores del **Factor de Bragg** y del **Chi-2** son adecuados para suponer un buen resultado. Por tanto, dejaremos el proceso hasta aquí con esta fase. Antes de continuar con el refinamiento de la segunda fase, miremos los resultados. En la carpeta de archivos podemos ver la presencia de un nuevo documento tipo **Archivo SUM**. 

</div>

<div align="center">

![Diapositiva81](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva81.PNG)

</div>

<div align="justify">

Si lo abrimos podemos encontrar varias cosas. Entre ellas el valor de los parámetros de red: _a = 4.05285 Å_. Este valor es un poco diferente al que calculamos previamente en la sección [Cálculo del parámetro de red](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n02#c%C3%A1lculo-de-par%C3%A1metros-de-red). El valor calculado en la sección anterior es más confiable:  _a = 4.05424 Å_

</div>

<div align="center">

![Diapositiva82](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva82.PNG)

</div>

<div align="justify">

También podemos observar la fracción de esta fase en el material, que por ahora es del 100%. Cuando agreguemos la segunda fase y hagamos el refinamiento ese valor deberá cambiar.

</div>

<div align="center">

![Diapositiva83](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Diapositiva83.PNG)

</div>

## Creación del archivo .PCR de la segunda fase

El archivo *.PCR de la segunda fase se crea siguiendo los pasos que veíamos en el apartado de [Creación del archivo .PCR de la primera fase](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/Readme.md#creaci%C3%B3n-de-archivo-pcr-de-la-primera-fase)

Nota: nombrarla adecuadamente, según el nombre de la fase.

El archivo *.CIF lo habremos descargado del MATCH!

![Imagen1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen1.png)

Revisar que la simetría y los parámetros de red del archivo *.CIF correspondan al material que queremos refinar.

![Imagen2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen2.png)

Después de creado el archivo aparecerá con la extensión *.PCR

![Imagen3](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen3.png)

## Adición del archivo .PCR de la segunda fase al de la primera fase

Vamos a adicionar alguna información del archivo **Fase 2_Al2O3.PCR** al archivo **Fase 1_Al.PCR**.

Para ello, abrimos el archivo **Fase 2_Al2O3_PCR** y vamos a copiar la información que vemos resaltada en el gráfico (desde el signo de admiración seguido de puntos hasta la línea que termina en ceros antes de ! 2Th1/T0F1).

![Imagen4](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen4.png)

Luego abrimos nuestro archivos **Fase 1_Al.PCR**. 

![Imagen5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen5.png)

Nos ubicamos en el espacio señalado en el gráfico siguiente, dando un _enter_ en la línea previa.

![Imagen6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen6.png)

Pegamos la información que habíamos copiado.

![Imagen10](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen10.png)

Antes de cerrar el archivo, nos dirigimos a la parte superior de éste. Miramos justo por debajo de <kbd>Nph</kbd>, que significa _number of phases_. Aparece un 1, porque era la cantidad de fases añadidas en ese archivo. 

![Imagen7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen7.png)

Cambiamos el número a 2, ya que ahora tenemos dos fases: Al y Al2O3.

![Imagen8](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen8.png)

Cerramos y guardamos cambios.

![Imagen9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen9.png)


## Refinamiento de la segunda fase

Empezamos abriendo el FullProf para desplegar la barra de tareas (_ToolBar_). En la barra de tareas clickeamos en ED PCR para abrir el editor de archivos PCR.

![Imagen11](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen11.png)

En el editor de archivos PCR damos _click_ en <kbd>File</kbd>y <kbd>Open</kbd>

![Imagen12](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen12.png)

Se abre la ventana para seleccionar el archivo *.PCR. Escogemos el de la fase 1, con la que estábamos trabajando y a la que añadimos los datos de la segunda fase.

![Imagen13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen13.png)

Al hacer esto, se activan los botones del editor de archivos PCR. Damos _click_ en el botón <kbd>Refinement</kbd>.

![Imagen14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen14-2.png)

Damos _click_ en <kbd>Phase 2</kbd> y después en <kbd>Profile</kbd>

![Imagen15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen15.png)

**RECOMENDACIÓN:** Fijarse en siempre seleccionar <kbd>Phase 2</kbd> antes de seleccionar alguna casilla. De otro modo, por defecto el programa selecciona a la fase 1 para el refinamiento.

Como ya sabemos, empezamos la rutina de refinamiento con el factor de escala:

![Imagen16](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen16.png)

Al correr el _software_ observamos ya aparece incluido el resultado de la fase 2, con un **Factor de Bragg = 64.25** y un **Chi-2 = 2.98**. Vemos que hacer esto también ha afectado los valores de la primera fase.

![Imagen17](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen17.png)

Continuamos con el refinamiento del <kbd>Background</kbd>

![Imagen18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen18.png)

El resultado es la estabilización del **Factor de Bragg** y del **Chi-2** de la primera fase y la disminución de estos valores para la fase 2.

![Imagen19](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen40.png)

Continuamos con el refinamiento de los parámetros de red. Estar pendiente de que la ventana corresponda a la fase que estamos refinando.

![Imagen20](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen41.png)

Esta acción baja un poco el **factor de Bragg** de la fase a 43.30:

![Imagen42](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen42.png)

Podemos ver cómo cambian los parámetros de red.

![Imagen43](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen43.png)

Los dejamos fijos:

<div align="center"> 

![Imagen44](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen44.png)

</div> 

Así como dejamos fijo el _Background_:

<div align="center"> 

![Imagen45](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen45.png)

</div>

Esto aumenta levemente el **Factor de Bragg**

![Imagen46](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen46.png)

Ahora refinamos el coeficiente del punto cero del instrumento:

![Imagen47](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen47.png)

Tampoco hay mucho cambio

![Imagen48](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen48.png)

De nuevo refinamos el **Factor de escala**

![Imagen49](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen49.png)

El resultado:

![Imagen50](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen50.png)

Ahora vamos con los parámetros del ancho a la altura media del pico. Empezamos con <kbd>U</kbd> y <kbd>V</kbd>

![Imagen51](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen51.png)

Esto disminuye el **Factor de Bragg**

![Imagen52](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen52.png)

Ahora vamos con con <kbd>U</kbd> y <kbd>W</kbd>

![Imagen53](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen53.png)

Esto baja bastante el **Factor de Bragg** de la fase 2, a 34.89 

![Imagen54](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen54.png)

Ahora vamos con con <kbd>V</kbd> y <kbd>W</kbd>

![Imagen55](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen55.png)

Esto aumenta levemente el **Factor de Bragg**

![Imagen56](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen56.png)

Ahora vamos con el coeficiente <kbd>X</kbd> del parámetro de forma:

![Imagen57](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen57.png)

Vemos un aumento en el **Factor de Bragg**

![Imagen58](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen58.png)

Ahora vamos con el coeficiente <kbd>Eta_0</kbd> del parámetro de forma:

![Imagen59](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen59.png)

De nuevo vemos un aumento en el **Factor de Bragg**

![Imagen60](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen60.png)

Ahora refinamos las posiciones atómicas:

![Imagen60-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen60-2.png)

No hay mucho cambio:

![Imagen61](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen61.png)

Vemos cómo cambian las posiciones atómicas:

![Imagen62](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen62.png)

Las dejamos fijas y refinamos el factor de ocupación de los cationes (iones de aluminio):

![Imagen63](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen63.png)

Y vemos que vuelve a disminuir el **Factor de Bragg**

![Imagen63-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen63-2.png)

Refinamos el factor de ocupación de los aniones (iones de oxígeno):

![Imagen64](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen64.png)

Eso incrementa nuevamente el **Factor de Bragg**

![Imagen65](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen65.png)

Fijamos todo en posiciones atómicas:

![Imagen66](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen66.png)

No cambia mucho el **Factor de Bragg**

![Imagen67](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen67.png)

Ahora refinamos el coeficiente <kbd>G1</kbd> de orientación preferencial

![Imagen68](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen68.png)

Pero esa acción incrementa el **Factor de Bragg**

![Imagen69](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen69.png)

Repetimos todo el procedimiento, con el fin de disminuir el **Factor de Bragg** de la segunda fase.

En mi caso, quedé en un **Factor de Bragg** de la segunda fase de 47.11. Que es un valor alto. Sin embargo, teniendo en cuenta que la intensidad de los picos es baja y que el **Chi-2** tiene un valor muy aceptable, dejaré el proceso hasta ahí.

![Imagen70](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen70.png)

## WinPlotr

WinPlotr es una herramienta del FullProf para graficar el resultado del refinamiento. Para abrirlo, hacemos _click_ en el ícono que se muestra a continuación en la barra de tareas. Eso abre la ventana que se ve más abajo.

![Imagen71](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen71.png)

Damos _click_ en <kbd>File</kbd> y <kbd>Open Rietveld/Profile file (*.PRF)</kbd>. El archivo con esta extensión se creó en el proceso de refinamiento y está en la carpeta de trabajo.

![Imagen72](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen72.png)

Abrimos el archivo:

![Imagen73](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen73.png)

Y se nos abre el gráfico. En rojo vemos el patrón experimental. En negro, el patrón teórico que resultó del refinamiento Rietveld. En azul el _background_.

![Imagen74](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen74.png)

Podemos hacer zum con ayuda del _mouse_ para ver la coincidencia entre ambos patrones. No es perfecta, pero es aceptable.

![Imagen75](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen75.png)

Podemos guardar el resultado en un PDF, dando _click_ en el ícono del disco azul.

![Imagen76](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen76.png)

Guardamos el archivo:

![Imagen77](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen77.png)

Y este luce así después de abrir el PDF.

![Imagen78](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen78.png)

## Archivos de salida

Como ya veíamos al acabar de refinar la fase 1, el archivo *.SUM resume el resultado del refinamiento. Este archivo también se creó durante el proceso:

![Imagen79](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen79.png)

Al abrirlo, casi al final del archivo, encontramos el resultado del porcentaje de fases. Nos da que el porcentaje del aluminio es de 89.64% y el de la alúmina o corindón es de 10.36%. 

![Imagen80](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen80.png)

También podemos ver los parámetros de red del corindón -ya veíamos los del aluminio-, que difieren levemente de los valores calculados en el Origin.

![Imagen81](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Imagen81.png)

##

Por último, podemos colocar parte de los resultados en un gráfico de Origin:

![Reporte final](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph_2/Reporte%20final.png)

 ##

<div align="center">
   
   <a href="https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL" target="_blank"><img src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20Obtener%20certificado%20PNG.png" alt="R.LTWB" width="260" border="0" /></a>

</div>

##

![Logo botón](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20cierre%20sección.png)
