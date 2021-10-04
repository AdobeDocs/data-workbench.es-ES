---
description: Abra Atribución de mejor ajuste en el menú Premium y siga estos pasos para crear un modelo de atribución de mejor ajuste.
title: Creación de un modelo de atribución de mejor ajuste
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
exl-id: e0a42374-2500-46a3-a72a-708ab2d228db
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 1%

---

# Creación de un modelo de atribución de mejor ajuste{#build-a-best-fit-attribution-model}

Abra Atribución de mejor ajuste en el menú Premium y siga estos pasos para crear un modelo de atribución de mejor ajuste.

Consulte una descripción general de [Atribución de mejor ajuste](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1).

1. Abra **Atribución de mejor ajuste**.

   Abra un espacio de trabajo y haga clic en **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >La atribución de mejor ajuste es una función de Adobe Analytics Premium que requiere que habilite Premium en el perfil. Requiere que actualice el certificado y añada el perfil Premium a su archivo profile.cfg. Consulte [Actualización del servidor DWB: 6.2 a 6.3](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md) para DWB 6.3.

1. Establezca la métrica **[!UICONTROL Success]**.

   >[!NOTE]
   >
   >Puede arrastrar una métrica de una tabla **[!UICONTROL Finder]** al panel izquierdo de la visualización Atribución o seleccionarla del menú **Entradas**.

   Haga clic **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. Se abrirá el menú de métricas. ![](assets/attrib_set_success_metric.png)

   Seleccione una métrica que identifique una conversión correcta.

1. (opcional) Configure la métrica **Ingresos**.

   Establezca una métrica para evaluar los ingresos en todo el proceso de conversión.

1. Establezca la métrica **Táctil**.

   >[!NOTE]
   >
   >La configuración de una métrica táctil solo es necesaria si está intentando crear métricas de éxito automáticamente arrastrando elementos de dimensión a la visualización.

   Haga clic en el menú **[!UICONTROL Inputs]** y seleccione **Definir contacto**, o arrastre una métrica desde el Buscador. ![](assets/attrib_set_touch.png)

   Se utilizará para derivar métricas de canal cuando los elementos de dimensión se utilicen como entradas.

1. Establezca una ventana **Success**.

   Haga clic en [!DNL Inputs > Success Window]. Seleccione un intervalo de fechas de una tabla y asigne un nombre a la ventana de éxito. Haga clic en **[!UICONTROL Workspace Selection]** y las fechas seleccionadas se asignarán como intervalo de tiempo para la métrica de éxito.

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >Dado que la ventana Éxito es una selección de estación de trabajo, puede incluir cualquier dimensión en la ventana Éxito.

1. Establezca un **[!UICONTROL Touch Window]**.

   Haga clic en [!DNL Inputs > Touch Window]. Seleccione un intervalo de fechas de una tabla y asigne un nombre a la ventana Táctil. Haga clic en **[!UICONTROL Workspace Selection]** y las fechas seleccionadas se asignarán como intervalo de tiempo para la métrica de éxito.

   ![](assets/attrib_set_touch_window.png)

   De forma predeterminada, la ventana **Touch** se establece en el mismo período de tiempo que la ventana **[!UICONTROL Success]**.

1. (opcional) Definir un filtro de formación.

   También puede especificar un **Filtro de capacitación** en el espacio de trabajo para filtrar los datos del visitante.

   >[!NOTE]
   >
   >Al configurar las ventanas de éxito y táctil, puede aplicar el filtro de formación a las selecciones actuales del espacio de trabajo para limitar aún más los datos.

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >El conjunto de formación siempre se obtiene de visitantes que satisfacen la ventana de éxito. Al filtrar con el Editor de filtros, puede crear un subconjunto de visitantes notificados en la ventana Éxito.

1. Especifique las métricas de canal que representan los toques.

   Arrastre métricas a la visualización o selecciónelas en el menú [!DNL Inputs] > [!DNL Add Channel] . Si todavía no tiene métricas definidas para campañas o canales, pero tiene dimensiones que representan canales, la visualización puede crearlas automáticamente con la especificación de una métrica Táctil.

   Por ejemplo, con la métrica Táctil configurada en [!DNL Hits] y un [!DNL dimension] llamado [!DNL Media Type] con elementos que incluyen elementos como [!DNL Email], [!DNL Press Release], [!DNL Print Ad] y [!DNL Social Media], la visualización generará métricas de canal del formulario [!DNL Hits where Media Type = Email] al arrastrar y soltar los elementos en la visualización.

1. Presione **Go**.

   Se ejecutará el proceso de análisis de mejor ajuste y un gráfico mostrará las atribuciones por canal en función de las entradas seleccionadas.

   >[!NOTE]
   >
   >Haga clic con el botón derecho en **Model Complete** en el análisis completado para ver las estadísticas del modelo de atribución.

   ![](assets/attrib_visualization.png)

Cuando se complete, un gráfico mostrará un modelo de atribución calculado por canal y una distribución de la métrica *Ingresos* (si se ha establecido). El modelo se puede guardar internamente o exportar a otros sistemas.

>[!NOTE]
>
>**[!UICONTROL Streaming]**,  **[!UICONTROL Online]** los  **[!UICONTROL Offline]** modos y producen diferentes efectos al crear un modelo de atribución en función de la latencia de los datos que se están evaluando. En el modo de transmisión, se mostrará el mensaje de detalle **[!UICONTROL Model Complete]**. En los modos En línea y sin conexión, se mostrará el detalle **[!UICONTROL Local Model Complete]**.

## Menú Opciones {#section-22288867f6c8483a8a38410f4b948346}

El menú **Opciones** proporciona funciones avanzadas para configurar y mostrar el análisis de atribución de mejor ajuste.

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Menú Opciones </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"><span class="uicontrol"> Definir filtro de formación  </span> </td>
   <td colname="col2"> El filtro de formación se utiliza con la ventana de éxito para filtrar la población al crear el modelo de atribución. Proporcionará un subconjunto de datos que incluye solo los visitantes que desee analizar. <p>Nota: Los usuarios con experiencia también pueden aprovechar la flexibilidad de los filtros para centrarse más allá de la línea temporal de las ventanas de éxito y táctiles. Por ejemplo, además de seleccionar un intervalo de tiempo, puede seleccionar un conjunto de <i>Dominios de referencia</i> para examinar únicamente la atribución para los usuarios de esos dominios. </p> </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Mostrar descripción del filtro complejo  </span> </td>
   <td colname="col2"> Muestra el código de filtro para el filtro de formación, la ventana de éxito y la ventana táctil. </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Guardar modelo  </span> </td>
   <td colname="col2"> Guarda el modelo de atribución actual para uso futuro. </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Modelo de carga  </span> </td>
   <td colname="col2"> Abre un modelo de atribución guardado anteriormente. </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Vista de presentación  </span> </td>
   <td colname="col2"> Oculta la barra de menús superior para la presentación. </td>
  </tr>
  <tr>
   <td colname="col1"> <p><b>Opciones &gt; </b> Avanzado incluye funciones para definir el tamaño del conjunto de formación y especificar el método que se aplicará en caso de desequilibrio de clase. </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Avanzado &gt; Tamaño del conjunto de formación  </span> </td>
   <td colname="col2"> <p>Define el tamaño del conjunto de formación. </p> <p>Nota:  El tamaño de formación predeterminado es Grande para 250 000 visitantes. </p>
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD">
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Pequeño = 50.000 </li>
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">Pequeño = 75.000 </li>
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">Normal = 100.000 </li>
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">Grande = 250,00 </li>
     <li id="li_34B60233C84F48F1BCB8040C5195411A">Enorme = 500.000 </li>
    </ul> </td>
  </tr>
  <tr>
   <td colname="col1"><b>Avanzado &gt; Equilibrio de clase  </b> </td>
   <td colname="col2"> <p>Identifica y define el número de registros de entrada que se generarán para un problema de desequilibrio de clase en función del tamaño del conjunto de datos. </p> </td>
  </tr>
 </tbody>
</table>

| Opciones Restablecer y eliminar | Descripción |
|---|---|
| **[!UICONTROL Reset Model]** | En el menú **[!UICONTROL Reset]**, seleccione **[!UICONTROL Reset Model]** para borrar la visualización pero mantener las métricas de entrada. |
| **[!UICONTROL Reset All]** | En el menú **[!UICONTROL Reset]**, seleccione **[!UICONTROL Reset All]** para borrar la visualización y las métricas de entrada. |
| **[!UICONTROL Remove]** | Haga clic con el botón derecho en cualquier entrada y seleccione **[!UICONTROL Remove]** para borrar la métrica de la entrada seleccionada. |
| **[!UICONTROL Remove All]** | Haga clic con el botón derecho en *Channels* y seleccione **[!UICONTROL Remove All]** para borrar todas las métricas de entrada. |
