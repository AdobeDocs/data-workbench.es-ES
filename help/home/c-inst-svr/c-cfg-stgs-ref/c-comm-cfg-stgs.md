---
description: Instrucciones para configurar las comunicaciones para Insight Server o el repetidor.
title: Configuración de ajustes de comunicaciones
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# Configuración de ajustes de comunicaciones{#communications-configuration-settings}

{{eol}}

Instrucciones para configurar las comunicaciones para Insight Server o el repetidor.

Complete los parámetros del siguiente archivo:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Antes de modificar cualquier parámetro que no aparezca en esta tabla, póngase en contacto con el Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Archivo de control de acceso </td> 
   <td colname="col2"> <p>Ubicación de la variable <span class="filepath"> Access Control.cfg </span> archivo. La ubicación predeterminada es la <span class="filepath"> Control de acceso </span> dentro de la carpeta <span class="keyword"> Insight Server </span> o <span class="wintitle"> Repetidor </span> directorio de instalación. </p> <p>Ejemplo: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Directorio de registro de acceso </td> 
   <td colname="col2"> <p>Carpeta a la que desea asignar los registros de auditoría. </p> <p>Ejemplo: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Nota: Puede asignar registros de auditoría a otra unidad local (ejemplo: <span class="filepath"> cadena: P:\\Audit\\ </span>), pero no asigne registros de auditoría a una unidad de red. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Access Log Verbose </td> 
   <td colname="col2"> Este parámetro se puede establecer en true o false. Se utiliza para habilitar y deshabilitar el filtrado de registros de auditoría. Para asegurarse de que se registre cada solicitud, establezca el parámetro en True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interfaz IP </td> 
   <td colname="col2"> <p>Dirección IP que se utilizará cuando haya dos tarjetas de red disponibles para acceder a dos redes diferentes. </p> <p>Ejemplo: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto </td> 
   <td colname="col2"> <p>Puerto no seguro (HTTP) en el que <span class="keyword"> Insight Server </span> o <span class="wintitle"> Repetidor </span> escucha. El puerto predeterminado es 80. Si se introduce un valor de 0, se deshabilitarán las conexiones no seguras. </p> <p>Ejemplo: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cifrados SSL </td> 
   <td colname="col2"> Algunos entornos requieren una mayor seguridad de las comunicaciones que otros. Si desea utilizar un grupo de cifrado SSL específico, puede especificarlo con este parámetro. <p>Ejemplo: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto SSL </td> 
   <td colname="col2"> <p>Puerto seguro (a través de SSL) en el que <span class="keyword"> Insight Server </span> o <span class="wintitle"> Repetidor </span> escucha. El puerto predeterminado es 443. Si se introduce un valor de 0, se deshabilitarán las conexiones seguras. </p> <p>Ejemplo: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>Servidor de registro: </td> 
   <td colname="col2"> Encabezado para la configuración del servidor de registro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre del cliente </td> 
   <td colname="col2"> <p>Nombre del cliente para que aparezca para clientes no especificados en alertas administrativas, como en el siguiente ejemplo: </p> <p>"No se recibieron datos del sensor XYZ para el cliente 'No especificado' en 15". </p> <p>Ejemplo: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Con el ejemplo anterior, las alertas administrativas para clientes sin especificar ahora serían las siguientes: </p> <p>"No se han recibido datos del sensor XYZ para la "Empresa AB" del cliente en 15". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>Servidor de archivos: </p> <p> Ruta local = cadena: Registros\ </p> </td> 
   <td colname="col2"> <p>Carpeta en la que desea almacenar los archivos de registro. </p> <p>Ejemplo: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Para poder acceder a esta carpeta desde la <span class="wintitle"> Administrador de archivos del servidor </span>, la ubicación especificada en este parámetro debe coincidir con la ubicación especificada en el parámetro Rutas de registro de <span class="filepath"> Log Processing.cfg </span> archivo. Para obtener más información sobre la modificación del directorio Registros en la variable <span class="filepath"> Log Processing.cfg </span> consulte el capítulo Archivo de configuración de procesamiento de registros de <i>Guía de configuración de conjuntos de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>Servidor de archivos: </p> <p> Ruta local = cadena: Auditoría\ </p> </td> 
   <td colname="col2"> <p>Carpeta a la que desea asignar los registros de auditoría. </p> <p>Ejemplo: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Nota:  <p>Puede asignar registros de auditoría a otra unidad local (ejemplo: <span class="filepath"> cadena: P:\\Audit\\ </span>), pero no asigne registros de auditoría a una unidad de red. </p> <p>Para poder acceder a esta carpeta desde la <span class="wintitle"> Administrador de archivos del servidor </span>, la ubicación especificada en este parámetro debe coincidir con la ubicación que haya en el parámetro Directorio de registro de acceso de este archivo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Este parámetro solo se aplica a <span class="keyword"> Insight Server </span>. </p> <p>Para obtener más información sobre cómo especificar el Servidor de Normalización Centralizada para su <span class="keyword"> Insight Server </span> , consulte el capítulo Archivo de configuración de procesamiento de registros de <i>Guía de configuración de conjuntos de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = cadena: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Este parámetro solo se aplica a <span class="keyword"> Insight Server </span>. </p> <p>Permite ver <span class="keyword"> Informes </span> estado en la interfaz Estado detallado de <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
