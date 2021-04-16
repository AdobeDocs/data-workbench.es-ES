---
description: La interfaz del Monitor de servidor es útil para solucionar problemas o simplemente para rastrear los parámetros de rendimiento de los equipos de servidor de Data Workbench y los equipos de informes que son clientes de los equipos de servidor de Data Workbench.
title: Interfaz de monitor de servidor
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Interfaz de monitor de servidor{#server-monitor-interface}

La interfaz del Monitor de servidor es útil para solucionar problemas o simplemente para rastrear los parámetros de rendimiento de los equipos de servidor de Data Workbench y los equipos de informes que son clientes de los equipos de servidor de Data Workbench.

La interfaz del Monitor de servidor muestra un punto verde o un punto rojo en la parte superior, a la izquierda del nombre del equipo. Un punto verde indica que el equipo funciona sin problemas. Un punto rojo indica que se han producido uno o más errores en el equipo.

La parte inferior de la interfaz Monitor de servidor muestra el estado de procesamiento de cada uno de los perfiles disponibles, así como detalles de rendimiento sobre el equipo.

Para obtener más información sobre [!DNL Data Workbench servers], consulte la *Guía de instalación y administración de productos de servidor*. Para obtener más información sobre [!DNL Report], consulte la *Guía del informe de Data Workbench*.

**Para abrir la interfaz del Monitor de servidor**

* En el Administrador de servidores, haga clic con el botón derecho en el nodo del servidor de Data Workbench o del equipo [!DNL Report]. t

Haga clic en **[!UICONTROL Server Monitor]** para ver los detalles de un servidor o haga clic en **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** para ver los detalles de un clúster de servidores relacionados.

![](assets/vis_ServerMonitor.png)

La interfaz [!DNL Server Monitor]se actualiza automáticamente cada 10 segundos.

En la tabla siguiente se enumeran las tareas que se pueden completar mediante la interfaz [!DNL Server Monitor] .

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
   <td colname="col2"> <p>Vea el vector Perfil <i>Perfil</i> Nombre. En el ejemplo anterior, vería el vector Profile ExampleProfile para ver que el perfil ExampleProfile se procesa en un servidor y su procesamiento de registros se ha completado al 100%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar cuánto tarda el equipo en responder a las solicitudes </p> </td> 
   <td colname="col2"> <p>Consulte el campo de latencia de la encuesta . Si este valor es bueno a 1000 ms, póngase en contacto con el servicio de soporte técnico de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver una estimación del tiempo que puede llevar completar la transformación o consulta </p> </td> 
   <td colname="col2"> <p>Ver el campo de tiempo de barrido (hh:mm:ss), que está presente solo durante la transformación o consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar el número actual de conexiones de red al equipo </p> </td> 
   <td colname="col2"> <p>Vea la última línea de la información del <span class="wintitle"> Monitor de servidor</span> del equipo. En el ejemplo anterior, verá que hay 2 conexiones de red procedentes de un equipo. </p> </td> 
  </tr> 
 </tbody> 
</table>
