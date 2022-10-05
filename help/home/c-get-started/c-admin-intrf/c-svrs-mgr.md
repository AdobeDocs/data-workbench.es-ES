---
description: La herramienta principal que utilizan los administradores del sistema es el Administrador de servidores.
title: Administrador de servidores
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Administrador de servidores{#servers-manager}

{{eol}}

La herramienta principal que utilizan los administradores del sistema es el Administrador de servidores.

Es la interfaz principal para determinar el estado general del sistema y para realizar funciones de configuración del sistema, administración de archivos y supervisión de errores.

El Administrador de servidores muestra un punto (nodo) de color para cada servidor de Data Workbench y [!DNL Sensor] en su sistema y proporciona un vistazo al estado del sistema para cada instalación. También muestra un nodo para la instalación de la Data Workbench.

Los nodos verdes representan conexiones activas, los nodos rojos representan conexiones deshabilitadas o inaccesibles de otro modo, y los nodos grises representan conexiones cuyos estados son indeterminados.

![](assets/vis_SysStat_RedGreenDots.png)

Al hacer clic con el botón derecho en un nodo se muestra información sobre el componente que se conecta y proporciona acceso a cualquier menú relacionado.

En las tablas siguientes se describe la información proporcionada al hacer clic con el botón derecho en un nodo para la Data Workbench, el servidor de Data Workbench (incluido un servidor de Data Workbench maestro en un clúster) o [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Producto </p> </td> 
   <td colname="col2"> <p>Nombre del producto, versión y número de compilación. </p> <p>Ejemplo: Data Workbench 5.3 (0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección </p> </td> 
   <td colname="col2"> <p>Dirección IP del equipo de Data Workbench. </p> <p>Ejemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar </p> </td> 
   <td colname="col2"> <p>Un vínculo a su <span class="keyword"> Data Workbench </span> archivo de configuración. Haga clic en <span class="uicontrol"> Configurar </span> &gt; <span class="uicontrol"> Insight.cfg </span> para mostrar la ventana de configuración de la Data Workbench. Cualquier cambio que realice y guarde en esta ventana se refleja en la variable <span class="filepath"> Insight.cfg </span> en el directorio de instalación de la Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Producto </p> </td> 
   <td colname="col2"> <p>Nombre del producto, versión y número de compilación. </p> <p>Ejemplo: Servidor de Data Workbench 5.3 (0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Nombre común del equipo servidor de Data Workbench. </p> <p>Ejemplo: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección </p> </td> 
   <td colname="col2"> <p>Dirección IP o nombre de dominio completo del servidor según se ha configurado en el archivo Direcciones del equipo y en el parámetro Ubicación de red del <span class="filepath"> Insight.cfg </span> archivo. </p> <p>Ejemplo: 100.0.0.1 </p> <p>Para obtener información sobre el archivo Direcciones , consulte la <i>Guía de instalación y administración de productos para servidor</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado </p> </td> 
   <td colname="col2"> <p>Estado actual del servidor de Data Workbench. Este campo muestra OK cuando el servidor de Data Workbench se está ejecutando normalmente. Si se ha producido un error y el nodo del servidor de Data Workbench está en rojo, el campo muestra el error (por ejemplo, "403 prohibido"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado detallado </p> </td> 
   <td colname="col2"> <p>Un vínculo a la variable <span class="keyword"> servidor de Data Workbench </span> <span class="wintitle"> Estado detallado </span> , que resulta útil para solucionar errores u otros problemas con el servidor de Data Workbench. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Interfaz de estado detallada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escritorio remoto </p> </td> 
   <td colname="col2"> <p>Abre un <span class="wintitle"> Escritorio remoto </span> al equipo servidor de Data Workbench. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> La opción Escritorio remoto </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archivos de servidor </p> </td> 
   <td colname="col2"> <p>Un vínculo a la variable <span class="wintitle"> Administrador de archivos del servidor </span>, que muestra los directorios y archivos en el directorio de instalación del servidor de Data Workbench. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Administrador de archivos del servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor de servidor </p> </td> 
   <td colname="col2"> <p>Un vínculo a la variable <span class="wintitle"> Monitor de servidor </span> , que resulta útil para solucionar problemas o rastrear parámetros de rendimiento. </p> <p>Para obtener más información, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Interfaz del monitor del servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores relacionados </p> </td> 
   <td colname="col2"> <p>Solo para clústeres de servidores de Data Workbench. </p> <p>Menú que enumera los nombres comunes de los equipos enumerados en el informe maestro <span class="filepath"> Dirección *.address del servidor de Data Workbench </span> archivo. Esta lista suele incluir todo el procesamiento <span class="keyword"> servidores de Data Workbench </span> en el clúster. Este menú aparece únicamente si la Data Workbench tiene una copia del maestro <span class="filepath"> Dirección *.address del servidor de Data Workbench </span> archivo. </p> <p>Al hacer clic en <span class="uicontrol"> Servidores relacionados </span>, puede hacer clic en: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Lista de monitores del servidor </span>, que muestra la variable <span class="wintitle"> Monitor de servidor </span> detalles de la lista de interfaz para todos los servidores relacionados </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">El nombre común de cualquier servidor de Data Workbench, que muestra un menú contextual que le permite abrir cualquiera de las siguientes opciones para ese servidor en particular: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Estado detallado </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Interfaz de estado detallada </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Escritorio remoto </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> La opción Escritorio remoto </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Administrador de archivos del servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Administrador de archivos del servidor </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Monitor de servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Interfaz del monitor del servidor </a>. </li> 
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
   <td colname="col1"> <p>Producto </p> </td> 
   <td colname="col2"> <p>Nombre del producto, versión y número de compilación. </p> <p>Ejemplo: Sensor 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> La variable <span class="wintitle"> Sensor </span> ID especificado en la variable <span class="wintitle"> Sensor </span> para esta instalación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Dirección IP del servidor de aplicaciones o web en el que <span class="wintitle"> Sensor </span> está instalado. </p> <p>Ejemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID de proceso asignado por el sistema operativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Si <span class="wintitle"> Sensor </span> y el servidor de Data Workbench se comunica mediante SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha </p> </td> 
   <td colname="col2"> <p>Tiempo (HH):MM:SS) que la variable <span class="wintitle"> Sensor </span> por última vez se estableció una conexión con el servidor de Data Workbench. </p> </td> 
  </tr> 
 </tbody> 
</table>
