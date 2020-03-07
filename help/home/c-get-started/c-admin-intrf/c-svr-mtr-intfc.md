---
description: La interfaz del Monitor de servidor resulta útil para solucionar problemas o simplemente para rastrear los parámetros de rendimiento de los equipos del servidor del Área de trabajo de datos y los equipos de informes que son clientes de los equipos del servidor del Área de trabajo de datos.
solution: Analytics
title: Interfaz de monitor de servidor
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interfaz de monitor de servidor{#server-monitor-interface}

La interfaz del Monitor de servidor resulta útil para solucionar problemas o simplemente para rastrear los parámetros de rendimiento de los equipos del servidor del Área de trabajo de datos y los equipos de informes que son clientes de los equipos del servidor del Área de trabajo de datos.

La interfaz del Monitor de servidor muestra un punto verde o un punto rojo en la parte superior, a la izquierda del nombre del equipo. Un punto verde indica que el equipo funciona sin problemas. Un punto rojo indica que se han producido uno o más errores en el equipo.

La parte inferior de la interfaz del Monitor de servidor muestra el estado de procesamiento de cada uno de los perfiles disponibles, así como detalles de rendimiento sobre el equipo.

Para obtener más información sobre [!DNL Data Workbench servers], consulte la Guía *de instalación y administración de productos* de servidor. Para obtener más información sobre [!DNL Report], consulte la Guía *de informes* de Área de trabajo de datos.

**Para abrir la interfaz del Monitor de servidor**

* En el Administrador de servidores, haga clic con el botón secundario en el nodo del servidor o [!DNL Report] equipo de Área de trabajo de datos. t

Haga clic en **[!UICONTROL Server Monitor]** para ver los detalles de un servidor o haga clic en **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** para ver los detalles de un clúster de servidores relacionados.

![](assets/vis_ServerMonitor.png)

La [!DNL Server Monitor]interfaz se actualiza automáticamente cada 10 segundos.

En la tabla siguiente se enumeran las tareas que se pueden completar mediante la [!DNL Server Monitor] interfaz.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para realizar esta tarea... </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para comprobar el estado de procesamiento de registros de un perfil </p> </td> 
   <td colname="col2"> <p>Vea el vector Nombre <i>del perfil</i> . En el ejemplo anterior, se vería el vector Profile ExampleProfile para ver que el perfil ExampleProfile se procesa en un servidor y el procesamiento de registro se completa al 100 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar cuánto tarda el equipo en responder a las solicitudes </p> </td> 
   <td colname="col2"> <p>Vea el campo de latencia de la encuesta. Si este valor es bueno a más de 1000 ms, póngase en contacto con los servicios de asistencia de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver una estimación del tiempo que puede llevar completar la transformación o realizar consultas </p> </td> 
   <td colname="col2"> <p>Vea el campo de tiempo de barrido (hh:mm:ss), que solo está presente durante la transformación o consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar el número actual de conexiones de red al equipo </p> </td> 
   <td colname="col2"> <p>Vea la última línea de la información del <span class="wintitle"> Monitor</span> de servidor del equipo. En el ejemplo anterior, se observa que 2 conexiones de red provienen actualmente de un equipo. </p> </td> 
  </tr> 
 </tbody> 
</table>

