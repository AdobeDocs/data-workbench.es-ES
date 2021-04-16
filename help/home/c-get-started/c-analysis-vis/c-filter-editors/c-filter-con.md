---
description: Información sobre cómo trabajar con condiciones de filtro, incluida la creación de un nuevo filtro y la adición de una condición a un nuevo filtro.
title: Trabajo con condiciones de filtro
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# Trabajo con condiciones de filtro{#working-with-filter-conditions}

Información sobre cómo trabajar con condiciones de filtro, incluida la creación de un nuevo filtro y la adición de una condición a un nuevo filtro.

## Crear un filtro {#section-70ba51ae625e493fa3ca70b93ffba406}

* Abra un editor de filtros en el espacio de trabajo haciendo clic con el botón derecho en **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**.

   -O bien-

* Si ya tiene un editor de filtros abierto y un filtro cargado, haga clic con el botón derecho en el nombre del filtro actual y haga clic en **[!UICONTROL New Blank Filter]**.

## Añadir una condición a un nuevo filtro {#section-50986db80f1148c489630a8a63fe9f28}

1. Cree un nuevo filtro. Asegúrese de que el filtro de diseño esté resaltado (en lugar de Aplicar filtro), lo que indica que está trabajando en el modo Filtro de diseño.
1. Haga clic con el botón derecho en el área marcada **[!UICONTROL Right-click to build filter]** y seleccione una de las siguientes opciones:

   * Para crear un filtro de inclusión, haga clic en **[!UICONTROL Include group with]**.
   * Para crear un filtro de exclusión, haga clic en **[!UICONTROL Exclude group with]**.

1. Seleccione el tipo de condición que desea añadir al filtro.

   La siguiente tabla proporciona descripciones de los tipos de condiciones de filtro disponibles:

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de condición </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>selección de espacio de trabajo </p> </td> 
   <td colname="col2"> <p>Define una condición de filtro basada en las selecciones del espacio de trabajo. Esta opción solo está disponible si hay una o más selecciones dentro del espacio de trabajo. </p> <p>Para obtener más información sobre la selección, haga clic con el botón derecho en la condición y haga clic en <span class="uicontrol"> Ver detalles</span>. Aparece una llamada para la condición. </p> <p>Si realiza otra selección en el espacio de trabajo, puede añadir la selección como una subcondición de la primera selección. Las selecciones se agrupan como Y lógicas. Por lo tanto, los datos que la condición incluye o excluye deben satisfacer todas las selecciones de espacio de trabajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>al menos una </p> </td> 
   <td colname="col2">Define una condición de filtro basada en la existencia de al menos un elemento (cualquiera) de una dimensión que elija. Para editar la condición, haga clic con el botón derecho en la condición y haga clic en <span class="uicontrol"> Cambiar</span> condición a. Haga clic en una de las dimensiones disponibles. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fórmula </p> </td> 
   <td colname="col2"> <p>Define una condición de filtro basada en la fórmula que haya introducido. Debe utilizar la sintaxis adecuada para que funcione el filtro. </p> <p> <p>Nota: Para obtener información sobre la sintaxis para definir filtros, consulte <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintaxis para expresiones de filtro</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>valor de métrica </p> </td> 
   <td colname="col2"> <p>Define una condición de filtro basada en un valor de métrica que especifique. </p> <p>Para definir la condición, siga estos pasos: 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Haga clic con el botón derecho <span class="uicontrol"> [elija nivel]</span> &gt; <span class="uicontrol"> Cambiar nivel</span> para seleccionar el nivel y la métrica de una lista de dimensiones en el conjunto de datos. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Haga clic con el botón derecho <span class="uicontrol"> [elija la métrica]</span> &gt; <span class="uicontrol"> Cambiar métrica</span> para seleccionar la métrica de una lista de métricas de su conjunto de datos. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Haga clic con el botón derecho en menos que y haga clic en <span class="uicontrol"> Cambiar comparación</span> para seleccionar una de las condiciones de comparación disponibles (menor que, mayor que, exactamente, al menos o como máximo). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Escriba el valor que desee para la métrica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>primer/último </p> </td> 
   <td colname="col2"> <p>Define un filtro que permite incluir o excluir un nivel con una dimensión específica. Por ejemplo, puede especificar un primer/último filtro para incluir (o excluir): </p> <p>Sesiones cuya última Vista de página tiene una Página de <span class="filepath"> /hme/rts/Our Rates</span>. </p> <p>Para definir una primera/última condición: 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Elija <span class="uicontrol"> Incluir grupo con</span> o <span class="uicontrol"> Excluir grupo con</span> &gt; <span class="uicontrol"> primero/último</span> como una nueva condición en el Editor de filtros. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Haga clic con el botón derecho en <span class="uicontrol"> [elija contenedor]</span> &gt; <span class="uicontrol"> Cambiar contenedor</span> para seleccionar el contenedor. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Haga clic con el botón derecho en <span class="uicontrol"> first</span> o <span class="uicontrol"> last</span> para especificar el nivel. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Haga clic con el botón derecho para especificar una dimensión y, a continuación, escriba un valor en el campo disponible. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Haga clic en <span class="uicontrol">Aplicar</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

El filtro de este ejemplo define un primer/último filtro para los usuarios cuya última vista de página fue [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. (Opcional) Para agregar más condiciones al filtro, haga clic con el botón derecho en el área de la ventana donde está creando el filtro y seleccione el tipo de filtro (consulte el Paso 2) y la regla de condición (consulte el Paso 3).

   >[!NOTE]
   >
   >Las condiciones de inclusión múltiple se agrupan como OR lógicos. Por lo tanto, los datos incluidos por el filtro deben satisfacer al menos una de las condiciones de inclusión definidas. Las condiciones de exclusión múltiple también se agrupan como OR lógicos. Para poder excluirse, los datos deben cumplir al menos una de las condiciones de exclusión.

El filtro de este ejemplo define un subconjunto de datos formado por espectadores de películas (usuarios) que clasificaron muchas películas pero no dieron a ninguna película una puntuación alta (4 o 5). Este filtro (correctamente denominado Muy difícil de Por favor) consiste en dos condiciones:

* **Una condición de valor de métrica:**  la condición incluye a los usuarios que han clasificado al menos 500 películas.
* **Una condición de selección de espacio de trabajo:** la condición excluye a los usuarios que hayan concedido a una película una puntuación de 4 o 5. La llamada le indica que 4 y 5 eran los elementos seleccionados de la dimensión Puntuación .

![](assets/vis_FilterEditor_ExampleMovies.png)

## Eliminar una condición de filtro {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>Las condiciones solo se pueden eliminar cuando se trabaja en el modo Filtro de diseño. Si ha aplicado un filtro al espacio de trabajo, debe hacer clic en Filtro de diseño para volver al modo Filtro de diseño antes de poder eliminar una o más condiciones del filtro.

* Haga clic en **x** a la izquierda de la condición para eliminarla.

## Editar una descripción de condición {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

Puede agregar descripciones a cada una de las condiciones que agregue a un filtro. Puede editar o eliminar las descripciones como desee.

>[!NOTE]
>
>Las descripciones de las condiciones solo aparecen cuando se trabaja en el modo Filtro de diseño.

* Haga clic con el botón derecho en la condición y haga clic en **[!UICONTROL Edit description]**.

   * Para añadir o editar una descripción, escriba la descripción en el campo [!DNL Edit condition description]. La descripción aparece entre comillas sobre la condición en la ventana del editor de filtros.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* Para quitar una descripción, haga clic en **[!UICONTROL Remove description]**. La condición permanece en la ventana del editor de filtros.
