---
description: Lista de archivos instalados con Insight Server y los archivos presentes después de su registro, y ejecutarlos por primera vez.
solution: Insight
title: Estructura de directorio de Insight Server
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Estructura de directorio de Insight Server{#insight-server-directory-structure}

Lista de archivos instalados con Insight Server y los archivos presentes después de su registro, y ejecutarlos por primera vez.

## Archivos incluidos en el paquete de instalación {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Los siguientes directorios se incluyen en el paquete de [!DNL Insight Server] instalación:

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
   <td colname="col2"> <span class="keyword"> Archivo de configuración de Insight Server </span> que especifica una lista de grupos de acceso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Direcciones </td> 
   <td colname="col2"> Direcciones utilizadas para la comunicación con <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auditoría </td> 
   <td colname="col2"> Registros de acceso diario que contienen detalles sobre todos los intentos de conexión a <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Archivos de programa ejecutables de Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificados </td> 
   <td colname="col2"> Certificados digitales SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes </td> 
   <td colname="col2"> <span class="keyword"> Archivos de configuración de componentes de Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes para servidores de procesamiento </td> 
   <td colname="col2"> <span class="keyword"> Archivos de configuración de componentes de Insight Server </span> para procesar servidores <span class="keyword"> Insight </span> dentro de un clúster de <span class="keyword"> Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Events </td> 
   <td colname="col2"> Registros diarios de eventos que contienen mensajes detallados de estado del evento, incluidos los mensajes de error. Los eventos capturados y registrados por <span class="keyword"> Insight Server </span> también se muestran en el Visor de eventos de Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros </td> 
   <td colname="col2"> <p>Archivos de registro producidos por <span class="wintitle"> sensores </span>(s). </p> <p>"Registros" es el directorio de registro predeterminado, pero es posible que se haya especificado un directorio alternativo en el archivo <span class="filepath"> Communications.cfg </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Búsquedas </td> 
   <td colname="col2"> Archivos de búsqueda, como listas de robots y motores de búsqueda. <span class="keyword"> Insight Server </span> debe cargar todos los archivos de búsqueda en la memoria. El tamaño total de todos los archivos de búsqueda a los que se hace referencia en los archivos de configuración de componentes, más la sobrecarga (por ejemplo, 12 bytes por fila para los archivos <span class="filepath"> FlatFileLookup </span> ), no debe superar la memoria física o virtual disponible después de cargar todas las demás aplicaciones de software. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfiles </td> 
   <td colname="col2"> <p>Archivos relacionados con cada perfil (archivos de configuración, espacio de trabajo y visualización). Los perfiles se rellenan con datos de un conjunto de datos. Los conjuntos de datos incluyen datos de eventos ("Datos de registro"); estos datos pueden ser capturados por <span class="wintitle"> sensores instalados </span>, transmitidos por señalizaciones Web o etiquetas de página, o por datos de almacenes de datos. <span class="keyword"> Los usuarios de Insight </span> con acceso a un perfil determinado pueden utilizar el conjunto de datos procesados para ese perfil, así como los espacios de trabajo y las visualizaciones definidos en dicho perfil. </p> <p>Los espacios de trabajo son áreas de trabajo para administración o análisis del sistema. Un espacio de trabajo puede contener varias interfaces que muestran diferentes detalles sobre el rendimiento del sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Actualizaciones </span> de software de Insight. Las actualizaciones de software de informes también se almacenan aquí. </td> 
  </tr> 
 </tbody> 
</table>

## Directorios y archivos creados tras el inicio {#section-ef7408e8fae64454b326ec07453d4628}

Los directorios que se enumeran a continuación se crean una vez [!DNL Insight Server] registrados y se ejecutan por primera vez:

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
   <td colname="col2"> <p>Ubicación de los archivos temporales utilizados por <span class="keyword"> Insight Server </span> durante el reprocesamiento y el funcionamiento. Normalmente hay un archivo (llamado <span class="filepath"> temp.db </span> de forma predeterminada) por unidad física. </p> <p> <span class="keyword"> Insight Server </span> debe estar configurado para escribir en este directorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seguimiento </td> 
   <td colname="col2"> Datos de registro y eventos sobre <span class="keyword"> Insight Server </span>. Útil para la resolución de problemas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuarios </td> 
   <td colname="col2"> Usuarios con nombre ( <span class="keyword"> Insight </span>) con acceso a los perfiles en el servidor. Se crea un directorio para cada usuario autorizado designado dentro del directorio Usuarios\ cuando el usuario accede por primera vez a <span class="keyword"> Insight Server </span> a través de <span class="keyword"> Insight </span>. El directorio de cada usuario con nombre contiene directorios que corresponden a todos los perfiles a los que el usuario ha accedido en ese <span class="keyword"> servidor de Insight </span> , así como sus archivos de dirección locales. </td> 
  </tr> 
 </tbody> 
</table>

