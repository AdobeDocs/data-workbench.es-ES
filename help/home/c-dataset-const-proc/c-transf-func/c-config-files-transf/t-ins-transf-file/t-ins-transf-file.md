---
description: El archivo data workbenchTransform.cfg contiene los parámetros que definen los orígenes de registro, las transformaciones de datos y los exportadores.
title: El archivo Transform.cfg
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 2%

---

# El archivo Transform.cfg{#the-transform-cfg-file}

El archivo data workbenchTransform.cfg contiene los parámetros que definen los orígenes de registro, las transformaciones de datos y los exportadores.

Las transformaciones que defina manipularán los datos sin procesar recopilados por los sensores (archivos [!DNL .vsl]) o contenidos en archivos de texto, archivos XML o bases de datos compatibles con ODBC y los generarán en campos existentes, sobrescribiendo los datos actuales o en campos recién definidos.

Para configurar la funcionalidad de transformación, edite el archivo [!DNL Transform.cfg] de Data Workbench en la carpeta Dataset para el perfil para el que desea exportar datos de evento. Normalmente, este perfil está dedicado a la funcionalidad de transformación (es decir, no se realiza ningún otro procesamiento de datos que no sea el definido en el archivo [!DNL Transform.cfg] de Data Workbench). Es importante tener en cuenta que todas las instrucciones de procesamiento especificadas en los archivos [!DNL Log Processing Dataset Include] para cualquier perfil heredado se aplican además de las especificadas en el archivo [!DNL Transform.cfg] de Data Workbench.

Para obtener información sobre los archivos de inclusión de conjuntos de datos, consulte [Archivos de inclusión de conjuntos de datos](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Si los datos que desea exportar se procesan mediante un clúster de servidores de Data Workbench, cada uno de los servidores de procesamiento (DPU) del clúster procesa los datos, pero solo el primer DPU (servidor de procesamiento número 0 en el archivo [!DNL profile.cfg]) escribirá los datos de salida en su sistema de archivos local.

**Para editar el archivo Transform.cfg de Data Workbench**

1. Mientras trabaja en el perfil cuyos datos desea exportar, abra [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar el contenido del directorio.
1. Haga clic con el botón derecho en la marca de verificación situada junto a Data Workbench [!DNL Transform.cfg] y, a continuación, haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la ventana [!DNL Transform.cfg] del área de trabajo de datos.
1. Edite los parámetros en el archivo de configuración utilizando la siguiente tabla como guía:

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
    <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de tiempo hasta, pero no incluidas, esta vez. Adobe recomienda usar uno de los siguientes formatos para el momento: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1 de enero de 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por ejemplo, si especifica el 29 de julio de 2013 a las 00:00:00 EDT como <span class="wintitle"> Hora de finalización </span> incluye datos hasta el 28 de julio de 2013 a las 11:59:59 PM EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no toma el valor predeterminado GMT si no se especifica. Para obtener una lista de abreviaciones de zona horaria admitidas por el servidor de Data Workbench, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> El parámetro Usar hora de inicio/fin para fuentes de archivos de registro y sensor está relacionado con este parámetro. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportadores </td> 
    <td colname="col2"> <p>Los subcampos de un exportador especifican cómo se procesan y/o dan formato a los datos de salida. Puede definir varios exportadores para un conjunto de orígenes de registro. Cada tipo de exportador crea la salida de forma independiente. </p> <p> Existen tres tipos de exportadores: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Para obtener más información sobre los tipos de exportadores, consulte <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definición de exportadores </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Umbral hash </td> 
    <td colname="col2"> Opcional. Un factor de muestreo para el submuestreo aleatorio de filas. Si se establece en un número n, solo se selecciona uno de cada n ID de seguimiento para la exportación, lo que reduce el número total de filas exportadas por un factor de n. Para exportar todas las filas, establecería Umbral hash en 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condición de entrada de registro </td> 
    <td colname="col2"> Opcional. Define las reglas según las cuales se tienen en cuenta las entradas de registro para la exportación. Para obtener más información acerca de la condición <span class="wintitle"> de entrada de registro </span>, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registros </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Fuentes de registro </td> 
    <td colname="col2"> <p>Las fuentes de datos. <span class="wintitle"> Los orígenes de registro  </span> pueden ser archivos  <span class="filepath"> .vsl,  </span> archivos de registro, archivos XML o datos de bases de datos compatibles con ODBC. Para obtener información sobre <span class="wintitle"> fuentes de registro </span>, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registros </a>. </p> <p> <span class="wintitle"> Transform  </span> espera que todos los datos de origen estén en orden cronológico dentro de archivos de entrada ordenados lexicográficamente. Si no se cumple este requisito, los cálculos As de son incorrectos y se pueden procesar datos de entrada adicionales después de cerrar los archivos de salida. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Modo sin conexión </td> 
    <td colname="col2"> <p>Opcional. Verdadero o falso. Si es true, <span class="wintitle"> Transform </span> supone que todos los archivos de entrada están presentes cuando comienza a procesar los datos. Cuando se leen todos los datos de entrada, la <span class="wintitle"> transformación </span> cierra todos los archivos de salida sin esperar a que se reciban datos adicionales. El valor predeterminado es false. </p> <p> <p>Nota:  Si el <span class="wintitle"> modo sin conexión </span> está establecido en verdadero, <span class="wintitle"> transformación </span> espera que todos los datos de origen estén presentes antes de que se inicie el procesamiento. Se genera un mensaje de advertencia en el archivo <span class="filepath"> VisualServer.log </span> si se reciben datos adicionales después de cerrar los archivos de salida. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Volver a procesar </td> 
    <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo en el equipo <span class="wintitle"> Transform </span>, se iniciará el reprocesamiento de datos. </p> <p> Para obtener información sobre el reprocesamiento de los datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Etapas </td> 
    <td colname="col2"> <p>Opcional. Los nombres de las etapas de procesamiento que se pueden utilizar en los archivos <span class="wintitle"> Log Processing Dataset Include </span> que se ejecutan además del archivo <span class="filepath"> Transform.cfg </span> del Data Workbench. Las etapas de procesamiento proporcionan una forma de ordenar las transformaciones que se definen en los archivos <span class="wintitle"> Inclusión del conjunto de datos de procesamiento de registros </span>. Este parámetro es muy útil si ha definido una o más transformaciones dentro de varios <span class="wintitle"> archivos </span> de inclusión de conjunto de datos de procesamiento de registros y desea que se realicen transformaciones específicas en puntos específicos durante el proceso de exportación. </p> <p> El orden en el que se enumeran las fases aquí determina el orden en el que se ejecutan las transformaciones de los archivos <span class="wintitle"> de inclusión de conjunto de datos de procesamiento de registros </span> durante la exportación de datos. <span class="wintitle"> El preprocesamiento  </span> y el  <span class="wintitle"> postprocesamiento  </span> son fases integradas;  <span class="wintitle"> El preprocesamiento siempre  </span> es la primera etapa y el  <span class="wintitle"> postprocesamiento siempre  </span> es la última. De forma predeterminada, hay una etapa denominada <span class="wintitle"> predeterminada </span>. </p> <p> <b>Adición de una nueva fase de procesamiento</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> En la ventana Data Workbench <span class="filepath"> Transform.cfg </span> , haga clic con el botón derecho en <span class="uicontrol"> Etapas </span> y, a continuación, haga clic en <span class="uicontrol"> Agregar nueva </span> &gt; <span class="uicontrol"> etapa </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Introduzca un nombre para la nueva etapa. </li> 
      </ul> <p> <b>Eliminar una etapa de procesamiento existente</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Haga clic con el botón derecho en el número correspondiente al escenario que desee eliminar y haga clic en <span class="uicontrol"> Quitar </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> <p> <p>Nota:  Cuando especifica un escenario en un archivo <span class="wintitle"> inclusión de conjunto de datos de procesamiento de registros </span> , el nombre del escenario debe coincidir exactamente con el nombre que escriba aquí. Para obtener más información sobre los archivos de inclusión de conjuntos de datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Archivos de inclusión de conjuntos de datos </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hora de inicio </td> 
    <td colname="col2"> <p>Opcional. Filtre los datos para incluir entradas de registro con marcas de hora en o después de esta hora. Adobe recomienda usar uno de los siguientes formatos para el momento: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 de enero de 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 de enero de 2013 HH:MM:SS GMT </li> 
      </ul> <p> Por ejemplo, si especifica el 29 de julio de 2013, 00:00:00 EDT como Hora de inicio, se incluirán datos a partir del 29 de julio de 2013, a las 12:00:00 a. m., EDT. </p> <p> Debe especificar una zona horaria. La zona horaria no toma el valor predeterminado GMT si no se especifica. Para obtener una lista de abreviaciones de zona horaria admitidas por el servidor de Data Workbench, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de zona horaria </a>. </p> <p> <p>Nota:  El parámetro Usar hora de inicio/fin para fuentes de archivos de registro y sensor está relacionado con este parámetro. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformaciones </td> 
    <td colname="col2"> <p>Opcional. Define las transformaciones que se deben aplicar a los datos. Para obtener información sobre los tipos de transformación disponibles, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones de datos </a>. </p> <p> <p>Nota:  Los siguientes tipos de transformación no funcionan cuando se definen en el archivo <span class="filepath"> Transform.cfg </span> de Data Workbench: </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Si se reciben datos adicionales después de cerrar los archivos de salida (consulte [!DNL Log Sources] y [!DNL Offline Mode] en la tabla anterior), [!DNL Transform] crea nuevos archivos de salida con los datos adicionales. Los nombres de los nuevos archivos de salida se generan a partir del nombre del archivo de salida original con la adición de un número de versión entre paréntesis justo antes de la extensión. Por ejemplo, si el archivo de salida original es [!DNL 20070701-ABC.vsl], las versiones posteriores de este archivo tendrán el nombre [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl], etc. Tenga en cuenta que el uso de archivos con versiones como entrada al servidor de Data Workbench puede provocar errores de procesamiento.
>
>
>Adobe recomienda evitar la creación de archivos de salida con versiones, asegurándose de que todos los datos de origen estén en orden cronológico dentro de archivos de entrada ordenados lexicográficamente y, si [!DNL Offline Mode] está establecido en true, que todos los datos de origen estén presentes antes de que se inicie el procesamiento. Para obtener más información, consulte las entradas [!DNL Log Sources] y [!DNL Offline Mode] en la tabla anterior.

1. Agregue transformaciones haciendo clic con el botón derecho en **[!UICONTROL Transformations]** y haciendo clic en **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Complete los campos de transformación.

   Consulte [Transformaciones de datos](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) para obtener descripciones y ejemplos de las transformaciones que puede utilizar con la funcionalidad de transformación.

1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente surtan efecto, en [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de Data Workbench [!DNL Transform.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, donde el nombre del perfil es el nombre del perfil para el que desea exportar datos. El reprocesamiento de los datos comienza después de la sincronización del perfil.

   >[!NOTE]
   >
   >Para obtener información sobre el reprocesamiento de los datos para su exportación, consulte [Reprocesamiento y retransformación](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
