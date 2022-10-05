---
description: Pasos para editar el archivo Transformation.cfg para un perfil de conjunto de datos.
title: Edición del archivo de configuración de transformación
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---

# Edición del archivo de configuración de transformación{#editing-the-transformation-configuration-file}

{{eol}}

Pasos para editar el archivo Transformation.cfg para un perfil de conjunto de datos.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.

   Para obtener información sobre cómo abrir y trabajar con la variable [!DNL Profile Manager], consulte la *Guía del usuario de Data Workbench*.

   >[!NOTE]
   >
   >Puede existir un subdirectorio Transformation dentro del directorio Dataset . Este subdirectorio contiene la variable [!DNL Transformation Dataset Include] archivos que se han creado para uno o más perfiles heredados. Para obtener información sobre [!DNL Transformation Dataset Include] archivos, consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Transformation.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. La variable [!DNL Transformation.cfg] se abre.

   También puede abrir el [!DNL Transformation.cfg] desde un [!DNL Transformation Dependency Map]. Para obtener información sobre [!DNL transformation dependency maps], consulte [Herramientas de configuración de conjuntos de datos](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía.

   Al editar el [!DNL Transformation.cfg] en una ventana de Data Workbench, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x ), copiar (Ctrl+c), pegar (Ctrl+v ), deshacer (Ctrl+z ), rehacer (Ctrl+Mayús+z ), seleccionar sección (clic+arrastrar) y seleccionar todo (Ctrl+a ). Además, puede utilizar los accesos directos para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] Los archivos de un perfil heredado contienen un subconjunto de los parámetros descritos en la siguiente tabla, así como algunos parámetros adicionales. Para obtener información sobre [!DNL Transformation Dataset Include] archivos, consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parámetro </th> 
      <th colname="col2" class="entry"> Descripción </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Hora de finalización </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de tiempo hasta, pero no incluidas, esta vez. Adobe recomienda usar uno de los siguientes formatos para el momento: 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 de enero de 2013 HH:MM:SED EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1 de Enero del 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si especifica "29 de julio de 2013 00:00:00 EDT", ya que la hora de finalización incluye datos hasta el 28 de julio de 2013, a las 11:59:59 PM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no toma el valor predeterminado GMT si no se especifica. Para obtener una lista de abreviaciones de zona horaria admitidas por el servidor de Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de huso horario </a>. </p> <p> <p>Nota: Si especifica un valor para Hora de finalización, se establece y aplica un parámetro denominado Hora de finalización durante la fase de transformación de la construcción del conjunto de datos. Para obtener información sobre los parámetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en archivos de inclusión de conjuntos de datos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensiones extendidas </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir dimensiones extendidas en una o más <span class="wintitle"> Incluir conjunto de datos de transformación </span> archivos. Para obtener más información, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Archivos de inclusión de conjunto de datos de transformación </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Umbral hash </td> 
      <td colname="col2"> <p>Opcional. Un factor de muestreo para el submuestreo aleatorio de filas. Si se establece en un número n, solo uno de cada n ID de seguimiento ingresa al conjunto de datos, lo que reduce el número total de filas en el conjunto de datos en un factor de n. Para crear un conjunto de datos que requiera una precisión del 100 por ciento (es decir, para incluir todas las filas), establecería el umbral hash en 1. </p> <p> Si el umbral hash se especifica en ambas <span class="filepath"> Log Processing.cfg </span> y <span class="filepath"> Transformation.cfg </span> archivos, no se aplica en secuencia; se aplica el máximo de los valores establecidos en cualquier archivo de configuración. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condición de entrada de registro </td> 
      <td colname="col2"> Opcional. Define las reglas según las cuales las entradas de registro que salen del procesamiento de registros se consideran para su inclusión en el perfil del conjunto de datos. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condición de nuevo visitante </td> 
      <td colname="col2"> Opcional. Para su uso con datos web. Define las reglas según las cuales se considera a los visitantes para su inclusión en los datos. La variable <span class="wintitle"> Condición de nuevo visitante </span> define la primera entrada de registro de un visitante (ordenada por el tiempo) que se utilizará en el conjunto de datos. Todas las entradas de registro subsiguientes para este visitante se incluyen en el conjunto de datos independientemente de si cumplen esta condición. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Condición de nuevo visitante </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Volver a procesar </td> 
      <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo, se iniciará la retransformación de datos. </p> <p> Para obtener información sobre cómo reprocesar los datos, consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Comprobación de esquema </td> 
      <td colname="col2"> Verdadero o falso. Si es true, el servidor de Data Workbench identifica problemas de corrupción de conjuntos de datos y registra información sobre los problemas en los archivos de registro en el directorio Trace del servidor de Data Workbench. El valor predeterminado es true. Adobe recomienda dejar este parámetro establecido como verdadero en todo momento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Etapas </td> 
      <td colname="col2"> <p>Opcional. Los nombres de las fases de procesamiento que se pueden utilizar en <span class="wintitle"> Incluir conjunto de datos de transformación </span> archivos. Las etapas de procesamiento proporcionan una forma de ordenar las transformaciones definidas en <span class="wintitle"> Incluir conjunto de datos de transformación </span> archivos. Este parámetro es muy útil si ha definido una o más transformaciones dentro de varios <span class="wintitle"> Incluir conjunto de datos de transformación </span> y desea que las transformaciones específicas se realicen en puntos específicos durante la transformación. </p> <p> El orden en el que se enumeran las etapas determina el orden en el que las transformaciones de la variable <span class="wintitle"> Incluir conjunto de datos de transformación </span> se ejecutan durante la transformación. <span class="wintitle"> Preprocesamiento </span> y <span class="wintitle"> Postprocesamiento </span> son fases integradas; <span class="wintitle"> Preprocesamiento </span> es siempre la primera etapa, y <span class="wintitle"> Postprocesamiento </span> es siempre el último paso. De forma predeterminada, hay un escenario llamado <span class="wintitle"> Predeterminado </span>. </p> <p> <b>Adición de una nueva fase de procesamiento</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> En el <span class="filepath"> Transformation.cfg </span> ventana, clic con el botón derecho <span class="uicontrol"> Etapas </span> y haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Prueba </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Introduzca un nombre para la nueva etapa. </li> 
      </ul> </p> <p> <b>Eliminar una etapa de procesamiento existente</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Haga clic con el botón derecho en el número correspondiente al escenario que desee eliminar y haga clic en <span class="uicontrol"> Eliminar </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Nota: Cuando se especifica un escenario en un <span class="wintitle"> Incluir conjunto de datos de transformación </span> archivos el nombre del escenario debe coincidir exactamente con el nombre que escriba aquí. Para obtener más información sobre los archivos de inclusión de conjuntos de datos, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Archivos de inclusión de conjunto de datos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de inicio </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora en o después de esta hora. Adobe recomienda usar uno de los siguientes formatos para el momento: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 de enero de 2013 HH:MM:SED EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 de Enero del 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si especifica 29 de julio de 2013 00:00:00 EDT como <span class="wintitle"> Hora de inicio </span> incluye datos a partir del 29 de julio de 2013, a las 12:00:00 AM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no toma el valor predeterminado GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor de Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de huso horario </a>. </p> <p> <p>Nota: Si especifica un valor para la Hora de inicio, se establecerá y aplicará un parámetro denominado Hora de inicio durante la fase de transformación de la construcción del conjunto de datos. Para obtener información sobre los parámetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en archivos de inclusión de conjuntos de datos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformaciones </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir transformaciones para la fase de transformación de la construcción de conjuntos de datos en uno o más <span class="wintitle"> Incluir conjunto de datos de transformación </span> archivos. Para obtener más información, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Archivos de inclusión de conjunto de datos de transformación </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zona horaria </td> 
      <td colname="col2"> <p>Zona horaria del perfil del conjunto de datos. Las zonas horarias se utilizan para las conversiones horarias y para la creación de dimensiones horarias. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Zonas horarias </a>. </p> <p> <p>Nota: Cuando se define en la variable <span class="filepath"> Log Processing.cfg </span> , el parámetro Zona horaria se utiliza solo para conversiones horarias. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Transformation.cfg]en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** para que los cambios realizados localmente tengan efecto. La retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

   Para obtener información sobre cómo reprocesar o retransformar los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
