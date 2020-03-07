---
description: El archivo de configuración Transform Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar orígenes sin conexión o especificar la frecuencia con la que el servidor del área de trabajo de datos que ejecuta la funcionalidad de transformación guarda los archivos de estado.
solution: Analytics
title: El archivo Transform Mode.cfg
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# El archivo Transform Mode.cfg{#the-transform-mode-cfg-file}

El archivo de configuración Transform Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar orígenes sin conexión o especificar la frecuencia con la que el servidor del área de trabajo de datos que ejecuta la funcionalidad de transformación guarda los archivos de estado.

La realización de cambios en el [!DNL Transform Mode.cfg] archivo, incluida la adición o eliminación de fuentes, no provoca el reprocesamiento de los datos.

**Para editar el archivo Transform Mode.cfg de un perfil de conjunto de datos**

1. Mientras trabaja en el perfil cuyos datos desea exportar, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar el contenido del directorio.
1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Transform Mode.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la [!DNL Transform Mode.cfg] ventana.
1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía:

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parámetro </th> 
    <th colname="col2" class="entry"> Descripción </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Fuentes sin conexión </td> 
    <td colname="col2"> <p>Máscara del origen del registro sin conexión. </p> <p> Para especificar un origen sin conexión: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Haga clic con el botón derecho del ratón <span class="uicontrol"> en Fuentes</span> sin conexión y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Origen</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> En el parámetro del nuevo origen, introduzca la máscara de la secuencia de registro. Para orígenes de registro de sensores con nombres de archivo con el formato <span class="filepath"> YYYMDD-SENSORID.vsl</span>, la máscara distingue entre mayúsculas y minúsculas <i>SENSORID.SENSORID</i> . Para los orígenes de registro de archivos de registro, la máscara es la cadena extraída por el patrón <span class="wintitle"> de</span> máscara (consulte <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Archivos</a>de registro). </li> 
    </ul> <p> La adición o eliminación de fuentes de <span class="wintitle"> fuentes</span> sin conexión no provoca el reprocesamiento del conjunto de datos. </p> <p> A partir del tiempo se mantienen las mediciones para el procesamiento de las fuentes en línea del perfil. Cuando el origen sin conexión vuelve a estar en línea, se reanuda el procesamiento de los archivos de registro entrantes para ese origen. </p> <p> <p>Nota: Siempre que una fuente vuelva a estar en línea, debe eliminarla de <span class="wintitle"> Fuentes</span>sin conexión. Si no lo hace, el servidor del área de trabajo de datos trata el origen como un origen en línea y actualiza el valor Con el tiempo mientras el origen esté enviando datos. Si la fuente se desconecta de nuevo, se detienen las mediciones Con el tiempo. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> En pausa </td> 
    <td colname="col2"> True o false. Si es true, los nuevos datos no se procesan en el conjunto de datos. El valor predeterminado es false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervalo de guardado (s) </td> 
    <td colname="col2"> <p>La frecuencia con la que el servidor del área de trabajo de datos en el que se ejecuta la funcionalidad de transformación guarda sus archivos de estado. El valor predeterminado es 3600. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar con Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Al editar el [!DNL Transform Mode.cfg] archivo dentro de una ventana del área de trabajo de datos, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x), copiar (Ctrl+c), pegar (Ctrl+v), deshacer (Ctrl+z), rehacer (Ctrl+Mayús+z), seleccionar la sección (hacer clic+arrastrar) y seleccionar todo (Ctrl+a). Además, puede utilizar los métodos abreviados para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del área de trabajo de datos [!DNL Transform Mode.cfg] en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, donde nombre del perfil es el nombre del perfil para el que está exportando datos. El reprocesamiento de los datos comienza después de la sincronización del perfil.

   Para obtener información sobre el reprocesamiento de datos para la exportación, consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
