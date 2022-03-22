---
description: Para detectar los errores del sensor lo antes posible y repararlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.
title: Monitorización de eventos administrativos (Sensor)
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 0%

---

# Supervisión de los eventos administrativos{#monitoring-administrative-events}

Para detectar los errores del sensor lo antes posible y repararlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.

**Frecuencia recomendada:** Al menos por hora

Puede controlar estos eventos utilizando el Visor de eventos de Windows o el archivo Syslog de Unix y el [!DNL *.sensor-log] los archivos ubicados de forma predeterminada en la variable [!DNL Logs] dentro de la carpeta [!DNL Sensor] directorio de instalación. Estos archivos indican la presencia de errores durante la recopilación de datos, especialmente si [!DNL Sensor] no se puede conectar al destino [!DNL data workbench server] y comienza a poner en cola los datos.

## Supervisión de eventos en Windows {#section-7c0443a356af4381bf22259654f5cd17}

El sensor registra errores en el registro de aplicaciones del Visor de eventos de Windows con una fuente de &quot;Adobe&quot;.

Los mensajes se registran como &quot;Información&quot;, &quot;Advertencia&quot; o &quot;Error&quot; según su gravedad.

**Para abrir el Visor de eventos de Windows**:

* Haga clic en **Inicio > Panel de control de Campaign > Herramientas administrativas > Visor de eventos**.

## Supervisión de eventos en Unix {#section-5de3947891fb47ac88b7c855e545d54a}

El sensor registra los errores en el [!DNL syslog] daemon.

El demonio syslog escribe mensajes de error en los archivos de registro en función de las reglas especificadas en el archivo syslog.conf. Los errores se registran con los indicadores &quot;LOG_DAEMON&quot; y &quot;LOG_NOTICE&quot; o &quot;LOG_ERR&quot;, según la gravedad.

**Para abrir el syslog Unix**

El syslog de Unix generalmente se encuentra en [!DNL /var/adm/messages] o [!DNL /var/log/messages].

Vaya a la ubicación adecuada y abra el syslog.

## Explicación de los formatos de mensaje {#section-a0899add30fd4b2da58a23b9e3324693}

Todos los mensajes del sensor contienen la cadena &quot;Sensor&quot; y están numerados para reflejar la importancia del mensaje que se está mostrando.

| Número de mensaje | Significado del mensaje | Cadena de mensajes |
|---|---|---|
| 1xxx | Información | N.º de información del sensor |
| 2xxx | Advertencia | Nº de advertencia del sensor |
| 3xxx | Error de configuración | Número de error del sensor |
| 4xxx | Error operativo | Número de error del sensor |
| 5xxx | Error interno | Número de error del sensor |

>[!NOTE]
>
>Las advertencias (2xxx) no están actualmente en uso. Estos números están reservados para uso futuro.

Su herramienta de gestión de red se puede configurar para supervisar sus mensajes cada 5-10 minutos en busca de errores con el origen &quot;Sensor&quot; y alertar al personal apropiado sobre los problemas que pueden requerir intervención. Puede elegir monitorizar el sistema solo para determinados tipos de mensajes de Evento, como la cadena &quot;Error de sensor&quot;. Como alternativa, puede aplicar diferentes reglas a los eventos prefijados con las cadenas &quot;Información del sensor&quot;, &quot;Advertencia del sensor&quot; y &quot;Error del sensor&quot;.

## Identificación de mensajes importantes {#section-5a20f5dc18ca4012931d194db855e54e}

Dentro de los registros de eventos, debe prestar especial atención a los mensajes relacionados con el tamaño de la cola y enviarlos inmediatamente.

Por ejemplo, mensajes como &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; necesitan atención.

## Respuesta a los mensajes de eventos del sensor {#section-0004c4a169dc4a8882d9bd87dd326ad4}

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
   <td colname="col1"> Información del sensor 1011: Sensor terminado. Total de clics en cola ## </td> 
   <td colname="col2"> No se requiere ninguna acción. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información del sensor 1012: La cola de disco de Adobe está #% llena </td> 
   <td colname="col2"> Este mensaje se registra cada vez que la utilización de la cola de disco supera un umbral del 10%. Si este porcentaje sigue creciendo, se deben realizar acciones antes de que la cola esté llena y se pierdan datos. El problema más probable es que el sensor haya dejado de comunicarse con el servidor de Insight. Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información del sensor 1013: Se ha modificado la configuración del sensor </td> 
   <td colname="col2"> No se requiere ninguna acción. El sensor detectó un cambio en uno de sus archivos de configuración y volverá a cargarse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información del sensor 1014: Problema al generar generador de números aleatorios </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información del sensor 1016: Se cargó el nombre del archivo de configuración </td> 
   <td colname="col2"> No se requiere ninguna acción. El sensor cargó correctamente el archivo de configuración enumerado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Información del sensor 1017: Nombre del archivo del experimento cargado </td> 
   <td colname="col2"> No se requiere ninguna acción. El sensor cargó correctamente el archivo de experimento enumerado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 3016: No se puede cargar el archivo de configuración /mypath/myfile </td> 
   <td colname="col2"> Confirme que el archivo de configuración del sensor especificado en la configuración del servidor web existe y que tiene los permisos necesarios para que los lea el proceso del servidor web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: No se puede cargar el archivo de configuración del experimento controlado /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Confirme que el archivo de experimento controlado especificado en txlogd.conf existe y que el proceso txlogd tiene los permisos necesarios para leer el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 3018: No se pueden analizar las listas de filtros de contenido. Comprobar archivo de configuración txlogd </td> 
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
   <td colname="col1"> Error de sensor 4022: No se puede asignar el bloque de memoria de longitud &lt;x&gt; desplazamiento &lt;y&gt; </td> 
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
   <td colname="col1"> Error de sensor 5030: Error de ramificación. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5031: setsid falló. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5032: Error de ramificación. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5033: error de chdir. </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5034: Señal recibida </td> 
   <td colname="col2"> Es probable que el programa haya terminado con una señal externa. Si no se puede determinar el origen de esta señal, póngase en contacto con el Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5035: Salida llamada desde fuera principal </td> 
   <td colname="col2"> Póngase en contacto con Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error de sensor 5036: txlogd ya se está ejecutando </td> 
   <td colname="col2"> Ya se está ejecutando otra instancia del demonio txlogd. Detenga primero la otra instancia si desea ejecutar una nueva. </td> 
  </tr> 
 </tbody> 
</table>

**Servidor HTTP Apache/IBM**

| Mensaje de evento | Acción sugerida |
|---|---|
| Error de sensor 3015: Falta la directiva VisualSciencesConfig en httpd.conf. | Este es un error de configuración. La directiva VisualSciencesConfig debe estar en httpd.conf con un parámetro que sea la ubicación de txlogd.conf. |
| Error de sensor 3019: no se llamó a vys-cookie antes de vys-log. Póngase en contacto con el servicio de asistencia técnica. | Póngase en contacto con Adobe ClientCare. |
| Error de sensor 3025: La subsolicitud vuelve a apuntarse a sí misma | Póngase en contacto con Adobe ClientCare. |

**Servidor AOL**

| Mensaje de evento | Acción sugerida |
|---|---|
| Error de sensor 3015: ns/server/[server]/module/[módulo] falta en el archivo de configuración de AOLServer. | Este es un error de configuración. Corrección como se indica en el error. |
| Error de sensor 3019: no se llamó a vys-cookie antes de vys-log. Póngase en contacto con el servicio de asistencia técnica. Póngase en contacto con Adobe ClientCare. | Póngase en contacto con el servicio de asistencia técnica. Póngase en contacto con Adobe ClientCare. |
| Error del sensor 3020: Falta VisualSciencesConfig como primera entrada en [sección] en el archivo de configuración de AOLServer. | Este es un error de configuración. Corrección como se indica en el error. |
| Error de sensor 3021: A VisualSciencesConfig le falta un valor en [sección] en el archivo de configuración de AOLServer. | Este es un error de configuración. Corrección como se indica en el error. |

**Servidores web de sistemas iPlanet y Java**

| Mensaje de evento | Acción sugerida |
|---|---|
| Error de sensor 3011: Directiva Init obligatoria. Como Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Este es un error de configuración. Falta la directiva iPlanet init. |
| Error de sensor 3015: El archivo de configuración no está especificado en la directiva iPlanet Init | Este es un error de configuración. La ruta al archivo de configuración no se suministró en la directiva iPlanet Init. |
| Error de sensor 3019: no se llamó a vys-cookie antes de vys-log. Compruebe el archivo de configuración | vys-cookie debe especificarse como la primera directiva NameTrans para cada servidor virtual de software. |
