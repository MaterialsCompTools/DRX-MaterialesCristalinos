<div align="center"> 

# Determinación de porcentajes de fases por refinamiento Rietveld. 

![FullProf logo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/FullProf%20logo%20PNG.png)

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

![Descarga CIF Match](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Descargar%20Match.png)

Esto automáticamente descarga el archivo, que queda con el nombre según el número:

<div align="center">

![Figura 116](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Descargar%20Match-2.png)

</div>

Se recomienda cambiarle al nombre según la fase de trabajo.

Otra opción para descargar un archivo con extensión **.CIF** sin acceder al MATCH!, es yendo directamente a la **base de datos** [Crystallography Open Database](http://www.crystallography.net/cod/) Damos _click_ en <kbd>SEARCH</kbd>, en el menú de la parte izquierda:

<div align="center">

![Diapositiva1-1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva1-1.PNG)

</div>

Inmediatamente se abre una nueva página, que nos pide información sobre la fase de la que necesitamos el archivo **.CIF**. Escribimos el nombre o fórmula química de la fase. Para efectos de este ejercicio práctico empezaremos con la fase 1, que es la de aluminio.

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

El archivo de nuestro patrón de difracción con extensión *.DAT que usa FullProf tiene algunas algunas características: En la primera fila deben ir el ángulo 2Theta de inicio de los datos; el paso (que es la diferencia que hay de un punto a otro); y el ángulo 2 Theta de finalización de los datos. Después tenemos columnas de datos con la información de las intensidades.

![Diapositiva6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva6.PNG)

Para descargar este archivo de MATCH! vamos a <kbd>File</kbd>, <kbd>Export</kbd> y <kbd>Profile data</kbd>. 

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/MatchDAT-1.png)

Al dar _click_ se nos abre una ventana que nos pregunta la ruta para guardar el archivo (la seleccionamos o buscamos), el nombre del archivo (lo cambiamos si es necesario) y el **tipo de archivo**. Desplegamos la ventana y escogemos <kbd>Profile (start,step,end, intensities)(*dat)</kbd>.

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/MatchDAT-2.png)

Al dar _click_ en <kbd>GUARDAR</kbd> se nos genera el archivo:

![Imagen9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/MatchDAT-3.png)

### Archivo .BGR

Para crear el archivo con extensión **.BGR** abrimos el FullProf. De la barra de tareas clickeamos en el botón que se muestra a continuación. Esto abre la ventana de **WinPLOTR**. Ahí damos _click_ en <kbd>File</kbd>

![Diapositiva7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva7.PNG)

amos _click_ en <kbd>Open pattern file </kbd>

![Diapositiva8](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva8.PNG)

Seleccionamos la segunda opción y damos <kbd>OK</kbd>.

![Diapositiva9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva9.PNG)

Abrimos el archivo **.DAT** que habíamos guardado:

<div align="center">

![Diapositiva10](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva10.PNG)

</div>

Esta acción abre el archivo

![Diapositiva11](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva11.PNG)

En <kbd>Points Selection</kbd> escogemos <kbd>Automatic Background</kbd>

![Diapositiva12](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva12.PNG)

Eso nos abre una ventana que nos pide información.

![Diapositiva13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva13.PNG)

En <kbd>Background threshold</kbd> un valor entre 0.05 y 0.07 funciona bien. Esto está relacionado con la cantidad de puntos que tendrá el archivo del background.

La cantidad de puntos generada fue de 58. Podemos cerrar la ventanita. Puede verse que en azul está representado nuestro patrón experimental, y en verde aparecen los puntos del _background_.

![Diapositiva14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva14.PNG)

Para guardar los datos vamos a <kbd>Points Selection</kbd>  y escogemos <kbd>SaVe background points</kbd>. Nospregunta, y le decimos que <kbd>sí</kbd>.

![Diapositiva15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva15.PNG)

Nombramos el archivo, cuidando de que la extensión sea **.BGR**.

![Diapositiva16](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva16.PNG)

Se nos confirma que se ha creado el archivo con la cantidad de puntos correspondiente.

![Diapositiva17](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva17.PNG)

Si se desea, podemos editar el archivo. Yo diré que no.

Ya tenemos listos los 4 archivos

* 2 archivos **.CIF** con la información cristalográfica de las fases <br>
* 1 archivo **.DAT** con la información experimental del patrón DRX que vamos a refinar<br>
* 1 archivo **.BGR** con la información del background o radiación de fondo<br>

![Diapositiva18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva18.PNG)

## Creación de archivo .PCR de la primera fase

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

Con esto quedamos de nuevo en el Editor de archivos PCR. Ahora damos _click_ en el botón de los 3 discos en azul, como se ve a continuación. 

![Diapositiva29](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva29.PNG)

Esto nos crea el archivo con extensión **.PCR**. Lo nombramos con el nombre de la fase o el material.

![Diapositiva30-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva30-2.PNG)


## Cargue del archivo .BGR

Para cargar el archivo de extensión **.BGR** vamos al Editor de archivos PCR y damos _click_ en el botón de <kbd>Refinement</kbd>.

![Diapositiva32](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva32.PNG)

Esto nos abre una ventana que se denomina **Refinement Information**. En la parte de <kbd>Cycles of Refinement</kbd> colocamos **40**, que es un valor adecuado. Abajo al lado derecho clickeamos en <kbd>Background</kbd>. Eso nos abre la ventana de **Linear interpolation between a set of Background Points**. Clickeamos en <kbd>Import from Background File</kbd>. Eso nos abre una ventana para buscar nuestro archivo con extensión **.BGR**. Lo cargamos. Al cargar el archivo, la ventanita de **Number of Points** debe actualizarse, y debe aparecer ahí el número de puntos de nuestro archivo de _Backgroound_. Damos <kbd>OK</kbd> y <kbd>OK</kbd>.

![Diapositiva33](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva33.PNG)

Con esta acción queda cargado nuestro archivo **.BGR**.

## Refinamiento de la primera fase

El refinamiento Rietveld con el FullProf consta de una serie de pasos, en los que se señalan ciertas casillas (lo que significa que ese parámetro se libera para la iteración del _software_, por lo que se espera que su valor cambie después de correr el programa) y otras no (cuando una casilla no está señalada, significa que su valor queda fijo durante la corrida del _software_).

Para el refinamiento usamos la casilla de Refinement del Editor de archivos PCR.  Hay cuatro botones con los que trabajaremos: <kbd>Background</kbd> <kbd>Instrumental</kbd> <kbd>Profile</kbd> e <kbd>Instrumental<kbd>

INSERTAR FIGURA

Estando en el Editor de archivos PCR, clickeamos en el botón de <kbd>Refinement</kbd>. La ventana que se abre consta de 5 zonas. Nos dirigimos a la zona de **Atoms** (zona inferior derecha) y clickeamos en <kbd>Profile</kbd>. Eso nos abre una nueva ventana (**Profile Parameters: Phase 1**). Señalamos la casilla de <kbd>Scale</kbd> de la parte de <kbd>Coefficients</kbd>. Al señalar una casilla lo que hacemos es decirle al sistema que haga iteraciones no dejándola fija. Es decir, puede variar su valor. Lo que no se señala queda fijo para el programa. Señalamos y damos _click_ en <kbd>OK</kbd> y <kbd>OK</kbd>. Posteriormente guardamos cambios con el botón del disco azul.

![Diapositiva36](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva36.PNG)

Para pedirle al _software_ que lleve a cabo las iteraciones de refinamiento damos _click_ en el logo que se muestra a continuación del Editor de archivos PCR. Cuando hago eso, él me pide confirmación del archivo con el que estamos trabajando. Lo seleccionamos para confirmar.

![Diapositiva37](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n03/.graph/Diapositiva37.PNG)

## Creación del archivo .PCR de la segunda fase

## Adición del archivo .PCR de la segunda fase al de la primera fase

## Refinamiento de la segunda fase

## WinPlotr

## Archivos de salida

 ##

<div align="center">

![Logo botón](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20Obtener%20certificado%20PNG.png)

[Formulario de admisión](https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL)

</div>

##

![Logo botón](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20cierre%20sección.png)
