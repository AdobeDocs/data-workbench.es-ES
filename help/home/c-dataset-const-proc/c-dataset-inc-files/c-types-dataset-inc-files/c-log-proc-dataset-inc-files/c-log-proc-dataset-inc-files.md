---
description: El archivo de inclusión de conjunto de datos de procesamiento de registros para un perfil heredado contiene parámetros asociados con la fase de procesamiento de registros de la construcción del conjunto de datos.
title: Archivos de inclusión de conjunto de datos de procesamiento de registros
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Archivos de inclusión de conjunto de datos de procesamiento de registros{#log-processing-dataset-include-files}

El archivo de inclusión de conjunto de datos de procesamiento de registros para un perfil heredado contiene parámetros asociados con la fase de procesamiento de registros de la construcción del conjunto de datos.

La primera línea de un archivo [!DNL Log Processing Dataset Include] define un tipo [!DNL LogProcessingInclude] que admite los parámetros Grupos de decodificadores, Campos, Condición de entrada de registro, Parámetros, Reprocesamiento, Etapa y Transformaciones. Todos los demás parámetros para el procesamiento de registros deben definirse en el archivo [!DNL Log Processing.cfg] en el directorio del conjunto de datos del perfil del conjunto de datos. Puede asignar cualquier nombre a un archivo [!DNL Log Processing Dataset Include] que desee, pero su extensión de archivo debe ser [!DNL .cfg]. El archivo debe almacenarse dentro del *nombre de perfil heredado*\Dataset\Log Processing directory. Debido a que los archivos se cargan recursivamente durante la fase de procesamiento de registros de la construcción del conjunto de datos, puede almacenar los archivos [!DNL Log Processing Dataset Include] en cualquier nivel dentro del directorio (por ejemplo, *nombre de perfil heredado*\Dataset\Log Processing\*nombre de carpeta*\*incluir nombre de archivo*.cfg).

>[!NOTE]
>
>Muchos parámetros de configuración específicos de la web para el sitio se definen en los archivos [!DNL Log Processing Dataset Include] . Para obtener información sobre estos parámetros, consulte [Configuración de datos web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

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
   <td colname="col2"> <p>Necesario si ha definido un archivo de registro o fuentes de registro de archivos XML en el archivo <span class="filepath"> Log Processing.cfg</span>. El archivo de texto o los descodificadores XML que se definen para extraer campos de datos de archivos de registro y orígenes de registro XML. </p> <p> <b>Agregar un nuevo grupo de decodificadores</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Haga clic con el botón derecho del ratón en <span class="uicontrol"> Grupo de decodificadores</span> y haga clic en <span class="uicontrol"> Agregar nuevo</span> &gt; <span class="uicontrol"> Grupo de decodificadores de texto</span> o <span class="uicontrol"> Grupo de códigos XML</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> En el parámetro Name del nuevo grupo, introduzca el nombre deseado del grupo de descodificadores. </li> 
     </ul> </p> <p> <p>Nota:  Cuando especifica un grupo de decodificadores en el archivo <span class="filepath"> Log Processing.cfg</span> para el perfil del conjunto de datos, el nombre debe coincidir exactamente con el nombre que escriba aquí. Para obtener más información, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Archivos de registro</a>. </p> </p> <p> Para obtener información sobre los descodificadores que puede definir para cada grupo, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Grupos de decodificadores de archivos de texto</a> o <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Grupos de decodificadores XML</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> <p>Aquí se enumeran los campos definidos en <span class="wintitle"> Orígenes de registro</span> o <span class="wintitle"> Transformaciones</span> en un archivo <span class="wintitle"> Configuración de conjunto de datos de procesamiento de registros</span> que se usan en transformaciones, condiciones o dimensiones extendidas en un archivo <span class="wintitle"> Configuración de conjunto de datos de transformación</span>. </p> <p> Cada campo de abajo debe estar enumerado en algún archivo <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros</span>: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición de entrada de registro </td> 
   <td colname="col2"> <p>Opcional. Define las reglas según las cuales se tienen en cuenta las entradas de registro para su inclusión en el conjunto de datos. Consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condición de entrada de registro</a>. </p> <p> <p>Nota:  Para que se incluya en el conjunto de datos, una entrada de registro debe satisfacer la <span class="wintitle"> Condición de entrada de registro</span> en el archivo <span class="filepath"> Log Processing.cfg</span> y en cada archivo <span class="wintitle"> Log Processing Dataset Include</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parámetros </td> 
   <td colname="col2"> Opcional. Variable a la que se puede hacer referencia en otros parámetros de configuración. Para obtener más información, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definición de parámetros en archivos de inclusión de conjuntos de datos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Volver a procesar </td> 
   <td colname="col2"> <p>Opcional. Aquí se puede introducir cualquier carácter o combinación de caracteres. Si se cambia este parámetro y se guarda el archivo en el servidor de Data Workbench, se inicia el reprocesamiento de datos. </p> <p> Para obtener información sobre el reprocesamiento de los datos, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocesamiento y retransformación</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prueba </td> 
   <td colname="col2"> <p>Opcional. Nombre de la fase de procesamiento que se aplica a este archivo <span class="wintitle"> inclusión de conjunto de datos de procesamiento de registros</span>. Las etapas de procesamiento se definen en el parámetro Stages del archivo <span class="filepath"> Log Processing.cfg</span>. </p> <p> <p>Nota:  Cuando especifica un escenario, el nombre del escenario debe coincidir exactamente con el nombre que aparece en el parámetro Stages en el archivo <span class="filepath"> Log Processing.cfg</span> para el perfil del conjunto de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformaciones </td> 
   <td colname="col2"> Opcional. Define las transformaciones de datos que deben aplicarse durante el procesamiento del registro. Para obtener información sobre los tipos de transformación disponibles, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformaciones de datos</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obtener descripciones de los parámetros del archivo [!DNL Log Processing.cfg], consulte [Archivo de configuración de procesamiento de registros](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Siempre que trabaje con archivos [!DNL Log Processing Dataset Include], debe tener en cuenta los siguientes puntos:

* Para cambiar cualquiera de los parámetros de este archivo es necesario volver a procesar todos los datos.
* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Log Processing Dataset Include] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en Data Workbench. Al añadir un nuevo parámetro, utilice la tecla Space (no la tecla Tab) para sangrar dos espacios (2) a la derecha del nivel de encabezado anterior.
