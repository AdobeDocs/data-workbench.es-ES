---
description: Información sobre las opciones de menú disponibles en el menú de archivos de Workspace.
title: Menú Archivo de Workspace
uuid: abbdb2db-d918-4edf-977c-1daaf8a71721
exl-id: b2bb7d89-249c-40f5-85aa-02fea0b0fc61
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 1%

---

# Menú Archivo de Workspace{#workspace-file-menu}

{{eol}}

Información sobre las opciones de menú disponibles en el menú de archivos de Workspace.

En el espacio de trabajo, haga clic en **[!UICONTROL File]**.

![](assets/mnu_file.png)

En la tabla siguiente se proporcionan descripciones de cada elemento de menú.

**Guardar**

Guarda el espacio de trabajo. Consulte [Guardar espacios de trabajo](../../../home/c-get-started/c-work-worksp/c-save-wksp.md#concept-e0c34e75cc194e57bd02d1f02316a606).

**Guardar copia como**

Guarda el espacio de trabajo con un nombre diferente o en una ubicación diferente. Consulte [Guardar espacios de trabajo](../../../home/c-get-started/c-work-worksp/c-save-wksp.md#concept-e0c34e75cc194e57bd02d1f02316a606).

**Revertir**

Revierte a la última versión guardada del espacio de trabajo actual.

**Ajustar espacio de trabajo**

Cambia el tamaño de las visualizaciones a la resolución de visualización que está utilizando. Esto resulta útil para ajustar rápidamente la visualización de las presentaciones.

**Tamaño de página**

Define el tamaño de página de trabajo de un espacio de trabajo. Puede seleccionar Pantalla completa, Estándar o cualquiera de los tamaños específicos para pantallas de equipos, páginas impresas e informes. Pantalla completa llena la pantalla en particular y Estándar es una configuración que se puede configurar para adaptarse al tamaño de pantalla estándar de la organización. La configuración estándar predeterminada llena la pantalla al usar una resolución de 1024 x 768.

Espacios de trabajo que se copian y se guardan como [!DNL .png] Los archivos, o impresos también utilizan este tamaño de página para los resultados. Los tamaños de página más grandes que la visualización de Data Workbench utilizan barras de desplazamiento, mientras que los tamaños más pequeños están centrados en la pantalla y muestran un borde gris claro alrededor del espacio de trabajo.

**Descripción**

Permite crear o editar una descripción textual del espacio de trabajo. Este texto aparece en la sección [!DNL Worktop] debajo de la miniatura. Consulte [Adición de una descripción a un espacio de trabajo](../../../home/c-get-started/c-work-worksp/t-add-wksp-desc.md#task-163734487e8848dfa0a4d8da6323a963).

**Calcular en segundo plano**

(Solo aparece cuando se trabaja en línea). Mantiene las consultas en el espacio de trabajo seleccionado ejecutándose en segundo plano mientras continúa trabajando. Cuando se selecciona, la miniatura muestra la siguiente información, que indica el progreso de las consultas:

* Trabajando: *n%* : indica que la consulta se está procesando y el porcentaje del procesamiento que se ha completado.
* *n* Carga de consulta de MB: tamaño total del resultado de la consulta. La carga de la consulta es proporcional a la carga total de memoria del servidor de Data Workbench, pero no se correlaciona directamente. Como guía, una carga de consulta de 10 MB o superior puede sobrecargar el sistema. La carga de consulta mostrada no tiene en cuenta la agrupación en clúster.

>[!NOTE]
>
>Si Compute in Background permanece seleccionado, las consultas del espacio de trabajo seleccionado se convierten en consultas permanentes, se actualizan y se utiliza la carga de memoria. Asegúrese de borrar la selección de Compute in Background cuando haya terminado de trabajar en el espacio de trabajo.

**Cierre**

Cierra el espacio de trabajo. Haga clic en **[!UICONTROL Close]** > **[!UICONTROL Save]** para guardar los cambios realizados en el espacio de trabajo, o haga clic en **[!UICONTROL Close]** > **[!UICONTROL Don’t Save]** para volver a la [!DNL Worktop] sin guardar los cambios realizados en el espacio de trabajo.

También puede guardar los cambios, cerrar el espacio de trabajo y volver al [!DNL Worktop] utilizando cualquiera de los siguientes métodos:

* Haga clic en el logotipo de Data Workbench en la esquina superior izquierda del espacio de trabajo.
* Si el ratón tiene botones de navegación, haga clic en el botón de retroceso del ratón.

También puede anular los cambios cerrando el espacio de trabajo sin guardar pulsando **Ctrl + Retroceso**.

**Exportar a Excel desde plantilla**

Si Microsoft Excel está instalado en el equipo de Data Workbench, inicia automáticamente Microsoft Excel y exporta los datos de ciertas visualizaciones, ciertas leyendas y anotaciones de texto al archivo de Excel de la plantilla ( [!DNL .xls]o [!DNL .xlsx]) que seleccione. Consulte [Exportación a un archivo de Excel de plantilla](../../../home/c-get-started/c-work-worksp/c-ex-wksp.md#section-814772929ca64cf6b92b89d3fdd02302).
