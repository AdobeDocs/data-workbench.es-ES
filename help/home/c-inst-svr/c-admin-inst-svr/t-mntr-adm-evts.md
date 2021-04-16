---
description: Debe supervisar regularmente los archivos de registro de eventos para rastrear los mensajes de evento del sistema de Insight Server, que se registran en los archivos <YYYMDD>-event.txt ubicados de forma predeterminada en la carpeta Eventos dentro del directorio de instalación de Insight Server.
title: Supervisión de los eventos administrativos
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Supervisión de los eventos administrativos{#monitoring-administrative-events}

Debe supervisar regularmente los archivos de registro de eventos para rastrear los mensajes de evento del sistema de Insight Server, que se registran en los archivos `<YYYYMMDD>-event.txt` ubicados de forma predeterminada en la carpeta Eventos dentro del directorio de instalación de Insight Server.

**Frecuencia recomendada:** cada 5-10 minutos

Puede monitorizar estos eventos utilizando [!DNL Server Files Manager] en [!DNL Insight], la herramienta de administración automatizada, los archivos [!DNL *-event.txt] o el Visor de eventos de Windows.

>[!NOTE]
>
>Los registros de eventos administrativos están completamente separados del registro de eventos de Windows, pero contienen algunos de los mismos eventos. Los registros de eventos administrativos solo contienen información sobre eventos [!DNL Insight Server] .

**Para ver los archivos events.txt a través de la variable[!DNL Server Files Manager]**

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de un [!DNL Insight Server] activo y haga clic en **[!UICONTROL Server Files]**.
1. En [!DNL Server Files Manager], haga clic en **[!UICONTROL Events]** para ver su contenido.
1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* junto al archivo deseado y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación junto al nombre del archivo en la columna [!DNL Temp].
1. Haga clic con el botón derecho en la marca de verificación de la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El archivo de evento aparece en una nueva ventana del Bloc de notas de Microsoft Windows.

   ![Información sobre los pasos](assets/vis_FileManager_eventfile.png)

   El archivo [!DNL Server.log] de la carpeta [!DNL Trace] dentro del directorio de instalación [!DNL Insight Server] contiene información de registro más detallada.

**Para ver eventos a través del Visor de eventos de Windows**

* Haga clic **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Para cambiar el directorio Registro de eventos administrativos**

El archivo de configuración Registros de eventos administrativos, [!DNL Administrative Events Log.cfg], especifica el directorio al que se genera el registro de eventos.

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. El archivo [!DNL Administrative Event Logs.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* para [!DNL Administrative Event Logs.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la columna [!DNL Temp] de [!DNL Administrative Event Logs.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada en la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. En la ventana [!DNL Administrative Event Logs.cfg], haga clic en **[!UICONTROL component]** para ver su contenido. La ruta de acceso predeterminada es la carpeta [!DNL Events] dentro del directorio de instalación [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. En el parámetro Path , escriba el nombre del directorio en el que desea generar los datos de registro de eventos.
1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL Temp] y seleccione **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
