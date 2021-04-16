---
description: Pasos para desinstalar Data WorkbenchGeography.
title: Desinstalación de la geografía de Data Workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Desinstalación de la geografía de Data Workbench{#uninstalling-data-workbench-geography}

Pasos para desinstalar Data WorkbenchGeography.

>[!NOTE]
>
>Si el perfil con el que utiliza Data Workbench [!DNL Geography] se está ejecutando en un clúster de servidores de Data Workbench, desinstale el perfil [!DNL Geography] del servidor maestro de Data Workbench en el clúster.

1. Siga los siguientes pasos para actualizar el archivo [!DNL profile.cfg] para cada perfil con el que utilizaba Data Workbench [!DNL Geography].

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece la ventana [!DNL profile.cfg].

   1. En la ventana [!DNL profile.cfg], elimine la entrada de perfil [!DNL Geography] del vector [!DNL Directories].

   1. Si ha estado utilizando un servicio de datos, elimine la entrada de perfil [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] del vector [!DNL Directories].

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimine la carpeta Geografía de la carpeta Perfiles del directorio de instalación del servidor de Data Workbench.
1. Si ha estado utilizando un servicio de datos, elimine la carpeta IP Geo-Intelligence o Geo-location de IP de la carpeta Profiles del directorio de instalación del servidor de Data Workbench.
1. Elimine la carpeta Geografía de la carpeta Búsquedas del directorio de instalación del servidor de Data Workbench.
1. Si ha estado utilizando un servicio de datos, elimine la carpeta IP Geo-Intelligence o Geo-location de la carpeta Lookups del directorio de instalación del servidor de Data Workbench.
1. Si ha creado imágenes de nuevo terreno, elimine el archivo [!DNL Terrain Images.cfg] de la carpeta Componentes en el directorio de instalación del servidor de Data Workbench.
