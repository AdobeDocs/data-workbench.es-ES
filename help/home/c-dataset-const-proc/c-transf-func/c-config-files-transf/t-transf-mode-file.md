---
description: El archivo de configuración Transform Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Data Workbench que ejecuta la funcionalidad de transformación guarda sus archivos de estado.
title: El archivo Transform Mode.cfg
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# El archivo Transform Mode.cfg{#the-transform-mode-cfg-file}

{{eol}}

El archivo de configuración Transform Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Data Workbench que ejecuta la funcionalidad de transformación guarda sus archivos de estado.

Realización de cambios en la variable [!DNL Transform Mode.cfg] , incluida la adición o eliminación de orígenes, no causa el reprocesamiento de los datos.

**Para editar el archivo Transform Mode.cfg de un perfil de conjunto de datos**

1. Mientras trabaja en el perfil cuyos datos desea exportar, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar el contenido del directorio.
1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Transform Mode.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La variable [!DNL Transform Mode.cfg] se abre.
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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Clic con el botón derecho <span class="uicontrol"> Fuentes sin conexión</span> y haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Fuente</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> En el parámetro para el nuevo origen, introduzca la máscara de la secuencia de registro. Para orígenes de registro de sensor con nombres de archivo del formato <span class="filepath"> YYYYMDD-SENSORID.vsl</span>, la máscara es <i>SENSORID.SENSORID</i> distingue entre mayúsculas y minúsculas. Para los orígenes de registro de archivos de registro, la máscara es la cadena extraída por la variable <span class="wintitle"> Patrón de máscara</span> (consulte <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Archivos de registro</a>). </li> 
    </ul> <p> Adición o eliminación de orígenes de <span class="wintitle"> Fuentes sin conexión</span> no causa el reprocesamiento del conjunto de datos. </p> <p> A partir del tiempo se mantienen las mediciones para el procesamiento de las fuentes en línea del perfil. Cuando el origen sin conexión vuelve a estar en línea, se reanuda el procesamiento de los archivos de registro entrantes de ese origen. </p> <p> <p>Nota: Siempre que una fuente vuelva a estar en línea, debe eliminarla de <span class="wintitle"> Fuentes sin conexión</span>. Si no lo hace, el servidor de Data Workbench trata el origen como una fuente en línea y actualiza el valor Con el tiempo siempre que el origen envíe datos. Si la fuente vuelve a desconectarse, las mediciones Con fecha y hora se detienen. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> En pausa </td> 
    <td colname="col2"> Verdadero o falso. Si es true, los nuevos datos no se procesan en el conjunto de datos. El valor predeterminado es false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervalo de guardado (s) </td> 
    <td colname="col2"> <p>Frecuencia con la que el servidor de Data Workbench en el que se ejecuta la funcionalidad de transformación guarda sus archivos de estado. El valor predeterminado es 3600. </p> <p> <p>Nota: No debe cambiar este valor sin consultar el Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Al editar el [!DNL Transform Mode.cfg] en una ventana de Data Workbench, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x ), copiar (Ctrl+c), pegar (Ctrl+v ), deshacer (Ctrl+z ), rehacer (Ctrl+Mayús+z ), seleccionar sección (clic+arrastrar) y seleccionar todo (Ctrl+a ). Además, puede utilizar los accesos directos para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de Data Workbench [!DNL Transform Mode.cfg] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, donde nombre de perfil es el nombre del perfil para el que se exportan datos. El reprocesamiento de los datos comienza después de la sincronización del perfil.

   Para obtener información sobre el reprocesamiento de los datos para la exportación, consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
