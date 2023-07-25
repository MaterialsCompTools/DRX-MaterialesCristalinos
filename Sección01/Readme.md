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







