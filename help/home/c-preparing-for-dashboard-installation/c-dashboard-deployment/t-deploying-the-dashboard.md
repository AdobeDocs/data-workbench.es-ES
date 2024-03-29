---
description: Pasos para implementar el tablero en IIS.
title: Implementación del panel
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Implementación del panel{#deploying-the-dashboard}

{{eol}}

Pasos para implementar el tablero en IIS.

1. Cree una carpeta de instalación para instalar el tablero, como [!DNL c:\inetpub\wwwroot\dashboard].
1. Cree el grupo de aplicaciones del tablero en IIS.
1. Abra la Consola del Administrador de IIS.
1. Vaya a **[!UICONTROL Application Pools]**.
1. Seleccione **[!UICONTROL Add Application Pool…]**en el **[!UICONTROL Actions]** a la derecha.
1. En el **[!UICONTROL Add Application Pool]** use el tablero para el nombre y seleccione .NET Framework v.4.0.xxxxxx como versión de .NET Framework.
1. Deje otros campos como predeterminados y haga clic en **[!UICONTROL OK]** para crear el grupo de aplicaciones.
1. Implemente la aplicación de tablero.
1. Abra la Consola del Administrador de IIS.
1. Expanda el **[!UICONTROL Default Web Site]**, debería ver la carpeta que creó en c:\inetpub\wwwroot\dashboard by default.
1. Haga clic con el botón derecho en la carpeta y seleccione **[!UICONTROL Convert to Application]**.
1. Seleccione el **[!UICONTROL Application Pool]**creado en el paso 2 (por ejemplo, &quot;Tablero&quot;).
1. En **[!UICONTROL Sites]**, haga clic con el botón derecho en el sitio web en el que desee implementar (por ejemplo, &quot;Sitio web predeterminado&quot;).
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Busque y seleccione el archivo de implementación de tablero proporcionado por el Adobe.
1. Haga clic en **[!UICONTROL Next]** dos veces para continuar a la pantalla Introducir información de la aplicación.
1. Desde esta pantalla, puede elegir personalizar la implementación del panel.
1. Para **[!UICONTROL Application Path]**, introduzca el nombre de la carpeta seleccionada anteriormente.
1. En **[!UICONTROL Disable Automatic Database Upgrade]**, introduzca `False`, ya que se trata de una instalación nueva.
1. Personalice la cadena de conexión si es necesario. Por ejemplo:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Haga clic en **[!UICONTROL Next]** e IIS comenzarán a instalar la aplicación.
1. Una vez finalizada la instalación, no debería ver errores en el registro de instalación.
