---
description: Instrucciones para instalar el Perfil de supervisión del área de trabajo de datos.
solution: Analytics
title: Instalación del perfil de supervisión
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: 300b4fb872e9a48cb90297c29a2f93e0db60e7c2
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---


# Instalación del perfil de supervisión{#installing-the-monitoring-profile}

Instrucciones para instalar el Perfil de supervisión del área de trabajo de datos.

## Pasos de instalación {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configure una nueva instancia de Sensor como si se utilizara para la recopilación de datos de páginas Web etiquetadas. Asegúrese de que el archivo zig.gif se encuentra en la raíz del documento del servidor web Sensor. El sensor se puede ejecutar en el mismo host que los perfiles del monitor. (Esto no supone ningún problema si se utiliza un archivo de texto con este fin).

   >[!NOTE]
   >
   >Esta instancia de Sensor debe estar dedicada a recibir sólo tráfico de los Agentes de supervisión. Además, el sensor se puede configurar para que se ejecute en un puerto diferente si va a cambiar el propósito de un servidor web para esta colección.

1. En el [!DNL txlogd.conf] archivo hay la línea predeterminada:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Para la aplicación de Perfil de supervisión del área de trabajo de datos (o para cualquier implementación de página &quot;etiquetada&quot;), el tipo de imagen debe eliminarse para poder recopilarse mediante un archivo GIF. La línea actualizada es:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copie el [!DNL insight_monitor.zip/insight_monitor_agent] en una ubicación temporal.
1. Actualice [!DNL insight_monitor_agent.cfg] el archivo para su entorno. Siga los comentarios dentro del archivo de configuración:

   **El archivo de configuración de supervisión:**

   ![](assets/monitor_agent_cfg_sensor.png)

   Defina dónde está recopilando toda la información y proporcione la dirección URL. Debe ser un sensor dedicado y no debe recibir tráfico excepto por esta aplicación.

   ![](assets/monitor_agent_cfg_dump.png)

   Existen rutas que suponen que hay una e: disco. Es posible que desee cambiar esta ruta para su entorno.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   En algún momento, al ejecutar un perfil de transformación, el área de trabajo de datos puede no responder. Este valor le permite enviar una alerta si tres veces seguidas el proceso no responde. Esta es una manera de reducir las alertas de falsos positivos.

   ![](assets/monitor_agent_cfg_groups.png)

   Aquí es donde se configuran las dimensiones de grupo y entorno. Esto puede ser diferente de host a host.

   Aquí es ![](assets/monitor_agent_cfg_debug.png)donde puede ver exactamente lo que hace el agente de supervisión viendo los registros de errores en esta ruta.

   ![](assets/monitor_agent_cfg_tempdb.png)

   Se utiliza la base de datos temp internamente. Se puede alertar al alcanzar la capacidad. Esto es diferente al uso físico del disco.

1. Copie la carpeta *insight_monitor_agent* en cada host DPU y FSU que ejecute el servidor del área de trabajo de datos. La ubicación predeterminada, como se indica en el archivo de configuración, es [!DNL e:\insight_monitor_agent] pero puede cambiar esta ubicación.

1. Añada una tarea programada de Windows para invocar al agente cada 10 minutos (este período se asume en los cálculos de velocidad de procesamiento). El programa es [!DNL e:insight_monitor/insight_monitor_agent.exe]. El argumento es config-file e:\insight_monitor\insight_monitor.cfg. Inicio en e:\insight_monitor. El usuario que ejecuta la tarea debe tener permiso para leer y escribir [!DNL e:\insight_monitor] y leer el objeto OLE Win32 [!DNL root\CIMV2] (necesario para comprobar el modo de inicio del servicio del servidor del área de trabajo de datos y comprobar el porcentaje de espacio en los discos locales)

1. Confirme que el archivo VSL está empezando a crecer a medida que se acumulan los registros del monitor. Esto llevará algún tiempo, ya que el volumen de tráfico será extremadamente bajo en una instalación pequeña (cada 10 minutos el agente envía una sola visita para los datos específicos del host, más una visita por perfil de procesamiento).
1. Descomprima insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Actualice el nombre de host en [!DNL profile.cfg], [!DNL dataset\cluster.cfg]y el [!DNL dataset\segment export.cfg].

1. Actualice los archivos al directorio de perfiles del área de trabajo de datos.
1. Actualice el servidor de registro y la ruta de acceso [!DNL dataset\log processing.cfg] a la ubicación donde se acumulan los VSL del sensor.
1. [Opcionalmente] , haga lo mismo con los perfiles [!DNL Insight Profile Status] y [!DNL Insight Server Status]. Además, los perfiles de estado deben volver a procesarse por la noche con una ventana final de dos días. Añadir una tarea programada de Windows: El programa es [!DNL e:\insight_monitor\insight_reprocess.exe]. El argumento es [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Deje [!DNL start in] en blanco. Añada otra tarea programada para *&quot;estado del servidor de perspectiva&quot;*. *insight_reprocess.exe* requiere acceso de lectura y escritura a *log processing.cfg* para actualizar el tiempo de inicio.

1. Además, los perfiles de estado deben volver a procesarse por la noche con una ventana final de dos días. Añadir una tarea programada de Windows: El programa es *e:\insight_monitor\insight_reprocess.exe*. El argumento es - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Deje *inicio en* blanco. Añada otra tarea programada para [!DNL "insight server status"]. [!DNL insight_reprocess.exe] requiere acceso de lectura y escritura para [!DNL log processing.cfg] actualizar el tiempo de inicio. Confirme que cada perfil está leyendo el VSL del monitor a medida que se acumula. Nuevamente, esto tomará algún tiempo —probablemente horas— debido al volumen extremadamente bajo.

## Notas de instalación {#section-17722441ab0046fcbcb46b957d56230a}

* **Configuración del Perfil de supervisión en un entorno** de prueba con licencia. El paquete de entorno de prueba se incluye con la implementación del área de trabajo de datos, lo que le permite instalar y configurar la aplicación. Si realiza la instalación en un servidor FSU o DPU de producción, deberá configurar el servidor para que se ejecute en un puerto independiente.
* **Implementación de un nuevo sensor específicamente para el Perfil** de supervisión. Deberá instalar una nueva instancia de Sensor en el servidor que ejecuta el Perfil de supervisión. Esto se suma a la instancia de producción de Sensor. (No hay ningún cargo adicional para instalar Sensor en un servidor de producción o no de producción específico para el Perfil de supervisión).
* **Deshabilite el agente de monitor durante el mantenimiento** del área de trabajo de datos. Para evitar contaminar las métricas de tiempo activo y rendimiento, puede establecer el modo de inicio de servicio en manual para el servicio InsightServer (Omniture Insight Server). Un comando práctico de PowerShell es *set-service -name insightserver -startuptype manual*. Vuelva a configurarlo automáticamente después del mantenimiento: *set-service -name insightserver -startuptype automático*. Otra opción es desactivar temporalmente la tarea programada del agente de supervisión.
* **Los perfiles de estado necesitan una ventana** final para soltar los hosts y perfiles antiguos, así como las asignaciones de perfil de host anteriores. Sin embargo, si la cantidad de datos de evento es tan pequeña que el área de trabajo de datos no la almacenará en el búfer, es posible que tenga que ampliar bastante el tamaño de la ventana para poder procesarla.
* **El agente recopila el tiempo total y el más antiguo a partir del estado** detallado del área de trabajo de datos, que se informa en el tiempo de host local, suponiendo que las marcas de hora del registro de datos de evento están en UTC (como en los archivos de VSL). Si las marcas de hora de los datos de evento se encuentran en un huso horario que no es UTC, el valor a partir del tiempo se compensará en el perfil de estado de Perfil de perspectiva resultante. Si **todas** las marcas de hora de los datos de evento están en la misma zona horaria, puede agregar ese desplazamiento a *Insight Perfil Status\metrics\as of delay minutes.metric*.

* **Se introdujeron dos nuevas dimensiones para ayudar al cliente a agrupar sus servidores si están en diferentes estados**, como producción, ensayo, servidores de prueba y servidores en otros estados. Por ejemplo, si busca &quot;tiempo de actividad&quot;, verá los servidores únicamente en modo de producción. Como resultado, la dimensión Grupo es sólo otra forma de agrupar los servidores de forma arbitraria según sus necesidades. Por ejemplo, en el archivo de configuración de supervisión puede establecer el host que está administrando su departamento, como Operaciones, Desarrollo o Marketing.

