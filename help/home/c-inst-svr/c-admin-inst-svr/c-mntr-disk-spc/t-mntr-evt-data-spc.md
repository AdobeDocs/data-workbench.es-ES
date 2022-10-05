---
description: Información sobre la monitorización del espacio de datos del evento y el cambio del directorio de registro para los datos del sensor.
title: Monitorización del espacio de datos de evento
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Monitorización del espacio de datos de evento{#monitoring-event-data-space}

{{eol}}

Información sobre la monitorización del espacio de datos del evento y el cambio del directorio de registro para los datos del sensor.

**Frecuencia recomendada:** Cada 5-10 minutos

[!DNL Insight Server] almacena un archivo de registro por [!DNL Sensor] por día en la unidad de procesamiento de datos o en la unidad de servidor de archivos, según la configuración. El tamaño de los archivos de registro y la cantidad de espacio de almacenamiento de datos necesario para ellos dependen de muchas variables, incluido, por ejemplo, el número de sitios web que se registran y el número de solicitudes que los servidores web reciben por segundo.

Una instalación típica de [!DNL Insight Server] (o [!DNL Insight Server] cluster) es capaz de almacenar múltiples terabytes de datos, suponiendo que la implementación utilice el hardware recomendado por el Adobe para el [!DNL Insight Server] máquinas.

Normalmente, todos los datos de registro permanecen presentes en la variable [!DNL Insight Server] máquina. Si es necesario disponer de más espacio de almacenamiento de datos en el equipo, puede mover todos los archivos de registro del día más actual a otro equipo o medio de almacenamiento de datos (unidad zip, cinta, etc.). Para mover los datos no es necesario que detenga [!DNL Insight Server], y no afecta a la funcionalidad disponible en ninguna [!DNL Insights] que puedan conectarse a [!DNL Insight Server] y trabajar con datos continuos. Siempre que no procese ni vuelva a procesar un conjunto de datos de análisis, conservará el acceso a todos los datos anteriores y los nuevos datos seguirán estando disponibles en [!DNL Insight]. Si procesa o vuelve a procesar un conjunto de datos de análisis, no podrá acceder a los datos hasta que se complete el procesamiento.

De forma predeterminada, los datos de evento generados por [!DNL Sensor] y transmitido a [!DNL Insight Server] se almacena en la variable [!DNL Logs] dentro de la carpeta [!DNL Insight Server] directorio de instalación. El archivo de configuración de comunicaciones, [!DNL Communications.cfg], especifica la ubicación de los archivos de registro de datos de evento que lee [!DNL Insight Server].

**Para cambiar el directorio de registro de [!DNL Sensor] data**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Communications.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL Communications.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Communications.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En el [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL component]** para ver su contenido.
1. En el [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL Servers]** para ver su contenido. Pueden aparecer varios tipos de servidores: Servidores de archivos, Servidores de registro, Servidores de entrada, Servidores de estado, Servidores de envío o Servidores de replicación.
1. Busque LoggingServer, que es donde [!DNL Sensor] escribe sus archivos de registro para que los procese [!DNL Insight Server]y haga clic en su número para ver el menú .

   ![Información sobre los pasos](assets/cfg_communications_examplevalues_logging.png)

   El directorio de registro predeterminado es [!DNL Logs] dentro de la carpeta [!DNL Insight Server] directorio de instalación.

1. Edite el parámetro Directorio de registros para reflejar la ubicación deseada de los archivos de registro.

   >[!NOTE]
   >
   >No modifique ningún otro parámetro para LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Es posible que se incluyan varios FileServers en la lista del nodo Servers , por lo que es posible que tenga que ver el contenido de muchos de ellos (haciendo clic en sus números en la lista [!DNL Servers] ) para encontrar el servidor con una ruta local de registros\ que se va a modificar.

1. Edite la ruta local para reflejar la ubicación deseada del [!DNL .vsl] archivos.

   >[!NOTE]
   >
   >No modifique ningún otro parámetro para FileServer.

   Aunque la ubicación de los archivos de registro se ha cambiado en la variable [!DNL Communications.cfg] , puede asignar estos archivos al directorio Logs del [!DNL Server Files Manager] especificando /Logs/ como el URI para FileServer.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
