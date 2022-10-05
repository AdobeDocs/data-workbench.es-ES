---
description: La interfaz del Monitor de servidor es útil para solucionar problemas o simplemente para rastrear los parámetros de rendimiento de los equipos de servidor de Data Workbench y los equipos de informes que son clientes de los equipos de servidor de Data Workbench.
title: Interfaz de monitor de servidor
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%

---

# Interfaz de monitor de servidor{#server-monitor-interface}

{{eol}}

La interfaz del Monitor de servidor es útil para solucionar problemas o simplemente para rastrear los parámetros de rendimiento de los equipos de servidor de Data Workbench y los equipos de informes que son clientes de los equipos de servidor de Data Workbench.

La interfaz del Monitor de servidor muestra un punto verde o un punto rojo en la parte superior, a la izquierda del nombre del equipo. Un punto verde indica que el equipo funciona sin problemas. Un punto rojo indica que se han producido uno o más errores en el equipo.

La parte inferior de la interfaz Monitor de servidor muestra el estado de procesamiento de cada uno de los perfiles disponibles, así como detalles de rendimiento sobre el equipo.

Para obtener más información, consulte [!DNL Data Workbench servers], consulte la *Guía de instalación y administración de productos para servidor*. Para obtener más información, consulte [!DNL Report], consulte la *Guía de informes de Data Workbench*.

**Para abrir la interfaz del Monitor de servidor**

* En el Administrador de servidores, haga clic con el botón derecho en el nodo del servidor de Data Workbench o [!DNL Report] equipo. t

Haga clic en **[!UICONTROL Server Monitor]** para ver detalles sobre un servidor o haga clic en **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** para ver detalles sobre un clúster de servidores relacionados.

![](assets/vis_ServerMonitor.png)

La variable [!DNL Server Monitor]la interfaz de se actualiza automáticamente cada 10 segundos.

La tabla siguiente enumera las tareas que se pueden completar utilizando la variable [!DNL Server Monitor] interfaz.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para realizar esta tarea... </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para comprobar el estado de procesamiento de registro de un perfil </p> </td> 
   <td colname="col2"> <p>Ver el perfil <i>Perfil</i> Nombre el vector. En el ejemplo anterior, vería el vector Profile ExampleProfile para ver que el perfil ExampleProfile se procesa en un servidor y su procesamiento de registros se ha completado al 100%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar cuánto tarda el equipo en responder a las solicitudes </p> </td> 
   <td colname="col2"> <p>Consulte el campo de latencia de la encuesta . Si este valor es bueno a 1000 ms, póngase en contacto con el servicio de soporte técnico de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver una estimación del tiempo que puede llevar completar la transformación o consulta </p> </td> 
   <td colname="col2"> <p>Ver la hora de barrido (hh:mm:s), que está presente solo durante la transformación o consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar el número actual de conexiones de red al equipo </p> </td> 
   <td colname="col2"> <p>Ver la última línea del <span class="wintitle"> Monitor de servidor</span> información. En el ejemplo anterior, verá que hay 2 conexiones de red procedentes de un equipo. </p> </td> 
  </tr> 
 </tbody> 
</table>
