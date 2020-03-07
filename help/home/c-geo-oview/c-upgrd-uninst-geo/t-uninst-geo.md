---
description: Pasos para desinstalar el área de trabajo de datosGeografía.
solution: Analytics
title: Desinstalación de Área geográfica de Área de trabajo de datos
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Desinstalación de Área geográfica de Área de trabajo de datos{#uninstalling-data-workbench-geography}

Pasos para desinstalar el área de trabajo de datosGeografía.

>[!NOTE]
>
>Si el perfil con el que está utilizando el área de trabajo de datos [!DNL Geography] se está ejecutando en un clúster de servidores del área de trabajo de datos, desinstale el [!DNL Geography] perfil del servidor maestro del área de trabajo de datos del clúster.

1. Siga los pasos siguientes para actualizar el [!DNL profile.cfg] archivo de cada perfil con el que estaba utilizando el área de trabajo de datos [!DNL Geography].

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

   1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la [!DNL profile.cfg] ventana.

   1. En la [!DNL profile.cfg] ventana, elimine la entrada del [!DNL Geography] perfil del [!DNL Directories] vector.

   1. Si ha estado utilizando un servicio de datos, elimine la entrada [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] del perfil del [!DNL Directories] vector.

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL profile.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimine la carpeta Geografía de la carpeta Perfiles del directorio de instalación del servidor del área de trabajo de datos.
1. Si ha estado utilizando un servicio de datos, elimine la carpeta IP Geo-Intelligence o la carpeta IP Geo-location de la carpeta Profiles del directorio de instalación del servidor del área de trabajo de datos.
1. Elimine la carpeta Geography de la carpeta Lookups del directorio de instalación del servidor del área de trabajo de datos.
1. Si ha estado utilizando un servicio de datos, elimine la carpeta IP Geo-Intelligence o la carpeta IP Geo-location de la carpeta Lookups del directorio de instalación del servidor del área de trabajo de datos.
1. Si ha creado nuevas imágenes de terreno, elimine el [!DNL Terrain Images.cfg] archivo de la carpeta Componentes del directorio de instalación del servidor del área de trabajo de datos.
