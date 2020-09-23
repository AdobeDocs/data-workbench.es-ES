---
description: Información sobre la supervisión del espacio de datos de evento y el cambio del directorio de registro de datos de Sensor.
solution: Analytics
title: Monitorización del espacio de datos de evento
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# Monitorización del espacio de datos de evento{#monitoring-event-data-space}

Información sobre la supervisión del espacio de datos de evento y el cambio del directorio de registro de datos de Sensor.

**Frecuencia recomendada:** Cada 5-10 minutos

[!DNL Insight Server] almacena un archivo de registro por [!DNL Sensor] día en la unidad de procesamiento de datos o en la unidad de servidor de archivos, según la configuración. El tamaño de los archivos de registro y la cantidad de espacio de almacenamiento de datos que necesitan dependen de muchas variables, como por ejemplo, el número de sitios Web que se registran y el número de solicitudes que los servidores Web reciben por segundo.

Una instalación típica de [!DNL Insight Server] (o un [!DNL Insight Server] clúster) puede almacenar varios terabytes de datos, siempre que la implementación utilice el hardware recomendado por Adobe para los [!DNL Insight Server] equipos.

Normalmente, todos los datos de registro permanecen presentes en el [!DNL Insight Server] equipo. Si es necesario para que haya más espacio en el almacenamiento de datos disponible en el equipo, puede mover todos los archivos de registro del día más actual, excepto los más recientes, a otro equipo o medio de almacenamiento de datos (unidad zip, cinta, etc.). Para mover los datos no es necesario detenerlos [!DNL Insight Server]y no afecta a la funcionalidad disponible en ninguna [!DNL Insights] que esté conectada a [!DNL Insight Server] y trabaje con datos continuos. Siempre que no procese ni vuelva a procesar un conjunto de datos de análisis, conservará el acceso a todos los datos anteriores y los nuevos datos seguirán estando disponibles en [!DNL Insight]. Si procesa o vuelve a procesar un conjunto de datos de análisis, no podrá acceder a los datos hasta que se complete el procesamiento.

De forma predeterminada, los datos de evento producidos [!DNL Sensor] y transmitidos a [!DNL Insight Server] se almacenan en la [!DNL Logs] carpeta dentro del directorio de [!DNL Insight Server] instalación. El archivo de configuración Comunicaciones [!DNL Communications.cfg]especifica la ubicación de los archivos de registro de datos de evento leídos por [!DNL Insight Server].

**Para cambiar el directorio de registro de[!DNL Sensor]datos**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para vista de su contenido. El [!DNL Communications.cfg] archivo se encuentra dentro de este directorio.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL Communications.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Communications.cfg].
1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En la [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL component]** para vista de su contenido.
1. En la [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL Servers]** para vista de su contenido. Pueden aparecer varios tipos de servidores: Servidores de archivos, Servidores de registro, Servidores de entrada, Servidores de estado, Servidores de envío o Servidores de replicación.
1. Busque LoggingServer, que es donde [!DNL Sensor] escribe los archivos de registro que va a procesar [!DNL Insight Server], y haga clic en su número para vista del menú.

   ![Información sobre los pasos](assets/cfg_communications_examplevalues_logging.png)

   El directorio de registro predeterminado es la [!DNL Logs] carpeta dentro del directorio [!DNL Insight Server] de instalación.

1. Edite el parámetro Directorio de registros para reflejar la ubicación deseada de los archivos de registro.

   >[!NOTE]
   >
   >No modifique ningún otro parámetro para LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Es posible que se incluyan varios FileServers en el nodo Servidores, por lo que es posible que tenga que realizar una vista del contenido de muchos de ellos (haciendo clic en sus números en la [!DNL Servers] lista) para encontrar el servidor con una Ruta local de registros\ que se va a modificar.

1. Edite la ruta local para reflejar la ubicación deseada de los [!DNL .vsl] archivos.

   >[!NOTE]
   >
   >No modifique ningún otro parámetro para FileServer.

   Aunque se ha cambiado la ubicación de los archivos de registro en el [!DNL Communications.cfg] archivo, puede asignar estos archivos al directorio Registros del [!DNL Server Files Manager] especificando /Logs/ como URI para el servidorDeArchivos.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

