---
description: Instrucciones para configurar comunicaciones para Insight Server o Repeater.
solution: Insight
title: Configuración de ajustes de comunicaciones
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: 2ed16fa0d447426c4de863e502792bfb292765cc
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 5%

---


# Configuración de ajustes de comunicaciones{#communications-configuration-settings}

Instrucciones para configurar comunicaciones para Insight Server o Repeater.

Complete los parámetros del siguiente archivo:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Antes de modificar cualquier parámetro que no aparezca en esta tabla, póngase en contacto con Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Archivo control de acceso </td> 
   <td colname="col2"> <p>Ubicación del <span class="filepath"> archivo Control de acceso.cfg </span> . La ubicación predeterminada es la <span class="filepath"> carpeta Control de acceso </span> del directorio de instalación de <span class="keyword"> Insight Server </span> o <span class="wintitle"> Repeater </span> . </p> <p>Ejemplo: <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Directorio de registro de acceso </td> 
   <td colname="col2"> <p>Carpeta a la que desea asignar los registros de auditoría. </p> <p>Ejemplo: <filepath></filepath> </p> <p> <p>Nota:  Puede asignar registros de auditoría a otra unidad local (ejemplo: <span class="filepath"> string: P:\\Audit\\ </span>), pero no asigne registros de auditoría a una unidad de red. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registro de acceso detallado </td> 
   <td colname="col2"> Este parámetro se puede establecer en true o false. Se utiliza para habilitar y deshabilitar el filtrado de registros de auditoría. Para asegurarse de que se registra cada solicitud, establezca el parámetro en True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interfaz IP </td> 
   <td colname="col2"> <p>Dirección IP que se utilizará cuando haya dos tarjetas de red disponibles para acceder a dos redes diferentes. </p> <p>Ejemplo: I <filepath></filepath><i>&lt; <span class="filepath"> Dirección IP </span>&gt;</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto </td> 
   <td colname="col2"> <p>Puerto no seguro (HTTP) en el que escucha <span class="keyword"> Insight Server </span> o <span class="wintitle"> Repeater </span> . El puerto predeterminado es 80. Si se introduce un valor de 0, se desactivan las conexiones no seguras. </p> <p>Ejemplo: <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cifrados SSL </td> 
   <td colname="col2"> Algunos entornos requieren una mayor seguridad de la comunicación que otros. Si desea utilizar un grupo de cifrado SSL específico, puede especificarlo con este parámetro. <p>Ejemplo: <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto SSL </td> 
   <td colname="col2"> <p>Puerto seguro (mediante SSL) en el que escucha el servidor de <span class="keyword"> Insight </span> o el <span class="wintitle"> repetidor </span> . El puerto predeterminado es 443. Si se introduce un valor de 0, se desactivan las conexiones seguras. </p> <p>Ejemplo: <span class="filepath"></span> </p> <filepath></filepath> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Encabezado para la configuración del servidor de registro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre del cliente </td> 
   <td colname="col2"> <p>Nombre del cliente que aparecerá para clientes no especificados en alertas administrativas, como en el siguiente ejemplo: </p> <p>"No se recibieron datos del sensor XYZ para el cliente 'No especificado' en 15". </p> <p>Ejemplo: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Con el ejemplo anterior, las alertas administrativas para clientes no especificados ahora serían las siguientes: </p> <p>"No se han recibido datos del sensor XYZ para el cliente 'CompanyAB' en 15". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Ruta local = cadena: Registros\\ </p> </td> 
   <td colname="col2"> <p>Carpeta en la que desea almacenar los archivos de registro. </p> <p>Ejemplo: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Para poder acceder a esta carpeta desde el Administrador de archivos del <span class="wintitle"> servidor </span>, la ubicación especificada en este parámetro debe coincidir con la ubicación especificada en el parámetro Rutas de registro del <span class="filepath"> archivo Log Processing.cfg </span> . Para obtener más información sobre la modificación del directorio Registros en el archivo <span class="filepath"> Log Processing.cfg </span> , consulte el capítulo Archivo de configuración de procesamiento de registros de la Guía <i>de configuración de</i>Dataset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Ruta local = cadena: Auditoría\\ </p> </td> 
   <td colname="col2"> <p>Carpeta a la que desea asignar los registros de auditoría. </p> <p>Ejemplo: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Nota:  <p>Puede asignar registros de auditoría a otra unidad local (ejemplo: <span class="filepath"> string: P:\\Audit\\ </span>), pero no asigne registros de auditoría a una unidad de red. </p> <p>Para poder acceder a esta carpeta desde el Administrador de archivos del <span class="wintitle"> servidor </span>, la ubicación especificada en este parámetro debe coincidir con la ubicación que se encuentra en el parámetro Directorio de registros de acceso de este archivo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Este parámetro solo se aplica a <span class="keyword"> Insight Server </span>. </p> <p>Para obtener más información sobre la especificación del servidor de normalización centralizada para el clúster de <span class="keyword"> Insight Server </span> , consulte Archivo de configuración de procesamiento de registros en la Guía <i>de configuración de</i>Dataset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Este parámetro solo se aplica a <span class="keyword"> Insight Server </span>. </p> <p>Le permite vista del <span class="keyword"> estado del </span> informe en la interfaz Estado detallado para <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
