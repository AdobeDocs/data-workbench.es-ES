---
description: El archivo data workbenchTransform.cfg contiene los parámetros que definen los orígenes de registro, las transformaciones de datos y los exportadores.
solution: Analytics
title: El archivo Transform.cfg
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# El archivo Transform.cfg{#the-transform-cfg-file}

El archivo data workbenchTransform.cfg contiene los parámetros que definen los orígenes de registro, las transformaciones de datos y los exportadores.

Las transformaciones que defina manipularán los datos sin procesar recopilados por los sensores ( [!DNL .vsl] archivos) o contenidos en archivos de texto, archivos XML o bases de datos compatibles con ODBC y los colocarán en campos existentes, sobrescribiendo los datos actuales o en campos recientemente definidos.

Para configurar la funcionalidad de transformación, edite el archivo del área de trabajo de datos [!DNL Transform.cfg] dentro de la carpeta Conjunto de datos para el perfil para el que desea exportar los datos del evento. Normalmente, este perfil está dedicado a la funcionalidad de transformación (es decir, no se realiza ningún otro procesamiento de datos que no sea el definido en el [!DNL Transform.cfg] archivo del área de trabajo de datos). Es importante tener en cuenta que las instrucciones de procesamiento especificadas en los [!DNL Log Processing Dataset Include] archivos para cualquier perfil heredado se aplican además de las especificadas en el [!DNL Transform.cfg] archivo del área de trabajo de datos.

Para obtener información sobre los archivos de inclusión de conjuntos de datos, consulte [Conjunto de datos Incluir archivos](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Si los datos que desea exportar son procesados por un clúster de servidores del área de trabajo de datos, cada uno de los servidores de procesamiento (DPU) del clúster procesa los datos, pero sólo el primer DPU (servidor de procesamiento Nº 0 del [!DNL profile.cfg] archivo) escribirá los datos de salida en su sistema de archivos local.

**Para editar el archivo Transform.cfg del área de trabajo de datos**

1. Mientras trabaja en el perfil para el que desea exportar datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar el contenido del directorio.
1. Haga clic con el botón secundario en la marca de verificación situada junto al área de trabajo de datos [!DNL Transform.cfg], luego haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la [!DNL Transform.cfg] ventana Área de trabajo de datos.
1. Edite los parámetros en el archivo de configuración utilizando la tabla siguiente como guía:

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
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
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1 de enero de 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si se especifica el 29 de julio de 2013 00:00:00 EDT como hora de finalización, <span class="wintitle"> </span> se incluyen los datos hasta el 28 de julio de 2013, a las 11:59:59 PM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor del área de trabajo de datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> El parámetro Usar hora de inicio/fin para orígenes de archivos de registro y sensor está relacionado con este parámetro. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportadores </td> 
    <td colname="col2"> <p>Los subcampos de un exportador especifican cómo se procesan o formatean los datos de salida. Puede definir varios exportadores para un conjunto de orígenes de registro. Cada tipo de exportador crea una salida de forma independiente. </p> <p> Existen tres tipos de exportadores: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Para obtener más información sobre los tipos de exportadores, consulte <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definición de exportadores </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Umbral de hash </td> 
    <td colname="col2"> Opcional. Factor de muestreo para el submuestreo aleatorio de filas. Si se establece en un número n, sólo se selecciona uno de cada ID de seguimiento n para la exportación, reduciendo el número total de filas exportadas por un factor de n. Para exportar todas las filas, debe establecer el umbral hash en 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condición de entrada de registro </td> 
    <td colname="col2"> Opcional. Define las reglas según las cuales se tienen en cuenta las entradas de registro para la exportación. Para obtener más información sobre la condición de entrada de <span class="wintitle"> registro </span>, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registro </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Fuentes de registro </td> 
    <td colname="col2"> <p>Las fuentes de datos. <span class="wintitle"> Los orígenes de registro </span> pueden ser archivos <span class="filepath"> .vsl </span> , archivos de registro, archivos XML o datos de bases de datos compatibles con ODBC. Para obtener información sobre las fuentes <span class="wintitle"> de registro </span>, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registros </a>. </p> <p> <span class="wintitle"> Transform </span> espera que todos los datos de origen estén en orden cronológico dentro de archivos de entrada ordenados lexicográficamente. Si no se cumple este requisito, los cálculos de A son incorrectos y se pueden procesar datos de entrada adicionales después de cerrar los archivos de salida. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Modo sin conexión </td> 
    <td colname="col2"> <p>Opcional. True o false. Si es true, <span class="wintitle"> Transform </span> supone que todos los archivos de entrada están presentes cuando comienza a procesar los datos. Una vez leídos todos los datos de entrada, Transformar <span class="wintitle"> </span> cierra todos los archivos de salida sin esperar a que se reciban datos adicionales. El valor predeterminado es false. </p> <p> <p>Nota:  Si <span class="wintitle"> el modo sin conexión </span> <span class="wintitle"> </span> está establecido en true, Transform espera que todos los datos de origen estén presentes antes de que se inicie el procesamiento. Se genera un mensaje de advertencia en el archivo <span class="filepath"> VisualServer.log </span> si se reciben datos adicionales después de cerrar los archivos de salida. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Volver a procesar </td> 
    <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo en el equipo <span class="wintitle"> Transformar </span> , se inicia el reprocesamiento de datos. </p> <p> Para obtener información sobre el reprocesamiento de los datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Etapas </td> 
    <td colname="col2"> <p>Opcional. Los nombres de las etapas de procesamiento que se pueden utilizar en el conjunto de datos de procesamiento <span class="wintitle"> de registros incluyen </span> archivos ejecutados además del archivo del área de trabajo de datos <span class="filepath"> Transform.cfg </span> . Las etapas de procesamiento proporcionan una manera de ordenar las transformaciones que se definen en los <span class="wintitle"> archivos de inclusión de conjuntos de datos de procesamiento de registros </span> . Este parámetro es muy útil si ha definido una o más transformaciones dentro de varios <span class="wintitle"> conjuntos de datos de procesamiento de registros Incluir </span> archivos y desea que se realicen transformaciones específicas en puntos específicos durante el proceso de exportación. </p> <p> El orden en el que se enumeran las fases aquí determina el orden en el que se ejecutan las transformaciones en el conjunto de datos de procesamiento <span class="wintitle"> de registros Incluir </span> archivos durante la exportación de datos. <span class="wintitle"> El preprocesamiento </span> y <span class="wintitle"> el postprocesamiento </span> están integrados en etapas; <span class="wintitle"> El preprocesamiento </span> es siempre la primera etapa y <span class="wintitle"> el postprocesamiento </span> es siempre la última. De forma predeterminada, hay una etapa con nombre denominada <span class="wintitle"> Predeterminado </span>. </p> <p> <b>Para agregar una nueva etapa de procesamiento</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> En la ventana del área de trabajo de datos <span class="filepath"> Transform.cfg </span> , haga clic con el botón secundario en <span class="uicontrol"> Etapas </span>y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Etapa </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Escriba un nombre para la nueva etapa. </li> 
      </ul> <p> <b>Para eliminar una etapa de procesamiento existente</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Haga clic con el botón secundario en el número correspondiente al escenario que desee eliminar y haga clic en <span class="uicontrol"> Eliminar </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Nota:  Cuando se especifica un escenario en un <span class="wintitle"> archivo de conjunto de datos de procesamiento de registros, </span> el nombre del escenario debe coincidir exactamente con el nombre introducido aquí. Para obtener más información sobre los archivos de inclusión de conjuntos de datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Conjunto de datos Incluir archivos </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hora de inicio </td> 
    <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora en este momento o después. Adobe recomienda utilizar uno de los siguientes formatos para el momento: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 de enero de 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> <p> Por ejemplo, si se especifica el 29 de julio de 2013, 00:00:00 EDT como hora de inicio, se incluirán datos a partir del 29 de julio de 2013, a las 12:00:00 AM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no se establece de forma predeterminada en GMT si no se especifica. Para obtener una lista de abreviaturas de zona horaria admitidas por el servidor del área de trabajo de datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> <p>Nota:  El parámetro Usar hora de inicio/fin para orígenes de archivos de registro y sensor está relacionado con este parámetro. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformaciones </td> 
    <td colname="col2"> <p>Opcional. Define las transformaciones que se van a aplicar a los datos. Para obtener información sobre los tipos de transformación disponibles, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones de datos </a>. </p> <p> <p>Nota:  Los siguientes tipos de transformación no funcionan cuando se definen en el archivo <span class="filepath"> Transform.cfg del área de trabajo de datos </span> : </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sesionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Si se reciben datos adicionales después de cerrar los archivos de salida (véase [!DNL Log Sources] y [!DNL Offline Mode] en la tabla anterior), [!DNL Transform] crea nuevos archivos de salida con los datos adicionales. Los nombres de los nuevos archivos de salida se generan a partir del nombre del archivo de salida original con la adición de un número de versión entre paréntesis justo antes de la extensión. Por ejemplo, si el archivo de salida original es [!DNL 20070701-ABC.vsl], las versiones posteriores de este archivo recibirán un nombre [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]etc. Tenga en cuenta que el uso de los archivos con versiones como entrada en el servidor del área de trabajo de datos puede provocar errores de procesamiento.
>
>
>Adobe recomienda evitar la creación de archivos de salida con versiones asegurándose de que todos los datos de origen están en orden cronológico dentro de archivos de entrada ordenados lexicográficamente y, si [!DNL Offline Mode] se establece en true, que todos los datos de origen están presentes antes de que se inicie el procesamiento. Para obtener más información, consulte las entradas [!DNL Log Sources] y [!DNL Offline Mode] de la tabla anterior.

1. Agregue transformaciones haciendo clic con el botón derecho **[!UICONTROL Transformations]** y haciendo clic en **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Complete los campos de transformación.

   Consulte Transformaciones [de datos](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) para obtener descripciones y ejemplos de las transformaciones que puede utilizar con la funcionalidad de transformación.

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del área de trabajo de datos [!DNL Transform.cfg] en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, donde nombre del perfil es el nombre del perfil para el que está exportando datos. El reprocesamiento de los datos comienza después de la sincronización del perfil.

   >[!NOTE]
   >
   >Para obtener información sobre el reprocesamiento de datos para la exportación, consulte [Reprocesamiento y retransformación](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
