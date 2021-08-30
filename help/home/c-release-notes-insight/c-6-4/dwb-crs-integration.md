---
description: La función de exportación Servicio de registro de clientes (CRS) le permite exportar datos de Data Workbench a los servicios principales de Adobe Analytics para integrarlos con otras funciones de Analytics, como Reports & Analytics.
title: Exportación a los servicios principales de Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# Exportación a los servicios principales de Analytics{#exporting-to-analytics-core-services}

La función de exportación Servicio de registro de clientes (CRS) le permite exportar datos de Data Workbench a los servicios principales de Adobe Analytics para integrarlos con otras funciones de Analytics, como Reports &amp; Analytics.

>[!NOTE]
>
>Para que la función de exportación de CRS funcione, el ID de Analytics de un visitante debe basarse en el servicio de ID de Experience Cloud (ECID). Aunque el ECID puede rellenarse en Data Workbench para un visitante, si el cliente está en el período de gracia o si la cookie del visitante no se ha sustituido por ECID, la exportación de CRS no funcionará para ese visitante. Para obtener más información, consulte [Identificación de visitantes](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) y [Período de gracia del servicio de ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html).

Desde una **Tabla de detalles** (haga clic con el botón derecho **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** en un espacio de trabajo), puede establecer valores de atributos y las variables necesarias para integrarse con Reports &amp; Analytics de Analytics (mediante los servicios de canalización de Adobe).

1. **Haga clic con el botón derecho en el encabezado de tabla y haga clic en Nuevo servicio de registro de cliente.**

   ![](assets/6_4_CRS.png)

1. **Asigne un nombre al archivo de exportación y guárdelo.**

   Se abrirá la ventana de edición del archivo de exportación.

1. **** **OpenQuery > Configuración CRS**.
1. **Haga clic con el botón derecho en Atributos CRS > Agregar nuevo.**
1. **** ***Introducir parámetros de*** **atributos CRS**.

   Abra la nueva entrada e introduzca o compruebe los valores en la sección *CRS Attributes* del archivo de exportación:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nombre de atributo</b> </p> </td> 
      <td colname="col2">Nombre de la variable <i>Customer Attributes</i> que se muestra en <i>Reports &amp; Analytics</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Tipo de atributo</b> </td> 
      <td colname="col2"> <p>Este parámetro acepta valores de (<i>int</i>, <i>string</i>). </p> <p>Nota: Si un atributo está <b>no</b> suscrito a en Analytics: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">El atributo se creará con cualquier tipo de atributo válido admitido por Analytics (para esta versión solo está limitado a <i>string</i> y <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Si se introduce un tipo de atributo no válido, recibirá un error que indica que no se ha suscrito a Analytics. </li> 
      </ul> </p> <p>Si un atributo <b>ya</b> está suscrito a en Analytics: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Asegúrese de introducir el tipo de atributo correcto para el atributo ya suscrito. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Si introduce el tipo incorrecto para el atributo, su comportamiento dependerá de la gestión de los tipos de atributo por parte de Analytics. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nombre del campo</b> </p> </td> 
      <td colname="col2">Nombre de la dimensión o métrica desde la que se seleccionan los valores de atributo. <p>Nota: El <i><b>Nombre de campo</b></i> en <i>Atributos CRS</i> debe ser el mismo que los <b><i>Campos de salida</i> &gt; <i>Nombre de campo</i></b> (que se rellena automáticamente en función del atributo seleccionado). Si el <i>Nombre de campo</i> no es válido, la exportación no se ejecutará. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Haga clic con el botón derecho en **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Especifique la información de **[!UICONTROL Report Suite ID]**.

   Abra la nueva entrada e introduzca o compruebe los valores en la sección *Grupo de informes* del archivo de exportación:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Grupo de informes</b> </td> 
      <td colname="col2">ID del grupo de informes en <i>Reports &amp; Analytics</i> que identifica las variables <i>Customer Attribute</i> que se exportan. <p> <p>Nota: Aunque <i>Reports &amp; Analytics</i> le permite agregar a varios grupos de informes, la Data Workbench 6.4 solo exportará un único grupo de informes identificado en el <i>índice 0</i>. <p>El valor del grupo de informes introducido en este campo es la ID del grupo de informes (y no el nombre del grupo de informes). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Introduzca el parámetro de campo ECID.

   **Campo ECID**: Nombre de la dimensión del perfil que representa el Adobe Experience Cloud ID. Se trata de un campo obligatorio y no se exportará ningún valor de dimensión no válido introducido.

1. (opcional) Complete el parámetro Campo de ID de visitante .

   **Campo** de ID de visitante: Si el usuario desea enviar cualquier otro ID personalizado para un visitante en sus datos, aquí es donde introduce el nombre de la dimensión que representa el ID de visitante personalizado. Se trata de un campo opcional y se puede dejar vacío.
