---
description: Evalúe un árbol de decisiones mediante la opción Árbol de regresión con nuevas funciones de muestreo y visualización.
title: Opción de árbol de regresión para el árbol de decisión
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
exl-id: e5f8d525-1530-4169-b246-cdaf30e984c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 3%

---

# Opción de árbol de regresión para el árbol de decisión{#regression-tree-option-for-decision-tree}

{{eol}}

Evalúe un árbol de decisiones mediante la opción Árbol de regresión con nuevas funciones de muestreo y visualización.

Evaluar un árbol de decisiones mediante la opción Árbol de regresión haciendo clic con el botón derecho y seleccionando Opciones > **Árbol de regresión** dentro de una visualización de árbol de decisiones.

**Generador de árboles de decisiones actualizado**: Se introdujo el nuevo algoritmo para crear un [Árbol de decisiones](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html). Gestiona datos más generales y proporciona una visualización más informativa para mejorar la precisión de la predicción.

**Módulo de muestreo de datos mejorado**: Un esquema de muestreo adaptable actualizado ayuda a que el árbol de decisiones y la puntuación de tendencia logren resultados de mayor precisión.

![](assets/CART-RegressionTreeOptions.jpg)

El verde y el rojo indican verdadero o falso. La saturación del color (como el rojo profundo frente al rojo claro) se utiliza para indicar la probabilidad. Por ejemplo, un nodo con rojo profundo tiene una alta probabilidad de ser falso, mientras que un nodo con rojo claro tiene una probabilidad menor de ser falso. Un nodo con verde profundo tiene una alta probabilidad de ser verdadero.

Todos los árboles de decisión tienen anchos de rama variables para indicar el nivel de tráfico de esa rama del árbol.

En una visualización de árbol de decisiones, haga clic con el botón derecho y seleccione Opciones > **Árbol de regresión**. Cuando se selecciona, se proporcionan ajustes adicionales:

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración de regresión </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Utilice Cada Función Solo Una Vez</b> </p> </td> 
   <td colname="col2"> <p>Al seleccionar esta opción, no se utilizará una función más de una vez (como el árbol de decisiones original), por lo que si tiene cinco entradas, el árbol no tendrá más de cinco niveles y la estructura del árbol se parecerá a un árbol de decisiones (pero será un poco más complicada). Esta opción hace que la creación del árbol sea rápida utilizando cada función solo una vez (como un árbol de decisiones original). El uso de esta función es una configuración predeterminada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Configuración del nivel del árbol de regresión </b> </p> </td> 
   <td colname="col2"> <p>Esta opción controla la complejidad del árbol de regresión. Según los datos, es posible que tenga que crear un <i>Fine</i> (con una estructura complicada con más nodos) para obtener una clasificación de árbol más significativa. Si tiene muchos datos, una <i>Normal</i> (menos complicado con menos nodos de árbol) podría funcionar bien. </p> <p> <p>Nota: <i>Típico</i> es la configuración predeterminada. Hay algunos casos extremos en los que la variable <i>Típico</i> no funciona bien y <i>Normal</i> o <i>Fine</i> puede proporcionar una mejor vista de los datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fine</i>: El árbol más complejo con los niveles más granulares de informes y la mayoría de las ramas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Típico</i>: Nivel medio de granularidad y ramas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Normal</i>: El árbol menos complejo con las categorías menos definidas y menos ramas. </p> </td> 
  </tr> 
 </tbody> 
</table>
