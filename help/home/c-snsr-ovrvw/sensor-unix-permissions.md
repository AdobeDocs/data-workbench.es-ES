---
description: Información sobre los permisos de archivos UNIX del sensor, como el módulo de recopilación, el proceso del transmisor, el archivo de configuración, etc.
title: Permisos del archivo UNIX de sensor
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 5%

---

# Permisos del archivo UNIX de sensor{#sensor-unix-file-permissions}

{{eol}}

Información sobre los permisos de archivos UNIX del sensor, como el módulo de recopilación, el proceso del transmisor, el archivo de configuración, etc.

## El módulo Collector {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calidad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombre del archivo </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so (en servidores web Apache y servidores HTTP IBM) </p> <p>libvisual_sciences.so y J2EECollector.jar (en servidores de aplicaciones J2EE) </p> <p>aol_visual_sciences.so (en servidores web de AOL) </p> <p>saf_visual_sciences.so (en servidores web de Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permisos predeterminados </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP y Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (servidores web J2EE, AOL y Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Leído por </p> </td> 
   <td colname="col2"> <p>El servidor web, que a veces se ejecuta como usuario raíz, pero que a menudo se ejecuta con una cuenta de usuario específica </p> <p>Si el servidor web se ejecuta en una cuenta no raíz, los permisos de este archivo deben permitir que esa cuenta lo lea. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se ejecuta como </p> </td> 
   <td colname="col2"> <p>Un proceso secundario en el servidor web </p> <p>Los procesos secundarios se ejecutan con una cuenta de usuario especificada en la configuración del servidor web. En muchos servidores, se trata de una cuenta especial con privilegios muy limitados denominada "nadie", pero no todos los servidores web utilizan esta cuenta. Compruebe el archivo de configuración de su servidor web para determinar qué cuenta de usuario está configurada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lecturas de </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>El archivo diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escribe en </td> 
   <td colname="col2"> El archivo diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## El proceso del transmisor {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calidad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre del archivo </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permisos predeterminados </p> </td> 
   <td colname="col2"> <p>rw- r— r— (servidores web HTTP, AOL y Sun Java de IBM) </p> <p>rw- rw- r— (servidores web Apache y servidores de aplicaciones J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leído por </td> 
   <td colname="col2"> El programa transmisor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## El archivo de configuración {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calidad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre del archivo </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permisos predeterminados </p> </td> 
   <td colname="col2"> <p>rw- r— r— (servidores web HTTP, AOL y Sun Java de IBM) </p> <p>rw- rw- r— (servidores web Apache y servidores de aplicaciones J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leído por </td> 
   <td colname="col2"> <p>Módulo de recolector </p> <p>El programa transmisor </p> <p>El administrador responsable de la instalación, configuración y mantenimiento del sensor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> El administrador responsable de la instalación, configuración y mantenimiento del sensor </td> 
  </tr> 
 </tbody> 
</table>

## El archivo de la autoridad de certificación {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calidad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre del archivo </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permisos predeterminados </p> </td> 
   <td colname="col2"> <p>rw- r— r— (servidores web HTTP, AOL y Sun Java de IBM) </p> <p>rw- rw- r— (servidores web Apache y servidores de aplicaciones J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leído por </td> 
   <td colname="col2"> El programa transmisor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## La cola de disco {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calidad </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre del archivo </td> 
   <td colname="col2"> Definido por el usuario </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Permisos predeterminados </td> 
   <td colname="col2"> rw- rw- rw- (Todos los tipos de servidor) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Leído por </p> </td> 
   <td colname="col2"> <p>Módulo de recolector </p> <p>El programa transmisor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escrito por </p> </td> 
   <td colname="col2"> <p>Módulo de recolector </p> <p>El programa transmisor </p> </td> 
  </tr> 
 </tbody> 
</table>
