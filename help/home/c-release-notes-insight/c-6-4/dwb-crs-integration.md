---
description: La función de exportación Servicio de registro de clientes (CRS) permite exportar datos del Área de trabajo de datos a los servicios principales de Adobe Analytics para integrarlos con otras funciones de Analytics, incluidos Informes y análisis.
title: Exportación a los servicios principales de Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportación a los servicios principales de Analytics{#exporting-to-analytics-core-services}

La función de exportación Servicio de registro de clientes (CRS) permite exportar datos del Área de trabajo de datos a los servicios principales de Adobe Analytics para integrarlos con otras funciones de Analytics, incluidos Informes y análisis.

>[!NOTE]
>
>Para que la función de exportación de CRS funcione, el ID de Analytics de un visitante debe basarse en el servicio de ID de Experience Cloud (ECID). Aunque el ECID se puede rellenar en el área de trabajo de datos para un visitante, si el cliente está en el período de gracia o la cookie del visitante no se ha reemplazado por ECID, la exportación de CRS no funcionará para ese visitante. Para obtener más información, consulte [Identificación de visitantes](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) y período [de gracia del servicio de](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)ID.

En una tabla **de** detalles (haga clic con el botón secundario **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** en un espacio de trabajo), puede establecer los valores de atributos y las variables necesarias para la integración con Informes y análisis de Analytics (mediante Adobe Pipeline Services).

1. **Haga clic con el botón secundario en el encabezado de la tabla y, a continuación, haga clic en Nuevo servicio de registro de clientes.**

   ![](assets/6_4_CRS.png)

1. **Asigne un nombre al archivo de exportación y guárdelo.**

   Se abrirá la ventana de edición del archivo de exportación.

1. **Abra** **Consulta > Configuración** de CRS.
1. **Haga clic con el botón secundario en Atributos de CRS > Agregar nuevo.**
1. **Introduzca** ***los*** parámetros **de atributos** CRS.

   Abra la nueva entrada e introduzca o compruebe los valores en la sección Atributos *de* CRS del archivo de exportación:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nombre de atributo</b> </p> </td> 
      <td colname="col2">Nombre de la variable Atributos <i>del</i> cliente que se muestra en <i>Informes y análisis</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Tipo de atributo</b> </td> 
      <td colname="col2"> <p>Este parámetro acepta valores de (<i>int</i>, <i>string</i>). </p> <p>Nota: Si un atributo <b>no está</b> suscrito en Analytics: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">El atributo se creará con cualquier tipo de atributo válido admitido por Analytics (para esta versión solo está limitado a <i>string</i> e <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Si se introduce un tipo de atributo no válido, recibirá un error que indica que no se pudo suscribir a Analytics. </li> 
      </ul> </p> <p>Si <b>ya</b> se ha suscrito a un atributo en Analytics: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Asegúrese de introducir el tipo de atributo correcto para el atributo ya suscrito. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Si escribe un tipo incorrecto para el atributo, su comportamiento dependerá del manejo que haga Analytics de los tipos de atributos. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nombre del campo</b> </p> </td> 
      <td colname="col2">Nombre de la dimensión o métrica desde la que se seleccionan los valores de atributo. <p>Nota: El nombre <i><b>del</b></i> campo en Atributos <i>de</i> CRS debe ser el mismo que los campos <b><i>de</i> salida &gt; Nombre <i></i></b> del campo (que se rellena automáticamente en función del atributo seleccionado). Si el nombre <i>del</i> campo no es válido, la exportación no se ejecutará. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Haga clic con el botón secundario **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Especifique la información de **[!UICONTROL Report Suite ID]**.

   Abra la nueva entrada e introduzca o verifique los valores en la sección Grupo *de* informes del archivo de exportación:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Report Suite</b> </td> 
      <td colname="col2">ID del grupo de informes en <i>Informes y análisis</i> que identifica las variables de atributos <i>del</i> cliente que se exportan. <p> <p>Nota: Aunque <i>Informes y análisis</i> permite agregar a varios grupos de informes, Área de trabajo de datos 6.4 solo exportará un grupo de informes único identificado en el <i>índice 0</i>. <p>El valor del grupo de informes ingresado en este campo es la ID del grupo de informes (y no el nombre del grupo de informes). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Introduzca el parámetro Campo ECID.

   **Campo** ECID: Nombre de la dimensión del perfil que representa el ID de Adobe Experience Cloud. Se trata de un campo obligatorio y no se exportará ningún valor de dimensión no válido introducido.

1. (opcional) Complete el parámetro Campo de ID de visitante.

   **Campo** de ID de visitante: Si el usuario desea enviar cualquier otro ID personalizado para un visitante en sus datos, es aquí donde introduce el nombre de la dimensión que representa el ID de visitante personalizado. Se trata de un campo opcional y se puede dejar vacío.
