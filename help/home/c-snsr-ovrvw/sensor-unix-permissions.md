---
description: Información sobre los permisos de archivos de Sensor UNIX, como el módulo del recopilador, el proceso del transmisor, el archivo de configuración, etc.
title: Permisos del archivo UNIX de sensor
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Permisos del archivo UNIX de sensor{#sensor-unix-file-permissions}

Información sobre los permisos de archivos de Sensor UNIX, como el módulo del recopilador, el proceso del transmisor, el archivo de configuración, etc.

## Módulo de recopilador {#section-49c855baece24c4695184bfcbeeddebf}

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
   <td colname="col2"> <p>mod_visual_sciences.so (en servidores web Apache y servidores HTTP IBM) </p> <p>libvisual_sciences.so y J2EECollector.jar (en servidores de aplicaciones J2EE) </p> <p>aol_visual_sciences.so (en servidores web de AOL) </p> <p>saf_visual_sciences.so (en servidores web Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permisos predeterminados </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP y Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (servidores web J2EE, AOL y Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Leído por </p> </td> 
   <td colname="col2"> <p>El servidor web, que a veces se ejecuta como usuario raíz, pero que más a menudo se ejecuta con una cuenta de usuario específica </p> <p>Si el servidor web se ejecuta con una cuenta que no es raíz, los permisos de este archivo deben permitir que dicha cuenta lo lea. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se ejecuta como </p> </td> 
   <td colname="col2"> <p>Proceso secundario en el servidor web </p> <p>Los procesos secundarios se ejecutan con una cuenta de usuario especificada en la configuración del servidor web. En muchos servidores, esta es una cuenta especial con privilegios muy limitados, llamada "nadie" — pero no todos los servidores Web utilizan esta cuenta. Compruebe el archivo de configuración del servidor web para determinar qué cuenta de usuario está configurada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lee desde </p> </td> 
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
   <td colname="col2"> <p>rw- r— r— (servidores web IBM HTTP, AOL y Sun Java) </p> <p>rw- rw- r— (servidores web Apache y servidores de aplicaciones J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leído por </td> 
   <td colname="col2"> El programa de transmisores </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> -- </td> 
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
   <td colname="col2"> <p>rw- r— r— (servidores web IBM HTTP, AOL y Sun Java) </p> <p>rw- rw- r— (servidores web Apache y servidores de aplicaciones J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leído por </td> 
   <td colname="col2"> <p>El módulo del selector </p> <p>El programa de transmisores </p> <p>El administrador responsable de instalar, configurar y mantener el sensor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> El administrador responsable de instalar, configurar y mantener el sensor </td> 
  </tr> 
 </tbody> 
</table>

## El archivo de autoridad certificadora {#section-2818dff887b8456992bdc589fd8510f3}

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
   <td colname="col2"> <p>rw- r— r— (servidores web IBM HTTP, AOL y Sun Java) </p> <p>rw- rw- r— (servidores web Apache y servidores de aplicaciones J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Leído por </td> 
   <td colname="col2"> El programa de transmisores </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## Cola de discos {#section-0407c52744de41af867d0b7933a69256}

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
   <td colname="col2"> <p>El módulo del selector </p> <p>El programa de transmisores </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escrito por </p> </td> 
   <td colname="col2"> <p>El módulo del selector </p> <p>El programa de transmisores </p> </td> 
  </tr> 
 </tbody> 
</table>

