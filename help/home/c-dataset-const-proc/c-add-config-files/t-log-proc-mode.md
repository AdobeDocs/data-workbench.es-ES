---
description: El archivo de configuración Log Processing Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Data Workbench guarda sus archivos de estado.
title: Registro de Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Registro de Processing Mode.cfg{#log-processing-mode-cfg}

El archivo de configuración Log Processing Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Data Workbench guarda sus archivos de estado.

La realización de cambios en el archivo [!DNL Log Processing Mode.cfg], incluida la adición o eliminación de fuentes, no provoca el reprocesamiento de los datos.

**Para editar el archivo Log Processing Mode.cfg para un perfil de conjunto de datos**

1. Mientras trabaja en el perfil del conjunto de datos, abra [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.

   >[!NOTE]
   >
   >Si el archivo [!DNL Log Processing Mode.cfg] no está ubicado en el directorio del perfil deseado, debe copiar este archivo del directorio Base en el equipo del servidor de Data Workbench en el directorio del perfil.

   Para obtener información sobre cómo abrir y trabajar con [!DNL Profile Manager,], consulte la *Guía del usuario de Data Workbench*.

1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo de configuración y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la ventana de configuración.
1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía.

   >[!NOTE]
   >
   >Algunos de los parámetros del archivo [!DNL Log Processing Mode.cfg] tienen nombres que incluyen [!DNL Fast Input] o [!DNL Fast Merge]. [!DNL Fast Input]hace referencia a la fase de procesamiento de registros de la construcción del conjunto de datos y es responsable de aproximadamente la mitad del tiempo total de procesamiento del conjunto de datos. [!DNL Fast Merge] hace referencia a la fase de transformación de la construcción del conjunto de datos solo cuando va precedida del procesamiento de registros. [!DNL Fast Merge] no se produce durante la retransformación que resulta de la modificación de un  [!DNL Transformation Dataset Configuration] archivo. Al igual que [!DNL Fast Input], [!DNL Fast Merge] también es responsable de aproximadamente la mitad del tiempo de procesamiento del conjunto de datos.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parámetro </th> 
      <th colname="col2" class="entry"> Descripción </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Bytes de nube </td> 
      <td colname="col2"> <p>Un parámetro de ajuste que afecta a la eficacia de la transformación de datos. El valor predeterminado es 128000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proporción de decisión de entrada rápida </td> 
      <td colname="col2"> <p>Un parámetro de ajuste que especifica la proporción de bytes de registro totales a no leídos en los que el sistema entra en modo <span class="wintitle"> Entrada rápida</span> (y posteriormente <span class="wintitle"> Fusión rápida</span>) en lugar de procesar datos en tiempo real. </p> <p> El valor predeterminado es 200, lo que significa que el sistema entra en modo <span class="wintitle"> Entrada rápida</span> desde el modo en tiempo real cuando los datos de registro sin leer se encuentran en el 1/200 de los datos totales. Una mayor proporción de decisiones hace que el sistema entre en modo <span class="wintitle"> Entrada rápida</span> con mayor facilidad, mientras que una menor proporción hace que sea menos probable que entre en modo <span class="wintitle"> Entrada rápida</span>. </p> <p> <p>Nota: Si el parámetro se establece en 0, el sistema no podrá entrar en modo <span class="wintitle"> Entrada rápida</span>, ni siquiera para el procesamiento inicial. Al establecer el parámetro en 1.1, el sistema puede introducir <span class="wintitle"> Entrada rápida</span> durante el procesamiento inicial, pero no para el procesamiento posterior. Adobe no recomienda el uso de valores entre 0 y 1.1. Para obtener más información sobre cómo configurar este parámetro, póngase en contacto con el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes FIFO de entrada rápida </td> 
      <td colname="col2"> <p>Un parámetro de ajuste que equilibra el uso de memoria y el rendimiento del sistema durante el procesamiento de datos. El valor predeterminado es 120000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes de búfer de combinación rápida </td> 
      <td colname="col2"> <p>Un parámetro de ajuste que equilibra el uso de memoria y el rendimiento del sistema durante el procesamiento de datos. El valor predeterminado es 128000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuentes sin conexión </td> 
      <td colname="col2"> <p>Máscara del origen del registro sin conexión. </p> <p> <b> Especificación de un origen sin conexión</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Haga clic con el botón derecho en <span class="uicontrol"> Fuentes sin conexión</span> y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Origen</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> En el parámetro para el nuevo origen, introduzca la máscara de la secuencia de registro. Para los orígenes de registro de sensor con nombres de archivo con el formato YYYYMDD-<i>SENSORID</i>.vsl, la máscara <i>SENSORID.SENSORID</i> distingue entre mayúsculas y minúsculas. Para los orígenes de registro de archivos de registro, la máscara es la cadena extraída por el <span class="wintitle"> Patrón de máscara</span>. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Archivos de registro</a>. </li> 
      </ul> </p> <p> Agregar o quitar fuentes de fuentes sin conexión no provoca el reprocesamiento del conjunto de datos. </p> <p> A partir del tiempo se mantienen las mediciones para el procesamiento de las fuentes en línea del perfil. Cuando el origen sin conexión vuelve a estar en línea, se reanuda el procesamiento de los archivos de registro entrantes de ese origen. </p> <p> Siempre que una fuente vuelva a estar en línea, debe eliminarla de las fuentes sin conexión. Si no lo hace, el servidor de Data Workbench trata el origen como una fuente en línea y actualiza el valor Con el tiempo siempre que el origen envíe datos. Si la fuente vuelve a desconectarse, las mediciones Con fecha y hora se detienen. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> En pausa </td> 
      <td colname="col2"> Verdadero o falso. Si es true, los nuevos datos no se procesan en el conjunto de datos. El valor predeterminado es false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Retraso en tiempo real </td> 
      <td colname="col2"> Cantidad de tiempo en segundos que el servidor de Data Workbench espera entre intervalos de procesamiento de datos en el conjunto de datos. Cuando este valor se establece en cero, el sistema intenta mantenerse al día con los datos entrantes en tiempo real. El valor predeterminado es cero (0), pero puede aumentar este valor para reducir la carga de la CPU. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes FIFO en tiempo real </td> 
      <td colname="col2"> <p>Cantidad de memoria en bytes utilizada para almacenar datos que están a la espera de ser procesados en el conjunto de datos. Es posible que tenga que cambiar este valor en función del número de segundos especificado para Retraso en tiempo real. El valor predeterminado es 16000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervalo de guardado (s) </td> 
      <td colname="col2"> <p>Frecuencia con la que el servidor de Data Workbench guarda sus archivos de estado. El valor predeterminado es 3600. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Al editar el archivo [!DNL Log Processing Mode.cfg] dentro de una ventana de Data Workbench, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x ), copiar (Ctrl+c), pegar (Ctrl+v ), deshacer (Ctrl+z ), rehacer (Ctrl+Mayús+z ), seleccionar la sección (clic+arrastrar) y seleccionar todo (Ctrl+a ). Además, puede utilizar los accesos directos para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
