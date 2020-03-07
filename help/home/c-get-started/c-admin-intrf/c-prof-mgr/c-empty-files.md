---
description: Si no tiene permiso para eliminar archivos de un perfil o no desea eliminar un archivo de forma permanente, puede utilizar archivos vacíos (de byte cero) para ocultar archivos.
solution: Analytics
title: Ocultar un archivo vaciándolo (byte cero)
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ocultar un archivo vaciándolo (byte cero){#hide-a-file-by-emptying-it-zero-byte}

Si no tiene permiso para eliminar archivos de un perfil o no desea eliminar un archivo de forma permanente, puede utilizar archivos vacíos (de byte cero) para ocultar archivos.

En la columna [!DNL Profile Manager], un guión (-), en lugar de una marca de verificación, identifica un archivo de byte cero.

![](assets/vis_ProfMgr_Zero-byte.png)

A diferencia de otros métodos para ocultar archivos (como [!DNL order.txt]el parámetro Mostrar y el parámetro Oculto), el Área de trabajo de datos considera que los archivos de byte cero no existen. Por ejemplo, si genera un byte cero en una dimensión que se ha utilizado en una visualización o en una definición de métrica, Área de trabajo de datos generará un error para esa visualización o métrica, respectivamente.

Esta funcionalidad es útil por varios motivos, incluido el momento en que desea realizar las siguientes acciones:

* **Convierta un archivo en inutilizable** en el área de trabajo de datos sin necesidad de los permisos de perfil necesarios para eliminarlo.
* **Mueva una métrica, dimensión o filtro** a otra ubicación sin necesidad de los permisos de perfil necesarios para eliminar el archivo de la ubicación original.
* **Ocultar elementos de menú.** Por ejemplo, el [!DNL Base] perfil tiene una [!DNL Metric Legend] definición en el [!DNL Metric.vw] archivo. Imagine que su empresa ha creado tres leyendas de métricas que desea que aparezcan en un submenú Agregar leyenda > Métrica. Puede generar un byte cero en el [!DNL Base] archivo de [!DNL Metric.vw] perfil para que solo aparezcan el nuevo submenú y las tres nuevas leyendas de métricas.

**Para ocultar un archivo**

1. En la carpeta [!DNL Profile Manager], abra las carpetas y subcarpetas necesarias para localizar el archivo de byte cero.
1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Make Local]**.
1. Abra el archivo local y elimine su contenido.
1. Guarde y cierre el archivo.

