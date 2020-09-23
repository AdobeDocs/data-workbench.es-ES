---
description: Instrucciones para desinstalar Insight Server, Transform o Repeater.
solution: Analytics
title: Desinstalación del software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---


# Desinstalación del software{#uninstalling-your-software}

Instrucciones para desinstalar Insight Server, Transform o Repeater.

## Desinstalación del Adobe de Insight Server {#section-7d7befe672854df79bb6c28ec02f6670}

1. Cancele el registro del servicio [!DNL Insight Server] Windows.

   1. Abra un símbolo del sistema y vaya al subdirectorio bin de la carpeta donde instaló [!DNL Insight Server].

      Ejemplo: [!DNL C:\Adobe\Server\bin]

   1. En el símbolo del sistema, ejecute el siguiente comando para detenerlo y anular el registro como un servicio en Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimine el directorio [!DNL Insight Server] de instalación.

## Desinstalación de Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Siga los pasos siguientes para actualizar el [!DNL profile.cfg] archivo de cada perfil con el que estaba utilizando [!DNL Transform].

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

   1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparecerá la [!DNL profile.cfg] ventana.

   1. En la [!DNL profile.cfg] ventana, elimine la entrada de [!DNL Transform] perfil del vector Directorios.

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL profile.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimine la [!DNL Transform] carpeta de la [!DNL Profiles] carpeta del directorio [!DNL Insight Server] de instalación.

## Desinstalación del repetidor {#section-2f94141d956749d88f549dbea26e5272}

1. Cancele el registro del servicio [!DNL Repeater] Windows.

   1. Abra un símbolo del sistema y vaya al subdirectorio bin de la carpeta donde instaló [!DNL Repeater].

      Ejemplo: [!DNL D:\Adobe\Repeater\bin]

   1. En el símbolo del sistema, ejecute el siguiente comando para detenerlo y anular el registro como un servicio en Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimine el directorio [!DNL Repeater] de instalación.

