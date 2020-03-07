---
description: La herramienta principal que utilizan los administradores del sistema es el Administrador de servidores.
solution: Analytics
title: Administrador de servidores
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Administrador de servidores{#servers-manager}

La herramienta principal que utilizan los administradores del sistema es el Administrador de servidores.

Es la interfaz principal para determinar el estado general del sistema y para realizar funciones de configuración del sistema, administración de archivos y supervisión de errores.

El Administrador de servidores muestra un punto (nodo) de color para cada servidor de Área de trabajo de datos y la instalación en el sistema, y proporciona un estado de sistema de un vistazo para cada instalación. [!DNL Sensor] También muestra un nodo para la instalación de Área de trabajo de datos.

Los nodos verdes representan conexiones activas, los nodos rojos representan conexiones desactivadas o inaccesibles de otro modo y los nodos grises representan conexiones cuyos estados no están determinados.

![](assets/vis_SysStat_RedGreenDots.png)

Al hacer clic con el botón derecho en un nodo se muestra información sobre el componente que se conecta y se proporciona acceso a cualquier menú relacionado.

En las tablas siguientes se describe la información proporcionada cuando se hace clic con el botón derecho en un nodo para Área de trabajo de datos, servidor de Área de trabajo de datos (incluido un servidor maestro de Área de trabajo de datos en un clúster) o [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nombre del producto, versión y número de compilación. </p> <p>Ejemplo: Área de trabajo de datos 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección </p> </td> 
   <td colname="col2"> <p>Dirección IP del equipo de Área de trabajo de datos. </p> <p>Ejemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar </p> </td> 
   <td colname="col2"> <p>Vínculo al archivo <span class="keyword"> de configuración del Área de trabajo de datos </span> . Haga clic en <span class="uicontrol"> Configurar </span> &gt; <span class="uicontrol"> Insight.cfg </span> para mostrar la ventana de configuración del Área de trabajo de datos. Cualquier cambio que realice y guarde en esta ventana se verá reflejado en el archivo <span class="filepath"> Insight.cfg </span> del directorio de instalación de Área de trabajo de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nombre del producto, versión y número de compilación. </p> <p>Ejemplo: Servidor de Área de trabajo de datos 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Nombre común del equipo del servidor de Área de trabajo de datos. </p> <p>Ejemplo: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección </p> </td> 
   <td colname="col2"> <p>Dirección IP o nombre de dominio completo del servidor según la configuración del archivo Direcciones del equipo y el parámetro Ubicación de red del <span class="filepath"> archivo Insight.cfg </span> . </p> <p>Ejemplo: 100.0.0.1 </p> <p>Para obtener información sobre el archivo Direcciones, consulte la Guía <i>de instalación y administración de productos</i>del servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado </p> </td> 
   <td colname="col2"> <p>Estado actual del servidor de Área de trabajo de datos. Este campo muestra Aceptar cuando el servidor de Área de trabajo de datos se está ejecutando normalmente. Si se ha producido un error y el nodo del servidor Área de trabajo de datos está en rojo, el campo muestra el error (por ejemplo, "403 Prohibido"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado detallado </p> </td> 
   <td colname="col2"> <p>Vínculo a la interfaz <span class="keyword"> del servidor de Área de trabajo de datos </span><span class="wintitle"> </span> Estado detallado, que resulta útil para solucionar errores u otros problemas con el servidor de Área de trabajo de datos. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> La interfaz</a>de estado detallada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escritorio remoto </p> </td> 
   <td colname="col2"> <p>Abre una sesión <span class="wintitle"> de Escritorio remoto </span> en el equipo servidor de Área de trabajo de datos. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> La opción Escritorio remoto </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archivos de servidor </p> </td> 
   <td colname="col2"> <p>Vínculo al Administrador de archivos del <span class="wintitle"> servidor </span>, que muestra los directorios y archivos en el directorio de instalación del servidor de Área de trabajo de datos. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> El Administrador de archivos del servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor de servidor </p> </td> 
   <td colname="col2"> <p>Vínculo a la interfaz del <span class="wintitle"> monitor de servidor </span> , que resulta útil para solucionar problemas o rastrear parámetros de rendimiento. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> La interfaz del monitor del servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores relacionados </p> </td> 
   <td colname="col2"> <p>Solo para clústeres de servidores de Área de trabajo de datos. </p> <p>Un menú que enumera los nombres comunes de los equipos enumerados en el archivo *.address <span class="filepath"> del servidor maestro </span> del área de trabajo de datos. Esta lista generalmente incluye todos los servidores de Área de trabajo de <span class="keyword"> datos de procesamiento </span> del clúster. Este menú aparece únicamente si el Área de trabajo de datos tiene una copia del archivo *.address <span class="filepath"> del servidor maestro </span> del Área de trabajo de datos. </p> <p>Al hacer clic en <span class="uicontrol"> Servidores relacionados </span>, puede hacer clic en: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Lista del monitor de servidor </span>, que muestra la interfaz del monitor de <span class="wintitle"> servidor </span> con los detalles de todos los servidores relacionados </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Nombre común de cualquier servidor de Área de trabajo de datos, que muestra un menú contextual que le permite abrir cualquiera de las siguientes opciones para ese servidor en particular: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Estado detallado </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> La Interfaz De Estado Detallada </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Escritorio remoto </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> La Opción Escritorio Remoto </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Administrador de archivos del servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> El Administrador De Archivos De Servidor </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Monitor de servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> La Interfaz Del Monitor De Servidor </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nombre del producto, versión y número de compilación. </p> <p>Ejemplo: Sensor 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> ID del <span class="wintitle"> sensor </span> especificado en el archivo de configuración <span class="wintitle"> del sensor </span> para esta instalación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Dirección IP del servidor web o de aplicaciones en el que <span class="wintitle"> está instalado Sensor </span> . </p> <p>Ejemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID de proceso asignado por el sistema operativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Indica si <span class="wintitle"> Sensor </span> y el servidor de Área de trabajo de datos se comunican mediante SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha </p> </td> 
   <td colname="col2"> <p>Fecha (HH:MM:SS) que el <span class="wintitle"> Sensor </span> estableció por última vez una conexión con el servidor de Área de trabajo de datos. </p> </td> 
  </tr> 
 </tbody> 
</table>
