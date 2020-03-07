---
description: Pasos para implementar el tablero en IIS.
solution: Analytics
title: Implementación del tablero
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Implementación del tablero{#deploying-the-dashboard}

Pasos para implementar el tablero en IIS.

1. Cree una carpeta de instalación para instalar el tablero, como [!DNL c:\inetpub\wwwroot\dashboard].
1. Cree el grupo de aplicaciones del tablero en IIS.
1. Abra la consola del Administrador de IIS.
1. Vaya a **[!UICONTROL Application Pools]**.
1. Seleccione **[!UICONTROL Add Application Pool…]**en el **[!UICONTROL Actions]** menú a la derecha.
1. En el **[!UICONTROL Add Application Pool]** formulario, utilice el tablero del nombre y seleccione .NET Framework v.4.0.xxxxx como versión de .NET Framework.
1. Deje otros campos como predeterminados y haga clic en **[!UICONTROL OK]** para crear el grupo de aplicaciones.
1. Implementar la aplicación de tablero.
1. Abra la consola del Administrador de IIS.
1. Expanda el **[!UICONTROL Default Web Site]**, debería ver la carpeta que creó en c:\inetpub\wwwroot\dashboard by default.
1. Haga clic con el botón derecho en la carpeta y seleccione **[!UICONTROL Convert to Application]**.
1. Seleccione el **[!UICONTROL Application Pool]**creado en el paso 2 (por ejemplo, &quot;Tablero&quot;).
1. En **[!UICONTROL Sites]**, haga clic con el botón secundario en el sitio Web en el que desee implementar (por ejemplo, &quot;Sitio Web predeterminado&quot;).
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Busque y seleccione el archivo de implementación de tablero proporcionado por Adobe.
1. Haga clic **[!UICONTROL Next]** dos veces para acceder a la pantalla Introducir información de la aplicación.
1. Desde esta pantalla, puede elegir personalizar la implementación del tablero.
1. Para **[!UICONTROL Application Path]**, introduzca el nombre de la carpeta previamente seleccionada.
1. En **[!UICONTROL Disable Automatic Database Upgrade]**, introduzca `False`, ya que se trata de una nueva instalación.
1. Personalice la cadena de conexión, si es necesario. Por ejemplo:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Haga clic en **[!UICONTROL Next]** e IIS comenzará a instalar la aplicación.
1. Una vez completada la instalación, no debería ver errores en el registro de instalación.
