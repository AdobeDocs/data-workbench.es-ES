---
description: El Administrador de archivos del servidor le permite administrar y administrar de forma remota los equipos del servidor de Data Workbench desde cualquier Data Workbench autorizada al proporcionar acceso a todos los directorios y archivos del directorio de instalación del producto, incluidos los archivos de configuración y búsqueda.
title: Administrador de archivos del servidor
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 1%

---

# Administrador de archivos del servidor{#server-files-manager}

El Administrador de archivos del servidor le permite administrar y administrar de forma remota los equipos del servidor de Data Workbench desde cualquier Data Workbench autorizada al proporcionar acceso a todos los directorios y archivos del directorio de instalación del producto, incluidos los archivos de configuración y búsqueda.

Puede acceder a [!DNL Server Files Manager] utilizando el menú [!DNL Admin], así como haciendo clic con el botón derecho en el nodo del equipo servidor de Data Workbench en [!DNL Servers Manager] y haciendo clic en **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Puede crear nuevos administradores de archivos de servidor que muestren los directorios seleccionados. Consulte [Creación de nuevos administradores de archivos de servidor](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

La columna izquierda de [!DNL Server Files Manager] enumera los nombres de archivo y carpeta. Las marcas de verificación en las columnas central y derecha indican en qué parte de la estructura de archivos se encuentran estos directorios y archivos.

Si un archivo reside en el directorio de instalación del producto, la columna *server name* (por ejemplo, servidor de Data Workbench) contiene una marca de verificación. Si un archivo reside en el equipo del usuario de la Data Workbench en el directorio *Data Workbench installation directory*\Temp, la columna [!DNL Temp] contiene una marca de verificación. El color de las marcas de verificación indica si los archivos que residen en diferentes ubicaciones se modificaron al mismo tiempo.

* Una marca de verificación roja en la columna de nombre del servidor indica que la carpeta o el archivo reside en el equipo servidor de Data Workbench.
* La marca de verificación roja de la columna [!DNL Temp] indica que la copia local del archivo o carpeta tiene la misma fecha y hora de modificación que el archivo o la carpeta del equipo servidor de Data Workbench.
* Una marca de verificación blanca en la columna [!DNL Temp] indica que el archivo o la carpeta del directorio de instalación de la Data Workbench **\Temp tiene una fecha y hora de modificación diferente a la del archivo o carpeta del equipo servidor de Data Workbench.

El siguiente gráfico muestra el [!DNL Server Files Manager] con marcas de verificación en rojo y blanco:

![](assets/vis_FileManager_RedWhiteChecks.png)

**Para administrar directorios y archivos con la variable[!DNL Server Files Manager]**

Puede utilizar [!DNL Server Files Manager] para manipular directorios y archivos en un equipo servidor de Data Workbench.

La siguiente tabla enumera las tareas que se pueden completar con el [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para realizar esta tarea... </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para ver los archivos de cualquier directorio </p> </td> 
   <td colname="col2"> <p>Haga clic en el nombre del directorio para ver su contenido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ocultar el contenido de un directorio </p> </td> 
   <td colname="col2"> <p>Haga clic en el nombre del directorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver detalles sobre un directorio </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la celda situada junto al directorio en la columna nombre del servidor o <span class="wintitle"> Temp</span>. Verá la siguiente información: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Ruta. Ruta del directorio. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. El nombre del directorio. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">De. La ubicación del directorio, Remoto o Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Fecha (solo columna temporal). Fecha de creación o la fecha de la última revisión de la copia local. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver detalles sobre un archivo </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación situada junto al archivo en la columna nombre del servidor o <span class="wintitle"> Temp</span> . Verá la siguiente información: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Ruta. Ruta del archivo. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Archivo. Nombre del archivo. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">De. La ubicación del directorio, Remoto o Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Fecha. Fecha de la última revisión del archivo. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Tamaño. El tamaño del archivo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para descargar un directorio en el equipo local </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación de la columna <i>server name</i> para este directorio y haga clic en <span class="uicontrol"> Make Directory Local</span>. En la columna <span class="wintitle"> Temp</span> aparece una marca de verificación para el directorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para descargar un archivo en el equipo local </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación de la columna <i>server name</i> para este archivo y haga clic en <span class="uicontrol"> Make Local</span>. En la columna <span class="wintitle"> Temp</span> aparece una marca de verificación para el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para descargar la última parte de un archivo de registro en el equipo local </p> </td> 
   <td colname="col2"> <p>Para evitar tener que descargar un archivo de registro completo (especialmente cuando sabe que el mensaje de error está cerca del final del archivo), haga clic con el botón derecho en la marca de verificación de la columna del nombre del servidor para el archivo, haga clic en <span class="uicontrol"> Carril</span> y seleccione el tamaño de la parte que desee descargar. En la columna <span class="wintitle"> Temp</span> aparece una marca de verificación para el archivo. El archivo local contiene solamente la cantidad de datos que especificó, empezando por el final del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para abrir un directorio </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación del directorio en la columna <span class="wintitle"> Temp</span> y haga clic en <span class="uicontrol"> Abrir</span> &gt; <span class="uicontrol"> carpeta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para abrir un archivo </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación del archivo en la columna <span class="wintitle"> Temp</span>, haga clic en <span class="uicontrol"> Abrir</span> y, a continuación, haga clic en <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> en Bloc de notas</span> o en <span class="uicontrol"> carpeta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guardar una copia local de un directorio en el servidor de Data Workbench </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación del directorio en la columna <span class="wintitle"> Temp</span> y haga clic en <span class="uicontrol"> Guardar directorio en</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guardar una copia local de un archivo en el servidor de Data Workbench </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación del archivo en la columna <span class="wintitle"> Temp</span> y haga clic en <span class="uicontrol"> Guardar en</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span></i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eliminación de una copia local de un directorio o archivo </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación del directorio o archivo en la columna <span class="wintitle"> Temp</span> y haga clic en <span class="uicontrol"> Quitar</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copiar y pegar un archivo como archivo adjunto de correo electrónico en Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en la marca de verificación del archivo en la columna <span class="wintitle"> Temp</span> y haga clic en <span class="uicontrol"> Copiar</span>. En el cuerpo del correo electrónico, pulse Ctrl+v para adjuntar el archivo. </p> </td> 
  </tr> 
 </tbody> 
</table>
