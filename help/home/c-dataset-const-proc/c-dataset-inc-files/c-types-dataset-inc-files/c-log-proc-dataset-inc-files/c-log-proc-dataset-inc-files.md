---
description: El archivo Incluir conjunto de datos de procesamiento de registros para un perfil heredado contiene parámetros asociados con la fase de procesamiento de registros de la construcción de conjuntos de datos.
solution: Analytics
title: Archivos de inclusión de conjunto de datos de procesamiento de registros
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Archivos de inclusión de conjunto de datos de procesamiento de registros{#log-processing-dataset-include-files}

El archivo Incluir conjunto de datos de procesamiento de registros para un perfil heredado contiene parámetros asociados con la fase de procesamiento de registros de la construcción de conjuntos de datos.

La primera línea de un [!DNL Log Processing Dataset Include] archivo define un tipo [!DNL LogProcessingInclude] que admite los parámetros Grupos, Campos, Condición de entrada de registro, Parámetros, Reprocesamiento, Fase y Transformaciones. Todos los demás parámetros para el procesamiento de registros deben definirse en el archivo del directorio Dataset del perfil del [!DNL Log Processing.cfg] conjunto de datos. Puede nombrar un [!DNL Log Processing Dataset Include] archivo como desee, pero su extensión debe ser [!DNL .cfg]. El archivo debe almacenarse en el nombre del perfil *heredado*\Dataset\Log Processing directory. Debido a que los archivos se cargan de forma recursiva durante la fase de procesamiento de registros de la construcción de conjuntos de datos, puede almacenar los [!DNL Log Processing Dataset Include] archivos en cualquier nivel dentro del directorio (por ejemplo, nombre *de perfil* heredado \Dataset\Log Processing\*nombre de carpeta*\*incluir nombre de archivo*.cfg).

>[!NOTE]
>
>Muchos parámetros de configuración específicos de Web para el sitio se definen en [!DNL Log Processing Dataset Include] los archivos. Para obtener información sobre estos parámetros, consulte Configuración [de configuración para datos](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)web.

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Grupos de decodificadores </td> 
   <td colname="col2"> <p>Necesario si ha definido orígenes de registro de archivos XML o archivos de registro en el archivo <span class="filepath"> Log Processing.cfg</span> . El archivo de texto o los descodificadores XML que se definen para extraer campos de datos de los archivos de registro y de los orígenes de registro XML. </p> <p> <b>Para agregar un nuevo grupo de decodificadores</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Haga clic con el botón secundario del mouse (ratón) en <span class="uicontrol"> Grupo</span> de decodificador y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> GrupoDeDecodificadorDeArchivosDeTexto</span> o GrupoDeCódigos <span class="uicontrol"> XMLD</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> En el parámetro Nombre del nuevo grupo, introduzca el nombre que desee para el grupo de descodificadores. </li> 
     </ul> </p> <p> <p>Nota:  Cuando se especifica un grupo de decodificadores en el archivo <span class="filepath"> Log Processing.cfg</span> para el perfil del conjunto de datos, el nombre debe coincidir exactamente con el nombre que se introduzca aquí. Para obtener más información, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Archivos</a>de registro. </p> </p> <p> Para obtener información sobre los descodificadores que puede definir para cada grupo, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Grupos</a> de descodificadores de archivos de texto o Grupos <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"></a>de descodificadores XML. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> <p>Enumera los campos definidos en Fuentes <span class="wintitle"> de</span> registro o en <span class="wintitle"> Transformaciones</span> en un archivo de configuración <span class="wintitle"> de conjunto de datos de procesamiento</span> de registros pero utilizados en transformaciones, condiciones o dimensiones extendidas en un archivo de configuración <span class="wintitle"></span> de conjunto de datos de transformación. </p> <p> Cada uno de los campos siguientes debe enumerarse en algún archivo <span class="wintitle"> Log Processing Dataset Include</span> : 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición de entrada de registro </td> 
   <td colname="col2"> <p>Opcional. Define las reglas según las cuales se consideran las entradas de registro para su inclusión en el conjunto de datos. Consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición</a>de entrada de registro. </p> <p> <p>Nota:  Para que se incluya en el conjunto de datos, una entrada de registro debe satisfacer la condición <span class="wintitle"> de entrada de registro en el archivo</span> Log Processing.cfg <span class="filepath"> y en todos los archivos</span> Log Processing Dataset Include <span class="wintitle"></span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parámetros </td> 
   <td colname="col2"> Opcional. Variable a la que se puede hacer referencia en otros parámetros de configuración. Para obtener más información, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en Conjunto de datos Incluir archivos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Volver a procesar </td> 
   <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Al cambiar este parámetro y guardar el archivo en el servidor del área de trabajo de datos, se inicia el reprocesamiento de datos. </p> <p> Para obtener información sobre el reprocesamiento de los datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fase </td> 
   <td colname="col2"> <p>Opcional. Nombre de la etapa de procesamiento que se aplica a este <span class="wintitle"> archivo de inclusión</span> de conjunto de datos de procesamiento de registros. Las etapas de procesamiento se definen en el parámetro Stages del <span class="filepath"> archivo Log Processing.cfg</span> . </p> <p> <p>Nota:  Cuando se especifica un escenario, el nombre del escenario debe coincidir exactamente con el nombre que aparece en el parámetro Stages en el archivo <span class="filepath"> Log Processing.cfg</span> para el perfil del conjunto de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformaciones </td> 
   <td colname="col2"> Opcional. Define las transformaciones de datos que deben aplicarse durante el procesamiento del registro. Para obtener información sobre los tipos de transformación disponibles, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones</a>de datos. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obtener descripciones de los parámetros del [!DNL Log Processing.cfg] archivo, consulte Archivo [de configuración de procesamiento](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)de registros.

Siempre que trabaje con [!DNL Log Processing Dataset Include] archivos, debe tener en cuenta los siguientes puntos:

* Cambiar cualquiera de los parámetros de este archivo requiere un reprocesamiento de todos los datos.
* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Log Processing Dataset Include] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en el área de trabajo de datos. Al agregar un parámetro nuevo, utilice la tecla Espacio (no la tecla Tabulador) para sangrar dos (2) espacios a la derecha del nivel de encabezado anterior.

