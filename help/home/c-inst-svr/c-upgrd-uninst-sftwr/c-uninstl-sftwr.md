---
description: Instrucciones para desinstalar Insight Server, Transform o Repeater.
title: Desinstalación del software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Desinstalación del software{#uninstalling-your-software}

{{eol}}

Instrucciones para desinstalar Insight Server, Transform o Repeater.

## Desinstalación del Adobe de Insight Server {#section-7d7befe672854df79bb6c28ec02f6670}

1. Desregistrar el [!DNL Insight Server] Servicio de Windows.

   1. Abra un símbolo del sistema y vaya al subdirectorio bin en la carpeta donde instaló [!DNL Insight Server].

      Ejemplo: [!DNL C:\Adobe\Server\bin]

   1. En el símbolo del sistema, ejecute el siguiente comando para detenerlo y anular el registro como un servicio en Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimine el [!DNL Insight Server] directorio de instalación.

## Desinstalación de Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Siga estos pasos para actualizar el [!DNL profile.cfg] para cada perfil con el que estaba utilizando [!DNL Transform].

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La variable [!DNL profile.cfg] se abre.

   1. En el [!DNL profile.cfg] , elimine el [!DNL Transform] entrada de perfil desde el vector Directorios.

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimine el [!DNL Transform] de [!DNL Profiles] en su [!DNL Insight Server] directorio de instalación.

## Desinstalación del repetidor {#section-2f94141d956749d88f549dbea26e5272}

1. Desregistrar el [!DNL Repeater] Servicio de Windows.

   1. Abra un símbolo del sistema y vaya al subdirectorio bin en la carpeta donde instaló [!DNL Repeater].

      Ejemplo: [!DNL D:\Adobe\Repeater\bin]

   1. En el símbolo del sistema, ejecute el siguiente comando para detenerlo y anular el registro como un servicio en Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimine el [!DNL Repeater] directorio de instalación.
