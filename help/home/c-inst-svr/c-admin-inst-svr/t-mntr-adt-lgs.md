---
description: Los archivos de registro de auditoría rastrean todos los intentos de conexión y desconexiones desde Insight Server, cada uno de los cuales se registra en los archivos <YYYMDD>-access.txt ubicados de manera predeterminada en la carpeta Audit dentro del directorio de instalación de Insight Server.
solution: Analytics
title: Supervisión de registros de auditoría
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# Supervisión de registros de auditoría{#monitoring-audit-logs}

Los archivos de registro de auditoría rastrean todos los intentos de conexión y desconexiones desde Insight Server, cada uno de los cuales se registra en los `<YYYYMMDD>-access.txt` archivos ubicados de manera predeterminada en la carpeta Audit dentro del directorio de instalación de Insight Server.

**Frecuencia recomendada:** Diario o según sea necesario para solucionar problemas

Los registros de auditoría pueden ser muy útiles para solucionar problemas relacionados con la conexión a [!DNL Insight Server]. Puede supervisar estos registros con la herramienta de administración automatizada o viendo los [!DNL access.txt] archivos directamente.

**Para vista de archivos access.txt mediante la variable[!DNL Server Files Manager]**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de un elemento activo [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Audit]** para vista de su contenido.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor junto al archivo deseado y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación junto al nombre del archivo en la [!DNL Temp] columna.
1. Haga clic con el botón secundario en la nueva marca de verificación de la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El registro de auditoría aparece en una nueva ventana del Bloc de notas de Microsoft Windows.

   ![Información sobre los pasos](assets/cfg_accesscontrol_accessFile.png)

