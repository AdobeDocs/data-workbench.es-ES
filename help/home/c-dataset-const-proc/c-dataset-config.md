---
description: La configuración del conjunto de datos hace referencia al proceso de edición de los archivos de configuración cuyos parámetros proporcionan las reglas para la construcción del conjunto de datos.
title: Explicación de la configuración del conjunto de datos
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 7%

---

# Explicación de la configuración del conjunto de datos{#understanding-dataset-configuration}

La configuración del conjunto de datos hace referencia al proceso de edición de los archivos de configuración cuyos parámetros proporcionan las reglas para la construcción del conjunto de datos.

El conjunto de datos construido reside físicamente en el archivo [!DNL temp.db] almacenado en el equipo servidor de Data Workbench, pero los archivos de configuración del conjunto de datos residen en un directorio para un perfil. Un perfil contiene un conjunto de archivos de configuración que construyen un conjunto de datos (incluidas sus dimensiones ampliadas) para un propósito de análisis específico. Además, un perfil contiene las definiciones de entidades como métricas, dimensiones derivadas, espacios de trabajo, informes y visualizaciones que permiten a los analistas interactuar con el conjunto de datos y obtener información de él.

El perfil cuyos archivos de configuración de conjuntos de datos está editando se denomina perfil de conjuntos de datos. Un perfil de conjunto de datos hace referencia a varios perfiles heredados, que pueden ser cualquier perfil que cree y mantenga para que pueda configurar la aplicación de Adobe para que se ajuste mejor a sus necesidades de análisis. Un perfil de conjunto de datos también puede hacer referencia a perfiles internos que se proporcionan con la aplicación de Adobe para formar la base de toda la funcionalidad disponible en la aplicación.

Para obtener más información sobre los distintos tipos de perfiles disponibles con aplicaciones de Adobe, consulte la *Guía del usuario de Data Workbench*.

<!--
c_req_config_files.xml
-->

Un perfil de conjunto de datos para cualquier aplicación de Adobe debe contener los siguientes archivos de configuración en el equipo de Insight Server:

* **Profile.cfg:** enumera los perfiles heredados y los servidores de procesamiento del perfil. Los servidores de procesamiento son las DPU de Insight Server que procesan los datos del perfil. Si ha instalado un clúster de Insight Server, puede especificar varios equipos de Insight Server para ejecutar un único perfil.

   Para obtener instrucciones para agregar perfiles heredados al archivo [!DNL Profile.cfg] de un perfil de conjunto de datos, consulte la *Guía de instalación y administración de productos de servidor*. Para obtener información sobre la instalación de un clúster de Insight Server o la configuración de un perfil de conjunto de datos para que se ejecute en un clúster de Insight Server, consulte la *Guía de instalación y administración de productos de servidor*.

* **Dataset\Log Processing.cfg:** controla la fase de procesamiento de registros del proceso de construcción del conjunto de datos. Consulte [Procesamiento de registros](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Para obtener más información sobre el archivo [!DNL Log Processing.cfg], consulte [Archivo de configuración de procesamiento de registros](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **Dataset\Transformation.cfg:** controla la fase de transformación del proceso de construcción del conjunto de datos. Consulte [Transformation](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). El archivo [!DNL Transformation.cfg] suele configurar el conjunto de datos para un análisis específico del perfil. Para obtener más información sobre el archivo [!DNL Transformation.cfg], consulte [Archivo de configuración de transformación](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **Archivos de inclusión de conjunto de datos:** un  [!DNL dataset include] archivo contiene un subconjunto de los parámetros contenidos en el  [!DNL Log Processing.cfg] archivo  [!DNL Transformation.cfg] o para el perfil del conjunto de datos, pero se almacena y administra dentro de un perfil heredado. [!DNL Dataset include] los archivos complementan los archivos de configuración del conjunto de datos principal. Para obtener más información, consulte [Archivos de inclusión de conjunto de datos](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

El perfil del conjunto de datos que se le proporcionó durante la implementación de la aplicación de Adobe contiene un conjunto de archivos de configuración de conjuntos de datos que puede abrir, editar y guardar con [!DNL Profile Manager].

Para obtener más información sobre [!DNL Profile Manager], consulte la *Guía del usuario de Insight*.

<!--
c_addl_config_files.xml
-->

Aunque no es necesario para todos los conjuntos de datos, estos archivos permiten controlar otros aspectos del proceso de construcción del conjunto de datos:

* **Log Processing Mode.cfg:** el  [!DNL Log Processing Mode.cfg] archivo permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Data Workbench guarda sus archivos de estado. Consulte [Archivos de configuración adicionales](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** el  [!DNL Server.cfg] archivo especifica el tamaño predeterminado de la caché de datos (en bytes) para los equipos de Data Workbench que se conectan al servidor de Data Workbench. Consulte [Archivos de configuración adicionales](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg y Transform Mode.cfg:**  estos archivos solo están disponibles si dispone de licencia para la funcionalidad de transformación de datos que se utiliza con la aplicación Adobe. El archivo [!DNL Transform.cfg] contiene los parámetros que definen las fuentes de registro y las transformaciones de datos para la funcionalidad de transformación. Las transformaciones que defina manipularán los datos de origen y los generarán en un formato que especifique. El archivo [!DNL Insight Transform Mode.cfg] permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Insight que ejecuta la funcionalidad de transformación guarda sus archivos de estado. Consulte [Funcionalidad de transformación](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Para obtener información sobre tareas específicas de configuración de conjuntos de datos, utilice la siguiente tabla para localizar y leer las tareas que le interesen:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si quieres... </th> 
   <th colname="col2" class="entry"> Consulte... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definir fuentes de registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fuentes de registro </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinar qué entradas de registro entran en el conjunto de datos durante el procesamiento del registro </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Habilitar la división de ID de seguimiento con grandes cantidades de datos de evento </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División clave</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuración de un servidor de Insight para que se ejecute como una unidad de servidor de archivos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuración de un servidor de Insight para que se ejecute como servidor de normalización centralizado </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Establezca la zona horaria que se utilizará para crear dimensiones horarias y realizar conversiones horarias </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zonas horarias </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realice cambios menores en los archivos de configuración del conjunto de datos incluidos con los perfiles internos proporcionados por el Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Edición de archivos de inclusión de conjuntos de datos existentes </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Especificar nuevos campos de datos para pasar del procesamiento de registros a la transformación </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creación de nuevos archivos de inclusión de conjunto de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Archivos de inclusión de conjunto de datos de procesamiento de registros </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir transformaciones </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creación de nuevos archivos de inclusión de conjunto de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Archivos de inclusión de conjuntos de datos de transformación </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Crear dimensiones extendidas </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensiones extendidas </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creación de nuevos archivos de inclusión de conjunto de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Archivos de inclusión de conjuntos de datos de transformación </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Defina los parámetros que se usarán durante el procesamiento o transformación del registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en archivos de inclusión de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Obtenga información sobre las interfaces de Insight que le permiten supervisar o administrar su conjunto de datos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab">Trabajo con interfaces de configuración de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ocultar determinadas dimensiones extendidas para que no se muestren en el menú de dimensiones en Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anule ciertos archivos de configuración de conjuntos de datos en un perfil que no pueda modificar o que no desee modificar </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Volver a procesar el conjunto de datos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
