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

## Preparar el archivo

Ya cargado el archivo, con la pestaña <kbd>Pattern</kbd> lo preparamos para el análisis de coincidencia o _matching_.
Primero, podemos revisar y/o cambiar la longitud de onda. Para ello, se hace _click_ en <kbd>Pattern</kbd> y posteriormente en <kbd>Wavelength</kbd>.

![Figura 5](https://github.com/MaterialsCompTools/DRX-MaterialesCristalinos/assets/133029646/1d78a8cc-6b18-446f-be08-d08807923478)

