---
description: Evalúe un árbol de decisiones mediante la opción Árbol de regresión con nuevas funciones de muestra y visualización.
title: Opción de árbol de regresión para el árbol de decisiones
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Opción de árbol de regresión para el árbol de decisiones{#regression-tree-option-for-decision-tree}

Evalúe un árbol de decisiones mediante la opción Árbol de regresión con nuevas funciones de muestra y visualización.

Evalúe un árbol de decisiones con la opción Árbol de regresión haciendo clic con el botón derecho y seleccionando Opciones > Árbol de **regresión** en una visualización de árbol de decisiones.

**Generador** de árboles de decisiones actualizado: El nuevo algoritmo se introdujo para crear un árbol de [decisiones](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html). Administra datos más generales y proporciona una visualización más informativa para mejorar la precisión de la predicción.

**Se mejoró el módulo** de muestreo de datos: Un esquema de muestreo adaptable actualizado ayuda al árbol de decisiones y a la puntuación de tendencia a obtener resultados de mayor precisión.

![](assets/CART-RegressionTreeOptions.jpg)

El verde y el rojo indican verdadero o falso. La saturación del color (como el rojo profundo o el rojo claro) se utiliza para indicar la probabilidad. Por ejemplo, un nodo con rojo profundo tiene una probabilidad muy alta de ser falso, mientras que un nodo con rojo claro tiene una probabilidad menor de ser falso. Un nodo con verde profundo tiene una probabilidad muy alta de ser verdadero.

Todos los árboles de decisión tienen anchura de ramificación variable para indicar el nivel de tráfico de esa rama del árbol.

En una visualización de árbol de decisiones, haga clic con el botón derecho y seleccione Opciones > Árbol **de regresión**. Cuando se selecciona, se proporcionan opciones de configuración adicionales:

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ajuste de regresión </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Usar cada función una sola vez</b> </p> </td> 
   <td colname="col2"> <p>Al seleccionar esta opción, no se utilizará una función más de una vez (como el árbol de decisiones original), por lo que si tiene cinco entradas, el árbol no tendrá más de cinco niveles y la estructura del árbol tendrá un aspecto similar al árbol de decisiones (pero un poco más complicado). Con esta opción, la creación de árbol será más rápida si se utiliza cada función una sola vez (como un árbol de decisiones original). Usar esta función es una configuración predeterminada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Configuración del nivel del árbol de regresión </b> </p> </td> 
   <td colname="col2"> <p>Esta opción controla la complejidad del árbol de regresión. Según los datos, es posible que necesite crear un árbol <i>fino</i> (con una estructura complicada con más nodos) para obtener una clasificación de árbol más significativa. Si tiene muchos datos, un árbol relativamente <i>grueso</i> (menos complicado con menos nodos de árbol) podría funcionar bien. </p> <p> <p>Nota: <i>Típica</i> es la configuración predeterminada. Hay algunos casos extremos en los que la configuración <i>Típica</i> no funciona bien y la configuración <i>Bruta</i> o <i>fina</i> puede proporcionar una mejor vista de los datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fino</i>: El árbol más complejo con los niveles más granulares de informes y la mayoría de las ramas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Típico</i>: Nivel medio de granularidad y ramas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Grueso</i>: Árbol menos complejo con la menor cantidad de categorías definidas y menos ramas. </p> </td> 
  </tr> 
 </tbody> 
</table>

