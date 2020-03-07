---
description: Pasos para editar el archivo Log Processing.cfg para un perfil de conjunto de datos.
solution: Analytics
title: Edición del archivo de configuración de procesamiento de registros
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Edición del archivo de configuración de procesamiento de registros{#editing-the-log-processing-configuration-file}

Pasos para editar el archivo Log Processing.cfg para un perfil de conjunto de datos.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.

   Para obtener información sobre cómo abrir y trabajar con el [!DNL Profile Manager], consulte la Guía del usuario *del área de trabajo de datos*.

   >[!NOTE]
   >
   >Puede existir un subdirectorio de Procesamiento de registros dentro del directorio Dataset. Este subdirectorio contiene los [!DNL Log Processing Dataset Include] archivos que se han creado para uno o varios perfiles heredados. Consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Log Processing.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Aparecerá la [!DNL Log Processing.cfg] ventana.

   También puede abrir el [!DNL Log Processing.cfg] archivo desde un [!DNL Transformation Dependency Map]. Para obtener información sobre los mapas de dependencia de transformación, consulte Herramientas [de configuración de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)conjuntos de datos.

1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía.

   Al editar el [!DNL Log Processing.cfg] archivo dentro de una ventana del área de trabajo de datos, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar ( Ctrl+x ), copiar ( Ctrl+c), pegar ( Ctrl+v ), deshacer ( Ctrl+z ), rehacer ( Ctrl+Mayús+z ), seleccionar la sección (hacer clic+arrastrar) y seleccionar todo ( Ctrl+a ). También puede utilizar los métodos abreviados para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

   >[!NOTE]
   >
   >Un [!DNL Log Processing Dataset Include] archivo para un perfil heredado contiene un subconjunto de los parámetros descritos en la siguiente tabla, así como algunos parámetros adicionales. Consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parámetro </th> 
      <th colname="col2" class="entry"> Descripción </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Fuentes de registro </td> 
      <td colname="col2"> Las fuentes de datos. Consulte Fuentes <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de finalización </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora hasta esta hora, pero sin incluirlas. Adobe recomienda utilizar uno de los siguientes formatos para el momento: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 de enero de 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> <p>Por ejemplo, si se especifica el 29 de julio de 2013, 00:00:00 EDT como hora de finalización, se incluyen los datos hasta el 28 de julio de 2013, a las 11:59:59 PM EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos </a>. </p> <p>Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor del área de trabajo de datos, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> <p>Nota:  El parámetro Usar hora de inicio/fin para fuentes <span class="wintitle"> Sensor </span>, registro y XML está relacionado con este parámetro. Consulte las secciones de Fuentes de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> registro </a> que analizan estos tipos de fuentes. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Campos </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir <span class="wintitle"> los campos </span> en uno o más archivos <span class="wintitle"> de inclusión de conjuntos de datos de procesamiento de registros </span> . Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Log Processing Dataset Include Files </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes de clave máxima del grupo </td> 
      <td colname="col2"> <p>Cantidad máxima de datos de eventos que el servidor puede procesar para un único ID de seguimiento. Los datos que excedan este límite se filtran del proceso de construcción del conjunto de datos. Este valor debe establecerse en 2e6 cuando la división de claves está activa y en 1e6 cuando la división de claves no está activa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División de claves </a>. </p> <p> <p>Nota:  No cambie este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Umbral de hash </td> 
      <td colname="col2"> <p>Opcional. Factor de muestreo para el submuestreo aleatorio de filas. Si se establece en un número n, sólo uno de cada ID de seguimiento n ingresa al conjunto de datos, reduciendo el número total de filas en el conjunto de datos por un factor de n. </p> <p>Para crear un conjunto de datos que requiera una precisión del 100 por ciento (es decir, para incluir todas las filas), debe establecer el umbral hash en 1. </p> <p>Valores: </p> <span class="filepath"> Umbral hash = 1 </span> (100 por ciento de los datos, incluidas todas las filas). <p> <span class="filepath"> Umbral hash = 2 </span> (1/2 de datos e incluye la mitad de las filas). </p> <p> <span class="filepath"> Umbral hash = 3 </span>(1/3 de datos e incluye una de tres filas, pero se redondea al 34% en Finalización de consulta) </p> <p> <span class="filepath"> Umbral hash = 4 </span>(1/4 de los datos e incluye una de cada cuatro filas). </p> <p> </p> <p> <p>Nota:  El uso de un umbral <span class="filepath"> hash = 8 </span> proporciona 1/8 de los datos, que es 12,5%. Sin embargo, el valor de Finalización de <span class="uicontrol"> consultas </span> se redondea al 13 % para este valor. Otros ejemplos incluyen un <span class="filepath"> Umbral hash = 6 </span> que resulta en una resolución de consulta del 17%. Un umbral <span class="filepath"> hash = 13 </span>resulta en una resolución de consulta del 8 %. </p> </p> <p>Si <span class="wintitle"> el umbral de hash </span> se especifica en los archivos <span class="filepath"> Log Processing.cfg </span> y <span class="filepath"> </span> Transformation.cfg, no se aplica en secuencia; se aplica el valor máximo establecido en cualquier archivo de configuración. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condición de entrada de registro </td> 
      <td colname="col2"> Opcional. Define las reglas según las cuales se consideran las entradas de registro para su inclusión en el conjunto de datos. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Volver a procesar </td> 
      <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Al cambiar este parámetro y guardar el archivo en el equipo del servidor del área de trabajo de datos, se inicia el reprocesamiento de datos. </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir espacio del bloque de claves </td> 
      <td colname="col2"> <p>Parámetro involucrado en la división de claves. Su valor debe ser 6e6 cuando la división de claves está activa. Consulte <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> División de claves </a>. </p> <p> <p>Nota:  No cambie este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir bytes clave </td> 
      <td colname="col2"> <p>Parámetro involucrado en la división de claves. Su valor debe ser 1e6 cuando la división de claves está activa y 0 cuando la división de claves no está activa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División de claves </a>. </p> <p> <p>Nota:  No cambie este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proporción de espacio clave dividida </td> 
      <td colname="col2"> <p>Parámetro involucrado en la división de claves. Su valor debe ser 10 cuando la división de claves está activa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División de claves </a>. </p> <p> <p>Nota:  No cambie este valor sin consultar con Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Etapas </td> 
      <td colname="col2"> <p>Opcional. Los nombres de las etapas de procesamiento que se pueden utilizar en los <span class="wintitle"> </span> archivos de inclusión de conjuntos de datos de procesamiento de registros. Las etapas de procesamiento proporcionan una manera de ordenar las transformaciones que se definen en los <span class="wintitle"> archivos de inclusión de conjuntos de datos de procesamiento de registros </span> . Este parámetro es muy útil si ha definido una o más transformaciones dentro de varios <span class="wintitle"> conjuntos de datos de procesamiento de registros Incluir </span> archivos y desea que se realicen transformaciones específicas en puntos específicos durante el procesamiento del registro. </p> <p>El orden en el que se enumeran las fases aquí determina el orden en el que se ejecutan las transformaciones en el conjunto de datos de procesamiento de registros <span class="wintitle"> Incluir </span> archivos durante el procesamiento del registro. El preprocesamiento y el postprocesamiento son fases integradas. El preprocesamiento es siempre la primera etapa y el postprocesamiento es siempre la última. De forma predeterminada, hay una etapa denominada Predeterminado. </p> <p> <b>Para agregar una nueva etapa de procesamiento</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">En la ventana <span class="filepath"> Log Processing.cfg </span> , haga clic con el botón derecho en <span class="uicontrol"> Etapas </span> y haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Etapa </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Escriba un nombre para la nueva etapa. </li> 
      </ul> </p> <p> <b>Para eliminar una etapa de procesamiento existente</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Haga clic con el botón secundario en el número correspondiente al escenario que desee eliminar y haga clic en <span class="uicontrol"> Eliminar </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Nota:  Cuando se especifica un <span class="wintitle"> escenario </span> en un conjunto de datos de procesamiento <span class="wintitle"> de registros, se incluyen </span> archivos, el nombre del escenario debe coincidir exactamente con el nombre que se especifica aquí. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Conjunto de datos Incluir archivos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de inicio </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora en este momento o después. Adobe recomienda utilizar uno de los siguientes formatos para el momento: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 de enero de 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si especifica "29 de julio de 2013, 00:00:00 EDT", la hora de inicio incluirá datos a partir del 29 de julio de 2013, a las 12:00:00 AM EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos </a>. </p> <p> Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor del área de trabajo de datos, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> <p>Nota:  El parámetro Usar hora de inicio/fin para fuentes <span class="wintitle"> Sensor </span>, registro y XML está relacionado con este parámetro. Consulte las secciones de Fuentes de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> registro </a> que analizan estos tipos de fuentes. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zona horaria </td> 
      <td colname="col2"> <p>Opcional. Zona horaria del servidor del área de trabajo de datos que se utiliza para las conversiones de tiempo (como la conversión representada por el campo x-local-timestring) durante el procesamiento del registro. </p> <p> <p>Nota:  Debe especificar el huso horario si desea acceder al campo de tiempo convertido durante la fase de procesamiento del registro de la construcción de conjuntos de datos. De lo contrario, el servidor del área de trabajo de datos registra un error en los registros de eventos. </p> </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Husos horarios </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformaciones </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir transformaciones para el procesamiento de registros en uno o varios <span class="wintitle"> </span> archivos de inclusión de conjuntos de datos de procesamiento de registros. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Log Processing Dataset Include Files </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En la [!DNL Profile Manager], haga clic con el botón secundario [!DNL Log Processing.cfg]en la marca de verificación de la [!DNL User] columna y, a continuación, haga clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* para que los cambios realizados localmente tengan efecto. El reprocesamiento de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

   Para obtener más información sobre el reprocesamiento de los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
