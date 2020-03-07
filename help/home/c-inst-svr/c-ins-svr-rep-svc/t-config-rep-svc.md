---
description: Debe configurar los servidores de Insight de destino para recuperar datos del repetidor en el que se almacenan los datos del evento original.
solution: Insight
title: Configuración del servicio de replicación
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración del servicio de replicación{#configuring-the-replication-service}

Debe configurar los servidores de Insight de destino para recuperar datos del repetidor en el que se almacenan los datos del evento original.

Para configurar la recuperación de datos de un destino [!DNL Repeater] a un destino [!DNL Insight Server], debe editar el [!DNL Replicate.cfg] archivo proporcionado en la [!DNL Components] carpeta del destino [!DNL Insight Server(s)] como se describe en el siguiente procedimiento:

**Para configurar el[!DNL Replication Service]en el equipo de destino**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del destino [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Components]** para ver su contenido. El [!DNL Replicate.cfg] archivo se encuentra dentro de este directorio.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL Replicate.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Replicate.cfg].
1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Se abre la [!DNL Replicate.cfg] ventana.
1. En la [!DNL Replicate.cfg] ventana, haga clic en **[!UICONTROL Replicate.cfg]** y, a continuación, **[!UICONTROL component]** para ver su contenido.
1. Edite los parámetros con el siguiente ejemplo y la tabla como guías:

   ![Información sobre los pasos](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Para este parámetro... </th> 
      <th colname="col2" class="entry"> Especifique... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Directorios </td> 
      <td colname="col2"> <p>Los directorios del <span class="wintitle"> Repetidor</span> que se van a copiar (replicar) en el <span class="keyword"> Insight Server</span>de destino. El servicio <span class="wintitle"> de</span> replicación permite la replicación de varios directorios desde un único <span class="wintitle"> repetidor</span>. </p> <p>Para agregar un nuevo directorio, haga clic con el botón secundario en <span class="uicontrol"> Directorios</span> y haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Directorio</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Acoplar rutas </td> 
      <td colname="col2"> <p>True o false. La acción definida por la configuración de este parámetro depende de la configuración del parámetro Recursive en este archivo: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Si Recursivo es falso, Acoplar rutas no tiene ningún efecto. Solo se replican los archivos del nivel superior del directorio especificado por el parámetro URI remoto. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Si Recursive es true y Flatten Paths es false, la estructura de directorio del directorio remoto (<span class="wintitle"> Repeater</span>) se duplica exactamente en la ruta local del <span class="keyword"> servidor</span>de Insight de destino. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Si las rutas Recursiva y Acoplar son verdaderas, no se crean subdirectorios en la ruta local. En su lugar, todos los archivos del árbol del directorio remoto se colocan en el nivel superior del directorio local. </li>
      </ul></p> <p> <p>Nota: Si tanto las Rutas de acoplamiento como las Recursivas son verdaderas y los archivos de los distintos subdirectorios del equipo remoto comparten los mismos nombres, el servicio <span class="wintitle"></span> de replicación puede detenerse o puede producirse otro comportamiento no definido. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ruta local </td> 
      <td colname="col2">La ubicación de almacenamiento de los archivos recuperados de <span class="wintitle"> Repeater</span>. La ruta es relativa al directorio de instalación de <span class="keyword"> Insight Server</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recurrente </td> 
      <td colname="col2"> True o false. Si es false, solo se replican los archivos del nivel superior del directorio especificado por el parámetro URI remoto. Consulte Acoplar rutas en esta tabla. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">El URI, incluida una máscara de archivo, para acceder al almacén de archivos del <span class="wintitle"> repetidor</span> . El <span class="filepath"> archivo Communications.cfg</span> del <span class="wintitle"> Repetidor</span> debe configurarse para que se pueda acceder a los datos del evento mediante este URI. Consulte <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoreo del espacio</a>de datos del evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Servidor </td> 
      <td colname="col2">Parámetros del <span class="wintitle"> repetidor</span> desde el que el servidor <span class="keyword"> de</span> Insight de destino recupera los archivos de datos de eventos. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nombre </td> 
      <td colname="col2">Opcional. Nombre para identificar el <span class="wintitle"> repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nombre común del servidor SSL </td> 
      <td colname="col2">Solo es necesario si Usar SSL está establecido en true. Nombre común del <span class="wintitle"> Repetidor</span> en el que se almacenan los datos del evento. Este nombre debe coincidir con el nombre común que aparece en el certificado de comunicaciones del equipo. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dirección </td> 
      <td colname="col2">Nombre de host o dirección IP numérica del <span class="wintitle"> Repetidor</span> en el que se almacenan los datos del evento. El nombre común del servidor no es una entrada válida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Puerto </td> 
      <td colname="col2"> Puerto utilizado para la transmisión de datos. El puerto predeterminado es 80.  </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificado de cliente SSL </td> 
      <td colname="col2">Solo es necesario si Usar SSL está establecido en true. Nombre del certificado de licencia utilizado para conectarse al <span class="wintitle"> repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usar SSL </td> 
      <td colname="col2"> <p>Determina si se utiliza SSL para la transmisión de datos. Las opciones son true o false y el valor predeterminado es false. </p> <p> <p>Nota: No se recomienda utilizar SSL porque puede afectar negativamente al rendimiento. Tenga en cuenta que SSL no es necesario a menos que la red que conecta el <span class="wintitle"> Repetidor</span> a los equipos de destino no sea segura. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de finalización, Hora de inicio </td> 
      <td colname="col2"> <p>(Opcional) Limita el conjunto de archivos de datos de eventos copiados en el servidor <span class="keyword"> de</span> Insight de destino a los que contienen datos en el intervalo definido por Hora de inicio y Hora de finalización. Si se establece la hora de inicio, no se copian los archivos de datos de eventos en los que todas las entradas de registro son anteriores a la hora de inicio especificada. Si se establece la hora de finalización, los archivos de datos del evento en los que no se copian todas las entradas del registro a partir del tiempo especificado o posterior. Si sólo una parte de los datos de un archivo se encuentra en el rango especificado, el archivo completo se copia en el equipo de destino. </p> <p>Adobe recomienda utilizar uno de los siguientes formatos para el momento: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 de enero de 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 de enero de 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Nota: Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en la hora del sistema si no se especifica. Si desea implementar Daylight Saving Time o una política de cambio de reloj similar, debe guardar el archivo <span class="filepath"> .dst</span> que contiene las reglas correspondientes en el Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> . Para obtener una lista de abreviaciones de zona horaria admitidas e información sobre la implementación de Horario de verano de verano, consulte <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos</a>de zona horaria. </p> </p> <p> <p>Nota:  Para utilizar esta configuración, los nombres de los archivos de datos del evento deben comenzar con una fecha ISO (AAAAMMDD) y cada archivo debe contener datos para el período de 24 horas que comienza a las 12 AM GMT de esa fecha. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Este ejemplo ilustra cómo se copian los archivos si los parámetros Acoplar rutas y Recursivo están definidos como true.

Supongamos que el URI remoto es [!DNL /RemoteRoot/] y que la ruta de acceso local es [!DNL E:\LocalRoot\]. En el equipo remoto ( [!DNL Repeater]), los archivos están organizados de la siguiente manera:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Cuando se completa la replicación, el directorio local tiene los siguientes archivos:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

En el directorio local, no se crean subdirectorios y todos los archivos del árbol del directorio remoto se colocan en el nivel superior del directorio local.

>[!NOTE]
>
>Si los archivos de los distintos subdirectorios del equipo remoto comparten los mismos nombres, es posible que [!DNL Replication Service] se detenga o que se produzca otro comportamiento no definido.
