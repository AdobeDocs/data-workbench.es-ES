---
description: La función Abrir le permite abrir elementos como documentos o URI en aplicaciones externas como un editor de texto o un explorador Web.
solution: Analytics
title: Configurar la funcionalidad abierta
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar la funcionalidad abierta{#configure-open-functionality}

La función Abrir le permite abrir elementos como documentos o URI en aplicaciones externas como un editor de texto o un explorador Web.

Actualmente, la funcionalidad de apertura solo se configura en la [!DNL Site] aplicación y solo para la apertura de URI. Esta sección proporciona información sobre cómo configurar la funcionalidad de URI abierta para [!DNL Site]. Para obtener información sobre la configuración de la funcionalidad Abrir para otra aplicación o para abrir otros elementos, póngase en contacto con los servicios de consultoría de Adobe.

En [!DNL Site], puede hacer clic con el botón derecho en un URI de una superposición de página o tabla para mostrar el URI en la aplicación para la que se le aplicó formato. Por ejemplo, desde una visualización de tabla URI, puede hacer clic en un URI para mostrar una página web en un explorador web.

Para abrir un URI desde una visualización, primero debe editar el [!DNL Open URI.cfg] archivo para la dimensión URI a fin de identificar las convenciones de ubicación y nombre que utiliza el área de trabajo de datos para abrir el URI. Para ver un URI en su formato nativo (como HTML), el área de trabajo de datos debe tener acceso a la ubicación a la que se hace referencia y a la aplicación necesaria para abrir ese elemento. Por ejemplo, para ver una página web, el Área de trabajo de datos necesita acceder a Internet y tener un explorador web instalado.

**Para editar Open URI.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. En la carpeta URI, haga clic con el botón derecho en la marca de verificación situada junto al [!DNL Open URI.vw]archivo y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]** si el archivo es un [!DNL .cfg] archivo o **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** si es un [!DNL .vw] archivo.
1. Haga clic en **[!UICONTROL Command]**, luego **[!UICONTROL Parameters]** para ver el contenido del archivo.
1. Modifique el parámetro [!DNL Site] y el parámetro Template según sea necesario:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parámetro... </th> 
   <th colname="col2" class="entry"> Proporcione esta información... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sitio </p> </td> 
   <td colname="col2"> <p>Ubicación de los URI que desea abrir. </p> <p>Ejemplo: mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plantilla </p> </td> 
   <td colname="col2"> <p>Parámetros que Área de trabajo de datos debe utilizar para localizar y abrir los URI. </p> <p>Ejemplo: <span class="filepath"> http://%Site%%URI%</span> </p> <p>La plantilla predeterminada que se muestra en el ejemplo indica a Área de trabajo de datos que abra un explorador Web, busque la ubicación definida en el parámetro <span class="wintitle"> Sitio</span> y, a continuación, busque el elemento de dimensión URI que intenta abrir. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Guarde el archivo.
1. Para que este cambio esté disponible para todos los usuarios del perfil de trabajo, haga clic con el botón secundario en la marca de verificación del [!DNL .vw] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

