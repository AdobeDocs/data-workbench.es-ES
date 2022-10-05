---
description: El archivo de inclusión de conjunto de datos de transformación para un perfil heredado contiene parámetros asociados con la fase de transformación de la construcción del conjunto de datos.
title: Archivos de inclusión de conjuntos de datos de transformación
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Archivos de inclusión de conjuntos de datos de transformación{#transformation-dataset-include-files}

{{eol}}

El archivo de inclusión de conjunto de datos de transformación para un perfil heredado contiene parámetros asociados con la fase de transformación de la construcción del conjunto de datos.

La primera línea del archivo define un tipo [!DNL TransformationInclude] que admite los parámetros de Dimension, parámetros, reprocesamiento, fase y transformaciones extendidos. Todos los demás parámetros deben definirse en la variable [!DNL Transformation.cfg] en el directorio del conjunto de datos del perfil del conjunto de datos.

Inclusión de parámetros que no sean Dimension extendidos, parámetros, reprocesamiento, fase y transformaciones en un [!DNL Transformation Dataset Include] genera errores.

Puede asignar un nombre a [!DNL Transformation Dataset Include] archivar lo que desee, pero la extensión de archivo debe ser [!DNL .cfg]. El archivo debe almacenarse dentro de la variable *nombre de perfil heredado*\Dataset\directorio de transformación. Debido a que los archivos se cargan recursivamente durante la fase de transformación de la construcción del conjunto de datos, puede almacenar la variable [!DNL Transformation Dataset Include] archivos en cualquier nivel dentro del directorio (por ejemplo, *nombre de perfil heredado*\Dataset\Transformation\*nombre de carpeta*\*incluir nombre de archivo*.cfg).

>[!NOTE]
>
>Muchos parámetros de configuración específicos de la web para el sitio se definen en [!DNL Transformation Dataset Include] archivos. Para obtener información sobre estos parámetros, consulte [Ajustes de configuración para datos web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

La tabla siguiente describe los parámetros disponibles en una [!DNL Transformation Dataset Include] archivo:

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensiones extendidas </td> 
   <td colname="col2"> Opcional. Define las dimensiones extendidas. Consulte <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimension extendidos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parámetros </td> 
   <td colname="col2"> Opcional. Variable a la que se puede hacer referencia en otros parámetros de configuración. Para obtener más información, consulte <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en archivos de inclusión de conjuntos de datos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Volver a procesar </td> 
   <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo, se iniciará la retransformación de datos. </p> <p> Para obtener información sobre cómo reprocesar los datos, consulte <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prueba </td> 
   <td colname="col2"> <p>Opcional. Nombre de la fase de procesamiento que se aplica a esta <span class="wintitle"> Incluir conjunto de datos de transformación</span> archivo. Las etapas de procesamiento se definen en el parámetro Stages de la variable <span class="filepath"> Transformation.cfg</span> archivo. </p> <p> <p>Nota: Cuando se especifica un escenario, el nombre del escenario debe coincidir exactamente con el nombre que aparece en el parámetro Stages de la variable <span class="filepath"> Transformation.cfg</span> para el perfil del conjunto de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformaciones </td> 
   <td colname="col2"> Opcional. Define las transformaciones de datos que deben aplicarse durante la transformación. Para obtener información sobre los tipos de transformación disponibles, consulte <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones de datos</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obtener descripciones de los parámetros de la variable [!DNL Transformation.cfg] archivo, consulte [Archivo de configuración de transformación](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Siempre que trabaje con [!DNL Transformation Dataset Include] archivos:

* Cambiar cualquiera de los parámetros de este archivo requiere la retransformación de los datos.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]y [!DNL AppendURI] las transformaciones solo funcionan cuando se definen en una [!DNL Transformation Dataset Configuration] archivo. Para obtener información sobre estas transformaciones, consulte [Transformaciones de datos](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Puede agregar cualquiera de los parámetros descritos anteriormente al [!DNL Transformation Dataset Include] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en Data Workbench. Al añadir un nuevo parámetro, utilice la tecla Space (no la tecla Tab) para sangrar dos espacios (2) a la derecha del nivel de encabezado anterior.

Si se suscribe al Adobe [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] servicio de datos, Adobe le proporciona un perfil interno que consta de un conjunto de transformaciones de datos y dimensiones ampliadas que se crean específicamente para el servicio de datos. Las transformaciones y dimensiones se definen en [!DNL Transformation Dataset Include] archivos que se incluyen en el directorio Dataset del perfil interno. Para obtener instrucciones para instalar el perfil interno de la variable [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] servicio de datos, consulte la *Guía del usuario de Data Workbench*.
