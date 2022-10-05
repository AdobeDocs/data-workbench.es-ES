---
description: Debe supervisar regularmente los archivos de registro de eventos para rastrear los mensajes de evento del sistema de Insight Server, que se registran en la <yyyymmdd>Los archivos -event.txt se encuentran de forma predeterminada en la carpeta Eventos del directorio de instalación de Insight Server.
title: Supervisión de eventos administrativos (Insight Server)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# Supervisión de los eventos administrativos{#monitoring-administrative-events}

{{eol}}

Debe supervisar regularmente los archivos de registro de eventos para rastrear los mensajes de evento del sistema de Insight Server, que se registran en la `<YYYYMMDD>-event.txt` archivos ubicados de forma predeterminada en la carpeta Eventos dentro del directorio de instalación de Insight Server.

**Frecuencia recomendada:** Cada 5-10 minutos

Puede monitorizar estos eventos usando la variable [!DNL Server Files Manager] en [!DNL Insight], su herramienta de administración automatizada, la variable [!DNL *-event.txt] o el Visor de eventos de Windows.

>[!NOTE]
>
>Los registros de eventos administrativos están completamente separados del registro de eventos de Windows, pero contienen algunos de los mismos eventos. Los registros de eventos administrativos solo contienen información sobre [!DNL Insight Server] eventos.

**Para ver los archivos events.txt a través de la variable[!DNL Server Files Manager]**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de un activo [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Events]** para ver su contenido.
1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* junto al archivo deseado y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación junto al nombre del archivo en la [!DNL Temp] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación de la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El archivo de evento aparece en una nueva ventana del Bloc de notas de Microsoft Windows.

   ![Información sobre los pasos](assets/vis_FileManager_eventfile.png)

   La variable [!DNL Server.log] en el [!DNL Trace] dentro de la carpeta [!DNL Insight Server] directorio de instalación contiene información de registro más detallada.

**Para ver eventos a través del Visor de eventos de Windows**

* Haga clic **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Para cambiar el directorio Registro de eventos administrativos**

El archivo de configuración Registros de eventos administrativos , [!DNL Administrative Events Log.cfg], especifica el directorio al que se genera el registro de eventos.

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Administrative Event Logs.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL Administrative Event Logs.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Administrative Event Logs.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. En el [!DNL Administrative Event Logs.cfg] ventana, haga clic en **[!UICONTROL component]** para ver su contenido. La ruta predeterminada es la [!DNL Events] dentro de la carpeta [!DNL Insight Server] directorio de instalación.

   ![](assets/cfg_adminevents_examplevalues.png)

1. En el parámetro Path , escriba el nombre del directorio en el que desea generar los datos de registro de eventos.
1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
