---
description: Pasos para editar el archivo Log Processing.cfg para un perfil de conjunto de datos.
title: Edición del archivo de configuración de procesamiento de registros
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 2%

---

# Edición del archivo de configuración de procesamiento de registros{#editing-the-log-processing-configuration-file}

{{eol}}

Pasos para editar el archivo Log Processing.cfg para un perfil de conjunto de datos.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.

   Para obtener información sobre cómo abrir y trabajar con la variable [!DNL Profile Manager], consulte la *Guía del usuario de Data Workbench*.

   >[!NOTE]
   >
   >Puede existir un subdirectorio de Procesamiento de registros dentro del directorio de conjuntos de datos. Este subdirectorio contiene la variable [!DNL Log Processing Dataset Include] archivos que se han creado para uno o más perfiles heredados. Consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Log Processing.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. La variable [!DNL Log Processing.cfg] se abre.

   También puede abrir el [!DNL Log Processing.cfg] desde un [!DNL Transformation Dependency Map]. Para obtener información sobre los mapas de dependencia de transformación, consulte [Herramientas de configuración de conjuntos de datos](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía.

   Al editar el [!DNL Log Processing.cfg] en una ventana de Data Workbench, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar ( Ctrl+x ), copiar ( Ctrl+c) , pegar ( Ctrl+v ), deshacer ( Ctrl+z ), rehacer ( Ctrl+Mayús+z ), seleccionar sección (clic+arrastrar) y seleccionar todo ( Ctrl+a ). También puede utilizar los accesos directos para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

   >[!NOTE]
   >
   >A [!DNL Log Processing Dataset Include] para un perfil heredado contiene un subconjunto de los parámetros descritos en la siguiente tabla, así como algunos parámetros adicionales. Consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

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
      <td colname="col2"> Las fuentes de datos. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fuentes de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de finalización </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de tiempo hasta, pero no esta vez. Adobe recomienda usar uno de los siguientes formatos para el momento: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 de enero de 2013 HH:MM:SED EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1 de Enero del 2013 HH:MM:SS GMT </li> 
      </ul> <p>Por ejemplo, si especifica 29 de julio de 2013 00:00:00 EDT, ya que la hora de finalización incluye datos hasta el 28 de julio de 2013, a las 11:59:59 PM EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos </a>. </p> <p>Debe especificar una zona horaria. La zona horaria no toma el valor predeterminado GMT si no se especifica. Para obtener una lista de abreviaciones de zona horaria admitidas por el servidor de Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de huso horario </a>. </p> <p> <p>Nota: El parámetro Use Start/End Times para <span class="wintitle"> Sensor </span>, el archivo de registro y los orígenes XML están relacionados con este parámetro. Consulte las secciones de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fuentes de registro </a> que analizan estos tipos de fuentes. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Campos </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir <span class="wintitle"> Campos </span> en uno o más <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> archivos. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Archivos de inclusión de conjunto de datos de procesamiento de registros </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes de clave máxima del grupo </td> 
      <td colname="col2"> <p>Cantidad máxima de datos de evento que el servidor puede procesar para un único ID de seguimiento. Los datos que exceden este límite se filtran del proceso de construcción del conjunto de datos. Este valor debe establecerse en 2e6 cuando la división de claves esté activa y 1e6 cuando la división de claves no esté activa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División clave </a>. </p> <p> <p>Nota: No cambie este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Umbral hash </td> 
      <td colname="col2"> <p>Opcional. Un factor de muestreo para el submuestreo aleatorio de filas. Si se establece en un número n, solo uno de cada n ID de seguimiento ingresa al conjunto de datos, lo que reduce el número total de filas en el conjunto de datos en un factor de n. </p> <p>Para crear un conjunto de datos que requiera una precisión del 100 por ciento (es decir, para incluir todas las filas), establecería el umbral hash en 1. </p> <p>Valores: </p> <span class="filepath"> Umbral de hash = 1 </span> (el 100 % de los datos, incluidas todas las filas). <p> <span class="filepath"> Umbral de hash = 2 </span> (1/2 de datos e incluye la mitad de las filas). </p> <p> <span class="filepath"> Umbral de hash = 3 </span>(1/3 de datos e incluye una de las tres filas, pero se redondea al 34% en Finalización de consulta) </p> <p> <span class="filepath"> Umbral de hash = 4 </span>(1/4 de los datos e incluye una de cada cuatro filas). </p> <p> </p> <p> <p>Nota: Uso de un <span class="filepath"> Umbral de hash = 8 </span> proporciona una octava parte de los datos, que es del 12,5%. Sin embargo, la variable <span class="uicontrol"> Finalización de la consulta </span> en redondea al 13% para este valor. Algunos ejemplos adicionales incluyen una <span class="filepath"> Umbral de hash = 6 </span> que resulta en una resolución de consulta del 17%. A <span class="filepath"> Umbral hash = 13 </span>genera una resolución de consulta del 8 %. </p> </p> <p>If <span class="wintitle"> Umbral hash </span> se especifica en <span class="filepath"> Log Processing.cfg </span> y <span class="filepath"> Transformation.cfg </span> archivos, no se aplica en secuencia; se aplica el valor máximo establecido en cualquier archivo de configuración. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condición de entrada de registro </td> 
      <td colname="col2"> Opcional. Define las reglas según las cuales se tienen en cuenta las entradas de registro para su inclusión en el conjunto de datos. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Volver a procesar </td> 
      <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo en el equipo del servidor de Data Workbench, se inicia el reprocesamiento de datos. </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir espacio del bloque de claves </td> 
      <td colname="col2"> <p>Parámetro involucrado en la división de claves. Su valor debe ser 6e6 cuando la división de claves está activa. Consulte <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> División clave </a>. </p> <p> <p>Nota: No cambie este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes de clave divididos </td> 
      <td colname="col2"> <p>Parámetro involucrado en la división de claves. Su valor debe ser 1e6 cuando la división de claves está activa y 0 cuando la división de claves no está activa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División clave </a>. </p> <p> <p>Nota: No cambie este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proporción de espacio de clave dividida </td> 
      <td colname="col2"> <p>Parámetro involucrado en la división de claves. Su valor debe ser 10 cuando la división de claves está activa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> División clave </a>. </p> <p> <p>Nota: No cambie este valor sin consultar el Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Etapas </td> 
      <td colname="col2"> <p>Opcional. Los nombres de las fases de procesamiento que se pueden utilizar en <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> archivos. Las etapas de procesamiento proporcionan una forma de ordenar las transformaciones definidas en <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> archivos. Este parámetro es muy útil si ha definido una o más transformaciones dentro de varios <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> y desea que se realicen transformaciones específicas en puntos específicos durante el procesamiento del registro. </p> <p>El orden en el que se enumeran las etapas determina el orden en el que las transformaciones de la variable <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> se ejecutan durante el procesamiento del registro. El procesamiento previo y el posprocesamiento son etapas integradas. El preprocesamiento siempre es la primera etapa y el postprocesamiento siempre es la última. De forma predeterminada, hay un escenario llamado Predeterminado. </p> <p> <b>Adición de una nueva fase de procesamiento</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">En el <span class="filepath"> Log Processing.cfg </span> ventana, clic con el botón derecho <span class="uicontrol"> Etapas </span> y haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Prueba </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Introduzca un nombre para la nueva etapa. </li> 
      </ul> </p> <p> <b>Eliminar una etapa de procesamiento existente</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Haga clic con el botón derecho en el número correspondiente al escenario que desee eliminar y haga clic en <span class="uicontrol"> Eliminar </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Nota: Al especificar un <span class="wintitle"> Prueba </span> en un <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> , el nombre del escenario debe coincidir exactamente con el nombre que escriba aquí. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Archivos de inclusión de conjunto de datos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de inicio </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora en o después de esta hora. Adobe recomienda usar uno de los siguientes formatos para el momento: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 de enero de 2013 HH:MM:SED EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1 de Enero del 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si especifica "29 de julio de 2013 00:00:00 EDT", ya que la hora de inicio incluye datos a partir del 29 de julio de 2013, a las 12:00:00 AM EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos </a>. </p> <p> Debe especificar una zona horaria. La zona horaria no toma el valor predeterminado GMT si no se especifica. Para obtener una lista de abreviaciones de zona horaria admitidas por el servidor de Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de huso horario </a>. </p> <p> <p>Nota: El parámetro Use Start/End Times para <span class="wintitle"> Sensor </span>, el archivo de registro y los orígenes XML están relacionados con este parámetro. Consulte las secciones de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fuentes de registro </a> que analizan estos tipos de fuentes. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zona horaria </td> 
      <td colname="col2"> <p>Opcional. Zona horaria del servidor de Data Workbench que se utiliza para las conversiones horarias (como la conversión representada por el campo x-local-timestring ) durante el procesamiento del registro. </p> <p> <p>Nota: Debe especificar la zona horaria si desea acceder al campo de tiempo convertido durante la fase de procesamiento de registros de la construcción del conjunto de datos. De lo contrario, el servidor de Data Workbench registra un error en los registros de eventos. </p> </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zonas horarias </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformaciones </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir transformaciones para el procesamiento de registros en uno o más <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros </span> archivos. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Archivos de inclusión de conjunto de datos de procesamiento de registros </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Log Processing.cfg]en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* para que los cambios realizados localmente tengan efecto. El reprocesamiento de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

   Para obtener más información sobre cómo reprocesar los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
