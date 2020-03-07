---
description: Pasos para editar el archivo Transformation.cfg para un perfil de conjunto de datos.
solution: Analytics
title: Edición del archivo de configuración de transformación
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Edición del archivo de configuración de transformación{#editing-the-transformation-configuration-file}

Pasos para editar el archivo Transformation.cfg para un perfil de conjunto de datos.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.

   Para obtener información sobre cómo abrir y trabajar con el [!DNL Profile Manager], consulte la Guía del usuario *del área de trabajo de datos*.

   >[!NOTE]
   >
   >Puede existir un subdirectorio Transformation dentro del directorio Dataset. Este subdirectorio contiene los [!DNL Transformation Dataset Include] archivos que se han creado para uno o varios perfiles heredados. Para obtener información sobre [!DNL Transformation Dataset Include] los archivos, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Transformation.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Aparecerá la [!DNL Transformation.cfg] ventana.

   También puede abrir el [!DNL Transformation.cfg] archivo desde un [!DNL Transformation Dependency Map]. Para obtener más información [!DNL transformation dependency maps], consulte Herramientas [de configuración](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)de conjuntos de datos.

1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía.

   Al editar el [!DNL Transformation.cfg] archivo dentro de una ventana del área de trabajo de datos, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x), copiar (Ctrl+c), pegar (Ctrl+v), deshacer (Ctrl+z), rehacer (Ctrl+Mayús+z), seleccionar la sección (hacer clic+arrastrar) y seleccionar todo (Ctrl+a). Además, puede utilizar los métodos abreviados para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

   >[!NOTE]
   >
   >Los [!DNL Transformation Dataset Include] archivos de un perfil heredado contienen un subconjunto de los parámetros descritos en la siguiente tabla, así como algunos parámetros adicionales. Para obtener información sobre [!DNL Transformation Dataset Include] los archivos, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

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
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora hasta, pero sin incluirlas, esta vez. Adobe recomienda utilizar uno de los siguientes formatos para el momento: 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 de enero de 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si se especifica "29 de julio de 2013, 00:00:00 EDT" como Hora de finalización, se incluyen los datos hasta el 28 de julio de 2013, a las 11:59:59 PM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor del área de trabajo de datos, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> <p>Nota:  Si especifica un valor para Hora de finalización, se establece y aplica un parámetro denominado Hora de finalización durante la fase de transformación de la construcción de conjuntos de datos. Para obtener información sobre los parámetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en conjuntos de datos Incluir archivos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensiones extendidas </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir dimensiones extendidas en uno o varios <span class="wintitle"> archivos de inclusión de conjuntos de datos de transformación </span> . Para obtener más información, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Conjunto de datos de transformación Incluir archivos </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Umbral de hash </td> 
      <td colname="col2"> <p>Opcional. Factor de muestreo para el submuestreo aleatorio de filas. Si se establece en un número n, sólo uno de cada ID de seguimiento n ingresa al conjunto de datos, reduciendo el número total de filas en el conjunto de datos por un factor de n. Para crear un conjunto de datos que requiera una precisión del 100 por ciento (es decir, para incluir todas las filas), debe establecer el umbral hash en 1. </p> <p> Si el umbral de hash se especifica en los archivos <span class="filepath"> Log Processing.cfg </span> y <span class="filepath"> Transformation.cfg </span> , no se aplica en secuencia; se aplica el máximo de los valores establecidos en cualquier archivo de configuración. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condición de entrada de registro </td> 
      <td colname="col2"> Opcional. Define las reglas según las cuales las entradas de registro resultantes del procesamiento de registros se consideran para su inclusión en el perfil del conjunto de datos. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nueva condición de visitante </td> 
      <td colname="col2"> Opcional. Para su uso con datos web. Define las reglas según las cuales se considera a los visitantes para su inclusión en los datos. La <span class="wintitle"> condición de nuevo visitante </span> define la primera entrada de registro de un visitante (ordenada por tiempo) que se utilizará en el conjunto de datos. Todas las entradas de registro posteriores para este visitante se incluyen en el conjunto de datos independientemente de si cumplen esta condición. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nueva condición de visitante </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Volver a procesar </td> 
      <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo, se inicia la retransformación de datos. </p> <p> Para obtener información sobre el reprocesamiento de los datos, consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Comprobación de esquemas </td> 
      <td colname="col2"> True o false. Si es true, el servidor del área de trabajo de datos identifica los problemas de corrupción de conjuntos de datos y registra información sobre los problemas en los archivos de registro en el directorio Trace del servidor del área de trabajo de datos. El valor predeterminado es true. Adobe recomienda dejar este parámetro establecido en true en todo momento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Etapas </td> 
      <td colname="col2"> <p>Opcional. Los nombres de las etapas de procesamiento que se pueden utilizar en <span class="wintitle"> Conjuntos de datos de transformación incluyen </span> archivos. Las etapas de procesamiento proporcionan una manera de ordenar las transformaciones que se definen en <span class="wintitle"> Transformation Dataset Include </span> files. Este parámetro es muy útil si ha definido una o más transformaciones dentro de varios <span class="wintitle"> </span> archivos de inclusión de conjuntos de datos de transformación y desea que se realicen transformaciones específicas en puntos específicos durante la transformación. </p> <p> El orden en el que se enumeran las fases aquí determina el orden en el que se ejecutan las transformaciones de los <span class="wintitle"> </span> archivos Incluir conjunto de datos de transformación durante la transformación. <span class="wintitle"> El preprocesamiento </span> y <span class="wintitle"> el postprocesamiento </span> están integrados en etapas; <span class="wintitle"> El preprocesamiento </span> es siempre la primera etapa y <span class="wintitle"> el postprocesamiento </span> es siempre la última. De forma predeterminada, hay una etapa con nombre denominada <span class="wintitle"> Predeterminado </span>. </p> <p> <b>Para agregar una nueva etapa de procesamiento</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> En la ventana <span class="filepath"> Transformation.cfg </span> , haga clic con el botón derecho en <span class="uicontrol"> Etapas </span> y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Etapa </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Escriba un nombre para la nueva etapa. </li> 
      </ul> </p> <p> <b>Para eliminar una etapa de procesamiento existente</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Haga clic con el botón secundario en el número correspondiente al escenario que desee eliminar y haga clic en <span class="uicontrol"> Eliminar </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Nota:  Cuando se especifica un escenario en un <span class="wintitle"> conjunto de datos de transformación, incluir </span> archivos, el nombre del escenario debe coincidir exactamente con el nombre que se introduzca aquí. Para obtener más información sobre los archivos de inclusión de conjuntos de datos, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Conjunto de datos Incluir archivos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de inicio </td> 
      <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora en este momento o después. Adobe recomienda utilizar uno de los siguientes formatos para el momento: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 de enero de 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si se especifica el 29 de julio de 2013 00:00:00 EDT como hora de <span class="wintitle"> inicio, </span> se incluyen datos a partir del 29 de julio de 2013 a las 12:00:00 AM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor del área de trabajo de datos, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> <p>Nota:  Si especifica un valor para Hora de inicio, se establece y aplica un parámetro denominado Hora de inicio durante la fase de transformación de la construcción de conjuntos de datos. Para obtener información sobre los parámetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en conjuntos de datos Incluir archivos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformaciones </td> 
      <td colname="col2"> Opcional. Adobe recomienda definir transformaciones para la fase de transformación de la construcción de conjuntos de datos en uno o varios <span class="wintitle"> archivos de inclusión de conjuntos de datos de transformación </span> . Para obtener más información, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Conjunto de datos de transformación Incluir archivos </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Zona horaria </td> 
      <td colname="col2"> <p>Zona horaria del perfil del conjunto de datos. Los husos horarios se utilizan para las conversiones horarias y para la creación de dimensiones horarias. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Husos horarios </a>. </p> <p> <p>Nota:  Cuando se define en el <span class="filepath"> archivo Log Processing.cfg </span> , el parámetro Huso horario se utiliza únicamente para las conversiones de tiempo. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En la [!DNL Profile Manager], haga clic con el botón secundario [!DNL Transformation.cfg]en la marca de verificación de la [!DNL User] columna y, a continuación, haga clic **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** para que los cambios realizados localmente tengan efecto. La retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

   Para obtener más información sobre el reprocesamiento o la retransformación de los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
