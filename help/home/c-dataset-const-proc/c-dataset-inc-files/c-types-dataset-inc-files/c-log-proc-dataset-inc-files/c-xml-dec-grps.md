---
description: Procesamiento de archivos XML como orígenes de registro para definir decodificadores para extraer datos del archivo XML.
solution: Analytics
title: Grupos de decodificadores XML
topic: Data workbench
uuid: 8fc9ab80-9a71-4fe2-a646-e830ffeb67b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Grupos de decodificadores XML{#xml-decoder-groups}

Procesamiento de archivos XML como orígenes de registro para definir decodificadores para extraer datos del archivo XML.

>[!NOTE]
>
>La definición de grupos de decodificadores XML para orígenes de registro XML requiere conocer la estructura y el contenido del archivo XML, los datos que se van a extraer y los campos en los que se almacenan dichos datos. Esta sección proporciona descripciones básicas de los parámetros que se pueden especificar para los descodificadores. La forma en que se utiliza cualquier decodificador depende del archivo XML que contiene los datos de origen.

Para obtener información sobre los requisitos de formato para orígenes de registro XML, consulte Fuentes [de registro](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea). Para obtener ayuda con la definición de los descodificadores XML, póngase en contacto con Adobe.

El nivel superior de un decodificador XML es un grupo de decodificadores (XMLDecoderGroup), que es un conjunto de tablas de decodificadores que se utilizan para extraer datos de un archivo XML de un formato determinado. Si tiene archivos XML de diferentes formatos, debe definir un grupo de descodificadores para cada formato. Cada grupo de decodificadores consta de una o varias tablas de decodificadores.

En la tabla siguiente se describe el parámetro Tables y todos los subparámetros que debe especificar para definir un grupo de decodificadores XML.

<table id="table_06C40C5149E94548A1B0C2ED4397624B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tablas </td> 
   <td colname="col2"> <p>Cada tabla de un grupo de decodificadores representa un nivel de datos que se extraerán del archivo XML. Por ejemplo: si desea extraer datos sobre los visitantes, debe crear una tabla de descodificadores que contenga la información que desee extraer para cada visitante. También puede crear tablas de decodificador dentro de tablas de decodificador (consulte Elementos secundarios). </p> <p> <b>Adición de una tabla a un grupo de descodificadores</b> 
     <ul id="ul_C73CAD77440B4465B9FCE08BF4FA0749"> 
      <li id="li_C4B8CC5A85D942898F1EB76778105818"> Haga clic con el botón secundario en <span class="uicontrol"> Tablas </span> y haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Tabla de códigos XMLDecoder </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> <p>Campos extendidos (por ejemplo, x-trackingid, x-email) en los que se almacenan los datos. Los datos que se almacenarán en el campo están determinados por los subcampos Ruta y/o Operación. </p> <p> La ruta es el nivel del campo dentro del archivo XML estructurado. La ruta de un campo es relativa a la ruta de la tabla en la que se define. Algunos ejemplos son <span class="filepath"> tag.tag.tag </span> o <span class="filepath"> tag.tag.tag.@attribute </span>. Tenga en cuenta que las rutas distinguen entre mayúsculas y minúsculas. </p> <p> Se aplica una operación a cada línea de la ruta especificada para generar una salida. Están disponibles las siguientes operaciones: 
     <ul id="ul_B264A411D7E3446288E7E69D62150B8B"> 
      <li id="li_5936E81C0EEF46AFB780E451A04A88E4"><b>ÚLTIMO:</b> El campo toma el valor de la última incidencia de la ruta en el archivo XML. </li> 
      <li id="li_7BC4F24F2CA84C2EB64B06FE09B4CAF6"><b>ALEATORIO:</b> Asigna un valor aleatorio al campo. Esta operación resulta útil si necesita generar una identificación única, como por ejemplo para el campo x-trackingid. </li> 
      <li id="li_C1D34EA11BFB4859A25A275A9B63FB56"><b>HERENCIA:</b> El campo definido hereda su valor del campo correspondiente de la tabla principal. </li> 
      <li id="li_F62FB8CD962E4E1495D9A2D5B7A78E2A"><b>"<i>constante </i>":</b> La constante debe ir entre comillas. Puede utilizar una operación constante para comprobar la existencia de una ruta determinada; si la ruta existe, se asigna al campo el valor de la constante. </li> 
     </ul> </p> <p> <b>Adición de un campo a una tabla de descodificador</b> </p> <p> 
     <ul id="ul_91D104D927424DEA9E788E43B2F6FEA9"> 
      <li id="li_5448B01EE82349569BBFC99C9604D7B8"> Haga clic con el botón secundario <span class="uicontrol"> Campos </span>, luego haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> XMLDecoderField </span>. Defina el campo, la operación y la ruta según corresponda. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ruta </td> 
   <td colname="col2"> <p>Nivel dentro del archivo XML estructurado para el que la tabla del decodificador contiene información. Para una tabla de decodificador XML secundaria, la ruta es relativa a la ruta de acceso de la tabla principal. Tenga en cuenta que las rutas distinguen entre mayúsculas y minúsculas. </p> <p> Por ejemplo, si el archivo XML contiene la estructura: </p> 

    &amp;lt;visitor&amp;gt;
    
    &amp;nbsp;
    
    ...
    
    &amp;nbsp;
    
    &amp;lt;/visitor&amp;gt;
    
    &amp;lt;/logdata&amp;gt;&amp;nbsp; &lt;/code> &lt;p> entonces la ruta sería &lt;span class=&quot;filepath&quot;> logdata.visitor &lt;/span>. &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col1"> Tabla </td> 
   <td colname="col2"> <p>El valor de este parámetro siempre debe ser "Entrada de registro". </p> <p> <p>Nota:  No cambie este valor sin consultar con Adobe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Niños </td> 
   <td colname="col2"> <p>Opcional. Una o más tablas de decodificador incrustadas. Cada elemento secundario incluye los parámetros Campos, Ruta y Tabla descritos anteriormente. </p> <p> <b>Adición de un elemento secundario a una tabla de descodificador</b> </p> <p> 
     <ul id="ul_902AC6CA5D66457D84CBA3194FF49BBE"> 
      <li id="li_07B4D60E7E2E4630B4878691E575936A"> Haga clic con el botón secundario <span class="uicontrol"> en Elementos secundarios </span> y haga clic en <span class="uicontrol"> Agregar nuevo </span> &gt; <span class="uicontrol"> Tabla de códigos XMLDecoder </span>. Defina el campo, la operación y la ruta según corresponda. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Para utilizar un archivo XML como origen de registro para un conjunto de datos, se deben definir grupos y tablas de decodificadores XML para extraer la información que se va a procesar en el conjunto de datos. En este ejemplo, puede ver cómo definir grupos y tablas de decodificadores para un origen de registro XML de ejemplo para un conjunto de datos web.

El siguiente archivo XML contiene información sobre un visitante de un sitio web, incluido un ID de Experience Cloud, una dirección de correo electrónico, una dirección física e información sobre las vistas de página del visitante.

![](assets/xmlFile_LogSource.png)

Dado que tenemos un único archivo XML, solo necesitamos un grupo de decodificadores, al que se le asigna el nombre &quot;Formato XML de muestra&quot;. Este grupo de descodificadores se aplica a cualquier otro archivo XML con el mismo formato que este archivo. Para empezar a construir tablas de decodificadores XML dentro de este grupo de decodificadores, primero debemos determinar qué información queremos extraer y los campos en los que se almacenarán los datos.

En este ejemplo, extraemos información sobre el visitante y las vistas de página asociadas con ese visitante. Para ello, creamos una tabla de decodificador XML de nivel superior (principal) con información sobre el visitante y una tabla de decodificador XML incrustada (secundaria) con información sobre las vistas de página de ese visitante.

**La información de la tabla principal (visitante) es la siguiente**

* Identificador de tipo de datos para cada fila de datos del archivo XML. Utilizamos VISITOR como identificador para poder identificar rápidamente las filas de datos pertenecientes al visitante y no las vistas de página. Podemos almacenar este valor en el campo x-rowtype.
* ID del visitante, que almacenamos en el campo x-trackingid.
* La dirección de correo electrónico del visitante (contact.email), que almacenamos en el campo x-email.
* El estado de registro del visitante. Si el visitante es un usuario registrado, podemos almacenar el valor &quot;1&quot; en el campo x-is-registration.
* El valor de Ruta es [!DNL logdata.visitor]y el valor de Tabla es [!DNL Log Entry]. Para obtener información sobre estos parámetros, consulte la tabla XMLDecoderGroup anterior.

**La información de la tabla secundaria (vistas de página) es la siguiente:**

* Identificador de tipo de datos para cada fila de datos del archivo XML. Utilizamos &quot;PAGEVIEW&quot; como identificador para poder identificar rápidamente las filas de datos pertenecientes a las vistas de página del visitante y no sólo al visitante. Almacenamos este valor en el campo x-rowtype.
* ID del visitante. Este valor se hereda de la tabla principal y se almacena en el campo x-trackingid.
* Marca de hora de cada vista de página, que se almacena en el campo x-event-time.
* URI de cada vista de página, que se almacena en el campo cs-uri-stem.
* El valor de Ruta es vista de página y el valor de Tabla es &quot;Entrada de registro&quot;. Para obtener información sobre estos parámetros, consulte la tabla XMLDecoderGroup anterior.

La siguiente captura de pantalla muestra una parte del [!DNL Log Processing Dataset Include] archivo con el grupo de decodificadores XML resultante para el archivo XML de ejemplo basado en la estructura analizada de las tablas de decodificadores XML principal y secundario.

![](assets/cft_LogProc_xmldecodergroup_top.png)

![](assets/cfg_LogProcessingInclude_XMLDecoderGroup_bottom.png)

Una tabla que muestra el resultado de este decodificador para nuestro archivo XML de ejemplo tiene un aspecto similar al siguiente:

| x-rowtype | cs—uri-stem | x-email | x-is-registration | x-event-time | x-tracking-id |
|---|---|---|---|---|---|
| VISITANTE |  | foo@bar.com | 1 |  | 1 |
| PAGEVIEW | /index.html |  |  | 2006-01-01 08:00:00 | 1 |
| PAGEVIEW | / |  |  | 2006-01-01 08:00:30 | 1 |

Puede crear una tabla como la anterior en el área de trabajo de datos mediante una interfaz de visor de campos. Para obtener información sobre la interfaz del visor de campos, consulte Herramientas [de configuración de](../../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)conjuntos de datos.

## Uso de #value en un elemento XML para leer su valor de atributo {#section-88758428afb94f0baa5a986604d53bc1}

You can now use the **[!DNL #value]** tag in XML paths to pull the value of an XML element.

Por ejemplo, al especificar previamente una ruta de acceso de la **`<Hit><Page name="Home Page" index="20">home.html</Page></Hit>`** izquierda, no se puede leer el valor de la `<Page>` etiqueta. Para leer el valor de una `<Page>` etiqueta y sus atributos, puede utilizar [!DNL Hit.Page.@name] y [!DNL Hit.Page.@index] respectivamente. También puede extraer el valor de la etiqueta mediante **`Hit.Page.#value`** expresión.

Por ejemplo, puede leer el valor de la etiqueta `<varValue>` agregando el siguiente campo en el decodificador:

```
7 = XMLDecoderField: 
Field = string: x-varvalue-name-added 
Operation = string: LAST 
Path = string:  
<b>#value</b> 
Path = string: varValue 
Table = string: Log Entry
```

Del mismo modo, puede leer el valor de la etiqueta `<Rep>` agregando el siguiente campo en el decodificador:

```
7 = XMLDecoderField: 
Field = string: x-rep-name-added 
Operation = string: LAST 
Path = string: Rep.# 
<b>value</b> 
Path = string: Reps 
Table = string: Log Entry
```

Por el contrario, para leer el valor de la etiqueta element sin atributo, una `<text>` etiqueta bajo una `<line>` etiqueta y su valor se puede leer directamente dando &quot; [!DNL text]&quot; en una ruta o utilizando [!DNL line.text], dependiendo de cómo haya creado el decodificador.

```
2 = XMLDecoderField: 
Field = string: x-chat-text 
Operation = string: LAST 
Path = string:  
<b>text</b> 
Path = string:  
<b>line</b> 
Table = string: Log Entry
```

