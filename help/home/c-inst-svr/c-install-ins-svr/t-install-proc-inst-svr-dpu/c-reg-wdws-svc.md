---
description: Procedimiento para iniciar Insight Server y registrarlo simultáneamente como un servicio de Microsoft Windows.
title: Registro de Insight Server como un servicio de Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---

# Registro de Insight Server como un servicio de Windows{#registering-insight-server-as-a-windows-service}

Procedimiento para iniciar Insight Server y registrarlo simultáneamente como un servicio de Microsoft Windows.

>[!NOTE]
>
>Cuando inicia [!DNL Insight Server] por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar el certificado digital. Para completar el proceso de registro correctamente, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

**Para iniciarlo  [!DNL Insight Server] y registrarlo como un servicio de Windows**

1. Abra un símbolo del sistema y vaya al subdirectorio bin en la carpeta donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\bin]

1. En el símbolo del sistema, ejecute el siguiente comando para iniciar [!DNL Insight Server] y registrelo simultáneamente para que se ejecute como un servicio en Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Para confirmar que [!DNL Insight Server] se está ejecutando correctamente, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En la lista de servicios, busque la entrada para **[!DNL Adobe Insight Server]** y confirme que su estado es Started y que su tipo de inicio es Automatic.
   1. Cierre el panel de control de Servicios.

1. Para comprobar si [!DNL Insight Server] experimentó algún error durante el inicio, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo de la ventana [!DNL Event Viewer] , seleccione el registro **[!UICONTROL Application]** .
   1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la columna [!DNL Source].
   1. Si encuentra un error de &quot;Adobe&quot;, haga doble clic en el error para mostrar la ventana [!DNL Event Properties]. Esta ventana proporciona información detallada sobre el error.

1. Cuando termine de examinar el registro [!DNL Applications], cierre el Visor de eventos.

Ha completado la instalación de [!DNL Insight Server]. [!DNL Insight Server] está diseñado para ejecutarse de forma continua. Si reinicia el equipo, [!DNL Insight Server] se reinicia automáticamente. Si necesita iniciar y detener [!DNL Insight Server] manualmente, puede hacerlo usando el panel de control de Servicios en Windows. Como se describe en la siguiente sección, opcionalmente puede configurar el servicio [!DNL Insight Server] para que se reinicie automáticamente periódicamente.

## Configuración del servicio para reiniciar automáticamente {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] está diseñado para continuar ejecutándose sin interrupciones. Normalmente, solo se detiene o se inicia cuando se realizan tareas poco frecuentes, como actualizaciones de software o cambios de certificado, o en caso de que se produzcan ciertos errores del sistema. No es necesario detener o reiniciar el servicio [!DNL Insight Server] durante el funcionamiento normal del sistema; sin embargo, puede configurar el servicio para que se reinicie periódicamente (diariamente, semanalmente o mensualmente) para, por ejemplo, borrar los mensajes de evento.

**Para configurar el  [!DNL Insight Server] servicio para que se reinicie automáticamente**

1. Vaya a la carpeta [!DNL Components] en el directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Components]

1. Utilice un editor de texto como el Bloc de notas para crear un nuevo archivo denominado [!DNL ScheduledRestart.cfg].
1. Introduzca el siguiente texto en el archivo [!DNL ScheduledRestart.cfg]:

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
      <td colname="col1"> <i>Mes DD, AAAA HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>El momento en el que desea que <span class="keyword"> Insight Server </span> se reinicie por primera vez. </p> <p>Ejemplo: 13 de agosto de 2013 22:30:00 EST </p> <p> <p>Nota:  Debe especificar una zona horaria. Si no se especifica nada, la zona horaria no pasará de forma predeterminada a la hora del sistema. Si desea implementar Daylight Saving Time o una política similar de cambio de reloj, debe guardar el archivo <span class="filepath"> .dst </span> que contiene las reglas adecuadas en el equipo Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>. Para obtener una lista de abreviaciones de zona horaria admitidas e información sobre la implementación del cambio de horario de verano, consulte <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de zona horaria </a>. </p> </p> </td> 
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

1. Guarde el archivo [!DNL ScheduledRestart.cfg].

   Compruebe que el archivo [!DNL ScheduledRestart.cfg] se encuentra en la carpeta [!DNL Components] del directorio donde instaló [!DNL Insight Server].
