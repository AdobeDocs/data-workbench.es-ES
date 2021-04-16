---
description: Puede personalizar el aspecto de cualquier menú editando el archivo order.txt asociado a ese menú.
title: Personalización de un menú mediante archivos order.txt
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# Personalización de un menú mediante archivos order.txt{#customize-a-menu-using-order-txt-files}

Puede personalizar el aspecto de cualquier menú editando el archivo order.txt asociado a ese menú.

Los pasos de esta sección se aplican a todos los tipos de menús.

**Edición del archivo order.txt para personalizar un menú**

1. En [!DNL Profile Manager], en la columna *profile name*, haga clic con el botón derecho en la marca de verificación del archivo [!DNL order.txt] y haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón derecho en la marca de verificación del archivo [!DNL order.txt] en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se muestra el archivo [!DNL order.txt] .

   ![Información sobre los pasos](assets/cfg_ordertxt.png)

1. (Opcional) Añada o cambie la configuración [Inclusive] o [Exclusive] en la parte superior del archivo si lo desea. Esta configuración controla si los elementos no enumerados en el archivo [!DNL order.txt] pero presentes en [!DNL Profile Manager] aparecen en la lista del menú. Las opciones incluyen:

   * **[Inclusivo]:** Esta es la configuración predeterminada. Esta configuración hace que los elementos de menú que no se especifican en el archivo [!DNL order.txt]se muestren en la parte inferior del menú en orden alfabético. Por ejemplo, si el [!DNL Profile Manager] contenía un elemento de Perfil además de los enumerados en el [!DNL order.txt] anterior, el Perfil se mostraría debajo de Datos.

   * **[Exclusivo]:** esta configuración hace que los elementos de menú que no se especifican en el  [!DNL order.txt] archivo se excluyan del menú. Por ejemplo, si el [!DNL Profile Manager] contenía un elemento de Perfil además de los enumerados en el [!DNL order.txt] anterior, Perfil no se mostraría en ninguna parte del menú.

   * **en blanco:** si ni  [] Inclusión ni  [] Exclusión aparecen en la parte superior del archivo, Data Workbench muestra los elementos de menú como si la configuración fuera  [Inclusivo].

1. Complete uno o varios de los siguientes pasos:

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Para realizar esta tarea... </th> 
    <th colname="col2" class="entry"> Haga lo siguiente... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Reordenar elementos de menú </p> </td> 
    <td colname="col2"> <p>Escriba los nombres de los elementos en el orden en que desea que aparezcan en la Data Workbench. </p> <p>Por ejemplo, siempre que cada nombre de elemento de menú coincida con su nombre de archivo o carpeta correspondiente, lo siguiente haría que<b> Agregar tabla</b> apareciera primero, luego <b>Agregar visualización</b>, <b>Agregar leyenda</b> y <b>Agregar nota</b> aparecieran por última vez. </p> <p><b>Agregar tabla  </b> </p> <p><b>Añadir visualización  </b> </p> <p><b>Agregar leyenda  </b> </p> <p><b>Agregar nota </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Cambiar el nombre de un elemento de menú </p> </td> 
    <td colname="col2"> <p>Cambie el nombre del archivo o carpeta correspondiente en el <span class="wintitle"> Administrador de perfiles</span> y cambie el nombre del elemento en el archivo <span class="filepath"> order.txt</span>. </p> <p>Por ejemplo, para cambiar el nombre de Agregar anotación a nueva anotación, cambie el nombre de la carpeta Agregar anotación en el <span class="wintitle"> Administrador de perfiles</span> por Nueva anotación y, a continuación, cambie el nombre del elemento Agregar anotación en el archivo <span class="filepath"> order.txt</span> por Nueva anotación. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ocultar un elemento de menú </p> </td> 
    <td colname="col2"> <p>Para ocultar el elemento de menú pero no eliminar el elemento en sí, escriba un signo menos (-) al principio de su nombre. </p> <p>Por ejemplo, los siguientes resultados hacen que <span class="wintitle"> Agregar anotación</span> no aparezca en el menú. </p> <p>Agregar leyenda </p> <p>-Agregar anotación </p> <p>Para volver a mostrar el elemento de menú oculto, simplemente elimine el signo menos (-) o utilice el parámetro Mostrar todo en el archivo <span class="filepath"> Insight.cfg</span>, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parámetros de configuración de Insight</a>. </p> <p>También puede ocultar elementos de menú utilizando los siguientes métodos: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>El parámetro Mostrar de un archivo <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span> o <span class="filepath"> .dim</span> oculta los filtros, las métricas y dimensiones derivadas y las dimensiones ampliadas de sus respectivos menús. Al utilizar esta opción, el elemento no aparece en la lista del menú, pero sigue en el perfil y está disponible para su uso. </p> <p>Para utilizar este parámetro para ocultar filtros y métricas y dimensiones derivadas, agregue la línea siguiente al final del archivo <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> o <span class="filepath"> .filter</span>: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Para utilizar este parámetro para ocultar dimensiones extendidas, consulte el capítulo 10 de la <i>Guía de configuración del conjunto de datos</i> para obtener instrucciones. </p> <p>Puede mostrar temporalmente los elementos ocultos con este método estableciendo el parámetro Mostrar todo en el archivo <span class="filepath"> Insight.cfg</span> . Para obtener más información sobre este parámetro, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parámetros de configuración de Insight</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">El parámetro oculto del archivo <span class="filepath"> Transformation.cfg</span> o cualquier archivo de inclusión de conjunto de datos oculta las dimensiones ampliadas del menú de dimensión. Al utilizar esta opción, el elemento no aparece en la lista del menú, pero sigue en el perfil y está disponible para su uso. <p> <p>Nota:  Al ocultar dimensiones extendidas mediante este método, debe volver a transformar el conjunto de datos para que las dimensiones se oculten. </p> </p> <p>Puede mostrar temporalmente los elementos ocultos con este método estableciendo el parámetro Mostrar todo en el archivo <span class="filepath"> Insight.cfg</span> . Para obtener más información sobre este parámetro, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parámetros de configuración de Insight</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Los archivos de byte cero ocultan cualquier tipo de elemento de cualquier menú. Al utilizar esta opción, un archivo vacío (byte cero) oculta la presencia de un archivo con el mismo nombre que contiene datos. La Data Workbench trata los archivos de byte cero como si no existieran. Para obtener más información, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ocultar archivos usando archivos vacíos (byte cero)</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Eliminar un elemento de menú </p> </td> 
    <td colname="col2"> <p>Si este archivo está configurado para utilizar la opción [Exclusivo], simplemente puede eliminar el elemento de menú de este archivo. El elemento en sí sigue en el perfil, pero no aparece en el menú. </p> <p>Si este archivo está configurado para utilizar la opción [Inclusivo], debe eliminar el nombre del elemento de menú de este archivo y eliminar o de byte cero el archivo correspondiente para eliminar el elemento del menú. </p> <p>Para obtener información sobre la eliminación de archivos, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Eliminación de archivos de su perfil de trabajo</a>. Para obtener información sobre archivos de byte cero, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ocultar archivos usando archivos vacíos (byte cero)</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Agregar un encabezado de grupo </p> </td> 
    <td colname="col2"> <p>Escriba tres guiones antes y después del texto del encabezado que desea que aparezca. </p> <p>Por ejemplo, lo siguiente resultaría en un encabezado Administrar grupo para un conjunto de elementos de menú relacionados. </p> <p>---Administrar--- </p> <p>Perfil </p> <p>Conjunto de datos </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Agregar una línea a secciones separadas de un menú </p> </td> 
    <td colname="col2"> <p>Escriba tres guiones donde desee que aparezca una línea. </p> <p>Por ejemplo, los siguientes resultados están en una línea que separa Agregar anotación y Agregar personalizado. </p> <p>Agregar anotación </p> <p>— </p> <p>Agregar personalizado </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Guarde y cierre el archivo.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca del archivo [!DNL order.txt] en la columna [!DNL User] y haga clic en **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
