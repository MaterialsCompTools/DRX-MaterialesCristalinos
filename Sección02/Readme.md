# Determinación de rasgos cristalográficos
![Origin logo](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/6595d0e0-7d57-46b2-87db-6069f6da86f7)

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

*	Descargar el Software [OriginPro](https://www.originlab.com/demodownload.aspx)

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




