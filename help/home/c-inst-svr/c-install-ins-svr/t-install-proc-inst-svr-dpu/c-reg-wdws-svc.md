---
description: Procedimiento para iniciar Insight Server y registrarlo simultáneamente como un servicio de Microsoft Windows.
solution: Insight
title: Registro de Insight Server como un servicio de Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Registro de Insight Server como un servicio de Windows{#registering-insight-server-as-a-windows-service}

Procedimiento para iniciar Insight Server y registrarlo simultáneamente como un servicio de Microsoft Windows.

>[!NOTE]
>
>Cuando se inicia [!DNL Insight Server] por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar el certificado digital. Para completar el proceso de registro correctamente, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

**Para iniciarlo[!DNL Insight Server]y registrarlo como un servicio de Windows**

1. Abra un símbolo del sistema y vaya al subdirectorio bin de la carpeta donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\bin]

1. En el símbolo del sistema, ejecute el siguiente comando para iniciar [!DNL Insight Server] y registrarlo simultáneamente para ejecutarlo como un servicio en Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Para confirmar que [!DNL Insight Server] se está ejecutando correctamente, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En la lista de servicios, busque la entrada para **[!DNL Adobe Insight Server]** y confirme que su estado es Iniciado y que su tipo de inicio es Automático.
   1. Cierre el panel de control Servicios.

1. Para comprobar si [!DNL Insight Server] se han producido errores durante el inicio, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo de la [!DNL Event Viewer] ventana, seleccione el **[!UICONTROL Application]** registro.
   1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la [!DNL Source] columna.
   1. Si encuentra un error de &quot;Adobe&quot;, haga doble clic en el error para mostrar la [!DNL Event Properties] ventana. Esta ventana proporciona información detallada sobre el error.

1. Cuando termine de examinar el [!DNL Applications] registro, cierre el Visor de eventos.

Ha completado la instalación de [!DNL Insight Server]. [!DNL Insight Server] está diseñado para ejecutarse de forma continua. Si reinicia el equipo, [!DNL Insight Server] se reinicia automáticamente. Si necesita iniciar y detener [!DNL Insight Server] manualmente, puede hacerlo mediante el panel de control Servicios de Windows. Como se describe en la sección siguiente, puede configurar [!DNL Insight Server] el servicio de forma opcional para que se reinicie automáticamente periódicamente.

## Configuración del servicio para reiniciar automáticamente {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] está diseñado para continuar ejecutándose sin interrupciones. Normalmente se detiene o se inicia solo cuando se realizan tareas poco frecuentes, como actualizaciones de software o cambios de certificado, o en caso de que se produzcan ciertos errores del sistema. No es necesario detener o reiniciar el [!DNL Insight Server] servicio durante el funcionamiento normal del sistema; sin embargo, puede configurar el servicio para que se reinicie periódicamente (diariamente, semanalmente o mensualmente) para, por ejemplo, borrar los mensajes del evento.

**Para configurar el[!DNL Insight Server]servicio para que se reinicie automáticamente**

1. Vaya a la [!DNL Components] carpeta del directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Components]

1. Utilice un editor de texto como Bloc de notas para crear un nuevo archivo denominado [!DNL ScheduledRestart.cfg].
1. Escriba el siguiente texto en el [!DNL ScheduledRestart.cfg] archivo:

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Para este valor... </th> 
      <th colname="col2" class="entry"> Especifique </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>DD Mes, AAAA HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Hora en la que desea reiniciar <span class="keyword"> Insight Server </span> por primera vez. </p> <p>Ejemplo: 13 de agosto de 2013, 22:30:00 EST </p> <p> <p>Nota:  Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en la hora del sistema si no se especifica. Si desea implementar Daylight Saving Time o una política de cambio de reloj similar, debe guardar el archivo <span class="filepath"> .dst </span> que contiene las reglas correspondientes en el Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> . Para obtener una lista de abreviaciones de zona horaria admitidas e información sobre la implementación de Horario de verano de verano, consulte <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de zona horaria </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frecuencia</i> </td> 
      <td colname="col2"> <p>Uno de los siguientes valores: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">mes </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">semana </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">día </li> 
       </ul> </p> <p>Para indicar la frecuencia con la que desea que <span class="keyword"> Insight Server </span> se reinicie después de la hora inicial especificada en Hora de inicio. </p> <p>Por ejemplo, si desea que <span class="keyword"> Insight Server </span> se reinicie una vez a la semana, establezca este valor en "semana". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   Compruebe que el [!DNL ScheduledRestart.cfg] archivo se encuentra en la [!DNL Components] carpeta del directorio donde instaló [!DNL Insight Server].
