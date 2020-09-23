---
description: Para detectar los errores del sensor lo antes posible y repararlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros del Evento.
solution: Analytics
title: Supervisión de los eventos administrativos
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# Supervisión de los eventos administrativos{#monitoring-administrative-events}

Para detectar los errores del sensor lo antes posible y repararlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros del Evento.

**Frecuencia recomendada:** Al menos por hora

Puede supervisar estos eventos con el archivo de Windows Evento Viewer o Unix Syslog y los [!DNL *.sensor-log] archivos ubicados de forma predeterminada en la [!DNL Logs] carpeta del directorio de [!DNL Sensor] instalación. Estos archivos indican la presencia de errores durante la recopilación de datos, especialmente si un usuario [!DNL Sensor] no puede conectarse a los datos de cola de destinatarios [!DNL data workbench server] y inicios.

## Monitoreo de Eventos en Windows {#section-7c0443a356af4381bf22259654f5cd17}

El sensor registra errores en el registro de aplicaciones del visor de Evento de Windows con una fuente de &quot;Adobe&quot;.

Los mensajes se registran como &quot;Información&quot;, &quot;Advertencia&quot; o &quot;Error&quot; según su gravedad.

**Para abrir el visor** de Evento de Windows:

* Haga clic en **Inicio > Panel de control de Campaign > Herramientas administrativas > Visor** de Evento.

## Monitoreo de Eventos en Unix {#section-5de3947891fb47ac88b7c855e545d54a}

El sensor registra errores en el [!DNL syslog] demonio.

El daemon syslog escribe mensajes de error en los archivos de registro basados en las reglas especificadas en el archivo syslog.conf. Los errores se registran con los indicadores &quot;LOG_DAEMON&quot; y &quot;LOG_NOTICE&quot; o &quot;LOG_ERR&quot;, según la gravedad.

**Para abrir el syslog Unix**

El syslog Unix generalmente se encuentra en [!DNL /var/adm/messages] o [!DNL /var/log/messages].

Vaya a la ubicación adecuada y abra el syslog.

## Explicación de los formatos de los mensajes {#section-a0899add30fd4b2da58a23b9e3324693}

Todos los mensajes del sensor contienen la cadena &quot;Sensor&quot; y están numerados para reflejar la importancia del mensaje que se muestra.

| Número de mensaje | Significado del mensaje | Cadena de mensajes |
|---|---|---|
| 1xxx | Información | Nº de información del sensor |
| 2xxx | Advertencia | Nº de advertencia del sensor |
| 3xxx | Error de configuración | Nº de error de sensor |
| 4xxx | Error operativo | Nº de error de sensor |
| 5xxx | Error interno | Nº de error de sensor |

>[!NOTE]
>
>Las advertencias (2xxx) no están en uso actualmente. Estos números están reservados para uso futuro.

La herramienta de administración de red se puede configurar para que supervise sus mensajes cada 5-10 minutos en busca de errores con la fuente &quot;Sensor&quot; y para que avise al personal apropiado sobre los problemas que puedan requerir la intervención. Puede elegir supervisar el sistema solo para determinados tipos de mensajes de Evento, como la cadena &quot;Error de sensor&quot;. De forma alternativa, puede aplicar diferentes reglas a los eventos con las cadenas &quot;Sensor Info&quot;, &quot;Sensor Warning&quot; y &quot;Sensor Error&quot;.

## Identificación de mensajes importantes {#section-5a20f5dc18ca4012931d194db855e54e}

Dentro de los registros de evento, debe prestar especial atención a cualquier mensaje relacionado con el tamaño de la cola y enviarlo inmediatamente.

Por ejemplo, mensajes como &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; necesitan atención.

## Respuesta a los mensajes de Evento del sensor {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tablas que describen eventos de sensor y acciones sugeridas para las plataformas de servidor web admitidas.

**Todas las plataformas**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mensaje de evento </th> 
   <th colname="col2" class="entry"> Acción sugerida </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Información del sensor 1010: Sensor inicializado. </td> 
   <td colname="col2"> No se requiere ninguna acción. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información de sensor 1011: Sensor terminado. Número de clics totales en la cola </td> 
   <td colname="col2"> No se requiere ninguna acción. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información de sensor 1012: La cola de Adobe está #% llena </td> 
   <td colname="col2"> Este mensaje se registra cada vez que la utilización de la cola de discos supera un umbral del 10 %. Si este porcentaje sigue creciendo, se debe realizar una acción antes de que la cola esté llena y se pierdan los datos. El problema más probable es que el sensor haya dejado de comunicarse con el servidor de Insight. Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información de sensor 1013: Se cambió la configuración del sensor </td> 
   <td colname="col2"> No se requiere ninguna acción. El sensor detectó un cambio en uno de sus archivos de configuración y volverá a cargarse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información de sensor 1014: Generador de números aleatorios con problemas de inicialización </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información de sensor 1016: Se cargó el nombre del archivo de configuración </td> 
   <td colname="col2"> No se requiere ninguna acción. El sensor cargó correctamente el archivo de configuración enumerado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información de sensor 1017: Se cargó el nombre del archivo del experimento </td> 
   <td colname="col2"> No se requiere ninguna acción. El sensor cargó correctamente el archivo de experimento que aparece en la lista. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 3016: No se puede cargar el archivo de configuración /mypath/myfile </td> 
   <td colname="col2"> Confirme que el archivo de configuración del sensor especificado en la configuración del servidor web existe y que tiene los permisos necesarios para ser leído por el proceso del servidor web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: No se puede cargar el archivo de configuración del experimento controlado /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Confirme que el archivo de experimento controlado especificado en txlogd.conf existe y que el proceso txlogd tiene los permisos necesarios para leer el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 3018: No se pueden analizar las listas del filtro de contenido. Comprobar archivo de configuración txlogd </td> 
   <td colname="col2"> Compruebe la sintaxis de las entradas ContentFilterInclude y ContentFilterExclude en txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 3023: No se pudo crear el bloqueo (g_lockThrottle) </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 3024: No se pudo crear el bloqueo (g_lockConfigCheck) </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 4014: No se pudo abrir la cola de discos. </td> 
   <td colname="col2"> Compruebe el nombre del archivo QueueFile en txlogd.conf y, si se cree que es correcto, póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 4020: No es un archivo de cola </td> 
   <td colname="col2"> Compruebe el nombre del archivo QueueFile en txlogd.conf y, si se cree que es correcto, póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 4021: La cola está llena </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 4022: No se puede asignar el bloque de memoria de longitud &lt;x&gt; en el desplazamiento &lt;y&gt; </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5012: No se pudo crear el mutex. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5013: No se pudo adquirir mutex. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5030: Error de horquilla de desove. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5031: setsid falló. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5032: Error de horquilla de desove. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5033: error de chdir. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5034: Señal recibida </td> 
   <td colname="col2"> Es probable que el programa haya terminado con una señal externa. Si no se puede determinar el origen de esta señal, póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5035: Salida llamada desde fuera principal </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5036: txlogd ya está en ejecución </td> 
   <td colname="col2"> Ya se está ejecutando otra instancia del demonio txlogd. Detenga primero la otra instancia si desea ejecutar una nueva. </td> 
  </tr> 
 </tbody> 
</table>

**Servidor HTTP Apache/IBM**

| Mensaje de evento | Acción sugerida |
|---|---|
| Error de sensor 3015: Falta la directiva VisualSciencesConfig en httpd.conf. | Se trata de un error de configuración. La directiva VisualSciencesConfig debe estar en httpd.conf con un parámetro que sea la ubicación de txlogd.conf. |
| Error de sensor 3019: no se llamó a vys-cookie antes de vys-log. Comuníquese con la asistencia técnica. | Póngase en contacto con Adobe ClientCare. |
| Error de sensor 3025: La subsolicitud se remite a sí misma | Póngase en contacto con Adobe ClientCare. |

**Servidor AOL**

| Mensaje de evento | Acción sugerida |
|---|---|
| Error de sensor 3015: Falta la sección ns/server/[server]/module/[module] en el archivo de configuración de AOLServer. | Se trata de un error de configuración. Corregir como se indica en el error. |
| Error de sensor 3019: no se llamó a vys-cookie antes de vys-log. Comuníquese con la asistencia técnica. Póngase en contacto con Adobe ClientCare. | Comuníquese con la asistencia técnica. Póngase en contacto con Adobe ClientCare. |
| Error de sensor 3020: Falta VisualSciencesConfig como primera entrada en la sección de [sección] del archivo de configuración de AOLServer. | Se trata de un error de configuración. Corregir como se indica en el error. |
| Error de sensor 3021: A VisualSciencesConfig le falta un valor en la sección de [sección] del archivo de configuración de AOLServer. | Se trata de un error de configuración. Corregir como se indica en el error. |

**Servidores Web de sistemas iPlanet y Java**

| Mensaje de evento | Acción sugerida |
|---|---|
| Error de sensor 3011: Se requiere la directiva Init. Como Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Se trata de un error de configuración. Falta la directiva iPlanet init. |
| Error de sensor 3015: config-file no está especificado en la directiva iPlanet Init | Se trata de un error de configuración. La ruta de acceso al archivo de configuración no se proporcionó en la directiva iPlanet Init. |
| Error de sensor 3019: no se llamó a vys-cookie antes de vys-log. Compruebe el archivo de configuración | vys-cookie debe especificarse como la primera directiva NameTrans para cada servidor virtual de software. |

