---
description: Pasos para asignar el portal de informes a un directorio virtual (IIS 5.0).
solution: Analytics
title: Asignación del portal de informes a un directorio virtual (IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Asignación del portal de informes a un directorio virtual (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

Pasos para asignar el portal de informes a un directorio virtual (IIS 5.0).

1. En el equipo en el que [!DNL Report Portal] está instalado, inicie el Administrador de IIS utilizando **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** o **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Haga clic con el botón derecho **[!UICONTROL Default Web Site]** y seleccione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Cuando se [!DNL Virtual Directory Wizard] abra, haga clic en **[!UICONTROL Next]**.

1. Complete los siguientes pasos para definir el directorio virtual raíz para [!DNL Report Portal]:

   1. Cuando se le pida un alias, escriba el nombre del [!DNL Report Portal]y haga clic en **[!UICONTROL Next]**. Por ejemplo, si desea utilizar &quot;Portal&quot; como nombre de su [!DNL Report Portal], asigne el alias &quot;Portal&quot; al directorio virtual. Haga clic en **[!UICONTROL Next]** cuando termine.

   1. Cuando se le solicite la ruta física, busque y seleccione el *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** directorio y, a continuación, haga clic en **[!UICONTROL Next]**.

      Ejemplo: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Cuando se le pida permiso, compruebe que las siguientes opciones están activadas:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Click **[!UICONTROL Next]**, then click **[!UICONTROL Finish]**. El directorio virtual que ha creado aparece en el sitio Web predeterminado, como se muestra en el siguiente ejemplo.
   ![](assets/RptPort_scrn_VirDirManual.png)

1. Haga clic con el botón derecho en el directorio virtual que acaba de crear y seleccione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Utilice el [!DNL Virtual Directory] asistente para crear un alias para cada uno de los directorios físicos siguientes. Al hacer esto, se crea un directorio virtual con el nombre adecuado para cada uno de estos recursos físicos.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cree este alias. . . </th> 
   <th colname="col2" class="entry"> Para este recurso físico . . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Núcleo </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imágenes </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> <p>Ubicación física del directorio en el que el servidor <span class="keyword"></span> de informes guarda el resultado de los conjuntos de informes. La carpeta de salida se puede ubicar en cualquier lugar, se le puede dar un nombre y contiene una subcarpeta para cada conjunto de informes. </p> <p>Debe ser el mismo directorio que especifique en el parámetro Raíz de salida en el archivo <span class="filepath"> Report.cfg</span> para un conjunto de informes. Para obtener más información, consulte <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Configuración de los archivos</a>Report.cfg. </p> <p>La ubicación predeterminada es \<i>PortalName</i>\PortalFiles\Output. </p> <p>Ejemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>El archivo <i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profile.xml</span> , que debe moverse al directorio de salida que especifique para este alias. </p> <p>Es fundamental que el atributo <span class="wintitle"> Path</span> esté configurado correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Cuando termine, compruebe que IIS muestre seis nuevos directorios virtuales. Asegúrese de que la estructura de directorios tiene una carpeta principal (con el mismo nombre que el portal) y cinco subcarpetas, como se muestra a continuación.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Cuando termine, vaya a [Editar el archivo](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) de configuración de sesión para continuar con el proceso de instalación.

