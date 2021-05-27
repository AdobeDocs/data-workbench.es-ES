---
description: Exportación, copia y marcador desde el escritorio.
title: Uso del menú de miniaturas de la superficie de trabajo
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Uso del menú de miniaturas de la superficie de trabajo{#using-the-worktop-thumbnail-menu}

Exportación, copia y marcador desde el escritorio.

Haga clic con el botón derecho en un espacio de trabajo para exportar, copiar y marcar funciones desde el escritorio.

![](assets/thumbnail_menu.png)

## Descripciones de la interfaz {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Los siguientes elementos están disponibles en el menú de miniaturas [!DNL Worktop]:

**Espacio de trabajo del servidor:** *nombre*

Solo aparece para espacios de trabajo de servidor sin editar. Identifica el espacio de trabajo con nombre como el mismo que el espacio de trabajo almacenado en el servidor.

**Fecha:** *día y hora*

Fecha y hora en que se abrió por última vez el espacio de trabajo.

**Versión local de:** *name*

Solo aparece para versiones locales de espacios de trabajo del servidor. Identifica el espacio de trabajo con nombre como una versión local editada de un espacio de trabajo almacenado en el servidor.

**Espacio de trabajo del usuario:** *nombre*

Solo aparece para espacios de trabajo de usuario. Identifica el espacio de trabajo con nombre como un espacio de trabajo que solo existe en el equipo local.

**Calcular en segundo plano**

Solo aparece cuando se trabaja en línea. Mantiene las consultas en el espacio de trabajo seleccionado ejecutándose en segundo plano mientras continúa trabajando. Cuando se selecciona, la miniatura muestra la siguiente información, que indica el progreso de las consultas:

* Trabajando: *n%* - indica que la consulta se está procesando y el porcentaje del procesamiento que se ha completado.
* ** nMB Query Load - tamaño total del resultado de la consulta. La carga de la consulta es proporcional a la carga total de memoria del servidor de Data Workbench, pero no se correlaciona directamente. Como guía, una carga de consulta de 10 MB o superior puede sobrecargar el sistema. La carga de consulta mostrada no tiene en cuenta la agrupación en clúster.

   >[!NOTE]
   >
   >Si Compute in Background permanece seleccionado, las consultas del espacio de trabajo seleccionado se convierten en consultas permanentes, que se actualizan y utilizan la carga de memoria. Asegúrese de anular la selección de Calcular en segundo plano cuando haya terminado de trabajar en el espacio de trabajo.

**Exportar a Excel**

Exportar datos de espacio de trabajo a tabla en Microsoft Excel (archivos .xls y .xslx). Al exportar un espacio de trabajo a Excel, la Data Workbench exporta datos de ciertas visualizaciones, leyendas de dimensiones y valores y anotaciones de texto a un nuevo libro de Excel con una visualización por hoja de cálculo.

**Exportar a plantilla de Excel**

Exportar a una plantilla de Excel (.xltx).

**Copy**

Copia el espacio de trabajo. Para obtener más información sobre cómo pegar un espacio de trabajo copiado, consulte [Copia y pegado de espacios de trabajo existentes](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Revertir a la versión del servidor**

Solo aparece para versiones locales de espacios de trabajo del servidor. Elimina la copia local de este espacio de trabajo. El original permanece en el servidor.

**Eliminar**

Solo aparece para espacios de trabajo de usuario. Elimina el espacio de trabajo del usuario, que solo existe en el equipo local. Para obtener información sobre la eliminación de espacios de trabajo del servidor de Datas Workbench conectado, consulte [Eliminación de archivos de su perfil de trabajo](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Guardar en servidor**

Solo aparece para versiones locales de espacios de trabajo de servidor y espacios de trabajo de usuario, y funciona solo para aquellos usuarios con los permisos adecuados. Guarda la copia local del espacio de trabajo en el servidor. De forma predeterminada, los espacios de trabajo se guardan en la carpeta `<profile name>\Workspaces\<tab name>` de trabajo correspondiente.

**Marcador**

Añada un marcador a un espacio de trabajo para recuperarlo rápidamente más tarde.

Un icono de marcador ![](assets/bookmark_icon.png) aparecerá encima del espacio de trabajo en la superficie de trabajo y el nombre del espacio de trabajo aparecerá en el panel Marcadores. ![](assets/bookmark_worktop.png)
