---
description: El menú Árbol de decisiones incluye funciones para establecer el caso de uso positivo, filtros, opciones de distribución de hojas, matriz de confusión y otras opciones avanzadas.
title: Opciones del árbol de decisión
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---

# Opciones del árbol de decisión{#decision-tree-options}

{{eol}}

El menú Árbol de decisiones incluye funciones para establecer el caso de uso positivo, filtros, opciones de distribución de hojas, matriz de confusión y otras opciones avanzadas.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Botones de la barra de herramientas </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ir </td> 
   <td colname="col2"> Haga clic en para ejecutar el algoritmo del árbol de decisiones y mostrar la visualización. Esto aparece atenuado hasta que hay entradas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Restablecer </td> 
   <td colname="col2"> Borra las entradas y el modelo del árbol de decisiones y restablece el proceso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Guardar </td> 
   <td colname="col2"><b>Guardar el árbol de decisiones</b>. Puede guardar el árbol de decisiones en diferentes formatos: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Lenguaje de marcado predictivo (<b>PMML</b>), un formato de archivo basado en XML que utilizan las aplicaciones para describir e intercambiar modelos de árbol de decisiones. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Texto</b> mostrar columnas simples y filas de true o false, porcentajes, número de miembros y valores de entrada. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> con ramas correspondientes a los elementos de resultado predichos. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opciones </td> 
   <td colname="col2"> Consulte la siguiente tabla para ver el menú Opciones. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menú Opciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Definir caso positivo </td> 
   <td colname="col2"> Define la selección actual del espacio de trabajo como el caso positivo del modelo. Borra el caso si no existe ninguna selección. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Definir filtro de población </td> 
   <td colname="col2"> Define la selección actual del espacio de trabajo como el filtro de población del modelo y se extraerá de los visitantes que cumplan esta condición. El valor predeterminado es "Todos". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostrar descripción del filtro complejo </td> 
   <td colname="col2"> Muestra descripciones de los filtros definidos. Haga clic en para ver las secuencias de comandos de filtrado para el caso positivo y el filtro de población. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar nodos </td> 
   <td colname="col2"> Oculta los nodos con solo un pequeño porcentaje de la población. Este comando de menú solo se muestra cuando se muestra el árbol de decisiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matriz de conversión </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Opciones</span> &gt; <span class="uicontrol"> Matriz de conversión</span> para ver los valores de precisión, recuperación, precisión y puntuación F. Cuanto más cerca del 100 por ciento, mejor será la puntuación. </p> <p>La matriz de confusión ofrece cuatro recuentos de precisión del modelo mediante una combinación de valores: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positivo real (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Predicted Positive (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Negativo real (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Predicted Negative (PN) </li> 
     </ul> </p> <p>Sugerencia: Estos números se obtienen aplicando el modelo de puntuación resultante de los datos de prueba del 20 % retenidos y ya conocidos como la respuesta verdadera. Si la puntuación es buena al 50 por ciento, se predice como un caso positivo (que coincide con el filtro definido). A continuación, Precisión = (TP + TN)/(TP + FP + TN + FN), Recuperación = TP / (TP + FN) y Precisión = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostrar leyenda </td> 
   <td colname="col2">Permite activar y desactivar una clave de leyenda en el árbol de decisiones. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Este comando de menú solo se muestra cuando se muestra el árbol de decisiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avanzadas </td> 
   <td colname="col2"> Haga clic en para abrir el menú Avanzado para un uso detallado del árbol de decisiones. Consulte la siguiente tabla para ver las opciones de menú. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menú avanzado </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tamaño del conjunto de formación </td> 
   <td colname="col2"> <p>Controla el tamaño del conjunto de formación utilizado para la construcción del modelo. Los conjuntos más grandes tardan más en entrenarse, los más pequeños tardan menos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalización de entrada </td> 
   <td colname="col2"> <p> Permite al usuario especificar si se utilizará la técnica Min-Max o la variable estandarizada para normalizar las entradas en el modelo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Factor de sobremuestreo SMOTE </td> 
   <td colname="col2"> Cuando el caso positivo no se produce muy a menudo (menos del 10 por ciento) en la muestra de formación, se utiliza SMOTE para proporcionar muestras adicionales. Esta opción permite al usuario indicar cuántas muestras más crear con SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Umbral de distribución de la clase de hoja </td> 
   <td colname="col2"> Permite definir el umbral que se supone para una hoja durante el proceso de creación del árbol. De forma predeterminada, todos los miembros de un nodo deben ser idénticos para que sea una hoja (antes de la fase de ejecución). </td> 
  </tr> 
 </tbody> 
</table>
