# Indexación de picos de patrones de difracción. Herramienta computacional: MATCH!<br>

![Logo Match](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/08725d33-c63f-4419-971c-beb2919c74fd)

## Objetivos<br>

* Conocer para qué sirve el software MATCH!
*	Conocer la extensión de archivos con la que trabaja el _software_
*	Aprender a cargar y preparar el patrón de difracción para el análisis de coincidencia o matching
*	Evaluar la coincidencia con los patrones de las bases de datos del _software_
*	Aprender a guardar el reporte
*	Conocer los archivos de salida del _software_

## Requerimientos

*	Descargar un demo del _Software_: [CrystalImpact](https://www.crystalimpact.com/match/download.htm)

## Qué es MATCH!

Es un _software_ para el análisis de fases cristalinas a partir de datos de difracción de polvo. Trabaja comparando el patrón de difracción de la muestra con una base de datos que contiene patrones de referencia para identificar las fases que están presentes. Una traducción del inglés al español de la palabra match es **coincidir**, así, lo que se busca es comparar el patrón de la muestra y ver con cuál patrón de la base de datos del _software_ coincide. Por lo tanto, usando el _software_ se puede hacer un análisis cualitativo de las fases cristalinas del material.

**Aclaración**: el _software_ ayuda con la identificación de fases cristalinas, no reporta composición química. Así, para usar el _software_ debe conocerse previamente la composición elemental del material.

## Tipos de archivo

El _software_ MATCH! puede abrir archivos de salida de diferentes difractómetros:
*	Bruker/Siemens raw data (*.raw)
*	Bruker/Siemens DIFFRAC AT peak (dif) data (*.dif)
*	DRON-3
*	G670 raw data (*.gdf)
*	GNR raw data (formerly Ital Structures raw data) (*.esg)
*	INEL raw data (*.dat)
*	Jade/MDI/SCINTAG raw data (*.mdi)
*	JEOL ASCII Export raw data (*.txt)
*	PANalytical/Philips raw data (*.rd)
*	PANalytical/Philips raw data (*.udf)
*	PANalytical/Philips peak data (*.udi)
*	Rigaku RAS raw data (*.ras)
*	Rigaku raw data (*.raw)
*	SCINTAG raw data (*.raw, *.rd)
*	Seifert
*	Shimadzu raw data (*.raw)
*	Siemens raw data (*.uxd)
*	Sietronics XRD scan data (*.cpi)
*	Stoe Raw data (*.raw)
*	Stoe Peak File (*.pks)
*	TXRD text export (*.txt)
*	XPowder raw data (*.plv)
*	XRDML Scan raw data (*.xrdml)

En este apartado vamos a trabajar con archivos XRDML. Esta es una extensión de nombre de archivo asociada con un programa para analizar la difracción en cristales, desarrollado por PANalytical.<br>
   ![Logo PANalytical](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/0e26da7f-eeb9-40e1-a9e1-bfc3da9c9a24)

## Interfaz de MATCH!

A continuación, se muestra la interfaz del _software_ al abrirlo. En la parte izquierda, grande, se ubica el panel donde se verá el patrón de difracción después de cargar el archivo. En la parte derecha se observa la tabla periódica, de donde se podrán escoger los elementos químicos que componen el material o la muestra, según su composición elemental. En la parte inferior izquierda aparecerán los patrones con los que se podría hacer match, mientras que en la parte inferior derecha aparecerán los que seleccionemos.

<img width="960" alt="Figura 1" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/dda1bf77-fd8d-4a9a-8645-95711631cc7d">

## Cargue de archivo

Para cargar el archivo _clickeamos_ en <kbd>File</kbd> y posteriormente en <kbd>Open</kbd>.

<img width="960" alt="Figura 3" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/93a216b2-4318-4c23-a2d4-a22cb6192545">

En la ventana que se abre buscamos el archivo, lo seleccionamos, y damos _click_ en <kbd>Abrir</kbd>.

![Figura 2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/df98b56f-65a2-44f6-8cb3-a0337be1a091)

Al hacer esto, se carga el patrón de difracción en el panel superior izquierdo de la pantalla. En azul puede verse el patrón de difracción experimental que cargué y en naranja se ve el _background_, que más adelante se explica qué es.

<img width="960" alt="Figura 4" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/dc33b104-4c15-49de-96f4-a3fd75d65c40">

## Preparación del archivo

Ya cargado el archivo, con la pestaña <kbd>Pattern</kbd> lo preparamos para el análisis de coincidencia o _matching_.
### Primer paso
Podemos revisar y/o cambiar la longitud de onda. Para ello, se hace _click_ en <kbd>Pattern</kbd> y posteriormente en <kbd>Wavelength</kbd>.

![Figura 5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1d78a8cc-6b18-446f-be08-d08807923478)

Al hacer esto, se abre la siguiente ventana. 

<img width="960" alt="Figura 6" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/e520a2ef-a814-4523-9461-54340e0ae2a8">

Al dar click en la pestañita, se despliega la siguiente lista. En este caso, la muestra se analizó con fuente de cobre, por eso sale resaltado en azul la longitud de onda correspondiente con Cu-kα.

<img width="960" alt="Figura 7" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/c74a06ec-9dab-450f-a2f3-9086eacfa548">

### Segundo paso

Vamos a eliminar la intensidad de los picos causada por la difracción kα-2. Primero veamos cómo se ve este, al hacer zum a 2 picos de ángulo de difracción alto (que es donde más se nota):

![Figura 8](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/fd39e98c-c9d6-4601-bb3f-06ce3e7e31b2)

Para eliminarla, hacemos _click_ en <kbd>Pattern</kbd> y en <kbd>Strip K-alpha2</kbd>. Sin embargo, es común que esto no esté habilitado en la versión Demo. 

<img width="960" alt="Figura 9" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/f2da0201-f5ba-4914-ac91-a44537cb6cef">

Al hacer esto, la intensidad en los picos relacionada con esta difracción desaparece, tal como se ve a continuación:

![Figura 10](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/4781adf6-6384-4ca3-b681-1c9fb42492c2)

### Tercer paso

Definimos la señal de fondo o _background_, que se observa como ruido en la señal. Tengamos en cuenta que esta señal de fondo surge por varios factores: el soporte de la muestra, el estado amorfo de la muestra, una mala monocromaticidad o calibración de la luz, o incluso por el tiempo de escaneo por paso. La señal de fondo se define con la línea roja, y es importante hacerlo bien, porque se entiende que lo que está encima de ella son picos difractados. De todos modos, el _software_ lo hace por defecto, como se vio al abrir el archivo, pero puede acomodarse. Para ello, se da _click_ en <kbd>Pattern</kbd>, luego en <kbd>Background</kbd> y luego en <kbd>Edit Background</kbd>.

<img width="960" alt="Figura 11" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/62dc6b34-9b34-4c7d-bb36-6ef9108cacdd">

Manualmente, cogiendo cada punto, de los que se señalan algunos con flechas rojas en el siguiente gráfico, se puede modificar la línea roja de definición del background.

![Figura 12](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/7d6a2a1f-8ec5-4d75-a1ca-c71d55965e08)

### Cuarto paso

Hacer que el _software_ reconozca los picos de nuestro patrón de difracción. Para ello, nos vamos a la pestaña de <kbd>Peaks</kbd>, <kbd>Peak searching</kbd> y _clickeamos_ en <kbd>Peak Search</kbd>.

![Figura 13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1a3b24f7-bd93-48f6-8d69-31bf2ba2195b)

El resultado se muestra a continuación. En la parte de abajo, en el eje _x_ que corresponde a 2 veces el ángulo de difracción, como unas rayitas azules. Con flechas en verde se muestran los picos reconocidos por el _software_, y con flechas en rojo se muestran los picos no reconocidos.

![Figura 14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/2df1226d-21fe-406d-9d4d-d94dc27ba668)

Para hacer que el _software_ reconozca todos los picos, se pueden incrementar la sensibilidad de búsqueda, como se muestra a continuación.

<img width="960" alt="Figura 15" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/19b83908-cf3d-4397-862c-531a6088168c">

Puede verse que con esto aumenta el número de picos reconocidos, aunque faltan aún algunos:

![Figura 16](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/c439b0eb-e2dc-4c23-a4b6-d517c9949793)

Se repite el paso, pero puede verse que ahora se han reconocido como picos puntos de la señal de fondo (porque la definición del _background_ pudo haberse hecho mejor).

![Figura 17](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/97c33fe2-4b0d-4d75-a5ad-cec0ae51a46e)

Esos picos extra señalados se pueden eliminar señalándonos con _click_ derecho, y haciendo _click_ en <kbd>Peaks</kbd> y <kbd>Delete</kbd>.

![Figura 18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/5a906bad-ece8-43b4-8499-785fd8ef7fc2)

![Figura 19](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/b3449333-0e8b-458f-af60-72b4b5377e13)

Ahora el patrón está listo para ser analizado por el _software_ y evaluar la coincidencia con los patrones de sus bases de datos. Se tienen 13 picos.

## Indexación de picos

Para evaluar la coincidencia, damos _click_ en <kbd>Search</kbd> y en <kbd>Search-Match</kbd>.

<img width="960" alt="Figura 21" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/a5280d66-d88f-4562-bb02-def4a84833b1">

Puede ver cómo en la parte inferior-izquierda de la pantalla aparece una lista de fases con las que podría coincidir nuestra muestra.

<img width="960" alt="Figura 22" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/c7dcc56d-361c-4902-ad3b-0a48c97e4a83"><br>

La lista resultante consta de 11 columnas. La primera muestra el <kbd>color</kbd> con el que aparece la fase en la que nos estamos parando en parte de arriba. Fíjese en la cuarta línea, que está en rojo, en la parte superior derecha del cuadro del patrón de difracción. Esa línea hace alusión a la fase en que nos estamos parando. Y las líneas rojas que se observan sobre el patrón son los picos de esa fase de la base de datos. <kbd>Qual</kbd>. Significa Quality, y la <kbd>c</kbd> quiere decir que fue calculada. La columna <kbd>Entry</kbd> tiene que ver con el código que tiene la fase en la base de datos, y que se usa para la referencia respectiva. La columna de <kbd>Formula</kbd> muestra la fórmula estequiométrica de la fase. La columna <kbd>Cryst.</kbd> muestra la familia cristalina de la fase (C, cúbico; H, hexagonal; R, romboédrica; T, tetragonal; O, ortorrómbica; M, monoclínica; T, triclínica). La fase que se está señalando en este caso es de aluminio, que es cúbica. La columna de <kbd>Candidate phase</kbd> muestra el nombre de la fase, que en este caso es aluminio.

La última columna, <kbd>FoM</kbd>, muestra la Figura de Mérito, o _Figure of Merit_, que es un valor numérico que describe la calidad de la coherencia entre el patrón experimental y la respectiva fase de la base de datos. El _software_ calcula el valor teniendo en cuenta las diferencias entre los ángulos 2Theta, entre las intensidades de los picos, entre la cantidad de picos correlacionados con los que deberían ser correlacionados, y el factor de escala de las intensidades. Mientras más alto el valor de la figura de mérito, más coincidencia hay con el patrón experimental. El _software_ muestra las fases candidatas con los valores más altos de FoM en la parte de arriba. Hacia abajo ese valor va disminuyendo.

![Figura 23](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/5b63cd8d-336f-4cc5-9e3f-7401b2326706)

Como la primera fase mostrada es la mejor candidata, damos doble-click. Al hacer esto, la fase pasa a la parte inferior derecha de nuestra pantalla y desaparecen las otras fases candidatas.

![Figura 24](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/af8229bd-a39f-4e54-8810-27ea9d1f72dd)

En <kbd>Data sheet</kbd> puede verse la información de la fase seleccionada. Primero, vemos el número de la fase, para la referencia. En este caso es #96-431-3207. Más abajo podemos ver la clasificación de la fase: su nombre, fórmula estequiométrica, y la razón de intensidad de referencia (I/Ic, que es importante para el análisis cuantitativo). Más abajo puede verse la publicación científica de la que salió ese patrón de difracción y un _link_ por si se desea descargar el archivo (más adelante lo requeriremos). Luego podemos ver la información cristalográfica de la fase: su grupo espacial, sistema cristalino, parámetros de red, número de átomos por celda y las coordenadas donde se ubican los átomos (asumiendo un sistema de 3 ejes y la celda unitaria, la notación muestra en qué puntos se ubican los átomos).<br>

Por último, observamos los picos difractados, con la distancia interatómica, las intensidades relativas (siendo de 1000 la del pico más intenso), los índices de Miller de los picos y la multiplicidad de los planos.<br>

Bajando con la barra se puede ver el patrón con algunas propiedades del material.<br>

![Figura 25](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/381730f8-7258-4950-81ed-2bc1f8883233)

Otra forma de buscar fases, si ya las conocemos, es con CTR+F, o en Search, Find phase/entry.

![Figura 26](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/7311785a-a371-4ddb-958b-eb2d31b1caac)

En el caso de este ejemplo, la otra fase es alúmina o Al2O3, que también se conoce como corindón o corundum, en inglés.

<img width="960" alt="Figura 27" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/28002d6a-06c9-4600-bf15-3b698f036db8">

Así, aparecen los candidatos de esta segunda fase. Las fases candidatas, en este caso, se muestran de color verde. En este caso se seleccionó el segundo archivo de la lista, por la mayor cercanía de 2Theta. Puede verse que todos los picos quedan indexados.

<img width="960" alt="Figura 28" src="https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/6fe89cce-0e04-464e-83dc-734997a8dbd9">

Como puede verse, el MATCH! también puede hacer un análisis cuantitativo del porcentaje de fases dentro del material. En este caso se muestra un 87.7% para el aluminio y un 12.3% para la alúmina. Sin embargo, este valor no es correcto. Para que lo sea, debe hacerse un proceso de refinamiento, que hace que el patrón calculado (rojo) sea igual al experimental (azul).

![Figura 29](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/dd4cb8a2-6c90-4f30-93d7-1ef92cefe106)

En la siguiente figura puede verse que estos aún no coinciden bien. Más adelante aprenderemos cómo hacerlo. Por ahora el análisis es sólo cualitativo.

![Figura 30](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/586e4a96-2b7b-4474-9b64-2bf22297d9b4)

Otra forma de buscar las fases es usando la tabla periódica de la izquierda. Después de cargar el archivo, marcamos en <kbd>Toogle</kbd> hasta que todo rojo (de lo que no se escoge ningún elemento).

![Figura 31](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/e04f5658-05e2-4f81-a6e8-8267682d6cf8)

Luego ubicamos el mouse sobre el elemento que queremos que se tenga en cuenta en la búsqueda, en este caso Al y O, lo dejamos en verde (que se usan para la búsqueda de fases).

![Figura 32](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/aefba7e5-df81-48c2-8df0-f693cc9bf559)

Abriendo la ventana de donde dice <kbd>Formula Sum</kbd>, escogemos la estequiometría deseada:

![Figura 33](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/f6e3863f-1770-402c-ae78-73ab3ec37cdf)

Pueden verse varias opciones. En este caso se escoge Al2O3, que es la fórmula estequiométrica de la alúmina.

![Figura 34](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/8530f157-4de2-4858-9222-6d99a45862d7)

Posteriormente se despliegan las opciones de las fases candidatas para proceder.

## Refinamiento automático

Para ello, clickeamos en el logo de FP (más adelante veremos qué significa).

![Figura 35](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/ef4143f3-c7fe-4449-b708-926c1817147e)

