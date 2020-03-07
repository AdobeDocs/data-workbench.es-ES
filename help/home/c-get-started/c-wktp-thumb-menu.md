---
description: Cómo exportar, copiar y marcar desde el escritorio.
solution: Analytics
title: Uso del menú de miniaturas de Escritorio
topic: Data workbench
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uso del menú de miniaturas de Escritorio{#using-the-worktop-thumbnail-menu}

Cómo exportar, copiar y marcar desde el escritorio.

Haga clic con el botón secundario en un espacio de trabajo para exportar, copiar y marcar funciones desde el escritorio.

![](assets/thumbnail_menu.png)

## Descripciones de interfaz {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Los siguientes elementos están disponibles en el menú de [!DNL Worktop] miniaturas:

**Espacio de trabajo del servidor:** *name*

Solo aparece para espacios de trabajo de servidor sin editar. Identifica el espacio de trabajo con nombre igual que el espacio de trabajo almacenado en el servidor.

**Fecha:** *día y hora*

Fecha y hora de la última vez que se abrió el área de trabajo.

**Versión local de:** *name*

Solo aparece para versiones locales de espacios de trabajo del servidor. Identifica el espacio de trabajo con nombre como una versión local editada de un espacio de trabajo almacenado en el servidor.

**Espacio de trabajo del usuario:** *name*

Solo aparece para espacios de trabajo de usuario. Identifica el espacio de trabajo con nombre como un espacio de trabajo que existe solamente en el equipo local.

**Calcular en segundo plano**

Solo aparece cuando se trabaja en línea. Mantiene las consultas del espacio de trabajo seleccionado en segundo plano mientras continúa trabajando. Cuando se selecciona, la miniatura muestra la siguiente información, que indica el progreso de las consultas:

* Trabajando: *n%* : indica que la consulta se está procesando y el porcentaje del procesamiento que se ha completado.
* *n* MB Carga de consulta: tamaño total del resultado de la consulta. La carga de consultas es proporcional a la carga total de memoria del servidor de Área de trabajo de datos, pero no se correlaciona directamente. Como guía, una carga de consulta de 10 MB o más puede agotar el sistema. La carga de consulta que se muestra no tiene en cuenta el agrupamiento.

   >[!NOTE]
   >
   >Si la opción Calcular en segundo plano permanece seleccionada, las consultas del espacio de trabajo seleccionado se convierten en consultas permanentes, que se actualizan y utilizan la carga de memoria. Asegúrese de anular la selección de Calcular en segundo plano cuando termine de trabajar en el espacio de trabajo.

**Exportar a Excel**

Exportar datos del espacio de trabajo a una tabla en Microsoft Excel (archivos .xls y .xslx). Al exportar un espacio de trabajo a Excel, el Área de trabajo de datos exporta datos de ciertas visualizaciones, leyendas de dimensión y valor y anotaciones de texto a un nuevo libro de Excel con una visualización por hoja de cálculo.

**Exportar a plantilla de Excel**

Exportar a una plantilla de Excel (.xltx).

**Copiar**

Copia el espacio de trabajo. Para obtener más información sobre cómo pegar un espacio de trabajo copiado, consulte [Copia y pegado de espacios de trabajo existentes](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Revertir a la versión del servidor**

Solo aparece para versiones locales de espacios de trabajo del servidor. Elimina la copia local de este espacio de trabajo. El original permanece en el servidor.

**Eliminar**

Solo aparece para espacios de trabajo de usuario. Elimina el espacio de trabajo del usuario, que solo existe en el equipo local. Para obtener información sobre la eliminación de espacios de trabajo del servidor del Área de trabajo de datos conectado, consulte [Eliminación de archivos del perfil](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b)de trabajo.

**Guardar en servidor**

Solo aparece para versiones locales de espacios de trabajo de servidor y espacios de trabajo de usuario y funciona solo para los usuarios con los permisos adecuados. Guarda la copia local del espacio de trabajo en el servidor. De forma predeterminada, los espacios de trabajo se guardan en la `<profile name>\Workspaces\<tab name>` carpeta de trabajo correspondiente.

**Marcador**

Marque un espacio de trabajo para recuperarlo rápidamente más tarde.

Aparecerá un icono de marcador ![](assets/bookmark_icon.png) encima del espacio de trabajo en la superficie de trabajo y el nombre del espacio de trabajo aparecerá en el panel Marcador. ![](assets/bookmark_worktop.png)

