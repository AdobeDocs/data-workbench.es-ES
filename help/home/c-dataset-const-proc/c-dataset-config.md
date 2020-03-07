---
description: La configuración del conjunto de datos se refiere al proceso de edición de los archivos de configuración cuyos parámetros proporcionan las reglas para la construcción del conjunto de datos.
solution: Analytics
title: Explicación de la configuración del conjunto de datos
topic: Data workbench
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Explicación de la configuración del conjunto de datos{#understanding-dataset-configuration}

La configuración del conjunto de datos se refiere al proceso de edición de los archivos de configuración cuyos parámetros proporcionan las reglas para la construcción del conjunto de datos.

El conjunto de datos construido reside físicamente en el [!DNL temp.db] archivo almacenado en el equipo servidor del área de trabajo de datos, pero los archivos de configuración del conjunto de datos residen en un directorio para un perfil. Un perfil contiene un conjunto de archivos de configuración que construyen un conjunto de datos (incluidas sus dimensiones ampliadas) para un propósito de análisis específico. Además, un perfil contiene las definiciones de entidades como métricas, dimensiones derivadas, espacios de trabajo, informes y visualizaciones que permiten a los analistas interactuar con el conjunto de datos y obtener información de él.

El perfil cuyos archivos de configuración de conjuntos de datos está editando se denomina perfil de conjunto de datos. Un perfil de conjunto de datos hace referencia a varios perfiles heredados, que pueden ser cualquier perfil que cree y mantenga para que pueda configurar la aplicación de Adobe de modo que se ajuste mejor a sus necesidades de análisis. Un perfil de conjunto de datos también puede hacer referencia a perfiles internos que se proporcionan con la aplicación de Adobe para formar la base de toda la funcionalidad disponible en la aplicación.

Para obtener más información sobre los distintos tipos de perfiles disponibles con las aplicaciones de Adobe, consulte la Guía del usuario *de Área de trabajo de datos*.

<!--
c_req_config_files.xml
-->

Un perfil de conjunto de datos para cualquier aplicación de Adobe debe contener los siguientes archivos de configuración en el equipo de Insight Server:

* **Profile.cfg:** Enumera los perfiles heredados y los servidores de procesamiento del perfil. Los servidores de procesamiento son las DPU de Insight Server que procesan los datos del perfil. Si ha instalado un clúster de Insight Server, puede especificar varios equipos de Insight Server para ejecutar un solo perfil.

   Para obtener instrucciones sobre cómo agregar perfiles heredados al [!DNL Profile.cfg] archivo de perfil de conjunto de datos, consulte la Guía *de instalación y administración de productos de* servidor. Para obtener información sobre la instalación de un clúster de Insight Server o la configuración de un perfil de conjunto de datos para que se ejecute en un clúster de Insight Server, consulte la Guía *de instalación y administración de productos de* servidor.

* **Dataset\Log Processing.cfg:** Controla la fase de procesamiento del registro del proceso de construcción del conjunto de datos. Consulte Procesamiento [de registro](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Para obtener más información sobre el [!DNL Log Processing.cfg] archivo, consulte Archivo [de configuración de procesamiento](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)de registros.

* **Dataset\Transformation.cfg:** Controla la fase de transformación del proceso de construcción del conjunto de datos. Consulte [Transformación](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). El [!DNL Transformation.cfg] archivo generalmente configura el conjunto de datos para análisis específicos del perfil. Para obtener más información sobre el [!DNL Transformation.cfg] archivo, consulte Archivo [de configuración de](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)transformación.

* **Archivos de inclusión de conjunto de datos:** Un [!DNL dataset include] archivo contiene un subconjunto de los parámetros contenidos en el [!DNL Log Processing.cfg] archivo o [!DNL Transformation.cfg] para el perfil del conjunto de datos, pero se almacena y administra en un perfil heredado. [!DNL Dataset include] los archivos complementan los archivos de configuración del conjunto de datos principal. Para obtener más información, consulte [Conjunto de datos Incluir archivos](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

El perfil de conjunto de datos que se le proporciona durante la implementación de la aplicación de Adobe contiene un conjunto de archivos de configuración de conjuntos de datos que puede abrir, editar y guardar con el [!DNL Profile Manager].

Para obtener más información sobre el [!DNL Profile Manager], consulte la Guía del usuario de *Insight*.

<!--
c_addl_config_files.xml
-->

Aunque no es necesario para todos los conjuntos de datos, estos archivos le permiten controlar otros aspectos del proceso de construcción de conjuntos de datos:

* **Modo de procesamiento de registros.cfg:** El [!DNL Log Processing Mode.cfg] archivo permite pausar el procesamiento de datos en un conjunto de datos, especificar orígenes sin conexión o especificar la frecuencia con la que el servidor del área de trabajo de datos guarda los archivos de estado. Consulte Archivos [de configuración](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)adicionales.

* **Server.cfg:** El [!DNL Server.cfg] archivo especifica el tamaño de caché de datos predeterminado (en bytes) para los equipos del área de trabajo de datos que se conectan al servidor del área de trabajo de datos. Consulte Archivos [de configuración](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)adicionales.

* **Transform.cfg y Transform Mode.cfg:** Estos archivos solo están disponibles si se ha concedido una licencia para la funcionalidad de transformación de datos que se utilizará con la aplicación de Adobe. El [!DNL Transform.cfg] archivo contiene los parámetros que definen las fuentes de registro y las transformaciones de datos para la funcionalidad de transformación. Las transformaciones que defina manipularán los datos de origen y los generarán en un formato que especifique. El [!DNL Insight Transform Mode.cfg] archivo permite pausar el procesamiento de datos en un conjunto de datos, especificar fuentes sin conexión o especificar la frecuencia con la que el servidor de Insight que ejecuta la funcionalidad de transformación guarda los archivos de estado. Consulte Funcionalidad [de transformación](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Para obtener información sobre tareas de configuración de conjuntos de datos específicas, utilice la tabla siguiente para localizar y leer las tareas que le interesen:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si quieres... </th> 
   <th colname="col2" class="entry"> Consulte... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definir orígenes de registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fuentes de registro </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinar qué entradas de registro ingresan al conjunto de datos durante el procesamiento del registro </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Habilitar la división de ID de seguimiento con grandes cantidades de datos de eventos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División de claves</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar un servidor de Insight para que se ejecute como una unidad de servidor de archivos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar un servidor de Insight para que se ejecute como servidor de normalización centralizado </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configure la zona horaria que se utilizará para crear dimensiones horarias y realizar conversiones horarias </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zonas horarias </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realice pequeños cambios en los archivos de configuración del conjunto de datos incluidos con los perfiles internos proporcionados por Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Edición de archivos de inclusión de conjuntos de datos existentes </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Especificar nuevos campos de datos que se pasarán del procesamiento de registros a la transformación </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creación de nuevos archivos de inclusión de conjunto de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Archivos de inclusión de conjunto de datos de procesamiento de registros </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir transformaciones </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creación de nuevos archivos de inclusión de conjunto de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Conjuntos de datos de transformación incluyen archivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Crear dimensiones extendidas </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensiones extendidas </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creación de nuevos archivos de inclusión de conjunto de datos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Conjuntos de datos de transformación incluyen archivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir los parámetros que se usarán durante el procesamiento o transformación del registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en archivos de inclusión de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Obtenga información sobre las interfaces de Insight que le permiten monitorear o administrar su conjunto de datos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Uso De Interfaces De Configuración De Conjunto De Datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ocultar determinadas dimensiones extendidas para que no se muestren en el menú de dimensiones de Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Omitir ciertos archivos de configuración de conjuntos de datos en un perfil que no se pueden modificar o que no se desean modificar </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes de conjuntos de datos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Volver a procesar el conjunto de datos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

