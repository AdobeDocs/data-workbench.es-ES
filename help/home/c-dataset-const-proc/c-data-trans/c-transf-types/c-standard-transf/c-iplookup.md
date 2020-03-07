---
description: La transformación IPLookup toma datos de geolocalización de IP o de inteligencia geográfica de IP (proporcionados por cualquier proveedor de dichos datos y convertidos a un formato propietario por Adobe) y transforma los datos en información geográfica que se puede utilizar en análisis.
solution: Analytics
title: IPLookup
topic: Data workbench
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IPLookup{#iplookup}

La transformación IPLookup toma datos de geolocalización de IP o de inteligencia geográfica de IP (proporcionados por cualquier proveedor de dichos datos y convertidos a un formato propietario por Adobe) y transforma los datos en información geográfica que se puede utilizar en análisis.

En el menú Agregar nuevo > *Tipo de transformación *se enumeran dos [!DNL IPLookup] transformaciones:

* [!DNL IPLookup] Quova para [!DNL IP geo-location] datos

* [!DNL IPLookup] Digital Envoy for [!DNL IP geo-intelligence] data

Al definir una [!DNL IPLookup] transformación, elija la transformación adecuada para los datos [!DNL IP geo-location] o [!DNL IP geo-intelligence] .

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo </td> 
   <td colname="col2"> Ruta y nombre de archivo del archivo de búsqueda. Las rutas relativas se refieren al directorio de instalación del servidor del área de trabajo de datos. Este archivo se encuentra generalmente en el directorio de búsquedas dentro del directorio de instalación del servidor del área de trabajo de datos. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección IP </td> 
   <td colname="col2"> Campo desde el cual leer la dirección IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2"> <p>Nombres de las cadenas de salida. </p> <p> Las transformaciones de <span class="wintitle"> IPLookup</span> Quova e <span class="wintitle"> IPLookup</span> Digital Envoy tienen parámetros de salida diferentes. Asegúrese de utilizar la transformación adecuada para los datos de búsqueda IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, [!DNL IP geo-location] los datos (en el archivo de búsqueda [!DNL Quova.bin]) se utilizan para crear los campos de salida enumerados. Las salidas (AOL, ASN, Area Code, etc.) se pueden usar para crear dimensiones para el análisis geográfico del tráfico de visitantes.

![](assets/cfg_TransformationType_IPLookup.png)

