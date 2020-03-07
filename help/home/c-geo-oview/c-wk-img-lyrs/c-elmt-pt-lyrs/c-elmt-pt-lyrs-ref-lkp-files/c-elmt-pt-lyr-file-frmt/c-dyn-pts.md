---
description: Al crear una capa de punto de elemento mediante puntos dinámicos, los datos de latitud y longitud se incrustan en cada elemento de la dimensión.
solution: Analytics
title: Definición de capas de puntos de elementos mediante puntos dinámicos
topic: Data workbench
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definición de capas de puntos de elementos mediante puntos dinámicos{#defining-element-point-layers-using-dynamic-points}

Al crear una capa de punto de elemento mediante puntos dinámicos, los datos de latitud y longitud se incrustan en cada elemento de la dimensión.

Para definir una capa de punto de elemento mediante puntos dinámicos, debe crear o tener ya disponible lo siguiente:

* **Una dimensión**, definida en el archivo [!DNL Transformation.cfg] o un conjunto de datos de transformación, incluye un archivo en el que cada elemento contiene la cadena &quot;latitud,longitud&quot; o &quot;latitud,longitud,nombre&quot;.

   Para ver los pasos para crear una dimensión, consulte la Guía *de configuración de* Dataset.

* **Un archivo** de capa que especifica la dimensión relacionada.

   Para obtener más información sobre el formato requerido del archivo de capa, consulte Formato [de archivo de capa de punto de](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)elemento.

>[!NOTE]
>
>Cuando se utiliza [!DNL Dynamic Points], es esencial garantizar que la cardinalidad de la dimensión especificada en el archivo de capa sea razonable. Si cada fila de un conjunto de datos tiene una latitud y longitud diferentes, la dimensión se rellena rápidamente y la mayoría de las filas caen en un elemento Elementos pequeños. Dado que el elemento Elementos pequeños no tiene latitud ni longitud, no aparece en el globo.

## Formato de archivo de capa de punto de elemento {#section-bbcc2baa2f754dba81eba93339a97cbd}

Cada archivo de capa de punto de elemento que utilice puntos dinámicos debe tener formato con la siguiente plantilla:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensión </td> 
   <td colname="col2"> <p>El nombre de la dimensión (definida en un archivo de configuración de transformación), que debe contener elementos con la cadena "latitud,longitud" o "latitud,longitud,nombre", como se muestra en los siguientes ejemplos: 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35,3317,-77,8126,En algún lugar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> El nombre de la métrica que se evalúa sobre la dimensión especificada en el parámetro Dimensión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puntos dinámicos </td> 
   <td colname="col2"> Habilita los puntos dinámicos. Establezca en true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> Opcional. Valor utilizado para cambiar el tamaño de los puntos de la capa. El valor predeterminado es 100. Los valores más grandes hacen que los puntos sean más grandes y los valores más pequeños los reducen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> Opcional. El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1.0, 0.0, 0.0) es rojo brillante y (0.5, 0.5, 0.5) es gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modo de representación </td> 
   <td colname="col2"> <p>Opcional. Valor entero que representa el modo de procesamiento que se va a utilizar para la capa. Los tres modos disponibles son los siguientes: 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Modo de procesamiento 1. El tamaño de los puntos se define en el espacio de la pantalla (los puntos mantienen un tamaño constante en relación con la pantalla del equipo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. Este es el modo de procesamiento predeterminado. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Modo de procesamiento 2. El tamaño del punto se define en el espacio del mundo (los puntos mantienen un tamaño constante en relación con el globo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Modo de procesamiento 3. El tamaño del punto se define en el espacio de la pantalla. Los puntos se representan mediante puntos de suavizado OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

El [!DNL IP Coordinates.layer] archivo tiene el formato siguiente:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

