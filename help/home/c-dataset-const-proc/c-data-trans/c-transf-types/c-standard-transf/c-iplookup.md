---
description: La transformación IPLookup toma datos de geoubicación IP o de geointeligencia IP (proporcionados por cualquier proveedor de dichos datos y convertidos en un formato propietario por Adobe) y transforma los datos en información geográfica que se puede utilizar en el análisis.
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 4%

---

# IPLookup{#iplookup}

{{eol}}

La transformación IPLookup toma datos de geoubicación IP o de geointeligencia IP (proporcionados por cualquier proveedor de dichos datos y convertidos en un formato propietario por Adobe) y transforma los datos en información geográfica que se puede utilizar en el análisis.

Two [!DNL IPLookup] las transformaciones se enumeran en el menú Add new > *Transformation type *:

* [!DNL IPLookup] Quova para [!DNL IP geo-location] data

* [!DNL IPLookup] Digital Envoy para [!DNL IP geo-intelligence] data

Al definir una [!DNL IPLookup] transformación, elija la transformación adecuada para su [!DNL IP geo-location] o [!DNL IP geo-intelligence] datos.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. </td> 
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
   <td colname="col2"> Ruta y nombre de archivo del archivo de búsqueda. Las rutas relativas son con respecto al directorio de instalación del servidor de Data Workbench. Este archivo se encuentra generalmente en el directorio de búsquedas dentro del directorio de instalación del servidor de Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección IP </td> 
   <td colname="col2"> Campo desde el que se debe leer la dirección IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2"> <p>Nombres de las cadenas de salida. </p> <p> La variable <span class="wintitle"> IPLookup</span> Quova y <span class="wintitle"> IPLookup</span> Las transformaciones de Digital Envoy tienen diferentes parámetros de salida. Asegúrese de utilizar la transformación adecuada para sus datos de búsqueda IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, [!DNL IP geo-location] datos (en el archivo de búsqueda) [!DNL Quova.bin]) se utiliza para crear los campos de salida enumerados. Los resultados (AOL, ASN, Código de área, etc.) se pueden usar para crear dimensiones para el análisis geográfico del tráfico de visitantes.

![](assets/cfg_TransformationType_IPLookup.png)
