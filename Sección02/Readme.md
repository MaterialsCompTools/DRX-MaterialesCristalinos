<div align="center">

# Determinación de rasgos cristalográficos

</div>

<div align="center">
  
![Origin logo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/6595d0e0-7d57-46b2-87db-6069f6da86f7)

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

![Figura 48](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/37d67ae2-37ef-40b7-b362-32257f9a0c74)

Esa acción nos abre un primer libro.<br>

<img width="960" alt="Figura 49" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b0a0bb02-5a46-4199-9f0e-be75a17a699b">

Como puede verse, tenemos 4 barras de tareas, en las partes superior, inferior, derecha e izquierda. En la parte superior tenemos varias ventas: <kbd>File</kbd>, <kbd>Edit</kbd>, <kbd>View</kbd>, <kbd>Plot</kbd>, <kbd>Column</kbd>, <kbd>Worksheet</kbd>, <kbd>Analysis</kbd>, <kbd>Statistics</kbd>, <kbd>Image</kbd>, <kbd>Tools</kbd>, <kbd>Format</kbd>, <kbd>Window</kbd> y <kbd>Help</kbd>. Veremos, de manera práctica, cómo las usamos.<br>

El libro tiene varias partes importantes. Nos indica la columna del eje _x_ y del eje _y_. El nombre del libro, que quedará definido por el título del archivo que abramos. Nos indica cuáles son las casillas para los nombres de las columnas, donde pondremos la variable medida. Esto definirá el título de cada uno de los ejes. Luego tenemos la casilla de las unidades de medida de cada variable. Los comentarios son para poner alguna información relevante sobre la muestra que vamos a analizar. Una temperatura o un tiempo de proceso, por ejemplo, o una composición química. Esto dependerá de lo que estemos analizando. Y <kbd>F(x)</kbd> es para colocar alguna fórmula matemática para que se haga alguna operación.<br>

![Figura 50](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/3bd498cb-9ce6-499c-9541-a75540586cdf)<br>

## Importar archivo y reportar el patrón de DRX

Para aprender a exportar el archivo, podemos dirigirnos a la sección anterior [Exportar archivos](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/tree/main/Secci%C3%B3n01#exportar-archivos). Para importarlo, vamos a la pestaña de <kbd>File</kbd>, <kbd>Import</kbd>, <kbd>Single ASCII</kbd>.

<img width="960" alt="Figura 51" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/d9d9a9bd-2003-4a0c-a4c3-e442d937f133">

Esta acción nos dirige a una ventana, donde podemos buscar nuestro archivo:<br>

<img width="960" alt="Figura 52" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/356f5e76-ae73-445b-9032-84743a4dbe9d">

Haciendo doble _click_ podemos abrir el archivo. Ponemos los títulos:

![Figura 53](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/f5fc4cc6-0fb0-4f49-8ddb-6a2db9df4d63)<br>

Para graficar, con el _click_ izquierdo sostenido, señalamos ambas columnas. Nos dirigimos a la barra de tareas inferior, y clickeamos en el ícono de línea:<br>

![Figura 54](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/eb1dcf20-1da6-4015-b50b-eee22aa6dc70)<br>

Esto acción nos construye el gráfico:

![Figura 55](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/79aece78-4339-4fd1-8043-0d3674dd54e3)

Dando doble _click_ sobre cada uno de los ejes podemos acomodar de qué valor a qué valor hacer el gráfico. Para el eje _x_, del 2Theta, quiero que vaya desde 5 a 120 grados. Cambiamos el valor en <kbd>From</kbd> y <kbd>To</kbd>, y clickeamos en <kbd>OK</kbd>.

![Figura 56](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/2f29183a-b64e-4ba6-a737-b6185bad0b73)

Para que el gráfico ocupe toda la pantalla, podemos dar doble _click_ sobre la barra azul.

![Figura 57](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/15872674-d3a0-4831-a4c1-89856983ad38)

El gráfico queda ocupando toda la pantalla (si quiero que vuelva a hacerse pequeña, podemos hacerlo con el ícono de la parte superior derecha).

<img width="960" alt="Figura 58" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8cfaa57c-94c9-4fd3-8f97-3583d11280b1">


Lo primero que vamos a hacer es hacer la indexación de los picos y las fases. Para ello, abro el reporte de MATCH, y veo a qué fase corresponde cada pico. En este caso, A es Al (aluminio) y B es Corindón (Al2O3).<br>

![Figura 59](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/37d620ab-fc14-49c5-ab92-3aaaf313476e)<br>

![Figura 60](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/3a5548b9-dfff-422c-8d8f-5284ef24d89d)<br>

Para escribir sobre el gráfico, clickeamos en la <kbd>T</kbd> de la barra de tareas del lado izquierdo. Después de clickear, nos paramos en el punto donde queremos escribir. En la parte baja de la barra superior encontramos los botones para cambiar el tipo de letra, tamaño, color, etc.

![Figura 61](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/0e176d81-1775-40b7-b67a-68317b062c56)

Escribimos el nombre de la fase, fórmula química y el número del archivo de la base de datos del MATCH! Ese lo encontramos en el reporte.

![Figura 62](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/d382fbba-792f-4aed-8452-8742491c704e)

Ahora, teniendo en cuenta la lista de picos, llevamos a cabo la indexación. Para identificar el ángulo 2Theta en el Origin, clickeamos en el logo mostrado en la siguiente figura, ubicado en la barra de tareas del lado izquierdo. Después de clickear sobre él, nos paramos en la parte superior del pico para ver a qué ángulo se ubica. Al hacer esto, aparece una cruz roja y un cuadro con la información del punto: su valor en 2Theta y en intensidad. Si quiero moverme a través de la curva, uso las flechas del teclado. Ahora, miramos su coincidencia con la lista de picos del reporte de Match!, y llevamos a cabo la indexación. En este caso, es el ubicado a 35.07 grados que, según el reporte, corresponde a la fase B.

![Figura 63](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/fe48d89c-a42c-4c14-ba0e-40427caa7299)

Vamos a otorgarle un símbolo a cada fase. Un cuadro, para la fase 1, de color negro; y un círculo, en azul, para la fase 2. A estas figuras geométricas también las encontramos en la barra de tareas de la izquierda.

![Figura 64](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/d7fb0d9c-9d71-4e4d-8844-a6246d37afc8)

Clickeamos en la pestañita y se despliega un submenú.

![Figura 65](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1df219d7-99f6-42a8-b123-3ab657b5e370)

Escogemos <kbd>Rectangle tool</kbd>. Movemos el cursor hacia la posición en la queremos dibujar la figura geométrica, y lo hacemos con el _mouse_. Si queremos moverlo, lo señalamos dando _click_, y lo desplazamos con ayuda de las flechas del teclado, o con el _mouse_, sosteniendo el _click_ izquierdo. Para copiar y pegar también lo señalamos con el _mouse_, clickeando, y usamos los comandos <kbd>Ctr+c</kbd> y <kbd>Ctr+v</kbd>. El resultado del patrón de difracción indexado queda así:

![Figura 66](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/46651bd8-1137-4dcd-aa03-ac064ffe34a9)

Podemos exportar el gráfico para pegarlo en algún reporte en WORD. Para ellos, vamos a <kbd>File</kbd>, <kbd>Export Graphs</kbd>, <kbd>Open Dialog</kbd>. Esto último, para poder escoger la ruta donde vamos a guardar la imagen, el tipo de archivo y darle nombre.

![Figura 67](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/d9cc1cc4-4626-429d-a816-fead70268caa)

Se abre la siguiente ventana. 

![Figura 68](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/16269426-1d9e-4486-933c-e7eb3d165115)

En <kbd>Image Type</kbd> escogemos el tipo de archivo que queremos. Las imágenes en .tiff funcionan muy bien.

![Figura 70](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/52f367bb-5f79-4432-85a1-4b679079fc1e)

En <kbd>File name(s)</kbd> ponemos el nombre de la figura y en <kbd>Path</kbd> buscamos la ruta donde queremos que se guarde (en el botón de los 3 puntos).

![Figura 71](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/96768025-ced4-479f-a3b7-5773d81b2da7)

Como resultado, se genera el gráfico con la extensión y nombre escogidos, en la carpeta seleccionada. Esa gráfica podemos pegarla en algún documento de interés:

![Patrón](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b44395bf-c23f-4615-86da-30a07102ebeb)

Otra forma de mostrar el resultado es poniendo los índices de Miller de los planos difractados. Para ello, en el archivo del Match! abrimos la lista de picos <kbd>Peak list</kbd>. Recordemos que al Match! le podemos pedir que muestre los índices de Miller sobre cada pico.

![Figura 72](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1c12f80e-9d3f-4429-af53-e4295ec8b9e6)

Así, podemos reportar el gráfico en esa forma. En el Origin puedo duplicar un gráfico (y un libro), parándome en la parte superior del marco y dando click derecho. Eso despliega un pequeño menú, de donde escogemos <kbd>Duplicate</kbd>.

![Figura 73](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/9ae6c01d-8a77-4a77-a577-692ac0384bc3)

Duplicamos el gráfico:

![Figura 74](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/cbc24213-bda7-4054-99a6-a182967a6598)

Con el _click_ izquierdo sostenido, hacemos un barrido para escoger todo lo que hemos hecho encima del gráfico:

![Figura 75](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/6da5297d-9894-412a-98f4-8d4a2519b7ed)

Cuando soltamos, todo queda seleccionado:

![Figura 76](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/69b46d2a-150f-4332-9494-3beaa181596e)

Le damos suprimir, para borrar. Otra vez queda limpio el gráfico:

![Figura 77](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/9c49c6fa-c15a-4675-98e8-125ce323113d)

Clickeamos el símbolo de <kbd>T</kbd> en la barra de tareas de la izquierda para escribir un texto. Después de escrito, nos salimos de él y le damos _click_ en el centro.

![Figura 78](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8c517e24-18c9-4561-8c30-39a9974b5430)

Eso habilita el cuadro para girar:

![Figura 79](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/3b2ae8c9-2d4f-40c7-982b-ba2866482339)

Lo giramos de tal forma que quede vertical, y lo movemos a su posición:

![Figura 80](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/82a79108-f98d-45a8-a1d2-552ca5d473f8)

Podemos copiar y pegar este texto, y editarlo para escribir los índices de Miller de cada plano:

![Figura 81](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/ff19455d-b0ad-4ff4-b771-fd164dc90d62)

Después de exportar el gráfico en *.tiff, queda así:

![Patrón 2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/951016ef-3b4d-4415-942a-f693e7fb92c9)

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

![Figura 82](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/6efebff6-0afc-43df-8906-faa965ae14d8)

Después de clickear en la lupa, se señala con un rectángulo –barriendo la pantalla con el _click_ izquierdo sostenido- el área que queremos aumentar.

![Figura 83](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/486069e1-6130-4c16-9c4e-80976775ef5a)

Así se ve el área aumentada:

![Figura 84](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/df355001-a6a4-410d-9e8f-cd94f1e9ebe7)

Al dar _click_ en el ícono señalado por la flecha roja que se mostró, se abre una ventana –que podemos mover clickeando en la parte de arriba, y sosteniendo el _click_ izquierdo-, que muestra el valor de 2Theta y de intensidad:

![Figura 85](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/2576f228-363e-4ffb-aa28-c919eea47b52)

Nos paramos cerca de donde inicia el pico, y leemos el dato de 2Theta:

![Figura 86](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/05b67b54-b0b6-475f-a538-c26ab53b8fb8)

Nos paramos donde termina el pico, y leemos el valor de 2Theta.

![Figura 87](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/bd1aca49-31ef-4965-bb4f-0c414a9e187b)<br>

Como puede verse, el pico va desde 37.75° hasta 38.98°. <br>
Para salir del modo lectura de puntos, utilizamos la tecla de <kbd>ESCAPE</kbd> y cerramos la ventana de lectura.<br>
Para volver la imagen al tamaño real, clickeamos en la lupa con el signo de menos.<br>
Ahora, hacemos pequeña la ventana de la figura, y del libro resaltamos, con _clik_ izquierdo sostenido, los datos que queremos copiar. Damos <kbd>CRT+C</kbd>.<br>

![Imagen2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1cf3eb51-709c-403b-8d38-d6c13745f827)

Con los datos copiados, creamos otro libro:<br>

![Imagen3](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/5a7b5724-b77c-4c94-8056-d6e3a32f7bad)<br>

Y copiamos los datos:<br>

![Figura 88](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/d08fddf0-8a5b-47c3-963a-87568073b61f)<br>

Con el _click_ izquierdo sostenido señalamos ambas columnas <kbd>(A(X)</kbd> y <kbd>B(Y))</kbd> y graficamos con el logo de la línea ubicado en la parte izquierda de la barra de tareas de la parte inferior.

![Figura 89](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/0184ea19-2032-4131-b636-fc55296a75f7)

Con doble-_clik_ izquierdo en la parte superior de la imagen la agrandamos. Ahora, vamos a probar el ajuste con las 3 curvas que mencionamos. Para ello, nos vamos a <kbd>ANALYSIS</kbd>, <kbd>FITTING</kbd>, <kbd>SINGLE-PEAK</kbd>, <kbd>OPEN DIALOG</kbd>.

![Figura 90](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/e7a84989-1a2c-41b2-9813-aa5cda526a9f)

Al hacer se abre un cuadro de diálogo:

![Figura 91](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b0b0809a-6ed6-4066-9c49-70772d0528ac)

Abrimos la pestaña de <kbd>FUNCTIONS</kbd>:

![Figura 92](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/c5faad50-e83c-42f3-8ad1-10add3368f6f)

Podemos ver que aparecen varias funciones, entre ellas las que ya mencionamos: gaussiana, lorentziana y pseudo-voigt. Vamos a comparar las tres, empezando con la **gaussiana**. La escogemos:

![Figura 93](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/072afe61-943a-4873-b383-1ab3ec8a2ed4)

Y damos _click_ en <kbd>FIT</kbd>.
El resultado se muestra a continuación. Puede verse que, aunque el $R^2 = 0.9877$, no están bueno. Esto indica que otra de las funciones podría ajustarse mejor a este pico.

![Figura 94](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b99b1165-a29a-42af-97a0-741ba874f7ae)

A continuación, se muestra el resultado con la Lorentziana, con un $R^2 = 0.9958$, que es un valor más alto que el reportado por la **Lorentziana** y el ajuste se ve mejor.

![Figura 95](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b568e3bb-cc6c-46df-8eb5-f3454a0c4b53)

La **Pearson VII** también da un buen ajuste, con $R^2 = 0.9971$.

![Figura 96](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/0e0d6d43-bbc2-4190-8128-8f716df30d5b)

La **pseudo-voigt1** es la que mejor ajuste muestra en este caso, con un $R^2 = 0.9975$.

![Figura 97](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/beb6f452-d989-4a1b-82ad-a873eaf62375)

## Cálculo de parámetros de red

Ya sabemos que hay una ecuación que relaciona la distancia interplanar de un plano con índices de Miller **(hkl)** con los parámetros de red de la estructura cristalina.

<div align="center">

  $\frac{{1}}{{{d^2}}} =\frac{{{h^2}}}{{{a^2}}} + \frac{{{k^2}}}{{{b^2}}} + \frac{{{l^2}}}{{{c^2}}}$

</div>


Si la **estructura cristalina** es **cúbica**, como es el caso del aluminio, que exhibe estructura cristalina FCC, la ecuación se simplifica:

<div align="center">

![FCC](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/09deb90c-2a44-46f6-8ace-52776ea9ddd8)

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

![Pico](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b0b8fa2c-32b9-41db-88e0-4b2a05598391)

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

![Imagen4](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b66ed67a-8646-43ea-b5bc-c276bdc9ac35)

Después de graficar los picos, le damos _click_ a <kbd>ANALYSIS</kbd> y <kbd>SINGLE-PEAK FIT</kbd>: <kbd>Last used</kbd>, ya que el guarda nuestra última elección. Seguiremos trabajando con **pseudo-voigt**.

![Figura 98](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/007282e1-45f4-4074-9926-d8b63c10920c)

![Imagen5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/fe5b056f-ffc9-437c-92cf-2bc4d56970bd)

Para los cálculos, podemos hacernos una tabla en **EXCEL**.

![Figura 99](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/613935a5-c71f-440f-9fa4-588bc5a068ee)

Graficamos, en ORIGIN, _a_ versus _F(theta)_.

![Figura 100](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/151cadd8-9cc6-4073-bc84-c41adae290a2)

Ajustamos los datos a una línea recta: <kbd>ANALYSIS</kbd>, <kbd>FITTING</kbd>, <kbd>LINEAR-FIT</kbd>, <kbd>Last-used</kbd>.

![Figura 101](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/79b4660b-51e6-47ac-819e-86063cc74e9e)

El intercepto de la línea corresponde al **parámetro de red** de la fase, que es el **aluminio**. El valor es, entonces, $a = 4.05424 ± 0.00027 Å$.

![Figura 102](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/96f8abe2-ddba-4115-b4f8-5a9e82f5835e)

Podemos acomodar la gráfica para exportarla: sacamos la tabla y el título fuera del área blanca; insertamos texto para colocar un título adecuado, y otro para colocar el valor del parámetro de red; también podemos dar doble _click_ en uno de los puntos de la gráfica y cambiar su forma, tamaño y color; y seleccionar la línea roja para aumentar su espesor y ponerla punteada.

![Figura 103](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/615e6235-3f7b-406e-b9a8-db5c0ee471c9)

![Figura 104](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/7789801a-fff2-4e7c-beb1-c50771f7ca9c)

Después de exportada, así queda la imagen:

![Nelson Riley-2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/356bbbbe-00cc-4e85-b326-7d8714b1b1ea)

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

![Imagen1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/30dd7256-54c5-4c4d-a43f-6aeabf90e80b)

En la siguiente tabla se hace la comparación de los valores reportados por cada método. 

| Método  | Parámetro de red (Å) |
|---------|:---------------------|
| Nelson-Riley  | 4.05424 ± 0.00027 |
| Bradley-Jay  | 4.05432 ± 0.00027  |
| Jay  | 4.05416 ± 0.00027   |
| Buerger  | 4.05463 ± 0.00026   |

Teniendo en cuenta que las barras de error se traslapan, puede decirse que los valores son bastante similares.

![Param red funciones extrap tif](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/91ec3ea1-16c8-4a76-b1d7-2689780eff8a)

Si la estructura cristalina no es cúbica, el cálculo de los parámetros de red es un poco diferente. Ese es el caso de la segunda fase del material con el que estamos trabajando. Esta fase es el corindón o alúmina, que exhibe **estructura cristalina hexagonal**. Esta estructura cristalina queda definida con 2 parámetros de red, _a_ y _c_.

<div align="center">

![Imagen7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1249998d-77f4-4900-b87d-0793a9d2cdd5)

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

![Figura 105](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b1f7a94d-073e-4a8f-b146-e281f5fce01f)

Al abrirse la ventana escogemos la función **Pesudo-Voigt** y damos _Ok_.

![Figura 106](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/08b0252f-8da8-45e7-872c-6fca83e9975b)

Al hacer esto se abre una nueva ventana que nos pide que escojamos el centro aproximado de cada pico con doble _click_ (en la flecha se señala cada centro de pico). Al dar doble _click_, cada pico queda seleccionado con una línea roja:

![Figura 107](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/bedd77d0-8ee8-405f-ad82-36624070f052)

Podemos ver que el mencionado pico se ubica a 37.67829°.

![Figura 108](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/ee4d5f72-573c-4589-ba06-f10fc529ddee)

Teniendo en cuenta la baja intensidad de los picos de la fase del corindón, es mejor seleccionar varios picos y hacer el ajuste por multipicos.

![Figura 109](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/11d41cbf-8aa2-4263-90a7-204fc477df0e)

Los dos picos con planos _(hk0)_ son:

|     Plano    | 2Theta |
|---------|:---------------------|
| (110)  | 37.67829 |
| (300)  | 68.10284  |

Haciendo los cálculos con **EXCEL**, encontraremos el valor del parámetro de red a del corindón para dos picos difractados.

![Figura 110](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/14902183-933a-46f8-b9a6-d4fea2255bb3)

De nuevo, podemos usar una función de extrapolación para calcular el valor real del parámetro de red. Usemos la de **Nelson-Riley**.

![Figura 111](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/90236524-fd63-4dcc-b17f-834f56f16b35)

Según esto, el parámetro de red $a = 4.76523 Å$.

![N-R corindón a - 2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/0f66a615-e765-4d51-a90b-2c9afe1b2455)

Ahora, teniendo el valor del parámetro de red _a_, podemos proceder con el cálculo del parámetro de red _c_. Usando los valores de la difracción de los planos _(102)_, _(113)_ y _(116)_ (porque el valor reportado por el pico del plano _(104)_ se sale de la tendencia), el resultado es el siguiente:

![Par red c corindón n-r - 2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1c3e98fd-9613-4694-aa08-6271a021795d)

Por lo tanto, usando el método de la función de extrapolación y las ecuaciones de la ley de Bragg y las que relacionan distancia interplanar con los índices de Miller y los parámetros de red pudimos calcular los parámetros de red de las dos fases que componen el material:

*	Aluminio, de estructura cristalina FCC, con _a_ = 4.05424 ± 0.00027 Å
*	Corindón, de fórmula química $Al_{2}O_{3}$ y estructura cristalina hexagonal compacta, con _a_ = 4.76523 Å y _c_ = 12.97831 ± 0.00645 Å.

## Cálculo de tamaño de cristalito y microdeformaciones

### Ensanchamiento de picos

Si los rayos X incidieran y fuera difractados de forma perfectamente paralela entre ellos, no debería producirse un pico ancho, sino una sola línea de difracción.

<div align="center">

![Imagen2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/e4f5adc8-1280-4c5a-a0e8-94cfe5f667fc)

</div>

Sin embargo, los rayos X que inciden sobre la muestran no llegan paralelos entre ellos, sino ligeramente paralelos. Esto causa el ensanchamiento de la línea.

![Figura 112](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/7b1ffc32-8eff-4249-b778-f23a77128707)

Ese tipo de ensanchamiento se denomina instrumental y debe corregirse. Para determinar el ensanchamiento instrumental se utiliza una muestra de calibración, la cual debe tener un tamaño de cristalito mayor a 100 nm, no poseer microtensiones y, si es posible, tener cristalitos uniformes.

<div align="center">

![Figura 113](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8b379313-209a-4edc-9e2d-3b55ce78d17a)

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

Remplazando los términos del ensanchamiento por tamaño de cristalito y por microdeformaciones en la ecuación del ensanchamiento y reacomodando los términos, tenemos la siguiente ecuación:

<div align="center">

$FWHM cos(θ) = \frac{{0.9λ}}{{D)}} + 2 ε sen(θ)$

</div>

El método de Williamson-Hall consiste, entonces, en calcular el ancho a la altura media de cada pico y su ángulo de difracción y hacer un gráfico de **FWHM×cos⁡θ** _versus_ **2sin⁡θ**. El resultado es una línea recta, cuya pendiente corresponde a la microdeformación y a partir de la pendiente, con la longitud de onda de los rayos X difractado, se puede calcular el tamaño de cristalito.

Vamos a hacer el cálculo para el aluminio de nuestro patrón de difracción de rayos X. Como ya habíamos ajustado los picos según la curva pseudo-voigt, vamos a colocar la información que requerimos en una tabla de EXCEL.
