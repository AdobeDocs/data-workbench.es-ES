---
description: Al crear una capa de punto de elemento utilizando puntos dinámicos, los datos de latitud y longitud se incrustan en cada elemento de la dimensión.
title: Definición de capas de puntos de elementos mediante puntos dinámicos
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# Definición de capas de puntos de elementos mediante puntos dinámicos{#defining-element-point-layers-using-dynamic-points}

Al crear una capa de punto de elemento utilizando puntos dinámicos, los datos de latitud y longitud se incrustan en cada elemento de la dimensión.

Para definir una capa de punto de elemento mediante puntos dinámicos, debe crear o tener ya disponible lo siguiente:

* **Una dimensión**, definida en el  [!DNL Transformation.cfg] archivo o un archivo de inclusión de conjunto de datos de transformación, en el que cada elemento contiene la cadena &quot;latitude,longitude&quot; o &quot;latitude,longitude,name&quot;.

   Para ver los pasos para crear una dimensión, consulte la *Guía de configuración del conjunto de datos*.

* **Un** archivo de capa que especifica la dimensión relacionada.

   Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato del archivo de capa de punto de elemento](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Al utilizar [!DNL Dynamic Points], es esencial asegurarse de que la cardinalidad de la dimensión especificada en el archivo de capa sea razonable. Si cada fila de un conjunto de datos tiene una latitud y longitud diferentes, la dimensión se rellena rápidamente y la mayoría de las filas se incluyen en un elemento Elementos pequeños. Dado que el elemento Elementos pequeños no tiene una latitud y longitud, no aparece en el globo.

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
   <td colname="col2"> <p>El nombre de la dimensión (definida en un archivo de configuración de transformación), que debe contener elementos con la cadena "latitude,longitude" o "latitude,longitude,name" como se muestra en los ejemplos siguientes: 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37 5181, 77 1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35 3317, 77 8126,En algún lugar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> Nombre de la métrica que se evalúa sobre la dimensión especificada en el parámetro de Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puntos dinámicos </td> 
   <td colname="col2"> Habilita Puntos Dinámicos. Establezca en true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> Opcional. Valor utilizado para cambiar el tamaño de los puntos de la capa. El valor predeterminado es 100. Los valores más grandes hacen que los puntos sean más grandes y los valores más pequeños los hacen más pequeños. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> Opcional. El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, se puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1,0, 0,0, 0,0) es de color rojo claro y (0,5, 0,5, 0,5) es de color gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modo de procesamiento </td> 
   <td colname="col2"> <p>Opcional. Valor entero que representa el modo de renderización que se utilizará para la capa. Los tres modos disponibles son los siguientes: 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Modo de procesamiento 1. El tamaño de los puntos se define en el espacio de pantalla (los puntos permanecen en un tamaño constante en relación con la pantalla del equipo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. Este es el modo de renderización predeterminado. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Modo de procesamiento 2. El tamaño del punto se define en el espacio del mundo (los puntos permanecen con un tamaño constante en relación con el globo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Modo de procesamiento 3. El tamaño de punto se define en el espacio de pantalla. Los puntos se procesan mediante puntos suaves de OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

El archivo [!DNL IP Coordinates.layer] tiene el formato siguiente:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
