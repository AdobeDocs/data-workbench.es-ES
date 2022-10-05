---
description: Tabla que muestra las convenciones aplicables a la construcción de transformaciones.
title: Convenciones para crear transformaciones
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# Convenciones para crear transformaciones{#conventions-for-constructing-transformations}

{{eol}}

Tabla que muestra las convenciones aplicables a la construcción de transformaciones.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Convención </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ejecución secuencial </td> 
   <td colname="col2"> <p>Las transformaciones dentro de un archivo de configuración de conjunto de datos se aplican secuencialmente a las entradas de registro (es decir, en el orden en que aparecen en el archivo de configuración). Por lo tanto, las transformaciones deben enumerarse en el orden en que sus productos se utilicen como insumos para otras transformaciones. Más específicamente, si el resultado de una transformación se utiliza como entrada para otra transformación, es importante que esa transformación anterior se incluya antes de la última transformación en los archivos de configuración del conjunto de datos. De lo contrario, el servidor de Data Workbench genera un error. </p> <p> Las etapas de procesamiento proporcionan una forma de ordenar las transformaciones que se definen dentro de varios archivos de inclusión de conjuntos de datos. Para todos los conjuntos de datos, incluya archivos asociados a una etapa de procesamiento determinada, las transformaciones se ordenan según sus entradas y salidas. Además, si varios conjuntos de datos incluyen archivos dentro de un escenario de datos de salida en el mismo campo como resultado de una transformación, el servidor de Data Workbench genera un error. </p> <p> Para obtener más información sobre las etapas, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registros</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> Archivo de configuración de transformación</a>y <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Archivos de inclusión de conjunto de datos</a>. </p> <p>A <span class="wintitle"> Mapa de dependencias de transformación</span> puede mostrar cómo se modifica un campo mediante una serie de transformaciones. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Herramientas de configuración de conjuntos de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombres de salida </td> 
   <td colname="col2"> La mayoría de las transformaciones especifican un campo de salida. Si el resultado es un campo ampliado definido por el usuario, el nombre de este campo debe comenzar por "x-". Los nombres de campo de salida no pueden contener espacios ni caracteres especiales. Los nombres de los campos ampliados se pueden escribir con mayúsculas y minúsculas mezcladas, como "x-NewCampaignName" o "x-New-Campaign-Name" para mayor legibilidad, pero el software los trata como si no tuvieran en cuenta las mayúsculas y minúsculas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos de entrada </td> 
   <td colname="col2"> <p>Los campos de entrada hacen referencia a uno de los campos de línea de base o a un campo creado por el usuario resultante de una transformación anterior. Si se necesita una cadena constante, se puede utilizar una cadena entre comillas en lugar de un campo de línea base o creado por el usuario. </p> <p> Para obtener una lista de algunos de los campos de datos definidos comúnmente que puede procesar el servidor de Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Campos de registro de datos de evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cadenas y vectores simples de cadenas </td> 
   <td colname="col2"> Todas las transformaciones funcionan en cadenas o vectores de cadenas. Las cadenas simples son secuencias literales de caracteres. Los vectores de cadenas contienen cero o cadenas más simples en un orden específico. </td> 
  </tr> 
 </tbody> 
</table>
