---
description: El texto o las expresiones se pueden introducir en cualquier celda de una hoja de cálculo.
title: Trabajo con datos en hojas de cálculo
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
exl-id: 40d9211b-8f5c-4051-8f93-638ffacf45bd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---

# Trabajo con datos en hojas de cálculo{#work-with-data-in-worksheets}

El texto o las expresiones se pueden introducir en cualquier celda de una hoja de cálculo.

Todas las expresiones de una hoja de cálculo van precedidas de un signo igual (=) a menos que se utilice [!DNL eval( )], que trata el texto de la celda a la que se hace referencia como una expresión.

Para obtener una lista completa de las reglas de sintaxis de métricas, dimensiones y filtros, consulte [Sintaxis del idioma de consulta](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

**Escribir datos en una hoja de cálculo**

1. Haga clic dos veces en una celda de la hoja de cálculo para entrar al modo de edición. La celda seleccionada se resalta.
1. Escriba o pegue los datos deseados en la celda.

**Copiar y pegar de una celda a otra**

1. Haga clic con el botón derecho en la celda que contiene los datos que desea copiar y haga clic en **[!UICONTROL Copy]**.
1. Haga clic con el botón derecho en la celda en la que desee pegar los datos copiados y haga clic en **[!UICONTROL Paste]**.

La Data Workbench actualiza automáticamente las referencias en la nueva celda para hacer referencia a las columnas y filas correspondientes.

**Copia y pegado de un grupo de celdas a otro**

1. Seleccione las celdas que contienen los datos que desea copiar.
1. Haga clic con el botón derecho en las celdas que contengan los datos que desee copiar y haga clic en **[!UICONTROL Copy]**.
1. Haga clic con el botón derecho en la primera celda en la que desee comenzar a pegar los datos copiados y haga clic en **[!UICONTROL Paste]**. Los datos se pegan en la primera celda y debajo de ella.

La Data Workbench actualiza automáticamente las referencias en la nueva celda para hacer referencia a las columnas y filas correspondientes.

**Inserción de una columna**

* Haga clic con el botón derecho en una columna y haga clic en **[!UICONTROL Insert Column]**. La nueva columna se inserta a la izquierda de la columna seleccionada.

**Eliminación de una columna**

* Haga clic con el botón derecho en la columna que desee eliminar y haga clic en **[!UICONTROL Delete Column]**. Se elimina la columna .

**Insertar una fila**

* Haga clic con el botón derecho en una fila y haga clic en **[!UICONTROL Insert Row]**. La nueva fila se inserta encima de la fila seleccionada.

**Eliminar una fila**

* Haga clic con el botón derecho en la fila que desee eliminar y haga clic en **[!UICONTROL Delete Row]**. Se quita la fila.

**Cambiar el tamaño de una columna**

1. En la fila del encabezado de la columna, coloque el cursor sobre la línea divisoria a la derecha de la columna cuyo tamaño desee cambiar.
1. Haga clic y arrastre hacia la derecha para aumentar el ancho de la columna o hacia la izquierda para reducir el ancho de la columna.

**Formato de una celda**

1. Haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Haga clic en el formato deseado en el menú de opciones disponibles:

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción del menú </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Número </p> </td> 
   <td colname="col2"> <p>Aplica el formato numérico seleccionado a los datos, como la hora, la fecha, el porcentaje o el decimal. </p> <p>Haga clic en <span class="uicontrol"> Predeterminado</span> para quitar el formato seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Justificar </p> </td> 
   <td colname="col2"> <p>Justifica los datos de la celda a la izquierda, al centro o a la derecha. Se deja la justificación predeterminada. </p> <p>Haga clic en <span class="uicontrol"> Predeterminado</span> para quitar el formato seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Color </p> </td> 
   <td colname="col2"> <p>Aplica el color de fuente seleccionado a los datos de la celda. El color de fuente predeterminado es blanco. </p> <p>Haga clic en <span class="uicontrol"> Predeterminado</span> para quitar el formato seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indicador </p> </td> 
   <td colname="col2"> <p>Crea un indicador de métrica utilizando esta celda. Para obtener más información, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Creación de indicadores de métricas</a>. </p> <p>Haga clic en <span class="uicontrol"> Predeterminado</span> para quitar el formato seleccionado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Celda de entrada </p> </td> 
   <td colname="col2"> <p>Convierte la celda seleccionada en una celda de entrada. Para obtener más información, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Creación de celdas de entrada</a>. </p> <p>Haga clic en <span class="uicontrol"> Predeterminado</span> para quitar el formato seleccionado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métodos abreviados de teclado {#section-05301f4d2c60418e86902635a7aeee20}

En las hojas de cálculo puede utilizar muchos de los métodos abreviados de teclado de edición básicos que puede utilizar en cualquier editor de texto, como el Bloc de notas o Microsoft Word.

En la tabla siguiente se enumeran los métodos abreviados de teclado básicos que se pueden usar al introducir datos en una hoja de cálculo.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Acceso directo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Teclas de flecha </p> </td> 
   <td colname="col2"> <p>Se mueve de celda en celda de la hoja de cálculo utilizando las teclas de flecha arriba, abajo, izquierda y derecha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Edite la celda colocando el cursor en la celda seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entrar </p> </td> 
   <td colname="col2"> <p>Completa la edición de la celda seleccionada. El cursor se elimina de la celda y el contenido de la celda refleja la edición. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>Cancelar la edición de la celda seleccionada. El cursor se elimina de la celda y el contenido de la celda vuelve a ser el que era antes de comenzar la edición. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eliminar </p> </td> 
   <td colname="col2"> <p>Elimine el contenido de las celdas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Seleccione el contenido de la celda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl + c </p> </td> 
   <td colname="col2"> <p>Copie el contenido de las celdas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl + x </p> <p>Mayús + Supr </p> </td> 
   <td colname="col2"> <p>Copie y elimine el contenido de las celdas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl + v </p> <p>Mayús + Insertar </p> </td> 
   <td colname="col2"> <p>Pegue el contenido de las celdas que ha copiado en las celdas seleccionadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl + z </p> </td> 
   <td colname="col2"> <p>Deshace escribir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl + Mayús + z </p> </td> 
   <td colname="col2"> <p>Rehaga la escritura. </p> </td> 
  </tr> 
 </tbody> 
</table>
