<div align="center">

# Indexación de picos de patrones de difracción. Herramienta computacional: MATCH!<br>

</div>

<div align="center">
   
![Logo Match](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20MATCH-5.png)

</div>

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

<div align="center">
   
   ![Logo PANalytical](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/Logo%20panalytical%20PNG.png)

</div>

## Interfaz de MATCH!

A continuación, se muestra la interfaz del _software_ al abrirlo. En la parte izquierda, grande, se ubica el panel donde se verá el patrón de difracción después de cargar el archivo. En la parte derecha se observa la tabla periódica, de donde se podrán escoger los elementos químicos que componen el material o la muestra, según su composición elemental. En la parte inferior izquierda aparecerán los patrones con los que se podría hacer match, mientras que en la parte inferior derecha aparecerán los que seleccionemos.

![Figura 1](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image003.png)

## Cargue de archivo

Para cargar el archivo _clickeamos_ en <kbd>File</kbd> y posteriormente en <kbd>Open</kbd>.

![Figura 2](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image004.png)
En la ventana que se abre buscamos el archivo, lo seleccionamos, y damos _click_ en <kbd>Abrir</kbd>.

![Figura 5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image005.png)

Al hacer esto, se carga el patrón de difracción en el panel superior izquierdo de la pantalla. En azul puede verse el patrón de difracción experimental que cargué y en naranja se ve el _background_, que más adelante se explica qué es.

![Figura 6](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image006.png)

## Preparación del archivo

Ya cargado el archivo, con la pestaña <kbd>Pattern</kbd> lo preparamos para el análisis de coincidencia o _matching_.
### Primer paso
Podemos revisar y/o cambiar la longitud de onda. Para ello, se hace _click_ en <kbd>Pattern</kbd> y posteriormente en <kbd>Wavelength</kbd>.

![Figura 7](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image007.png)

Al hacer esto, se abre la siguiente ventana. 

![Figura 8](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image008.png)

Al dar _click_ en la pestañita, se despliega la siguiente lista. En este caso, la muestra se analizó con fuente de cobre, por eso sale resaltado en azul la longitud de onda correspondiente con **Cu-kα**.

![Figura 9](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image009.png)

### Segundo paso

Vamos a eliminar la intensidad de los picos causada por la difracción **kα-2**. Primero veamos cómo se ve este, al hacer zum a 2 picos de ángulo de difracción alto (que es donde más se nota):

![Figura 10](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image010.png)

Para eliminarla, hacemos _click_ en <kbd>Pattern</kbd> y en <kbd>Strip K-alpha2</kbd>. Sin embargo, es común que esto no esté habilitado en la versión Demo. 

![Figura 11](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image011.png)

Al hacer esto, la intensidad en los picos relacionada con esta difracción desaparece, tal como se ve a continuación:

![Figura 12](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image012.png)

### Tercer paso

Definimos la señal de fondo o _background_, que se observa como ruido en la señal. Tengamos en cuenta que esta señal de fondo surge por varios factores: el soporte de la muestra, el estado amorfo de la muestra, una mala monocromaticidad o calibración de la luz, o incluso por el tiempo de escaneo por paso. La señal de fondo se define con la línea roja, y es importante hacerlo bien, porque se entiende que lo que está encima de ella son picos difractados. De todos modos, el _software_ lo hace por defecto, como se vio al abrir el archivo, pero puede acomodarse. Para ello, se da _click_ en <kbd>Pattern</kbd>, luego en <kbd>Background</kbd> y luego en <kbd>Edit Background</kbd>.

![Figura 13](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image013.png)

Manualmente, cogiendo cada punto, de los que se señalan algunos con flechas rojas en el siguiente gráfico, se puede modificar la línea roja de definición del background.

![Figura 14](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image014.png)

### Cuarto paso

Hacer que el _software_ reconozca los picos de nuestro patrón de difracción. Para ello, nos vamos a la pestaña de <kbd>Peaks</kbd>, <kbd>Peak searching</kbd> y _clickeamos_ en <kbd>Peak Search</kbd>.

![Figura 15](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image015.png)

El resultado se muestra a continuación. En la parte de abajo, en el eje _x_ que corresponde a 2 veces el ángulo de difracción, como unas rayitas azules. Con flechas en verde se muestran los picos reconocidos por el _software_, y con flechas en rojo se muestran los picos no reconocidos.

![Figura 16](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image016.png)

Para hacer que el _software_ reconozca todos los picos, se pueden incrementar la sensibilidad de búsqueda, como se muestra a continuación.

![Figura 17](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image017.png)

Puede verse que con esto aumenta el número de picos reconocidos, aunque faltan aún algunos:

![Figura 18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image018.png)

Se repite el paso, pero puede verse que ahora se han reconocido como picos puntos de la señal de fondo (porque la definición del _background_ pudo haberse hecho mejor).

![Figura 19](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image019.png)

Esos picos extra señalados se pueden eliminar señalándonos con _click_ derecho, y haciendo _click_ en <kbd>Peaks</kbd> y <kbd>Delete</kbd>.

![Figura 20](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image020.png)

![Figura 21](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image021.png)

Ahora el patrón está listo para ser analizado por el _software_ y evaluar la coincidencia con los patrones de sus bases de datos. Se tienen 13 picos.

## Indexación de picos

Para evaluar la coincidencia, damos _click_ en <kbd>Search</kbd> y en <kbd>Search-Match</kbd>.

![Figura 22](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image022.png)

Puede ver cómo en la parte inferior-izquierda de la pantalla aparece una lista de fases con las que podría coincidir nuestra muestra.

![Figura 23](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image023.png)

La lista resultante consta de 11 columnas. La primera muestra el <kbd>color</kbd> con el que aparece la fase en la que nos estamos parando en parte de arriba. Fíjese en la cuarta línea, que está en rojo, en la parte superior derecha del cuadro del patrón de difracción. Esa línea hace alusión a la fase en que nos estamos parando. Y las líneas rojas que se observan sobre el patrón son los picos de esa fase de la base de datos. <kbd>Qual</kbd>. Significa Quality, y la <kbd>c</kbd> quiere decir que fue calculada. La columna <kbd>Entry</kbd> tiene que ver con el código que tiene la fase en la base de datos, y que se usa para la referencia respectiva. La columna de <kbd>Formula</kbd> muestra la fórmula estequiométrica de la fase. La columna <kbd>Cryst.</kbd> muestra la familia cristalina de la fase (C, cúbico; H, hexagonal; R, romboédrica; T, tetragonal; O, ortorrómbica; M, monoclínica; T, triclínica). La fase que se está señalando en este caso es de aluminio, que es cúbica. La columna de <kbd>Candidate phase</kbd> muestra el nombre de la fase, que en este caso es aluminio.

La última columna, <kbd>FoM</kbd>, muestra la Figura de Mérito, o _Figure of Merit_, que es un valor numérico que describe la calidad de la coherencia entre el patrón experimental y la respectiva fase de la base de datos. El _software_ calcula el valor teniendo en cuenta las diferencias entre los ángulos 2Theta, entre las intensidades de los picos, entre la cantidad de picos correlacionados con los que deberían ser correlacionados, y el factor de escala de las intensidades. Mientras más alto el valor de la figura de mérito, más coincidencia hay con el patrón experimental. El _software_ muestra las fases candidatas con los valores más altos de FoM en la parte de arriba. Hacia abajo ese valor va disminuyendo.

![Figura 24](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image024.png)

Como la primera fase mostrada es la mejor candidata, damos doble-click. Al hacer esto, la fase pasa a la parte inferior derecha de nuestra pantalla y desaparecen las otras fases candidatas.

![Figura 25](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image025.png)

En <kbd>Data sheet</kbd> puede verse la información de la fase seleccionada. Primero, vemos el número de la fase, para la referencia. En este caso es #96-431-3207. Más abajo podemos ver la clasificación de la fase: su nombre, fórmula estequiométrica, y la razón de intensidad de referencia (I/Ic, que es importante para el análisis cuantitativo). Más abajo puede verse la publicación científica de la que salió ese patrón de difracción y un _link_ por si se desea descargar el archivo (más adelante lo requeriremos). Luego podemos ver la información cristalográfica de la fase: su grupo espacial, sistema cristalino, parámetros de red, número de átomos por celda y las coordenadas donde se ubican los átomos (asumiendo un sistema de 3 ejes y la celda unitaria, la notación muestra en qué puntos se ubican los átomos).<br>

Por último, observamos los picos difractados, con la distancia interatómica, las intensidades relativas (siendo de 1000 la del pico más intenso), los índices de Miller de los picos y la multiplicidad de los planos.<br>

Bajando con la barra se puede ver el patrón con algunas propiedades del material.<br>

![Figura 26](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image026.png)

Otra forma de buscar fases, si ya las conocemos, es con CTR+F, o en <kbd>Search</kbd>, <kbd>Find phase/entry</kbd>.

![Figura 27](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image027.png)

En el caso de este ejemplo, la otra fase es alúmina o Al2O3, que también se conoce como corindón o corundum, en inglés.

![Figura 28](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image028.png)

Así, aparecen los candidatos de esta segunda fase. Las fases candidatas, en este caso, se muestran de color verde. En este caso se seleccionó el segundo archivo de la lista, por la mayor cercanía de 2Theta. Puede verse que todos los picos quedan indexados.

![Figura 29](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image029.png)

Como puede verse, el MATCH! también puede hacer un análisis cuantitativo del porcentaje de fases dentro del material. En este caso se muestra un 87.7% para el aluminio y un 12.3% para la alúmina. Sin embargo, este valor no es correcto. Para que lo sea, debe hacerse un proceso de refinamiento, que hace que el patrón calculado (rojo) sea igual al experimental (azul).

![Figura 300](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image0300.png)

En la siguiente figura puede verse que estos aún no coinciden bien. Más adelante aprenderemos cómo hacerlo. Por ahora el análisis es sólo cualitativo.

![Figura 30](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image030.png)

Otra forma de buscar las fases es usando la tabla periódica de la izquierda. Después de cargar el archivo, marcamos en <kbd>Toogle</kbd> hasta que todo rojo (de lo que no se escoge ningún elemento).

![Figura 31](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image031.png)

Luego ubicamos el mouse sobre el elemento que queremos que se tenga en cuenta en la búsqueda, en este caso Al y O, lo dejamos en verde (que se usan para la búsqueda de fases).

![Figura 32](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image032.png)

Abriendo la ventana de donde dice <kbd>Formula Sum</kbd>, escogemos la estequiometría deseada:

![Figura 33](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image033.png)

Pueden verse varias opciones. En este caso se escoge Al2O3, que es la fórmula estequiométrica de la alúmina.

![Figura 34](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image034.png)

Posteriormente se despliegan las opciones de las fases candidatas para proceder.

## Refinamiento automático

Para ello, clickeamos en el logo de FP (más adelante veremos qué significa).<br>

![Figura 35](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image035.png)

Señalamos Automatic Rietveld Refinement (parte superior derecha) y damos _click_ en el botón <kbd>Run FullProf</kbd> (Rietveld Refinement). 

![Figura 36](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image036.png)

Al hacer esto, la coincidencia entre el patrón calculado y el experimental debería ser mejor. Dos valores importantes son el Factor de Bragg y el Chi-2 que, como puede verse, han cambiado. Aunque lo entenderemos mejor después, por ahora diremos que el valor del Chi-2 está bien, pero el del factor de Bragg es muy alto. Además, la línea azul claro en la parte inferior presenta aún mucho ruido. Lo que quiere decir que el refinamiento automático no es suficiente.<br>
Sin embargo, los valores de porcentajes de fases, que han cambiado después del refinamiento, son más confiables que los mostrados anteriormente.<br>

![Figura 37](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image037.png)

## Resultados

Al dar _click_ en el ícono señalado, se despliega un reporte de lo hecho.

![Figura 38](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image038.png)

El reporte luce como se muestra a continuación. Muestra el nombre de la muestra, la ruta para encontrar el archivo y las condiciones de medida, las fases coincidentes y cómo las indexa –la fase A es el aluminio y la fase B es el corindón-, la composición elemental y las características de las fases seleccionadas de las bases de datos. Recordar que los porcentajes de fases o de elementos químicos, hasta este punto, no es correcta debido a que no se ha hecho un refinamiento.<br>

![Figura 39](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image039.png)

Además de esto, el informe muestra otras fases candidatas, con su número de archivo y su Figura de Mérito. <br>

![Figura 40](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image040.png)

Además de otra información, el reporte muestra la lista de picos y cómo quedaron indexados.<br>

![Figura 41](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image041.png)

Por último, el reporte puede guardarse como un archivo PDF.<br>
Si queremos ver los índices de Miller de cada plano difractado, podemos hacerlo dando _click_ derecho sobre la pantalla del patrón de difracción. Así, se despliegan varias opciones. Damos _click_ en <kbd>Miller Indices</kbd>.

![Figura 42](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image042.png)

Los índices de Miller aparecerán sobre cada pico:<br>

![Figura 43](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image043.png)

## Exportar archivos

Por último, vamos a exportar un archivo con extensión .dat para abrir en el OriginPro, que nos ayuda a procesar los datos de forma elegante. Damos _click_ en <kbd>File</kbd>, <kbd>Export</kbd>, <kbd>Profile Data</kbd>.<br>

![Figura 44](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image044.png)

![Figura 45](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image045.png)

Escogemos la opción de 2 columnas: 2Theta Intensity.

![Figura 46](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image046.png)

El archivo resultante queda de dos columnas. La de la izquierda corresponde al ángulo 2Theta y la de la derecha a la intensidad.

![Figura 47](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/blob/main/.graph/image047.png)

##

<div align="center">

![image](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/a62bde9b-b559-41e5-8c87-07ec98a4f24a)

[Formulario de admisión](https://enlace-academico.escuelaing.edu.co/psc/FORMULARIO/EMPLOYEE/SA/c/EC_LOCALIZACION_RE.LC_FRM_ADMEDCO_FL.GBL)

</div>

##

![Imagen18](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/2f8eec20-a779-4e30-9981-dea14550742a)
