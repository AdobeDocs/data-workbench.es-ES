---
description: Debe configurar los Insight Server de destino para recuperar datos del repetidor en el que se almacenan los datos del evento original.
title: Configuración del servicio de replicación
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Configuración del servicio de replicación{#configuring-the-replication-service}

{{eol}}

Debe configurar los Insight Server de destino para recuperar datos del repetidor en el que se almacenan los datos del evento original.

Para configurar la recuperación de datos desde un [!DNL Repeater] a un destinatario [!DNL Insight Server], debe editar la variable [!DNL Replicate.cfg] en el [!DNL Components] carpeta en el destino [!DNL Insight Server(s)] tal como se describe en el siguiente procedimiento:

**Para configurar la variable [!DNL Replication Service] en el equipo de destino**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono del destino [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Replicate.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL Replicate.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Replicate.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La variable [!DNL Replicate.cfg] se abre.
1. En el [!DNL Replicate.cfg] ventana, haga clic en **[!UICONTROL Replicate.cfg]**, luego **[!UICONTROL component]** para ver su contenido.
1. Edite los parámetros utilizando el ejemplo y la tabla siguientes como guías:

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
      <td colname="col2"> <p>Los directorios de la variable <span class="wintitle"> Repetidor</span> que se van a copiar (replicar) en el destino <span class="keyword"> Insight Server</span>. La variable <span class="wintitle"> Servicio de replicación</span> permite la duplicación de varios directorios desde un único <span class="wintitle"> Repetidor</span>. </p> <p>Para añadir un directorio nuevo, haga clic con el botón derecho <span class="uicontrol"> Directorios</span> y haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Directorio</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Acoplar rutas </td> 
      <td colname="col2"> <p>Verdadero o falso. La acción definida por la configuración de este parámetro depende de la configuración del parámetro Recursive en este archivo: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Si Recursivo es falso, Acoplar rutas no tiene ningún efecto. Solo se replican los archivos del nivel superior del directorio especificado por el parámetro URI remoto. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Si Recursive es true y Flatten Paths es false, la estructura de directorio del remoto (<span class="wintitle"> Repetidor</span>) se duplica exactamente en la ruta local del destino <span class="keyword"> Insight Server</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Si tanto las rutas recursivas como las de acoplamiento son verdaderas, no se crean subdirectorios en la ruta local. En su lugar, todos los archivos del árbol del directorio remoto se colocan en el nivel superior del directorio local. </li>
      </ul></p> <p> <p>Nota: Si tanto Flatten Rutas como Recursive son verdaderas y los archivos de los distintos subdirectorios del equipo remoto comparten los mismos nombres, la variable <span class="wintitle"> Servicio de replicación</span> puede detenerse u otro comportamiento indefinido. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ruta local </td> 
      <td colname="col2">La ubicación de almacenamiento de los archivos recuperados de <span class="wintitle"> Repetidor</span>. La ruta es relativa al <span class="keyword"> Insight Server</span> directorio de instalación. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursivo </td> 
      <td colname="col2"> Verdadero o falso. Si es false, solo se replican los archivos del nivel superior del directorio especificado por el parámetro Remote URI . Consulte Acoplar rutas en esta tabla. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">El URI, incluida una máscara de archivo, para acceder a la variable <span class="wintitle"> del repetidor</span> almacén de archivos. La variable <span class="filepath"> Communications.cfg</span> en el <span class="wintitle"> Repetidor</span> debe configurarse para que se pueda acceder a los datos de evento mediante este URI. Consulte <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitorización del espacio de datos del evento</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Servidor </td> 
      <td colname="col2">Parámetros para la variable <span class="wintitle"> Repetidor</span> desde el cual el objetivo <span class="keyword"> Insight Server</span> recupera archivos de datos de evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nombre </td> 
      <td colname="col2">Opcional. El nombre para identificar el <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nombre común del servidor SSL </td> 
      <td colname="col2">Requerido solo si Use SSL está establecido en true. Nombre común de la variable <span class="wintitle"> Repetidor</span> en el que se almacenan los datos del evento. Este nombre debe coincidir con el nombre común enumerado en el certificado de comunicaciones del equipo. </td> 
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
      <td colname="col2">Requerido solo si Use SSL está establecido en true. Nombre del certificado de licencia utilizado para conectarse al <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usar SSL </td> 
      <td colname="col2"> <p>Determina si SSL se utiliza para la transmisión de datos. Las opciones son true o false, y el valor predeterminado es false. </p> <p> <p>Nota: No se recomienda utilizar SSL porque puede afectar negativamente al rendimiento. Tenga en cuenta que SSL no es necesario a menos que la red que conecta el <span class="wintitle"> Repetidor</span> a los equipos de destino no es seguro. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de finalización, hora de inicio </td> 
      <td colname="col2"> <p>(Opcional) Limita el conjunto de archivos de datos de evento copiados en el destino <span class="keyword"> Insight Server</span> a aquellos que contienen datos en el intervalo definido por la hora de inicio y la hora de finalización. Si se establece la hora de inicio, no se copiarán los archivos de datos de evento en los que todas las entradas de registro sean anteriores a la hora de inicio especificada. Si se establece la hora de finalización, no se copiarán los archivos de datos de evento en los que todas las entradas de registro desde la hora especificada o posterior. Si solo parte de los datos de un archivo se encuentra en el rango especificado, todo el archivo se copia en el equipo de destino. </p> <p>Adobe recomienda usar uno de los siguientes formatos para el momento: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 de enero de 2013 HH:MM:SED EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 de Enero del 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Nota: Debe especificar una zona horaria. Si no se especifica nada, la zona horaria no pasará de forma predeterminada a la hora del sistema. Si desea implementar Horario de verano o una política similar de cambio de reloj, debe guardar la variable <span class="filepath"> .dst</span> archivo que contiene las reglas adecuadas en el directorio Base\Dataset\Timezone de la <span class="keyword"> Insight Server</span> máquina. Para obtener una lista de abreviaturas de zona horaria admitidas e información sobre la implementación del horario de verano, consulte <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de huso horario</a>. </p> </p> <p> <p>Nota: Para utilizar esta configuración, los nombres de los archivos de datos de evento deben comenzar por una fecha ISO (AAAAMMDD), y cada archivo debe contener datos del periodo de 24 horas que comienza a las 12 AM GMT de esa fecha. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Este ejemplo ilustra cómo se copian los archivos si los parámetros Acoplar rutas y Recursivo están establecidos en true.

Supongamos que el URI remoto es [!DNL /RemoteRoot/] y la ruta local es [!DNL E:\LocalRoot\]. En el mando a distancia ( [!DNL Repeater]), los archivos están organizados de la siguiente manera:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Cuando se completa la replicación, el directorio local tiene los siguientes archivos:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

En el directorio local, no se crean subdirectorios y todos los archivos del árbol de directorios remotos se colocan en el nivel superior del directorio local.

>[!NOTE]
>
>Si los archivos de los distintos subdirectorios del equipo remoto comparten los mismos nombres, la variable [!DNL Replication Service] puede detenerse u otro comportamiento indefinido.
