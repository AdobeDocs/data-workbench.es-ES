---
description: El archivo de configuración Log Processing Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar orígenes sin conexión o especificar la frecuencia con la que el servidor del área de trabajo de datos guarda sus archivos de estado.
solution: Analytics
title: Modo de procesamiento de registros.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modo de procesamiento de registros.cfg{#log-processing-mode-cfg}

El archivo de configuración Log Processing Mode.cfg permite pausar el procesamiento de datos en un conjunto de datos, especificar orígenes sin conexión o especificar la frecuencia con la que el servidor del área de trabajo de datos guarda sus archivos de estado.

La realización de cambios en el [!DNL Log Processing Mode.cfg] archivo, incluida la adición o eliminación de fuentes, no provoca el reprocesamiento de los datos.

**Para editar el archivo Log Processing Mode.cfg de un perfil de conjunto de datos**

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.

   >[!NOTE]
   >
   >Si el [!DNL Log Processing Mode.cfg] archivo no se encuentra en el directorio del perfil deseado, debe copiar este archivo del directorio Base del equipo del servidor del área de trabajo de datos en el directorio del perfil.

   Para obtener información sobre cómo abrir y trabajar con el [!DNL Profile Manager,] servidor, consulte la Guía del usuario *del área de trabajo de datos*.

1. Haga clic con el botón secundario en la marca de verificación situada junto al nombre del archivo de configuración y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece la ventana de configuración.
1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía.

   >[!NOTE]
   >
   >Algunos de los parámetros del [!DNL Log Processing Mode.cfg] archivo tienen nombres que incluyen [!DNL Fast Input] o [!DNL Fast Merge]. [!DNL Fast Input]hace referencia a la fase de procesamiento de registros de la construcción de conjuntos de datos y es responsable de aproximadamente la mitad del tiempo total de procesamiento del conjunto de datos. [!DNL Fast Merge] hace referencia a la fase de transformación de la construcción de conjuntos de datos sólo cuando está precedida por el procesamiento de registros. [!DNL Fast Merge] no se produce durante la retransformación que resulta de la modificación de un [!DNL Transformation Dataset Configuration] archivo. Al igual [!DNL Fast Input], [!DNL Fast Merge] también es responsable de aproximadamente la mitad del tiempo de procesamiento del conjunto de datos.

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
      <td colname="col2"> <p>Parámetro de ajuste que afecta a la eficacia de la transformación de datos. El valor predeterminado es 128000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proporción de decisión de entrada rápida </td> 
      <td colname="col2"> <p>Parámetro de ajuste que especifica la proporción de bytes de registro totales a no leídos en los que el sistema entra en el modo de entrada <span class="wintitle"> rápida (y, posteriormente, en</span> Combinación <span class="wintitle"></span>rápida) en lugar de procesar los datos en tiempo real. </p> <p> El valor predeterminado es 200, lo que significa que el sistema entra en el modo de entrada <span class="wintitle"></span> rápida desde el modo de tiempo real cuando los datos del registro sin leer se encuentran en el 1/200 de los datos totales. Una mayor proporción de decisión hace que el sistema entre en el modo de entrada <span class="wintitle"> rápida con mayor facilidad, mientras que una menor proporción hace que sea menos probable que entre en el modo de entrada</span> <span class="wintitle"></span> rápida. </p> <p> <p>Nota: Si se establece el parámetro en 0, se evita que el sistema entre en el modo de entrada <span class="wintitle"></span> rápida, incluso para el procesamiento inicial. Al establecer el parámetro en 1.1, el sistema puede introducir <span class="wintitle"> Fast Input</span> durante el procesamiento inicial, pero no para el procesamiento posterior. Adobe no recomienda el uso de valores entre 0 y 1.1. Para obtener más información sobre la configuración de este parámetro, póngase en contacto con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes FIFO de entrada rápida </td> 
      <td colname="col2"> <p>Parámetro de ajuste que equilibra el uso de la memoria y el rendimiento del sistema durante el procesamiento de datos. El valor predeterminado es 120000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes del búfer de combinación rápida </td> 
      <td colname="col2"> <p>Parámetro de ajuste que equilibra el uso de la memoria y el rendimiento del sistema durante el procesamiento de datos. El valor predeterminado es 128000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuentes sin conexión </td> 
      <td colname="col2"> <p>Máscara del origen del registro sin conexión. </p> <p> <b> Especificación de un origen sin conexión</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Haga clic con el botón secundario <span class="uicontrol"> en Fuentes</span>sin conexión y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Origen</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> En el parámetro del nuevo origen, introduzca la máscara de la secuencia de registro. Para orígenes de registro de sensores con nombres de archivo con el formato YYYMMDD-<i>SENSORID</i>.vsl, la máscara distingue entre mayúsculas y minúsculas <i>SENSORID.SENSORID</i> . Para los orígenes de registro de archivos de registro, la máscara es la cadena extraída por el patrón <span class="wintitle"> de</span>máscara. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </li> 
      </ul> </p> <p> La adición o eliminación de fuentes de fuentes sin conexión no provoca el reprocesamiento del conjunto de datos. </p> <p> A partir del tiempo se mantienen las mediciones para el procesamiento de las fuentes en línea del perfil. Cuando el origen sin conexión vuelve a estar en línea, se reanuda el procesamiento de los archivos de registro entrantes para ese origen. </p> <p> Siempre que una fuente vuelva a estar en línea, debe eliminarla de las fuentes sin conexión. Si no lo hace, el servidor del área de trabajo de datos trata el origen como un origen en línea y actualiza el valor Con el tiempo mientras el origen esté enviando datos. Si la fuente se desconecta de nuevo, se detienen las mediciones Con el tiempo. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> En pausa </td> 
      <td colname="col2"> True o false. Si es true, los nuevos datos no se procesan en el conjunto de datos. El valor predeterminado es false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Retraso en tiempo real </td> 
      <td colname="col2"> Cantidad de tiempo en segundos que el servidor del área de trabajo de datos espera entre intervalos de procesamiento de datos en el conjunto de datos. Cuando este valor se establece en cero, el sistema intenta mantenerse al día con los datos entrantes en tiempo real. El valor predeterminado es cero (0), pero puede aumentar este valor para reducir la carga de la CPU. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes FIFO en tiempo real </td> 
      <td colname="col2"> <p>Cantidad de memoria en bytes utilizada para almacenar datos que están esperando ser procesados en el conjunto de datos. Es posible que tenga que cambiar este valor en función del número de segundos que especifique para el retraso en tiempo real. El valor predeterminado es 16000000. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervalo de guardado (s) </td> 
      <td colname="col2"> <p>Frecuencia con la que el servidor del área de trabajo de datos guarda sus archivos de estado. El valor predeterminado es 3600. </p> <p> <p>Nota:  No debe cambiar este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Al editar el [!DNL Log Processing Mode.cfg] archivo dentro de una ventana del área de trabajo de datos, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x), copiar (Ctrl+c), pegar (Ctrl+v), deshacer (Ctrl+z), rehacer (Ctrl+Mayús+z), seleccionar la sección (hacer clic+arrastrar) y seleccionar todo (Ctrl+a). Además, puede utilizar los métodos abreviados para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo de la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
