---
description: Los árboles de decisiones son una visualización de análisis predictivo que se utiliza para evaluar las características y relaciones del visitante. El Generador de árboles de decisiones genera una visualización de árboles de decisiones en función de un caso positivo especificado y un grupo de entradas.
solution: Analytics
title: Árbol de decisiones Generador
topic: Data workbench
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generador de árboles de decisiones{#decision-tree-builder}

Los árboles de decisiones son una visualización de análisis predictivo que se utiliza para evaluar las características y relaciones del visitante. El Generador de árboles de decisiones genera una visualización de árboles de decisiones en función de un caso positivo especificado y un grupo de entradas.

Un Árbol de decisiones es un clasificador binario con un grupo de reglas (o filtros) que identifica a visitantes que satisfacen reglas específicas en función de un caso positivo. Un árbol de decisiones establece reglas para clasificar a visitantes que satisfacen (o no) este caso positivo. Estas reglas generan un mapa de árboles para proporcionar un nivel de confianza y cumplir estos resultados de caso positivo.

El árbol de decisiones se crea examinando las entradas de cada nivel y eligiendo la que proporciona una ganancia máxima de información en un punto de división específico. La división de puntos para cada nivel de variable genera dos conjuntos:

* Valores inferiores o iguales al punto de división, y
* Valores buenos que no son los puntos divididos.

Use árboles de decisión para

* Realizar análisis e interpretación significativos en menos tiempo.
* Emplee la generación automatizada de segmentos.
* Haga inferencias rápidamente de un modelo en base a una gran cantidad de datos.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Barra de herramientas y menús</b> </p> <p>La barra de herramientas incluye botones y comandos de menú para el árbol de decisiones, incluidas funciones para definir el caso positivo y agregar listas de entrada. </p> <p>Al igual que otras visualizaciones, el cuadro <span class="uicontrol"> Elemento</span> permite arrastrar y soltar dimensiones y elementos, aunque también puede arrastrar directamente desde el panel Buscadores. </p> <p>Para obtener más información, consulte <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Opciones</a>del árbol de decisiones. </p> </td> 
   <td colname="col2"> <p><b>Lista de entrada</b> </p> <p>Esta área muestra las entradas en el modelo de árbol. Tienen un código de color para coincidir con los nodos del área Visualización de árbol. </p> <p>Al hacer clic con el botón derecho en una entrada, puede quitar la entrada del modelo y restablecer. </p> <p>Si pasa el ratón por encima de un nodo de árbol, se mostrarán las condiciones de división a lo largo de la rama de dicho nodo y la predicción en ese nodo con su valor de confianza. </p> </td> 
   <td colname="col3"> <p><b>Visualización de árbol</b> </p> <p>Esta área muestra el modelo de árbol con nodos de hoja con un código de color basado en su predicción: verde para una predicción True del caso positivo y rojo para una predicción False. </p> <p>Los nodos divididos tienen un código de color para las entradas que coinciden con su condición de selección. Al pasar el ratón sobre un nodo se muestra información sobre la división y se expande la lista de entradas para mostrar los puntos divididos a lo largo de la rama y la distribución del conjunto de formación. </p> <p>Los nodos por debajo de un umbral no se muestran de forma predeterminada. Haga clic en un nodo ampliable (indicado por un símbolo +) para explorar una rama. Haga clic en el nodo raíz para volver a la pantalla de árbol completa. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->

