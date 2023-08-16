---
description: Muestra tres formas de exportar datos y cómo recuperar exportaciones.
title: Exportación de datos
uuid: de37a60b-09db-4976-b427-f28b4697a8aa
exl-id: b581d617-62e7-4f39-84f3-853c0424bb3b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: ht
source-wordcount: '409'
ht-degree: 100%

---

# Exportación de datos {#exporting-data}

{{eol}}

Muestra tres formas de exportar datos y cómo recuperar exportaciones.

Los datos se pueden exportar desde el tablero de tres formas.

En primer lugar, puede exportarlos desde una visualización individual. En segundo lugar, puede exportar el tablero de trabajo actual, incluidas las configuraciones y selecciones que haya realizado. En tercer lugar, puede exportar un tablero guardado sin necesidad de abrirlo.

Las exportaciones se realizan mediante un proceso de dos pasos. En primer lugar, las exportaciones se ponen en cola en el servidor mediante uno de los tres métodos anteriores. El estado de la exportación se muestra en el menú **[!UICONTROL Exportaciones]** mientras se prepara la exportación. A continuación, cuando las exportaciones estén listas, puede descargar los datos en formato CSV o Excel.

Las exportaciones pueden tardar varios minutos, pero puede seguir utilizando la aplicación durante una exportación.

## Exportación de visualizaciones {#section-46b74b46c2eb44129c8b85a9eabd2304}

Para exportar datos desde una visualización, haga clic en **[!UICONTROL Guardar]** en el menú de herramientas de la visualización.

![](assets/export_visual.png)

La exportación se inicia en el servidor y se añadie un indicador de exportación al menú Exportaciones.

![](assets/export_queued.png)

## Exportación de tableros {#section-27329f2a5fed44b49deb26dc5164531f}

Para iniciar una exportación de datos desde un tablero de trabajo, seleccione **[!UICONTROL Exportar]** en el menú **[!UICONTROL Tablero]**.

![](assets/export_dashboard.png)

La exportación se inicia en el servidor y se añadie un indicador de exportación al menú Exportaciones.

## Exportación de tableros guardados {#section-e989f7b16e25479ab77454f2c34471ba}

Para iniciar una exportación de datos desde un tablero guardado, utilice el Explorador de tableros. En el explorador de tableros, vaya al tablero deseado y selecciónelo para que aparezcan los detalles. En el panel de detalles de la derecha, debajo de **[!UICONTROL Operaciones]**, seleccione **[!UICONTROL Exportar datos]**.

La exportación se inicia en el servidor y se añade un indicador de exportación al menú **[!UICONTROL Exportaciones]**.


## Recuperando exportaciones {#section-0f03c5321c804867b7c72cf92f6f67d0}

Cuando se complete una exportación, aparecerá una notificación emergente para notificarle que la exportación está lista.

![](assets/export_ready.png)

Para recuperar la exportación, utilice el menú **[!UICONTROL Exportaciones]**. Al hacer clic en la marca de verificación verde a la derecha del elemento de exportación deseado, se muestra un menú desplegable. En el submenú **[!UICONTROL Guardar exportación como...]**, seleccione la opción del menú adecuada para descargar la exportación en formato CSV o Excel.

![](assets/export_save_as.png)

Ahora se inicia el proceso de descarga de archivos del explorador.

Las exportaciones no se quitan automáticamente, por lo que puede descargar fácilmente la exportación en cada formato. Puede quitar las exportaciones del menú **[!UICONTROL Exportaciones]** en el panel de navegación izquierdo. De lo contrario, se quitan automáticamente cuando cierre la sesión.

Para quitar una exportación de la **[!UICONTROL Lista de exportaciones]**, haga clic en la marca de verificación a la derecha del título de la exportación y seleccione **[!UICONTROL Quitar de la lista]**.

![](assets/export_remove_from_list.png)
