---
description: La funcionalidad abierta le permite abrir elementos como documentos o URI en aplicaciones externas como un editor de texto o un explorador web.
title: Configuración de la funcionalidad abierta
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# Configuración de la funcionalidad abierta{#configure-open-functionality}

{{eol}}

La funcionalidad abierta le permite abrir elementos como documentos o URI en aplicaciones externas como un editor de texto o un explorador web.

La funcionalidad abierta solo está configurada actualmente en la variable [!DNL Site] y solo para URI de apertura. Esta sección proporciona información sobre cómo configurar la funcionalidad de URI abierto para [!DNL Site]. Para obtener información sobre la configuración de la funcionalidad Abrir para otra aplicación o para abrir otros elementos, póngase en contacto con los servicios de consultoría de Adobe.

En [!DNL Site], puede hacer clic con el botón derecho en un URI de una superposición o tabla de página para mostrar el URI en la aplicación para la que se le aplicó formato. Por ejemplo, desde una visualización de tabla URI, puede hacer clic en un URI para mostrar una página web en un explorador web.

Para abrir un URI desde una visualización, primero debe editar la variable [!DNL Open URI.cfg] para la dimensión URI para identificar la ubicación y las convenciones de nomenclatura que utiliza la Data Workbench para abrir el URI. Para ver un URI en su formato nativo (como HTML), la Data Workbench debe tener acceso a la ubicación a la que se hace referencia y a la aplicación necesaria para abrir ese elemento. Por ejemplo, para ver una página web, la Data Workbench tendría que tener acceso a Internet, así como tener instalado un explorador web.

**Para editar Open URI.vw**

1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. En la carpeta URI, haga clic con el botón derecho en la marca de verificación situada junto a la [!DNL Open URI.vw]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]** si el archivo es un [!DNL .cfg] archivo o **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** si es un [!DNL .vw] archivo.
1. Haga clic en **[!UICONTROL Command]**, luego **[!UICONTROL Parameters]** para ver el contenido del archivo.
1. Modifique el [!DNL Site] y el parámetro Template como sea necesario:

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
   <td colname="col2"> <p>La ubicación de los URI que desea abrir. </p> <p>Ejemplo: mysite.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Plantilla </p> </td>
   <td colname="col2"> <p>Los parámetros que la Data Workbench debe utilizar para localizar y abrir los URI. </p> <p>Ejemplo: <span class="filepath"> https://%Site%%URI%</span> </p> <p>La plantilla predeterminada que se muestra en el ejemplo indica a la Data Workbench que abra un explorador web, busque la ubicación definida en la variable <span class="wintitle"> Sitio</span> , busque el elemento de dimensión URI que está intentando abrir. </p> </td>
  </tr>
 </tbody>
</table>

1. Guarde el archivo.
1. Para que este cambio esté disponible para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación de [!DNL .vw] en el [!DNL User] y haga clic en **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
