---
description: Lista de archivos instalados con Insight Server y los archivos presentes después de que se hayan registrado y ejecutados por primera vez.
title: Estructura de directorio de Insight Server
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Estructura de directorio de Insight Server{#insight-server-directory-structure}

{{eol}}

Lista de archivos instalados con Insight Server y los archivos presentes después de que se hayan registrado y ejecutados por primera vez.

## Archivos incluidos en el paquete de instalación {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Los siguientes directorios están incluidos en la variable [!DNL Insight Server] paquete de instalación:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directorio </th> 
   <th colname="col2" class="entry"> Descripción del contenido del directorio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Control de acceso </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> archivo de configuración que especifica una lista de grupos de acceso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Direcciones </td> 
   <td colname="col2"> Direcciones utilizadas para la comunicación con <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auditoría </td> 
   <td colname="col2"> Registros de acceso diario que contienen detalles sobre todos los intentos de conexión con <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> archivos de programa ejecutables. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificados </td> 
   <td colname="col2"> Certificados digitales SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> archivos de configuración de componentes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes para servidores de procesamiento </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> archivos de configuración de componentes para procesamiento <span class="keyword"> Servidores de Insight </span> dentro de un <span class="keyword"> Insight Server </span> clúster. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventos </td> 
   <td colname="col2"> Registros de eventos diarios que contienen mensajes de estado de eventos detallados, incluidos mensajes de error. Eventos capturados y registrados por <span class="keyword"> Insight Server </span> también se muestran en el Visor de eventos de Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros </td> 
   <td colname="col2"> <p>Archivos de registro producidos por <span class="wintitle"> Sensor </span>s) </p> <p>"Registros" es el directorio de registro predeterminado, pero es posible que se haya especificado un directorio alternativo en <span class="filepath"> communications.cfg </span> archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Búsquedas </td> 
   <td colname="col2"> Archivos de búsqueda, como listas de robots y motores de búsqueda. <span class="keyword"> Insight Server </span> debe cargar todos los archivos de búsqueda en la memoria. El tamaño total de todos los archivos de búsqueda a los que se hace referencia en los archivos de configuración de componentes, además de la sobrecarga (por ejemplo, 12 bytes por fila para <span class="filepath"> FlatFileLookup </span> ), no debe superar la memoria física o virtual disponible después de cargar todas las demás aplicaciones de software. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfiles </td> 
   <td colname="col2"> <p>Archivos relacionados con cada perfil (archivos de configuración, espacio de trabajo y visualización). Los perfiles se rellenan con datos de un conjunto de datos. Los conjuntos de datos incluyen datos de evento ("Datos de registro"); estos datos pueden ser capturados por <span class="wintitle"> Sensores </span>, transmitido mediante señalizaciones web o etiquetas de página, o mediante entrada desde almacenes de datos. <span class="keyword"> Insight </span> los usuarios con acceso a un perfil determinado pueden utilizar el conjunto de datos procesados para ese perfil, así como los espacios de trabajo y visualizaciones definidos dentro de ese perfil. </p> <p>Los espacios de trabajo son áreas de trabajo para la administración o análisis del sistema. Un espacio de trabajo puede contener varias interfaces que muestran diferentes detalles sobre el rendimiento del sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> actualizaciones de software. Las actualizaciones de software de informes también se almacenan aquí. </td> 
  </tr> 
 </tbody> 
</table>

## Directorios y archivos creados después del inicio {#section-ef7408e8fae64454b326ec07453d4628}

Los directorios que se enumeran a continuación se crean después de [!DNL Insight Server] está registrado y se ejecuta por primera vez:

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directorio </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Estado </td> 
   <td colname="col2"> Información de procesamiento generada por <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Ubicación de los archivos temporales utilizados por <span class="keyword"> Insight Server </span> durante el reprocesamiento y la operación. Normalmente hay un archivo (con el nombre <span class="filepath"> temp.db </span> de forma predeterminada) por unidad física. </p> <p> <span class="keyword"> Insight Server </span> debe estar configurado para escribir en este directorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seguimiento </td> 
   <td colname="col2"> Datos de registro y eventos acerca de <span class="keyword"> Insight Server </span>. Útil para la resolución de problemas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuarios </td> 
   <td colname="col2"> Con el nombre ( <span class="keyword"> Insight </span>) usuarios con acceso a los perfiles del servidor. Se crea un directorio para cada usuario con nombre autorizado dentro del directorio Users\ cuando el usuario accede por primera vez <span class="keyword"> Insight Server </span> via <span class="keyword"> Insight </span>. El directorio de cada usuario con nombre contiene directorios correspondientes a todos los perfiles a los que el usuario ha accedido <span class="keyword"> Insight Server </span> así como sus archivos de dirección local. </td> 
  </tr> 
 </tbody> 
</table>
