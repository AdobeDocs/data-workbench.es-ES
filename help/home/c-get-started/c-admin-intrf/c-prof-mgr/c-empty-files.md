---
description: Si no tiene permiso para eliminar archivos de un perfil o no desea eliminarlos permanentemente, puede utilizar archivos vacíos (de byte cero) para ocultar archivos.
title: Ocultar un archivo vaciándolo (byte cero)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Ocultar un archivo vaciándolo (byte cero){#hide-a-file-by-emptying-it-zero-byte}

{{eol}}

Si no tiene permiso para eliminar archivos de un perfil o no desea eliminarlos permanentemente, puede utilizar archivos vacíos (de byte cero) para ocultar archivos.

En el [!DNL Profile Manager], un guión (-), en lugar de una marca de verificación, en una columna identifica un archivo de byte cero.

![](assets/vis_ProfMgr_Zero-byte.png)

A diferencia de otros métodos de ocultación de archivos (como [!DNL order.txt], el parámetro Show y el parámetro Hidden ), la Data Workbench considera que los archivos de byte cero no existen. Por ejemplo, si genera un byte cero para una dimensión que se ha utilizado en una visualización o una definición de métrica, la Data Workbench genera un error para esa visualización o métrica, respectivamente.

Esta funcionalidad es útil por varios motivos, como cuando desea hacer lo siguiente:

* **Hacer que un archivo sea inutilizable** en Data Workbench sin necesidad de los permisos de perfil necesarios para eliminar el archivo.
* **Mover una métrica, dimensión o filtro** a otra ubicación sin necesidad de los permisos de perfil necesarios para eliminar el archivo de la ubicación original.
* **Ocultar elementos de menú.** Por ejemplo, la variable [!DNL Base] el perfil tiene un [!DNL Metric Legend] definida en la variable [!DNL Metric.vw] archivo. Imagine que su empresa ha creado tres leyendas de métricas que desea que aparezcan en el submenú Agregar leyenda > Métrica . Puede usar bytes cero para [!DNL Base] perfil [!DNL Metric.vw] para que solo aparezca el nuevo submenú y las tres nuevas leyendas de métricas.

**Ocultar un archivo**

1. En el [!DNL Profile Manager], abra las carpetas y subcarpetas necesarias para localizar el archivo que desea bytes cero.
1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Make Local]**.
1. Abra el archivo local y elimine su contenido.
1. Guarde y cierre el archivo.
