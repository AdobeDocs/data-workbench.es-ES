---
description: Utilice los paneles del Buscador en Data Workbench para seleccionar métricas, dimensiones y filtros. Estos paneles proporcionan compatibilidad con la búsqueda, opciones de clasificación y capacidades de arrastrar y soltar.
title: Buscadores
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---


# Buscadores{#finders}

Utilice los paneles del Buscador en Data Workbench para seleccionar métricas, dimensiones y filtros. Estos paneles proporcionan compatibilidad con la búsqueda, opciones de clasificación y capacidades de arrastrar y soltar.

Un panel Buscador se puede abrir en la barra lateral izquierda o dentro de un espacio de trabajo.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Buscador de Dimension </th> 
   <th colname="col2" class="entry"> Buscador de métricas </th> 
   <th colname="col3" class="entry"> Buscador de filtros </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Una lista de todas las dimensiones del modelo de consulta. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>Una lista de todas las métricas del modelo de consulta. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>Una lista de todos los filtros creados para su organización. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**Para abrir un Buscador:**

* Haga clic con el botón derecho en un espacio de trabajo y seleccione **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

   El panel Buscador con pestañas para Métricas, Dimension y Filtros se abrirá en el espacio de trabajo.

* Haga clic con el botón derecho en la barra lateral izquierda y seleccione **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

   El panel Buscador se abrirá en el panel izquierdo.

El **Finder** incluye las siguientes funciones:

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funciones del Buscador </th> 
   <th colname="col2" class="entry"> Detalles </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Arrastrar y soltar</b> </td> 
   <td colname="col2"> <p> Puede arrastrar y soltar dimensiones o métricas del panel en una visualización del espacio de trabajo para cambiar la dimensión o agregar nuevas métricas. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Mantenga pulsadas las teclas <span class="uicontrol"> &lt;Ctrl&gt;</span> y <span class="uicontrol"> &lt;Alt&gt;</span> y seleccione la dimensión o métrica en el panel Buscador. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Arrastre una nueva dimensión desde el panel y suéltela en la visualización para cambiar o añadir dimensiones. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Para agregar métricas, arrastre una nueva métrica del panel y suéltela en el encabezado de métrica de la visualización seleccionada. </li> 
    </ol> <p>Esto funcionará para todas las visualizaciones relevantes, incluidas las tablas, el clúster de visitantes, la matriz de correlación, los gráficos de puntos y el gráfico de barras 2D (en función del eje). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Buscar</b> </td> 
   <td colname="col2">Un cuadro <span class="uicontrol"> Buscar</span> en los paneles Buscador le permite filtrar nombres para Dimension, Métricas y Filtros. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Coincidencia de patrones (búsqueda global simple). Empiece a escribir el nombre de una dimensión, métrica o entidad de filtro necesaria en el campo Buscar y solo las cadenas coincidentes contenidas en cualquier parte del nombre se filtrarán y mostrarán en el panel Buscadores . </p> <p>Por ejemplo, introduzca: </p> <code><b>Search:</b>click</code> <p>Puede obtener los siguientes resultados en el Buscador de Dimension: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>La coincidencia de patrones estándar permite utilizar caracteres comodín, como . (punto), "?" y "*" (estrella). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Expresiones regulares. También se admiten expresiones regulares más complejas para la capacidad de búsqueda añadida. Añada el prefijo "re:" antes del término de búsqueda (sin espacios) para interpretarlo como expresión regular. </p> <p>Por ejemplo, introduzca: </p> <code><b>Search:</b>re.*ip</code> <p>Puede obtener los siguientes resultados en el Buscador de Dimension: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Para obtener información detallada sobre la búsqueda, consulte <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> expresiones regulares</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Tipo de Dimension</b> </td> 
   <td colname="col2">En la pestaña Dimension , puede hacer clic con el botón derecho en el encabezado de la pestaña para ordenar por tipo de dimensión. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Atributos: Dimension creados en función de características del visitante, productos, ubicación geográfica, tiempo, vídeo y otros atributos. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Clústeres: Dimension creados dentro del generador de clústeres. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Puntuaciones: Dimension creados dentro de la puntuación de tendencia. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Etiqueta</b> </td> 
   <td colname="col2">En cada ficha, puede hacer clic con el botón derecho y seleccionar <span class="uicontrol"> Etiqueta</span> para cambiar el nombre del panel del Buscador. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Las etiquetas predeterminadas Dimension, Métricas y Filtros se pueden cambiar por un nombre de ficha que cumpla las convenciones de su organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Agregar elemento</b> </td> 
   <td colname="col2">En cada ficha, puede hacer clic con el botón derecho y seleccionar <span class="uicontrol"> Agregar elemento</span> para abrir una tabla y agregar manualmente Dimension, métricas y filtros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Barra de buscadores</b> </td> 
   <td colname="col2">Haga clic con el botón derecho en la barra <span class="uicontrol"> Buscadores</span> de la barra lateral izquierda para abrir un menú para funciones adicionales. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Cierre</b> </td> 
   <td colname="col2">Haga clic con el botón derecho en la barra <span class="uicontrol"> Buscadores</span> y seleccione <span class="uicontrol"> Cerrar</span> para cerrar un panel Buscadores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Guardar</b> </td> 
   <td colname="col2">Guarde la lista localmente haciendo clic con el botón derecho en la barra de encabezado y seleccionando la opción <span class="uicontrol"> Guardar</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Exportar</b> </td> 
   <td colname="col2">Puede exportar una lista de dimensiones, métricas o filtros seleccionados desde el panel Buscador haciendo clic con el botón derecho en la barra Buscadores y seleccionando <span class="uicontrol"> Exportar</span> en el menú. <p> Agregue un nombre y exporte a Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copy</b> </td> 
   <td colname="col2"> Copiar una lista de Dimension, métricas o filtros. Puede copiar como archivo o como gráfico en Fondo oscuro, Fondo claro o Monocromo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Minimizar</b> </td> 
   <td colname="col2"> Minimice el panel Buscador. Solo aparecerá la barra de buscadores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Sin borde</b> </td> 
   <td colname="col2"> Muestra un panel sin líneas de borde para Buscadores en el espacio de trabajo (pero no en la barra lateral izquierda). </td> 
  </tr> 
 </tbody> 
</table>

