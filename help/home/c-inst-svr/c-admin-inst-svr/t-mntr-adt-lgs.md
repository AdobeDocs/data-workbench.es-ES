---
description: Los archivos de registro de auditoría rastrean todos los intentos de conexión y desconexión desde Insight Server, cada uno de los cuales se registra en los archivos <YYYMDD>-access.txt ubicados de forma predeterminada en la carpeta Audit dentro del directorio de instalación de Insight Server.
title: Supervisión de registros de auditoría
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Supervisión de registros de auditoría{#monitoring-audit-logs}

Los archivos de registro de auditoría rastrean todos los intentos de conexión y desconexión desde Insight Server, cada uno de los cuales se registra en los archivos `<YYYYMMDD>-access.txt` ubicados de forma predeterminada en la carpeta Audit dentro del directorio de instalación de Insight Server.

**Frecuencia recomendada:** diaria o según sea necesario para la resolución de problemas

Los registros de auditoría pueden ser muy útiles para solucionar problemas de conexión con [!DNL Insight Server]. Puede monitorizar estos registros con la herramienta de administración automatizada o viendo los archivos [!DNL access.txt] directamente.

**Para ver los archivos access.txt a través de la variable[!DNL Server Files Manager]**

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de un [!DNL Insight Server] activo y haga clic en **[!UICONTROL Server Files]**.
1. En [!DNL Server Files Manager], haga clic en **[!UICONTROL Audit]** para ver su contenido.
1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* junto al archivo deseado y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación junto al nombre del archivo en la columna [!DNL Temp].
1. Haga clic con el botón derecho en la nueva marca de verificación de la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El registro de auditoría aparece en una nueva ventana del bloc de notas de Microsoft Windows.

   ![Información sobre los pasos](assets/cfg_accesscontrol_accessFile.png)
