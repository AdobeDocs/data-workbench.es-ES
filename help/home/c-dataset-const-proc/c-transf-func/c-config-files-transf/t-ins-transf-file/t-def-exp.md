---
description: Los exportadores proporcionan las instrucciones para enviar los datos del evento.
title: Definición de exportadores
uuid: 565d4482-6c25-407c-bda7-0d116180902a
exl-id: 5de6266a-e959-414c-9512-5e9f4011881b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 2%

---

# Definición de exportadores{#defining-exporters}

{{eol}}

Los exportadores proporcionan las instrucciones para enviar los datos del evento.

La funcionalidad de transformación proporciona tres tipos de exportadores para la exportación [!DNL .vsl] archivos, archivos de registro, archivos XML y datos ODBC como [!DNL .vsl] archivos, archivos de texto o archivos de texto delimitados que se pueden utilizar mediante rutinas de carga de DataWarehouse, agencias de auditoría u otros destinos.

>[!NOTE]
>
>Para que un exportador funcione correctamente, el origen de registro debe cumplir los requisitos adecuados que se describen en la [Fuentes de registro](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) sección de [Archivo de configuración de procesamiento de registros](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

**Definición de un exportador**

1. Apertura [!DNL Transform.cfg] en data workbench. Consulte [Para editar el archivo Insight Transform.cfg](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13).
1. Clic con el botón derecho **[!UICONTROL Exporters]** y haga clic en **[!UICONTROL Add New]**.
1. Seleccione una de las siguientes opciones:

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**

   >[!NOTE]
   >
   >Para la variable [!DNL ExportVSLFile] , todos los campos ampliados del archivo de entrada y todos los campos definidos por el usuario del formulario cs(*header*) siempre se escriben en el archivo de salida VSL. Si sobrescribe un campo extendido existente, el nuevo valor se escribirá en el archivo de salida, incluso si el campo está en blanco.

1. Edite los parámetros de Exportadores en el archivo de configuración utilizando la siguiente tabla como guía:

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Parámetro </th> 
      <th colname="col2" class="entry"> Descripción </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Formato de datos </td> 
      <td colname="col2"> <p>Para <span class="wintitle"> ExportTextFile</span> solo. El formato de cada línea de salida, que consiste en secuencias de escape del nombre del campo (expresado como %<i>fieldname</i>%) y cualquier otro texto fijo deseado. El formato debe incluir un separador de líneas, normalmente [CR] [LF]. </p> <p> Se puede incrustar un signo de porcentaje literal (%) en la cadena de formato escapando el carácter como se muestra aquí: %% </p> <p> Un ejemplo de entrada para el parámetro Formato de datos es <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Campos </td> 
      <td colname="col2">Para <span class="wintitle"> ExportDelimitedTextFile</span> solo. Nombres de los campos que se van a generar. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Delimitador </td> 
      <td colname="col2"> <p>Opcional. Para <span class="wintitle"> ExportDelimitedTextFile</span> solo. Carácter que se utiliza para separar los campos del archivo de salida. </p> <p> El software no puede omitir los delimitadores que están incluidos en los valores de los datos. Como resultado, Adobe no recomienda utilizar comas como delimitadores. </p> <p> Si mantiene pulsada la tecla Ctrl y hace clic con el botón derecho en el parámetro Delimitador, se muestra una <span class="wintitle"> Insertar</span> aparece. Este menú contiene una lista de caracteres especiales que a menudo se utilizan como delimitadores. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Separador de líneas </td> 
      <td colname="col2">Opcional. Para <span class="wintitle"> ExportDelimitedTextFile</span> solo. Caracteres utilizados para separar líneas en los archivos de salida. El valor predeterminado es [CR] [LF]. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Nombre </td> 
      <td colname="col2"> <p>Opcional. Identificador del exportador. Este nombre aparece en la sección <span class="wintitle"> Estado detallado</span> interfaz. </p> <p> Para obtener información sobre la variable <span class="wintitle"> Estado detallado</span> , consulte la <i>Guía del usuario de Data Workbench</i>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Comentarios </td> 
      <td colname="col2"> Opcional. Notas sobre el exportador. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Ruta de salida </td> 
      <td colname="col2"> <p>Ruta en la que se deben almacenar los archivos de salida. La ruta de acceso es relativa a la carpeta de instalación del servidor de Data Workbench. </p> <p> <p>Nota: El servidor de Data Workbench que almacena los datos de salida es el servidor de procesamiento número 0 en la variable <span class="filepath"> profile.cfg</span> archivo. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Período de rotación del archivo </td> 
      <td colname="col2"> <p>Opcional. Frecuencia con la que se exportan los datos al archivo de salida. Cada archivo de salida contiene datos relacionados con un período de tiempo específico denominado período de rotación. Todos los cálculos de hora están en GMT: Un día comienza a medianoche GMT y finaliza el día siguiente a la medianoche GMT, incluso si los datos escritos en el archivo incluyen un campo que se ha transformado a la hora local. </p> <p> Los valores disponibles son los siguientes: </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> AÑO. Cada archivo contiene datos de un año natural. </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MES. Cada archivo contiene datos de un mes natural. Los meses se numeran del 1 (enero) al 12 (diciembre). </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> SEMANA. Cada archivo contiene datos durante una semana. Una semana empieza el lunes. La semana que comienza en uno de los primeros siete días del año es la semana 1, y la semana anterior (parcial), si la hay, es la semana 0. </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> DÍA. Cada archivo contiene datos de un día del calendario. </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> HORA. Cada archivo contiene datos de una hora. </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE. No se realiza ninguna rotación. Todos los datos se escriben en el mismo archivo (o en un conjunto de archivos determinado por otros parámetros de configuración). Consulte la <span class="wintitle"> Formato de nombre de archivo</span> en esta tabla. </li> 
      </ul> <p>El periodo de rotación predeterminado del archivo es DAY. </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Establezca la rotación del archivo en NONE solo cuando trabaje en <span class="wintitle"> Modo sin conexión</span>. Consulte la <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> Modo sin conexión</a> descripción del parámetro. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Formato de nombre de archivo </td> 
      <td colname="col2"> <p>Opcional. Formato del nombre del archivo de salida. </p> <p> Cada entrada de registro se puede almacenar en un archivo cuyo nombre se deriva de la hora de inicio del periodo de rotación y, opcionalmente, de los valores de los campos en las filas que contiene. Los campos que se van a utilizar en el nombre del archivo están incrustados como escapes de nombre de campo (expresados como %<i>fieldname</i>%). </p> <p>Los componentes de nombre de archivo relacionados con el periodo de rotación están incrustados en la cadena de formato mediante las siguientes secuencias de escape: 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy% (año de cuatro dígitos) </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (año de dos dígitos) </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (mes de dos dígitos, 01 - 12) </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww% (semana de dos dígitos, 01 - 52) </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (día de dos dígitos, 01 - 31) </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (hora de dos dígitos, 00 - 23) </li> 
      </ul> </p> <p> El formato de nombre de archivo predeterminado es <span class="filepath"> %yyyy%%mm%%dd%-%xmask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> Las secuencias de escape distinguen entre mayúsculas y minúsculas. </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> Cuando el periodo de rotación de archivos está establecido en NINGUNO, se sustituye una cadena vacía por cada una de las secuencias de escape, si está presente. </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> Se genera un error si <span class="wintitle"> Formato de nombre de archivo</span> no genera un nombre de archivo único para cada periodo de rotación (consulte el parámetro Periodo de rotación de archivos en esta tabla). Por ejemplo, al usar el período de rotación DAY, las secuencias de escape %dd%, %mm% y %yy% o %yyyy% deben estar presentes en el patrón para evitar la pérdida de datos. </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> Si utiliza secuencias de escape de nombre de campo dentro del patrón y el campo dado tiene muchos valores distintos, se escriben muchos archivos de salida para cada período de rotación. Tenga en cuenta que este escenario puede provocar un rendimiento deficiente, por lo que debe utilizar esta función con precaución. </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> Todos los cálculos están en GMT. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Ejecutar al pasar el ratón por encima </td> 
      <td colname="col2"> <p>Opcional. Cuando se finaliza cada archivo, se puede ejecutar un comando externo (Windows). La línea de comandos se deriva del nombre del archivo final sustituyendo las siguientes secuencias de escape en este parámetro: </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. La parte de directorio del nombre del archivo final, incluida la barra invertida final. </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. El nombre del archivo (excepto el directorio y la extensión) del archivo final. </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. La extensión (incluido el "." inicial) del nombre del archivo final. </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %Ruta%. El nombre de la ruta de acceso completa del archivo, equivalente a %dir%%file%%ext%. </li> 
      </ul> <p> De forma predeterminada, este parámetro está vacío (no se ejecuta ningún comando). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Límite de memoria </td> 
      <td colname="col2"> <p>Opcional. Cantidad de memoria en bytes utilizada para almacenar en búfer la salida del exportador. El valor predeterminado es 10 000 000 bytes. </p> <p> <p>Nota: Si tiene muchos archivos de salida abiertos al mismo tiempo, puede que desee aumentar este valor, pero puede disminuir la cantidad de memoria disponible para el uso de otros componentes del sistema. Sin embargo, reducir este valor puede ralentizar el proceso de exportación. Para obtener ayuda, póngase en contacto con el Adobe. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Límite de archivos abiertos </td> 
      <td colname="col2"> <p>Opcional. Número máximo de archivos que pueden abrirse al mismo tiempo para la salida del exportador. Si se supera este número, se registra un error en el registro de eventos y el servidor de Data Workbench deja de ejecutarse. El valor predeterminado es 1000. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Una vez definido el exportador (y haya realizado cambios en otros parámetros) en la variable [!DNL Transform.cfg] guarde el archivo localmente y guárdelo en el perfil correspondiente del equipo servidor de Data Workbench.
