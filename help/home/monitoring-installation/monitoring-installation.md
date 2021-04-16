---
description: Instrucciones para instalar el perfil de supervisión de Data Workbench.
title: Instalación del perfil de supervisión
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Instalación del perfil de supervisión{#installing-the-monitoring-profile}

Instrucciones para instalar el perfil de supervisión de Data Workbench.

## Pasos de instalación {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configure una nueva instancia de sensor como si se utilizara para la recopilación de datos de páginas web etiquetadas. Asegúrese de que el archivo zig.gif se encuentra en la raíz del documento del servidor web Sensor. El sensor se puede ejecutar en el mismo host que los perfiles del monitor. (Esto no supone un problema si se utiliza un archivo de texto con este fin).

   >[!NOTE]
   >
   >Esta instancia de sensor debe estar dedicada a recibir solo tráfico de los agentes de supervisión. Además, el sensor se puede configurar para que se ejecute en un puerto diferente si va a cambiar el propósito de un servidor web para esta colección.

1. En el archivo [!DNL txlogd.conf] hay la línea predeterminada:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Para la aplicación de perfil de monitorización de Data Workbench (o cualquier implementación de página &quot;etiquetada&quot;), el tipo de imagen debe eliminarse para recopilarse mediante un archivo GIF. La línea actualizada es:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copie el [!DNL insight_monitor.zip/insight_monitor_agent] en una ubicación temporal.
1. Actualice el archivo [!DNL insight_monitor_agent.cfg] para su entorno. Siga los comentarios dentro del archivo de configuración:

   **El archivo de configuración de supervisión:**

   ![](assets/monitor_agent_cfg_sensor.png)

   Defina dónde está recopilando toda la información y proporcione la dirección URL. Debe ser un sensor dedicado y no debe recibir tráfico excepto por esta aplicación.

   ![](assets/monitor_agent_cfg_dump.png)

   Hay rutas que suponen que hay una e: disco. Es posible que desee cambiar esta ruta para su entorno.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   En algún momento, al ejecutar un perfil de transformación, Data Workbench puede no responder. Este valor permite enviar una alerta si tres veces seguidas el proceso no responde. Esta es una forma de reducir las alertas de falsos positivos.

   ![](assets/monitor_agent_cfg_groups.png)

   Aquí es donde se configuran las dimensiones de entorno y grupo. Puede ser diferente de host a host.

   Esto es con ![](assets/monitor_agent_cfg_debug.png)aquí puede ver exactamente lo que está haciendo el agente de monitor al ver los registros de errores en esta ruta.

   ![](assets/monitor_agent_cfg_tempdb.png)

   Esto es para usar la base de datos temporal internamente. Se puede avisar al alcanzar la capacidad. Esto es diferente al uso físico del disco.

1. Copie la carpeta *insight_monitor_agent* a cada host DPU y FSU que ejecute el servidor de Data Workbench. La ubicación predeterminada que se indica en el archivo de configuración es [!DNL e:\insight_monitor_agent] pero puede cambiar esta ubicación.

1. Agregue una tarea programada de Windows para invocar al agente cada 10 minutos (este periodo se asume en los cálculos de tasa de procesamiento). El programa es [!DNL e:insight_monitor/insight_monitor_agent.exe]. El argumento es config-file e:\insight_monitor\insight_monitor.cfg. Comience en e:\insight_monitor. El usuario que ejecute la tarea debe tener permiso para leer/escribir [!DNL e:\insight_monitor] y leer el objeto OLE Win32 [!DNL root\CIMV2] (necesario para comprobar el modo de inicio del servicio del servidor de Data Workbench y comprobar el porcentaje de espacio en los discos locales)

1. Confirme que el archivo VSL está empezando a crecer a medida que se acumulan los registros del monitor. Esto tardará algún tiempo, ya que el volumen de tráfico será extremadamente bajo en una instalación pequeña (cada 10 minutos el agente envía solo una visita para los datos específicos del host, más una visita por perfil de procesamiento).
1. Descomprima insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Actualice el nombre de host en [!DNL profile.cfg], [!DNL dataset\cluster.cfg] y [!DNL dataset\segment export.cfg].

1. Actualice los archivos al directorio de perfiles de Data Workbench.
1. Actualice el servidor de registro y la ruta en [!DNL dataset\log processing.cfg] a la ubicación donde se acumulan los VSL del sensor.
1. [] Opcionalmente, haga lo mismo con los perfiles  [!DNL Insight Profile Status] y  [!DNL Insight Server Status]. Además, los perfiles de estado deben volver a procesarse todas las noches con una ventana final de dos días. Agregar una tarea programada de Windows: El programa es [!DNL e:\insight_monitor\insight_reprocess.exe]. El argumento es [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Deje [!DNL start in] en blanco. Agregue otra tarea programada para *&quot;insight server status&quot;*. *insight_reprocess.* requiere acceso de lectura y escritura al  *log processing.* cfgpara actualizar la hora de inicio.

1. Además, los perfiles de estado deben volver a procesarse todas las noches con una ventana final de dos días. Agregar una tarea programada de Windows: El programa es *e:\insight_monitor\insight_reprocess.exe*. El argumento es - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Deje *start in* en blanco. Agregue otra tarea programada para [!DNL "insight server status"]. [!DNL insight_reprocess.exe] requiere acceso de lectura y escritura a  [!DNL log processing.cfg] para actualizar la hora de inicio. Confirme que cada perfil está leyendo el monitor VSL a medida que se acumulan. Una vez más, esto llevará algún tiempo (probablemente horas) debido al volumen extremadamente bajo.

## Notas de instalación {#section-17722441ab0046fcbcb46b957d56230a}

* **Configuración del perfil de supervisión en un entorno** de prueba con licencia. El paquete de entorno de prueba se incluye en la implementación de Data Workbench, lo que le permite instalar y configurar la aplicación. Si realiza la instalación en un servidor FSU o DPU de producción, deberá configurar el servidor para que se ejecute en un puerto independiente.
* **Implementar un nuevo sensor específicamente para el perfil de supervisión**. Deberá instalar una nueva instancia de Sensor en el servidor que ejecute el Perfil de supervisión. Esto se suma a la instancia de producción del sensor. (No hay cargos adicionales para instalar Sensor en un servidor de producción o no de producción específicamente para el Perfil de supervisión).
* **Deshabilite el agente de monitor durante el mantenimiento** de Data Workbench. Para evitar contaminar las métricas de tiempo activo y rendimiento, puede establecer el modo de inicio del servicio en manual para el servicio InsightServer (Omniture Insight Server). Un comando práctico de PowerShell es *set-service -name insightserver -startuptype manual*. Vuelva a configurarlo automáticamente después del mantenimiento: *set-service -name insightserver -startuptype automático*. Otra opción es deshabilitar temporalmente la tarea programada del agente de monitor.
* **Los perfiles de estado necesitan una** ventana de seguimiento para soltar los hosts y perfiles antiguos, así como las asignaciones de perfil de host antiguas. Sin embargo, si la cantidad de datos de evento es tan pequeña que Data Workbench no la almacenará en búfer, es posible que tenga que ampliar bastante el tamaño de la ventana para que se procese.
* **El agente recopila el valor global y el valor más antiguo a partir del tiempo a partir del estado** detallado de Data Workbench, que se comunica en la hora del host local suponiendo que las marcas de hora del registro de datos del evento estén en UTC (como en los archivos VSL). Si las marcas de tiempo de los datos de evento se encuentran en una zona horaria que no es UTC, el valor a partir de la hora se verá desplazado en el perfil de estado del perfil de perspectiva resultante. Si **todas** las marcas de hora de los datos de evento están en la misma zona horaria, puede agregar ese desplazamiento a *Perfil de perspectiva Status\metrics\as of delay minutes.metric*.

* **Se introdujeron dos nuevas dimensiones para ayudar al cliente a agrupar sus servidores si están en distintos estados**, como producción, ensayo, servidores de prueba y servidores en otros estados. Por ejemplo, si busca &quot;tiempo de actividad&quot;, solo verá los servidores en modo de producción. Como resultado, la dimensión Grupo es solo otra forma de agrupar arbitrariamente los servidores según sus necesidades. Por ejemplo, en el archivo de Configuración de supervisión puede configurar el host que está administrando el departamento, como Operaciones, Desarrollo o Marketing.
