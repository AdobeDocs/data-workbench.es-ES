---
description: Debe supervisar regularmente los archivos de registro de evento para rastrear los mensajes de evento del sistema de Insight Server, que se registran en los archivos <YYYMDD>-evento.txt ubicados de forma predeterminada en la carpeta Eventos dentro del directorio de instalación de Insight Server.
solution: Analytics
title: Supervisión de los eventos administrativos
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---


# Supervisión de los eventos administrativos{#monitoring-administrative-events}

Debe supervisar regularmente los archivos de registro de evento para rastrear los mensajes de evento del sistema de Insight Server, que se registran en los `<YYYYMMDD>-event.txt` archivos ubicados de forma predeterminada en la carpeta Eventos dentro del directorio de instalación de Insight Server.

**Frecuencia recomendada:** Cada 5-10 minutos

Puede supervisar estos eventos mediante la [!DNL Server Files Manager] función [!DNL Insight], la herramienta de administración automatizada, los [!DNL *-event.txt] archivos o el visor de Evento de Windows.

>[!NOTE]
>
>Los registros de Evento administrativo están completamente separados del registro de Eventos de Windows, pero contienen algunos de los mismos eventos. Los registros de Evento administrativo contienen información solamente sobre [!DNL Insight Server] eventos.

**Para vista de archivos eventos.txt mediante la variable[!DNL Server Files Manager]**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de un elemento activo [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Events]** para vista de su contenido.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor junto al archivo deseado y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación junto al nombre del archivo en la [!DNL Temp] columna.
1. Haga clic con el botón secundario en la marca de verificación de la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El archivo evento aparece en una nueva ventana del Bloc de notas de Microsoft Windows.

   ![Información sobre los pasos](assets/vis_FileManager_eventfile.png)

   El [!DNL Server.log] archivo de la [!DNL Trace] carpeta del directorio de [!DNL Insight Server] instalación contiene información de registro más detallada.

**Vista de Eventos mediante el visor de Windows Evento**

* Haga clic **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Para cambiar el directorio Registro de Eventos administrativos**

El archivo de configuración Registros de Evento administrativo [!DNL Administrative Events Log.cfg], especifica el directorio al que se genera el registro de eventos.

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para vista de su contenido. El [!DNL Administrative Event Logs.cfg] archivo se encuentra dentro de este directorio.

1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL Administrative Event Logs.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Administrative Event Logs.cfg].

1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. En la [!DNL Administrative Event Logs.cfg] ventana, haga clic en **[!UICONTROL component]** para vista de su contenido. La ruta de acceso predeterminada es la [!DNL Events] carpeta dentro del directorio [!DNL Insight Server] de instalación.

   ![](assets/cfg_adminevents_examplevalues.png)

1. En el parámetro Path, escriba el nombre del directorio en el que desea obtener los datos de registro de eventos.
1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

