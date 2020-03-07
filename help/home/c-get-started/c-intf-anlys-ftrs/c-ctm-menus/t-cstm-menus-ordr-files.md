---
description: Puede personalizar la apariencia de cualquier menú editando el archivo order.txt asociado a ese menú.
solution: Analytics
title: Personalización de un menú mediante archivos order.txt
topic: Data workbench
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalización de un menú mediante archivos order.txt{#customize-a-menu-using-order-txt-files}

Puede personalizar la apariencia de cualquier menú editando el archivo order.txt asociado a ese menú.

Los pasos de esta sección se aplican a todos los tipos de menús.

**Edición del archivo order.txt para personalizar un menú**

1. En la [!DNL Profile Manager], en la columna Nombre *del* perfil, haga clic con el botón secundario en la marca de verificación del [!DNL order.txt] archivo y haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón secundario en la marca de verificación del [!DNL order.txt] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se muestra el [!DNL order.txt] archivo.

   ![Información sobre los pasos](assets/cfg_ordertxt.png)

1. (Opcional) Agregue o cambie la configuración [Inclusivo] o [Exclusivo] en la parte superior del archivo si lo desea. Esta configuración controla si los elementos que no aparecen en el [!DNL order.txt] archivo pero sí en el [!DNL Profile Manager] aparecen en el menú. Las opciones incluyen:

   * **[Inclusivo]:**Ésta es la configuración predeterminada. Esta configuración hace que los elementos de menú que no se especifican en el[!DNL order.txt]archivo se muestren en la parte inferior del menú en orden alfabético. Por ejemplo, si el elemento[!DNL Profile Manager]contenía un elemento de perfil además de los enumerados en[!DNL order.txt]arriba, el perfil se mostraría debajo de Datos.

   * **[Exclusivo]:**Esta configuración hace que los elementos de menú que no se especifican en el[!DNL order.txt]archivo se excluyan del menú. Por ejemplo, si el elemento[!DNL Profile Manager]contenía un elemento de perfil además de los enumerados en[!DNL order.txt]arriba, el perfil no se mostraría en ninguna parte del menú.

   * **blank:** Si ni [Inclusivo] ni [Exclusivo] aparece en la parte superior del archivo, Área de trabajo de datos muestra los elementos de menú como si la configuración fuera [inclusivo].

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
    <td colname="col2"> <p>Escriba los nombres de los elementos en el orden en que desea que aparezcan en Área de trabajo de datos. </p> <p>Por ejemplo, siempre que cada nombre de elemento de menú coincida con el nombre de archivo o carpeta correspondiente, lo siguiente provocará<b> que la opción Agregar tabla</b> aparezca primero y, a continuación, <b>Agregar visualización</b>, <b>Agregar leyenda</b>y <b>Agregar nota</b> aparezca en último lugar. </p> <p><b>Agregar tabla </b> </p> <p><b>Agregar visualización </b> </p> <p><b>Agregar leyenda </b> </p> <p><b>Agregar nota </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Cambiar el nombre de un elemento de menú </p> </td> 
    <td colname="col2"> <p>Cambie el nombre del archivo o la carpeta correspondiente en el Administrador <span class="wintitle"> de</span>perfiles y, a continuación, cambie el nombre del elemento en el <span class="filepath"> archivo order.txt</span> . </p> <p>Por ejemplo, para cambiar el nombre de Agregar anotación a nueva anotación, cambie el nombre de la carpeta Agregar anotación en el Administrador <span class="wintitle"> de perfiles a Nueva anotación y, a continuación, cambie el nombre del elemento Agregar anotación en el archivo</span> order.txt <span class="filepath"></span> a Nueva anotación. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ocultar un elemento de menú </p> </td> 
    <td colname="col2"> <p>Para ocultar el elemento de menú pero no eliminarlo, escriba un signo menos (-) al principio del nombre. </p> <p>Por ejemplo, el siguiente resultado es que <span class="wintitle"> Agregar anotación</span> no aparece en el menú. </p> <p>Agregar leyenda </p> <p>-Agregar anotación </p> <p>Para volver a mostrar el elemento de menú oculto, simplemente elimine el signo menos (-) o utilice el parámetro Mostrar todo en el archivo <span class="filepath"> Insight.cfg</span> , consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parámetrosde configuración de Insight</a>. </p> <p>También puede ocultar elementos de menú mediante los siguientes métodos: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>El parámetro Mostrar de un archivo <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span>o <span class="filepath"> .dim</span> oculta los filtros, las métricas y dimensiones derivadas y las dimensiones ampliadas de sus respectivos menús. Al utilizar esta opción, el elemento no aparece en el menú, pero aún está en el perfil y disponible para su uso. </p> <p>Para utilizar este parámetro para ocultar filtros y métricas y dimensiones derivadas, agregue la línea siguiente al final del archivo <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>o <span class="filepath"> .filter</span> : </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Para utilizar este parámetro para ocultar dimensiones extendidas, consulte el Capítulo 10 de la Guía <i>de configuración de</i> Dataset para obtener instrucciones. </p> <p>Puede mostrar temporalmente los elementos ocultos mediante este método estableciendo el parámetro Mostrar todo en el archivo <span class="filepath"> Insight.cfg</span> . Para obtener más información sobre este parámetro, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parámetros</a>de configuración de Insight. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">El parámetro Oculto del archivo <span class="filepath"> Transformation.cfg</span> o cualquier conjunto de datos que incluya un archivo oculta las dimensiones extendidas del menú de dimensiones. Al utilizar esta opción, el elemento no aparece en el menú, pero aún está en el perfil y disponible para su uso. <p> <p>Nota:  Al ocultar dimensiones extendidas mediante este método, debe volver a transformar el conjunto de datos para que las dimensiones se oculten. </p> </p> <p>Puede mostrar temporalmente los elementos ocultos mediante este método estableciendo el parámetro Mostrar todo en el archivo <span class="filepath"> Insight.cfg</span> . Para obtener más información sobre este parámetro, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parámetros</a>de configuración de Insight. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Los archivos de byte cero ocultan cualquier tipo de elemento en cualquier menú. Al utilizar esta opción, un archivo vacío (de byte cero) oculta la presencia de un archivo con el mismo nombre que contiene datos. Área de trabajo de datos trata los archivos de byte cero como si no existieran. Para obtener más información, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ocultar archivos usando archivos</a>vacíos (byte cero). </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Eliminar un elemento de menú </p> </td> 
    <td colname="col2"> <p>Si este archivo está configurado para utilizar la opción [Exclusivo], simplemente puede eliminar el elemento de menú de este archivo. El elemento en sí sigue en el perfil, pero no aparece en el menú. </p> <p>Si este archivo está configurado para utilizar la opción [Inclusivo], debe quitar el nombre del elemento de menú de este archivo y eliminar o de byte cero el archivo correspondiente para eliminar el elemento del menú. </p> <p>Para obtener información sobre la eliminación de archivos, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Eliminación de archivos del perfil</a>de trabajo. Para obtener información sobre los archivos de byte cero, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ocultar archivos usando archivos</a>vacíos (de byte cero). </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Agregar un encabezado de grupo </p> </td> 
    <td colname="col2"> <p>Escriba tres guiones antes y después del texto del encabezado que desea que aparezca. </p> <p>Por ejemplo, lo siguiente resultaría en un encabezado de grupo Administrar para un conjunto de elementos de menú relacionados. </p> <p>---Administrar--- </p> <p>Perfil </p> <p>Conjunto de datos </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Agregar una línea a secciones separadas de un menú </p> </td> 
    <td colname="col2"> <p>Escriba tres guiones en los que desee que aparezca una línea. </p> <p>Por ejemplo, el resultado siguiente es una línea que separa Agregar anotación y Agregar personalizada. </p> <p>Agregar anotación </p> <p>--- </p> <p>Agregar personalizado </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Guarde y cierre el archivo.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca del [!DNL order.txt] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
