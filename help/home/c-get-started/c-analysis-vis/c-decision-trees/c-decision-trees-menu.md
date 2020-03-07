---
description: El menú Árbol de decisiones incluye funciones para configurar el caso de uso positivo, filtros, opciones de distribución de hojas, matriz de confusión y otras opciones avanzadas.
title: Opciones del árbol de decisiones
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opciones del árbol de decisiones{#decision-tree-options}

El menú Árbol de decisiones incluye funciones para configurar el caso de uso positivo, filtros, opciones de distribución de hojas, matriz de confusión y otras opciones avanzadas.

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
   <td colname="col2"> Haga clic para ejecutar el algoritmo del árbol de decisiones y mostrar la visualización. Esto aparece atenuado hasta que hay entradas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reset </td> 
   <td colname="col2"> Borra las entradas y el modelo de árbol de decisiones y restablece el proceso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Guardar </td> 
   <td colname="col2"><b>Guarde el árbol</b>de decisiones. Puede guardar el árbol de decisiones en diferentes formatos: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Predictive Markup Language (<b>PMML</b>), un formato de archivo basado en XML que utilizan las aplicaciones para describir e intercambiar modelos de árbol de decisiones. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Texto</b> que muestra columnas simples y filas de verdadero o falso, porcentajes, número de miembros y valores de entrada. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">Una <b>dimensión</b> con ramas que corresponden a los elementos de resultado predichos. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opciones </td> 
   <td colname="col2"> Consulte la tabla siguiente para ver el menú Opciones. </td> 
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
   <td colname="col2"> Define la selección actual del espacio de trabajo como el caso positivo del modelo. Borra el caso si no hay selección. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Definir filtro de población </td> 
   <td colname="col2"> Define la selección actual del espacio de trabajo como el filtro de población del modelo y se extraerá de los visitantes que cumplan esta condición. El valor predeterminado es "Todos". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostrar descripción del filtro complejo </td> 
   <td colname="col2"> Muestra descripciones de los filtros definidos. Haga clic para ver las secuencias de comandos de filtrado para el filtro Caso positivo y Población. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar nodos </td> 
   <td colname="col2"> Oculta nodos con un pequeño porcentaje de la población. Este comando de menú solo se muestra cuando se muestra el árbol de decisiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matriz de conversión </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Opciones</span> &gt; <span class="uicontrol"> Matriz</span> de confusión para ver los valores de precisión, recuperación, precisión y puntuación F. Cuanto más se acerque al 100 por ciento, mejor será la puntuación. </p> <p>La matriz de confusión ofrece cuatro recuentos de precisión del modelo mediante una combinación de valores: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positivo real (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Positivo Predicho (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Negativo real (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Negativo previsto (PN) </li> 
     </ul> </p> <p>Sugerencia:  Estos números se obtienen aplicando el modelo de puntuación resultante de los datos de prueba del 20 por ciento retenidos y ya conocidos como la respuesta verdadera. Si la puntuación es buena al 50 por ciento, se predice como un caso positivo (que coincide con el filtro definido). A continuación, Precisión = (TP + TN)/(TP + FP + TN + FN), Recuperación = TP / (TP + FN) y Precisión = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostrar leyenda </td> 
   <td colname="col2">Permite activar y desactivar una clave de leyenda en el árbol de decisiones. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Este comando de menú solo se muestra cuando se muestra el árbol de decisiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advanced </td> 
   <td colname="col2"> Haga clic para abrir el menú Avanzadas para un uso profundo del Árbol de decisiones. Consulte la tabla siguiente para ver las opciones de menú. </td> 
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
   <td colname="col2"> <p>Controla el tamaño del conjunto de formación utilizado para la creación del modelo. Los conjuntos más grandes tardan más en entrenarse, los más pequeños tardan menos tiempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalización de entrada </td> 
   <td colname="col2"> <p> Permite al usuario especificar si se debe utilizar la técnica Min-Max o la Puntuación Z para normalizar las entradas en el modelo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Factor de sobremuestreo SMOTE </td> 
   <td colname="col2"> Cuando el caso positivo no se produce muy a menudo (menos del 10 por ciento) en la muestra de formación, se utiliza SMOTE para proporcionar ejemplos adicionales. Esta opción permite al usuario indicar cuántos ejemplos más se van a crear con SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Umbral de distribución de la clase de hoja </td> 
   <td colname="col2"> Permite establecer el umbral que se supone para una hoja durante el proceso de creación de árbol. De forma predeterminada, todos los miembros de un nodo deben ser idénticos para que sea una hoja (antes de la etapa de purgado). </td> 
  </tr> 
 </tbody> 
</table>

