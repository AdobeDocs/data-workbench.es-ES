---
description: El archivo Incluir conjunto de datos de transformación para un perfil heredado contiene parámetros asociados con la fase de transformación de la construcción de conjuntos de datos.
solution: Analytics
title: Conjuntos de datos de transformación incluyen archivos
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Conjuntos de datos de transformación incluyen archivos{#transformation-dataset-include-files}

El archivo Incluir conjunto de datos de transformación para un perfil heredado contiene parámetros asociados con la fase de transformación de la construcción de conjuntos de datos.

La primera línea del archivo define un tipo [!DNL TransformationInclude] que admite los parámetros Dimensiones extendidas, Parámetros, Reprocesamiento, Fase y Transformaciones. Todos los demás parámetros deben definirse en el archivo [!DNL Transformation.cfg] del directorio Dataset del perfil del conjunto de datos.

La inclusión de parámetros que no sean Dimensiones extendidas, Parámetros, Reprocesamiento, Fase y Transformaciones en un [!DNL Transformation Dataset Include] archivo genera errores.

Puede nombrar un [!DNL Transformation Dataset Include] archivo como desee, pero su extensión debe ser [!DNL .cfg]. El archivo debe almacenarse en el nombre del perfil *heredado*\Dataset\Transformation directory. Debido a que los archivos se cargan de forma recursiva durante la fase de transformación de la construcción de conjuntos de datos, puede almacenar los [!DNL Transformation Dataset Include] archivos en cualquier nivel dentro del directorio (por ejemplo, nombre *de perfil* heredado \Dataset\Transformation\*nombre de carpeta*\*incluir nombre de archivo*.cfg).

>[!NOTE]
>
>Muchos parámetros de configuración específicos de Web para el sitio se definen en [!DNL Transformation Dataset Include] los archivos. Para obtener información sobre estos parámetros, consulte Configuración [de configuración para datos](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)web.

En la tabla siguiente se describen los parámetros disponibles en un [!DNL Transformation Dataset Include] archivo:

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
   <td colname="col2"> Opcional. Define las dimensiones extendidas. Consulte <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensiones</a>ampliadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parámetros </td> 
   <td colname="col2"> Opcional. Variable a la que se puede hacer referencia en otros parámetros de configuración. Para obtener más información, consulte <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en Conjunto de datos Incluir archivos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Volver a procesar </td> 
   <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo, se inicia la retransformación de datos. </p> <p> Para obtener información sobre el reprocesamiento de los datos, consulte <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fase </td> 
   <td colname="col2"> <p>Opcional. Nombre de la etapa de procesamiento que se aplica a este <span class="wintitle"> archivo de inclusión</span> de conjunto de datos de transformación. Las etapas de procesamiento se definen en el parámetro Stages del <span class="filepath"> archivo Transformation.cfg</span> . </p> <p> <p>Nota: Cuando se especifica un escenario, el nombre del escenario debe coincidir exactamente con el nombre que aparece en el parámetro Stages del <span class="filepath"> archivo Transformation.cfg</span> para el perfil del conjunto de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformaciones </td> 
   <td colname="col2"> Opcional. Define las transformaciones de datos que deben aplicarse durante la transformación. Para obtener información sobre los tipos de transformación disponibles, consulte <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones</a>de datos. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obtener descripciones de los parámetros del [!DNL Transformation.cfg] archivo, consulte Archivo [de configuración de](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)transformación.

Siempre que trabaje con [!DNL Transformation Dataset Include] archivos, debe tener en cuenta los siguientes puntos:

* Cambiar cualquiera de los parámetros de este archivo requiere la retransformación de los datos.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]y [!DNL AppendURI] las transformaciones solo funcionan cuando se definen en un [!DNL Transformation Dataset Configuration] archivo. Para obtener información sobre estas transformaciones, consulte Transformaciones [de datos](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Transformation Dataset Include] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en el área de trabajo de datos. Al agregar un parámetro nuevo, utilice la tecla Espacio (no la tecla Tab) para sangrar dos (2) espacios a la derecha del nivel de encabezado anterior.

Si se suscribe al servicio de datos [!DNL IP Geo-location] [!DNL IP Geo-intelligence] o al servicio de datos de Adobe, Adobe le proporciona un perfil interno que consta de un conjunto de transformaciones de datos y dimensiones ampliadas que se crean específicamente para el servicio de datos. Las transformaciones y dimensiones se definen en [!DNL Transformation Dataset Include] archivos que se incluyen en el directorio Dataset del perfil interno. Para obtener instrucciones sobre cómo instalar el perfil interno del servicio de datos [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] , consulte la Guía *del usuario* del área de trabajo de datos.
