---
description: Pasos para asignar el portal de informes a un directorio virtual (IIS 5.0).
title: Asignación del portal de informes a un directorio virtual (IIS 5.0)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# Asignación del portal de informes a un directorio virtual (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

Pasos para asignar el portal de informes a un directorio virtual (IIS 5.0).

1. En la máquina donde [!DNL Report Portal] está instalado, inicie el Administrador de IIS mediante **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** o **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Seleccione **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Clic con el botón derecho **[!UICONTROL Default Web Site]** y seleccione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Cuando la variable [!DNL Virtual Directory Wizard] abre, haga clic en **[!UICONTROL Next]**.

1. Complete los siguientes pasos para definir el directorio virtual raíz para [!DNL Report Portal]:

   1. Cuando se le pida un alias, escriba el nombre del [!DNL Report Portal]y haga clic en **[!UICONTROL Next]**. Por ejemplo, si desea utilizar &quot;Portal&quot; como nombre de su [!DNL Report Portal], asigne el alias &quot;Portal&quot; al directorio virtual. Haga clic en **[!UICONTROL Next]** cuando termine.

   1. Cuando se le pida la ruta física, busque y seleccione la variable *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** a continuación, haga clic en **[!UICONTROL Next]**.

      Ejemplo: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Cuando se le solicite permisos, compruebe que las siguientes opciones están habilitadas:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Haga clic en **[!UICONTROL Next]**, luego en **[!UICONTROL Finish]**. El directorio virtual que ha creado aparece en el Sitio Web predeterminado como se muestra en el siguiente ejemplo.

   ![](assets/RptPort_scrn_VirDirManual.png)

1. Haga clic con el botón derecho en el directorio virtual que acaba de crear y seleccione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Utilice la variable [!DNL Virtual Directory] para crear un alias para cada uno de los directorios físicos siguientes. Al hacerlo, se crea un directorio virtual con el nombre adecuado para cada uno de estos recursos físicos.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cree este alias . . . </th> 
   <th colname="col2" class="entry"> Para este recurso físico . . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\Archivos de portal\Core </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\Archivos de portal\CSS </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\Archivos de portal\HTC </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imágenes </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\Archivos de portal\Imágenes </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> <p>Ubicación física del directorio en el que <span class="keyword"> Servidor de informes</span> guarda el resultado de los conjuntos de informes. La carpeta de salida se puede ubicar en cualquier lugar, se le puede dar un nombre y contiene una subcarpeta para cada conjunto de informes. </p> <p>Debe ser el mismo directorio que especifique en el parámetro Raíz de salida en la variable <span class="filepath"> Report.cfg</span> para un conjunto de informes. Para obtener más información, consulte <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Configuración de los archivos de Report.cfg</a>. </p> <p>La ubicación predeterminada es \<i>PortalName</i>\Archivos de portal\Salida. </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>La variable <i>PortalName</i>\PortalFiles\El directorio Output contiene el <span class="filepath"> profiles.xml</span> , que debe moverse al directorio de salida que especifique para este alias. </p> <p>Es fundamental que <span class="wintitle"> Ruta</span> se ha configurado correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Cuando haya terminado, compruebe que IIS muestre seis directorios virtuales nuevos. Asegúrese de que la estructura del directorio tiene una carpeta principal (con el mismo nombre que el portal) y cinco subcarpetas, como se muestra a continuación.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Cuando termine, vaya a [Edición del archivo de configuración de sesión](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) para continuar con el proceso de instalación.
