<div align="center">

# Determinación de rasgos cristalográficos

</div>

<div align="center">
  
![Origin logo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/OriginPro_Logo%20PNG.png)

</div>
  
## Objetivos

*	Conocer la interfaz de OriginPro
*	Conocer la extensión de archivos con la que trabaja el software
*	Aprender a exportar el archivo del MATCH! según la extensión necesaria
*	Aprender a ajustar los picos de forma individual
*	Aprender a calcular el parámetro de red a partir del método de las funciones de extrapolación
*	Aprender a calcular el tamaño de cristalito y las microdeformaciones usando el método de Williamson-Hall
*	Aprender a calcular la densidad de dislocaciones
*	Ver la aplicación

## Requerimientos

*	Descargar un Demo del Software [OriginPro](https://www.originlab.com/demodownload.aspx)

## Qué es Origin

Origin es un programa que ayuda a importar, graficar, explorar, analizar e interpretar datos. La interfaz es de apuntar y hacer _click_ y el trabajo se puede hacer por lotes. En este caso, lo usaremos como herramienta para presentar adecuadamente los datos de la indexación de picos y para ajustar los picos y extraer información valiosa como los parámetros de red de estructuras cristalinas y el tamaño de cristalito y las microdeformaciones de la red.<br>

## Extensiones de archivos de trabajo

Origin es capaz de abrir varios tipos de archivos, con diferentes extensiones.<br>

*	Los archivos de proyectos de Origin tienen extensión *.opj y *.opju
*	Los archivos de ventana secundaria (Child Windows Files) pueden ser de extensión *.txt, que son los que usaremos acá.

Si quiere conocer los otros tipos de archivos que puede abrir Origin, puede dirigirse a [6 Origin File Types](https://www.originlab.com/doc/en/User-Guide/Origin-File-Types)<br>

## Interfaz de Origin

Al abrir Origin nos encontramos con una ventana que se denomina _New WorkBook_. En nuestro caso, escogemos la primera opción, de un libro de trabajo en blanco. Lo escogemos dando doble _click_.<br>

![Figura 52](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image052.png)

Esa acción nos abre un primer libro.<br>

![Figura 53](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image053.png)

Como puede verse, tenemos 4 barras de tareas, en las partes superior, inferior, derecha e izquierda. En la parte superior tenemos varias ventas: <kbd>File</kbd>, <kbd>Edit</kbd>, <kbd>View</kbd>, <kbd>Plot</kbd>, <kbd>Column</kbd>, <kbd>Worksheet</kbd>, <kbd>Analysis</kbd>, <kbd>Statistics</kbd>, <kbd>Image</kbd>, <kbd>Tools</kbd>, <kbd>Format</kbd>, <kbd>Window</kbd> y <kbd>Help</kbd>. Veremos, de manera práctica, cómo las usamos.<br>

El libro tiene varias partes importantes. Nos indica la columna del eje _x_ y del eje _y_. El nombre del libro, que quedará definido por el título del archivo que abramos. Nos indica cuáles son las casillas para los nombres de las columnas, donde pondremos la variable medida. Esto definirá el título de cada uno de los ejes. Luego tenemos la casilla de las unidades de medida de cada variable. Los comentarios son para poner alguna información relevante sobre la muestra que vamos a analizar. Una temperatura o un tiempo de proceso, por ejemplo, o una composición química. Esto dependerá de lo que estemos analizando. Y <kbd>F(x)</kbd> es para colocar alguna fórmula matemática para que se haga alguna operación.<br>

![Figura 54](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image054.png)<br>

## Importar archivo y reportar el patrón de DRX

Para aprender a exportar el archivo, podemos dirigirnos a la sección anterior [Exportar archivos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#exportar-archivos). Para importarlo, vamos a la pestaña de <kbd>File</kbd>, <kbd>Import</kbd>, <kbd>Single ASCII</kbd>.

![Figura 55](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image055.png)

Esta acción nos dirige a una ventana, donde podemos buscar nuestro archivo:<br>

![Figura 56](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image056.png)

Haciendo doble _click_ podemos abrir el archivo. Ponemos los títulos:

![Figura 57](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image057.png)<br>

Para graficar, con el _click_ izquierdo sostenido, señalamos ambas columnas. Nos dirigimos a la barra de tareas inferior, y clickeamos en el ícono de línea:<br>

![Figura 59](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image059.png)<br>

Esto acción nos construye el gráfico:

![Figura 60](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image060.png)

Dando doble _click_ sobre cada uno de los ejes podemos acomodar de qué valor a qué valor hacer el gráfico. Para el eje _x_, del 2Theta, quiero que vaya desde 5 a 120 grados. Cambiamos el valor en <kbd>From</kbd> y <kbd>To</kbd>, y clickeamos en <kbd>OK</kbd>.

![Figura 61](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image061.png)

Para que el gráfico ocupe toda la pantalla, podemos dar doble _click_ sobre la barra azul.

![Figura 62](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image062.png)

El gráfico queda ocupando toda la pantalla (si quiero que vuelva a hacerse pequeña, podemos hacerlo con el ícono de la parte superior derecha).

![Figura 63](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image063.png)

Lo primero que vamos a hacer es hacer la indexación de los picos y las fases. Para ello, abro el reporte de MATCH, y veo a qué fase corresponde cada pico. En este caso, A es Al (aluminio) y B es Corindón ($Al_2O_3$).<br>

![Figura 64](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image064.png)<br>

![Figura 65](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image065_2.png)<br>

Para escribir sobre el gráfico, clickeamos en la <kbd>T</kbd> de la barra de tareas del lado izquierdo. Después de clickear, nos paramos en el punto donde queremos escribir. En la parte baja de la barra superior encontramos los botones para cambiar el tipo de letra, tamaño, color, etc.

![Figura 66](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image066.png)<br>

Escribimos el nombre de la fase, fórmula química y el número del archivo de la base de datos del MATCH! Ese lo encontramos en el reporte.

![Figura 67](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image067.png)<br>

Ahora, teniendo en cuenta la lista de picos, llevamos a cabo la indexación. Para identificar el ángulo 2Theta en el Origin, clickeamos en el logo mostrado en la siguiente figura, ubicado en la barra de tareas del lado izquierdo. Después de clickear sobre él, nos paramos en la parte superior del pico para ver a qué ángulo se ubica. Al hacer esto, aparece una cruz roja y un cuadro con la información del punto: su valor en 2Theta y en intensidad. Si quiero moverme a través de la curva, uso las flechas del teclado. Ahora, miramos su coincidencia con la lista de picos del reporte de Match!, y llevamos a cabo la indexación. En este caso, es el ubicado a 35.07 grados que, según el reporte, corresponde a la fase B.

![Figura 68](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image068.png)<br>

Vamos a otorgarle un símbolo a cada fase. Un cuadro, para la fase 1, de color negro; y un círculo, en azul, para la fase 2. A estas figuras geométricas también las encontramos en la barra de tareas de la izquierda.

![Figura 69](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image069.png)<br>

Clickeamos en la pestañita y se despliega un submenú.

![Figura 70](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image070.png)<br>

Escogemos <kbd>Rectangle tool</kbd>. Movemos el cursor hacia la posición en la queremos dibujar la figura geométrica, y lo hacemos con el _mouse_. Si queremos moverlo, lo señalamos dando _click_, y lo desplazamos con ayuda de las flechas del teclado, o con el _mouse_, sosteniendo el _click_ izquierdo. Para copiar y pegar también lo señalamos con el _mouse_, clickeando, y usamos los comandos <kbd>Ctr+c</kbd> y <kbd>Ctr+v</kbd>. El resultado del patrón de difracción indexado queda así:

![Figura 71](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image071.png)<br>

Podemos exportar el gráfico para pegarlo en algún reporte en WORD. Para ellos, vamos a <kbd>File</kbd>, <kbd>Export Graphs</kbd>, <kbd>Open Dialog</kbd>. Esto último, para poder escoger la ruta donde vamos a guardar la imagen, el tipo de archivo y darle nombre.

![Figura 72](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image072.png)<br>

Se abre la siguiente ventana. 

![Figura 73](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image073.png)<br>

En <kbd>Image Type</kbd> escogemos el tipo de archivo que queremos. Las imágenes en .tiff funcionan muy bien.

![Figura 74](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image074.png)<br>

En <kbd>File name(s)</kbd> ponemos el nombre de la figura y en <kbd>Path</kbd> buscamos la ruta donde queremos que se guarde (en el botón de los 3 puntos).

![Figura 75](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image075.png)<br>

Como resultado, se genera el gráfico con la extensión y nombre escogidos, en la carpeta seleccionada. Esa gráfica podemos pegarla en algún documento de interés:

![Figura 76](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image076.png)<br>

Otra forma de mostrar el resultado es poniendo los índices de Miller de los planos difractados. Para ello, en el archivo del Match! abrimos la lista de picos <kbd>Peak list</kbd>. Recordemos que al Match! le podemos pedir que muestre los índices de Miller sobre cada pico.

![Peak list](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image046.png)

Así, podemos reportar el gráfico en esa forma. En el Origin puedo duplicar un gráfico (y un libro), parándome en la parte superior del marco y dando click derecho. Eso despliega un pequeño menú, de donde escogemos <kbd>Duplicate</kbd>.

![Figura 77](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image077.png)<br>

Duplicamos el gráfico:

![Figura 78](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image078.png)<br>

Con el _click_ izquierdo sostenido, hacemos un barrido para escoger todo lo que hemos hecho encima del gráfico:

![Figura 79](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image079.png)<br>

Cuando soltamos, todo queda seleccionado:

![Figura 80](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image080.png)<br>

Le damos suprimir, para borrar. Otra vez queda limpio el gráfico:

![Figura 81](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image081.png)<br>

Clickeamos el símbolo de <kbd>T</kbd> en la barra de tareas de la izquierda para escribir un texto. Después de escrito, nos salimos de él y le damos _click_ en el centro.

![Figura 82](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image082.png)<br>

Eso habilita el cuadro para girar:

![Figura 83](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image083.png)<br>

Lo giramos de tal forma que quede vertical, y lo movemos a su posición:

![Figura 84](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image084.png)<br>

Podemos copiar y pegar este texto, y editarlo para escribir los índices de Miller de cada plano:

![Figura 85](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image085.png)<br>

Después de exportar el gráfico en *.tiff, queda así:

![Figura 86](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image086.png)<br>

## Ajuste de picos

Ajustar los picos significa encontrar la curva o función matemática que los representa. Típicamente hay varias curvas que sirven para ajustar los picos de difracción de rayos X. Entre ellas están las siguientes, que se muestran con sus respectivas ecuaciones:

*	Curva gaussiana

<div align="center">

$G = \frac{{ \sqrt {C_{0}} }}{{Γ_{k}\sqrt {π}}} e^{[-\frac{{ C_{0}}}{{{Γ_{k}^2}}}(2θ_{i}-2θ_{k})]};C_{0}=4ln2$

</div>

*	Curva Lorentziana

<div align="center">

$L = \frac{{ 2 \sqrt {C_{0}} }}{{ π Γ_{k}}} \frac{{1}}{{1 + \frac{{C_{0}}}{{{Γ_{k}^2}(2θ_{i}-2θ_{k})}} }};C_{0}=4$

</div>

* Pearson VII

<div align="center">

$P_{VII} = \frac{{C_{0}}}{{Γ_{k}}} {[1 + \frac{{4 ( \sqrt [m]{2} -1)}}{{{Γ_{k}^2}}}{(2θ_{i}-2θ_{k})^2}]^{-m}};C_{0} = \frac{{2 \sqrt {m} {(\sqrt [m]{2} - 1)}^{1/2} }}{{\sqrt {π(m-0.5)} }}$

</div>

* Pseudo-Voight, que hace una combinación entre gaussiana y lorentziana, siendo η la fracción de cada función.

<div align="center">

$pV = η L + (1-η) G$

</div>

Como ejemplo, miremos el archivo con el que estamos trabajando. Vamos a trabajar con el pico (111) de la fase del aluminio. Para ello, vamos a copiar sus datos y los vamos a copiar en otro libro dentro del proyecto de Origin. Primero, con el ícono mostrado en la siguiente figura nos vamos a parar en el inicio y en el final del pico, para saber el valor del ángulo 2Theta en el que inicia y termina. Si desea aumentar el pico, puede usar la lupa con el signo más que se ve de segundo de arriba abajo en la barra de tareas de la izquierda.

![Figura 91](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image091.png)<br>

Después de clickear en la lupa, se señala con un rectángulo –barriendo la pantalla con el _click_ izquierdo sostenido- el área que queremos aumentar.

![Figura 92](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image092.png)<br>

Así se ve el área aumentada:

![Figura 93](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image093.png)<br>

Al dar _click_ en el ícono señalado por la flecha roja que se mostró, se abre una ventana –que podemos mover clickeando en la parte de arriba, y sosteniendo el _click_ izquierdo-, que muestra el valor de 2Theta y de intensidad:

![Figura 94](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image094.png)<br>

Nos paramos cerca de donde inicia el pico, y leemos el dato de 2Theta:

![Figura 95](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image095.png)<br>

Nos paramos donde termina el pico, y leemos el valor de 2Theta.

![Figura 96](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image096.png)<br>

Como puede verse, el pico va desde 37.75° hasta 38.98°. <br>
Para salir del modo lectura de puntos, utilizamos la tecla de <kbd>ESCAPE</kbd> y cerramos la ventana de lectura.<br>
Para volver la imagen al tamaño real, clickeamos en la lupa con el signo de menos.<br>
Ahora, hacemos pequeña la ventana de la figura, y del libro resaltamos, con _clik_ izquierdo sostenido, los datos que queremos copiar. Damos <kbd>CRT+C</kbd>.<br>

![Figura 97](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image097.png)<br>

Con los datos copiados, creamos otro libro:<br>

![Figura 98](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image098.png)<br>

Y copiamos los datos:<br>

![Figura 99](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image099.png)<br>

Con el _click_ izquierdo sostenido señalamos ambas columnas <kbd>(A(X)</kbd> y <kbd>B(Y))</kbd> y graficamos con el logo de la línea ubicado en la parte izquierda de la barra de tareas de la parte inferior.

![Figura 100](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image100.png)<br>

Con doble-_clik_ izquierdo en la parte superior de la imagen la agrandamos. Ahora, vamos a probar el ajuste con las 3 curvas que mencionamos. Para ello, nos vamos a <kbd>ANALYSIS</kbd>, <kbd>FITTING</kbd>, <kbd>SINGLE-PEAK</kbd>, <kbd>OPEN DIALOG</kbd>.

![Figura 101](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image101.png)<br>

Al hacer se abre un cuadro de diálogo:

![Figura 102](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image102.png)<br>

Abrimos la pestaña de <kbd>FUNCTIONS</kbd>:

![Figura 103](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image103.png)<br>

Podemos ver que aparecen varias funciones, entre ellas las que ya mencionamos: gaussiana, lorentziana y pseudo-voigt. Vamos a comparar las tres, empezando con la **gaussiana**. La escogemos:

![Figura 104](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image104.png)<br>

Y damos _click_ en <kbd>FIT</kbd>.
El resultado se muestra a continuación. Puede verse que, aunque el $R^2 = 0.9877$, no están bueno. Esto indica que otra de las funciones podría ajustarse mejor a este pico.

![Figura 105](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image105.png)<br>

A continuación, se muestra el resultado con la Lorentziana, con un $R^2 = 0.9958$, que es un valor más alto que el reportado por la **Lorentziana** y el ajuste se ve mejor.

![Figura 106](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image106.png)<br>

La **Pearson VII** también da un buen ajuste, con $R^2 = 0.9971$.

![Figura 107](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image107.png)<br>

La **pseudo-voigt1** es la que mejor ajuste muestra en este caso, con un $R^2 = 0.9975$.

![Figura 108](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image108.png)<br>

## Cálculo de parámetros de red

Ya sabemos que hay una ecuación que relaciona la distancia interplanar de un plano con índices de Miller **(hkl)** con los parámetros de red de la estructura cristalina.

<div align="center">

  $\frac{{1}}{{{d^2}}} =\frac{{{h^2}}}{{{a^2}}} + \frac{{{k^2}}}{{{b^2}}} + \frac{{{l^2}}}{{{c^2}}}$

</div>


Si la **estructura cristalina** es **cúbica**, como es el caso del aluminio, que exhibe estructura cristalina FCC, la ecuación se simplifica:

<div align="center">

![FCC](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/FCC%20PNG.png)

$\frac{{1}}{{{d^2}}} = \frac{{{h^2}+{k^2}+{l^2}}}{{{a^2}}}$

</div>

Despejando, vemos que podríamos calcular el parámetro de red de una estructura cúbica si conocemos la distancia interplanar y los índices de Miller del plano de un pico difractado.

<div align="center">

$a = d_{(hkl)} \sqrt {{h^2}+{k^2}+{l^2}}$

</div>

Para conocer la distancia interplanar, como ya veíamos, usamos la Ley de Bragg, usando _n_ = 1.

<div align="center">

$2 d Sen(θ) = n λ$

</div>

Si combinamos ambas ecuaciones, tenemos que:

<div align="center">

$a = \frac{{λ}}{{2 Sen(θ)}} \sqrt {{h^2}+{k^2}+{l^2}}$

</div>

Recordemos que theta es el ángulo al que difracta el pico. Por lo tanto, para conocer el parámetro de red debemos conocer _λ_, que es la longitud de onda de los rayos X; el ángulo de difracción del pico, que es _θ_; y los índices de Miller del pico. El ángulo _2Theta_ de difracción lo muestra Origin después de hacer el ajuste, como $x_{c}$.

![Figura 114](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image114.png)<br>

Si nos fijamos en el pico ajustado por la función pesudo-voigt, el pico se ubica a $x_{c} = 38.3964°$.

Los datos de este pico con el que estamos trabajando son:

|         | Valor |
|---------|:---------------------|
| 2θ (grados)  | 38.3964 |
| θ (grados)  | 19.1982  |
| λ (Å)  | 1.5419   |
| (_hkl_)  | (111)   |

Por lo tanto:

<div align="center">

$a = \frac{{1.54184 Å}}{{2 Sen(19.1982°)}} \sqrt {{1^2}+{1^2}+{1^2}} = 4.06059 Å$

</div>

Sin embargo, esta medida tiene un error asociado (aunque el valor es muy cercano al valor teórico del parámetro de red para el aluminio, que es de 4.05049 Å). En el caso del cálculo de los parámetros de red _los errores sistemáticos tienden a cero cuando Theta tiende a 90°_, por lo que pueden eliminarse usando una **función de extrapolación**.

<div align="center">

$(\frac{{δa}}{{a}})_{abs}∝[\frac{{{Cos^2}(θ)}}{{Sen(θ)}}+\frac{{{Cos^2}(θ)}}{{θ}}]$

</div>

### Función de extrapolación de Nelson-Riley

La función de **Nelson-Riley** es una función de extrapolación que se usa para calcular el parámetro de red. El método consiste, entonces, en calcular el parámetro de red para cada pico difractado de la fase, y hacer un gráfico de esos parámetros de red versus la función de Nelson-Riley, que también se calcula para cada pico. En el gráfico, el corte corresponde al valor real del parámetro de red, mientras que la pendiente indica el error sistemático: a mayor pendiente, mayor error sistemático. A continuación, se muestra la función de Nelson-Riley.

<div align="center">

$F(θ) = \frac{{1}}{{2}} [\frac{{{Cos^2}(θ)}}{{Sen(θ)}}+\frac{{{Cos^2}(θ)}}{{θ}}]$


</div>

Por lo tanto, debe graficarse cada pico difractado de la fase que queremos analizar, y extraer el valor de Theta.

![Figura 118](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image118.png)<br>

Después de graficar los picos, le damos _click_ a <kbd>ANALYSIS</kbd> y <kbd>SINGLE-PEAK FIT</kbd>: <kbd>Last used</kbd>, ya que el guarda nuestra última elección. Seguiremos trabajando con **pseudo-voigt**.

![Figura 119](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image119.png)<br>

![Figura 120](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image120.png)<br>

Para los cálculos, podemos hacernos una tabla en **EXCEL**.

![Figura 121](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image121.png)<br>

Graficamos, en ORIGIN, _a_ versus _F(theta)_.

![Figura 122](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image122.png)<br>

Ajustamos los datos a una línea recta: <kbd>ANALYSIS</kbd>, <kbd>FITTING</kbd>, <kbd>LINEAR-FIT</kbd>, <kbd>Last-used</kbd>.

![Figura 123](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image123.png)<br>

El intercepto de la línea corresponde al **parámetro de red** de la fase, que es el **aluminio**. El valor es, entonces, $a = 4.05424 ± 0.00027 Å$.

![Figura 124](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image124.png)<br>

Podemos acomodar la gráfica para exportarla: sacamos la tabla y el título fuera del área blanca; insertamos texto para colocar un título adecuado, y otro para colocar el valor del parámetro de red; también podemos dar doble _click_ en uno de los puntos de la gráfica y cambiar su forma, tamaño y color; y seleccionar la línea roja para aumentar su espesor y ponerla punteada.

![Figura 125](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image125.png)<br>

![Figura 126](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image126.png)<br>

Después de exportada, así queda la imagen:

![Figura 127](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image127.png)<br>

### Otras funciones de extrapolación

Hay otras funciones además de la de Nelson-Riley:

* Bradley-Jay

<div align="center">

$F(θ) = \frac{{{Cos^2}(θ)}}{{θ}}$

</div>

* Jay

<div align="center">

$F(θ) = \frac{{{Cos^2}(θ)}}{{Sen(θ)}}$

</div>

* Buerger

<div align="center">

$F(θ) = cot(θ) {Cos^2}(θ)$

</div>

A continuación podemos comparar los resultados al usar las cuatro funciones mencioandas.

![Figura 131](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image131.png)<br>

En la siguiente tabla se hace la comparación de los valores reportados por cada método. 

| Método  | Parámetro de red (Å) |
|---------|:---------------------|
| Nelson-Riley  | 4.05424 ± 0.00027 |
| Bradley-Jay  | 4.05432 ± 0.00027  |
| Jay  | 4.05416 ± 0.00027   |
| Buerger  | 4.05463 ± 0.00026   |

Teniendo en cuenta que las barras de error se traslapan, puede decirse que los valores son bastante similares.

![Figura 132](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image132.png)<br>

Si la estructura cristalina no es cúbica, el cálculo de los parámetros de red es un poco diferente. Ese es el caso de la segunda fase del material con el que estamos trabajando. Esta fase es el corindón o alúmina, que exhibe **estructura cristalina hexagonal**. Esta estructura cristalina queda definida con 2 parámetros de red, _a_ y _c_.

<div align="center">

![Figura 133](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image133.png)<br>

</div>

La ecuación para esta estructura cristalina es:

<div align="center">

$\frac{{1}}{{{d^2}}} = \frac{{4}}{{3}} \frac{{{h^2}+hk+{k^2}}}{{{a^2}}} + \frac{{l^2}}{{c^2}}$

</div>

Combinándola con la ley de Bragg, tenemos:

<div align="center">

${sen^2}(θ) = \frac{{{λ^2}}}{{4}} (\frac{{4}}{{3}} (\frac{{{h^2}+hk+{k^2}}}{{{a^2}}}) + \frac{{{l^2}}}{{{c^2}}})$

</div>

Sacando $1⁄{a^2}$  como factor común, nos queda:

<div align="center">

${sen^2}(θ) = \frac{{{λ^2}}}{{4{a^2}}} (\frac{{4}}{{3}} ({h^2}+hk+{k^2}) + \frac{{{l^2}}}{{{(c/a)^2}}})$

</div>

Vamos a asumir que el valor de _c/a_ es conocido (podemos encontrar el valor teórico, según el material que estemos trabajando). En el caso del corindón, el valor teórico es de 2.72892694.
Con los picos difractados de índices de miller _(hk0)_ vamos a calcular el parámetro de red _a_, ya que la ecuación se simplifica así:

<div align="center">

${sen^2}(θ) = \frac{{{λ^2}}}{{4{a^2}}} (\frac{{4}}{{3}} ({h^2}+hk+{k^2}))$

</div>

En este caso, esos picos son los correspondientes a los planos _(110)_ y _(300)_. En el Origin miramos el ángulo 2Theta correspondiente.

Teniendo en cuenta que el pico del plano _(110)_ de la alúmina está muy cerca del pico del plano (111) del aluminio, podemos hacer el ajuste con pico múltiple. Clickeamos en <kbd>ANALYSIS</kbd>, <kbd>Peaks and Baselines</kbd>, <kbd>Multiple Peak Fit</kbd>, <kbd>Open Dialog</kbd>.

![Figura 139](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image139.png)<br>

Al abrirse la ventana escogemos la función **Pesudo-Voigt** y damos _Ok_.

![Figura 140](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image140.png)<br>

Al hacer esto se abre una nueva ventana que nos pide que escojamos el centro aproximado de cada pico con doble _click_ (en la flecha se señala cada centro de pico). Al dar doble _click_, cada pico queda seleccionado con una línea roja:

![Figura 141](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image141.png)<br>

Podemos ver que el mencionado pico se ubica a 37.67829°.

![Figura 142](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image142.png)<br>

Teniendo en cuenta la baja intensidad de los picos de la fase del corindón, es mejor seleccionar varios picos y hacer el ajuste por multipicos.

![Figura 143](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image143.png)<br>

Los dos picos con planos _(hk0)_ son:

|     Plano    | 2Theta |
|---------|:---------------------|
| (110)  | 37.67829 |
| (300)  | 68.10284  |

Haciendo los cálculos con **EXCEL**, encontraremos el valor del parámetro de red a del corindón para dos picos difractados.

![Figura 144](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image144.png)<br>

De nuevo, podemos usar una función de extrapolación para calcular el valor real del parámetro de red. Usemos la de **Nelson-Riley**.

![Figura 145](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image145.png)<br>

Según esto, el parámetro de red $a = 4.76523 Å$.

![Figura 146](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image146.png)<br>

Ahora, teniendo el valor del parámetro de red _a_, podemos proceder con el cálculo del parámetro de red _c_. Usando los valores de la difracción de los planos _(102)_, _(113)_ y _(116)_ (porque el valor reportado por el pico del plano _(104)_ se sale de la tendencia), el resultado es el siguiente:

![Figura 147](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image147.png)<br>

![Figura 148](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image148.png)<br>

Por lo tanto, usando el método de la función de extrapolación y las ecuaciones de la ley de Bragg y las que relacionan distancia interplanar con los índices de Miller y los parámetros de red pudimos calcular los parámetros de red de las dos fases que componen el material:

*	Aluminio, de estructura cristalina FCC, con _a_ = 4.05424 ± 0.00027 Å
*	Corindón, de fórmula química $Al_{2}O_{3}$ y estructura cristalina hexagonal compacta, con _a_ = 4.76523 Å y _c_ = 12.97831 ± 0.00645 Å.

## Cálculo de tamaño de cristalito y microdeformaciones

### Ensanchamiento de picos

Si los rayos X incidieran y fuera difractados de forma perfectamente paralela entre ellos, no debería producirse un pico ancho, sino una sola línea de difracción.

<div align="center">

![Figura 149](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image149.png)<br>

</div>

Sin embargo, los rayos X que inciden sobre la muestran no llegan paralelos entre ellos, sino ligeramente paralelos. Esto causa el ensanchamiento de la línea.

<div align="center">

![Figura 150](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image150.png)<br>
![Figura 151](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image151.png)<br>

</div>

Ese tipo de ensanchamiento se denomina instrumental y debe corregirse. Para determinar el ensanchamiento instrumental se utiliza una muestra de calibración, la cual debe tener un tamaño de cristalito mayor a 100 nm, no poseer microtensiones y, si es posible, tener cristalitos uniformes.

<div align="center">

![Figura 152](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/Secci%C3%B3n02/.graph/image152.png)<br>)

</div>

La corrección se hace al FWHM, ancho a la altura media de cada pico, usando la siguiente ecuación:

<div align="center">

$FWHM = {[{(FWHM_{medido})^2}-{(FWHM_{instrumental})^2}]^{1/2}}$

</div>

Para esto, debe sacarse una ecuación de FWHM en función de θ para, a partir de ella, calcular el ancho instrumental a un determinado ángulo y restarlo a cada pico de nuestro patrón de difracción que nos interese corregir. Para esto se requiere un concepto que veremos a profundidad más adelante, que es el de refinamiento, ya que el patrón de difracción de la muestra de calibración debe refinarse. La ecuación usada es la de Caglioti, que tiene la siguiente forma:

<div align="center">

${FWHM^2} = U {tan^2}(θ) + V tan(θ) + W$

</div>

Además del ensanchamiento instrumental, también hay un efecto del tamaño de cristalito y de las microdeformaciones del cristal en el ensanchamiento de los picos difractados.

Asumiendo que ∆θ es el ensanchamiento del pico después de haber restado el ensanchamiento instrumental,  el método de **Williamson-Hall** asume que éste es debido a microdeformaciones de la red y a la disminución del tamaño de cristalito (regiones realmente cristalinas dentro de los granos), por debajo de los 100 nm.

<div align="center">

$∆θ = β_{D} + β_{ε}$

</div>

Siendo $β_{D}$ el ensanchamiento causado por el tamaño de cristalito y $β_{ε}$ el ensanchamiento causado por las microdeformaciones.
La ecuación del ensanchamiento por tamaño de cristalito tiene la siguiente forma:

<div align="center">

$β_{D} = \frac{{kλ}}{{D cos(θ)}}$

</div>

Donde _k_ típicamente es igual a 0.9, aunque depende de la forma del cristalito; _λ_ es la longitud de onda de los rayos X incidentes; _θ_ es medio ángulo de difracción; y _D_ es la dimensión lineal del cristalito, como el diámetro.

La ecuación del ensanchamiento por microdeformaciones tiene la siguiente forma:

<div align="center">

$β_{ε} = 4 ε tan(θ)$

</div>

Donde _θ_ es medio ángulo de difracción y _ε_ es la medida de las microdeformaciones.

### Ecuación de Williamson-Hall

Remplazando los términos del ensanchamiento por tamaño de cristalito y por microdeformaciones en la ecuación del ensanchamiento y reacomodando los términos, tenemos la siguiente ecuación:

<div align="center">

$FWHM cos(θ) = \frac{{0.9λ}}{{D)}} + 2 ε sen(θ)$

</div>

El método de Williamson-Hall consiste, entonces, en calcular el ancho a la altura media de cada pico y su ángulo de difracción y hacer un gráfico de **FWHM×cos⁡θ** _versus_ **2sin⁡θ**. El resultado es una línea recta, cuya pendiente corresponde a la microdeformación y a partir de la pendiente, con la longitud de onda de los rayos X difractado, se puede calcular el tamaño de cristalito.

Vamos a hacer el cálculo para el aluminio de nuestro patrón de difracción de rayos X. Como ya habíamos ajustado los picos según la curva pseudo-voigt, vamos a colocar la información que requerimos en una tabla de EXCEL.

![Figura 114](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/fd677d57-ad7c-48d4-a2be-a2fd4b77e17d)

A continuación, se muestra el resultado de la gráfica en Origin. El ajuste es aceptable, con un R2 = 0.9408 para una línea recta.

<div align="center">

![Williamson-Hall Aluminio](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8b086f96-c16c-4bbe-bf8b-cc1548e96ce8)

</div>

Las microdeformaciones tienen el valor de 0.00188 ± 0.00021
Haciendo el cálculo del tamaño de cristalito, tenemos:

<div align="center">

$D = \frac{{0.9×0.154184 nm}}{{0.00218}} = 63.6 nm$

</div>

Podemos calcular, también, la propagación del error, teniendo que b, en este caso, es el intercepto.

<div align="center">

$∆D = \lvert \frac{{∂D}}{{∂b}} \rvert ∆b = 0.9×0.154184 {b^{-2}} ∆b = \frac{{0.9×0.154184}}{{{b^2}}} ∆b$

$∆D = \frac{{0.9×0.154184}}{{{0.00218^2}}} 0.00025 = 7.3 nm$

</div>

Así, el dato completo del tamaño de cristalito del aluminio es 63.6 ± 7.3 nm.

## Cálculo de densidad de dislocaciones

Teniendo el valor de la microdeformación del cristal, podemos calcular, según la siguiente ecuación, la densidad de dislocaciones de la fase:

<div align="center">

$ρ = \frac{{2 \sqrt {3} ε}} {{D×b}}$

</div>

Siendo _ε_ el valor absoluto de la microdeformación, _D_ el tamaño de cristalito y _b_ el vector de Burger.

Recordemos que para la estructura cristalina FCC, según la siguiente tabla, el módulo del vector de Burger es $b = \frac{{a}} {{\sqrt {3}}}$. 

|     Estructura cristalina    | Dirección de deslizamiento | Vector de Burgers |
|---------|:---------------------|:--------:|
| CS  | <100>                |  _a_   |
| FCC  | <110>                |  $\frac{{a}} {{\sqrt {2}}}$   |
| BCC  | <111>                |  $\frac{{a}} {{\sqrt {3}}}$   |
| HCP  | <100> y <110>                |  _a_   |

Como ya conocemos el valor del parámetro de red porque lo calculamos con el método de Nelson-Riley, podemos calcular del valor del vector de Burger:

<div align="center">

$b = \frac{{4.05424 Å}} {{\sqrt {3}}}$ = 2.34072 Å = 0.234072 nm

</div>

Calculando la densidad de dislocaciones:

<div align="center">

$ρ = \frac{{2 \sqrt {3} ε}} {{D×b}} = \frac{{2 \sqrt {3} × 00188}} {{63.62 nm × 0.234072 nm}}$ = 4.37332× ${10^5}$ $\frac{{dislocaciones}}{nm^2}$

</div>

Pasándolo a ${cm^2}$, tenemos 4.37 * ${10^{11}}$ $\frac{{dislocaciones}}{cm^2}$, que también pueden expresarse como 4.37 * ${10^{11}}$ cm de línea de $\frac{{dislocaciones}}{cm^3}$.
##

<div align="center">

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/a62bde9b-b559-41e5-8c87-07ec98a4f24a)

[Formulario de admisión](https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL)

</div>

##

![Imagen18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/80157826-863f-40fb-919c-40449bfe4e9e)

