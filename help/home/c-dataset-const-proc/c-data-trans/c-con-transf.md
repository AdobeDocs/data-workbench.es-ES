---
description: Tabla que muestra qué convenciones se aplican al construir transformaciones.
solution: Analytics
title: Convenciones para construir transformaciones
topic: Data workbench
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Convenciones para construir transformaciones{#conventions-for-constructing-transformations}

Tabla que muestra qué convenciones se aplican al construir transformaciones.

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
   <td colname="col2"> <p>Las transformaciones dentro de un archivo de configuración de conjunto de datos se aplican secuencialmente a las entradas de registro (es decir, en el orden en que aparecen en el archivo de configuración). Por lo tanto, las transformaciones deben enumerarse en el orden en que sus salidas se utilizan como entradas para otras transformaciones. Más concretamente, si se utiliza el resultado de una transformación como entrada para otra transformación, es importante que esa transformación anterior se incluya antes de la última transformación en los archivos de configuración del conjunto de datos. De lo contrario, el servidor del área de trabajo de datos genera un error. </p> <p> Las etapas de procesamiento proporcionan una manera de ordenar las transformaciones que se definen en varios archivos de inclusión de conjuntos de datos. En todos los conjuntos de datos se incluyen archivos asociados a una etapa de procesamiento determinada, las transformaciones se ordenan en función de sus entradas y salidas. Además, si varios conjuntos de datos incluyen archivos dentro de una etapa en los datos de salida al mismo campo como resultado de una transformación, el servidor del área de trabajo de datos generará un error. </p> <p> Para obtener más información sobre las etapas, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo</a>de configuración de procesamiento de registros, Archivo <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> de configuración de transformación y</a>Archivos <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"></a>de inclusión de conjunto de datos. </p> <p>Un mapa <span class="wintitle"> de dependencia</span> de transformación puede mostrar cómo se modifica un campo mediante una serie de transformaciones. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Herramientas</a>de configuración de conjuntos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombres de salida </td> 
   <td colname="col2"> La mayoría de las transformaciones especifican un campo de salida. Si el resultado es un campo extendido definido por el usuario, el nombre de este campo debe comenzar por "x-". Los nombres de campo de salida no pueden contener espacios ni caracteres especiales. Los nombres de los campos extendidos se pueden escribir con mayúsculas y minúsculas mezcladas, como "x-NewCampaignName" o "x-New-Campaign-Name" para mayor legibilidad, pero el software los trata como si no tuvieran en cuenta las mayúsculas y minúsculas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos de entrada </td> 
   <td colname="col2"> <p>Los campos de entrada hacen referencia a uno de los campos de línea de base o a un campo creado por el usuario como resultado de una transformación anterior. Si se necesita una cadena constante, se puede utilizar una cadena entre comillas en lugar de un campo de línea base o creado por el usuario. </p> <p> Para obtener una lista de algunos de los campos de datos definidos comúnmente que el servidor del área de trabajo de datos puede procesar, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Campos</a>de registro de datos de eventos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cadenas y vectores simples de cadenas </td> 
   <td colname="col2"> Todas las transformaciones funcionan en cadenas o vectores de cadenas. Las cadenas simples son secuencias literales de caracteres. Los vectores de cadena contienen cero o más cadenas simples en un orden específico. </td> 
  </tr> 
 </tbody> 
</table>

