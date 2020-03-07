---
description: Puede exportar un espacio de trabajo como archivo de imagen .png o exportar los datos desde determinadas ventanas a un archivo de Excel (.xls o .xlsx).
solution: Analytics
title: Exportación de un espacio de trabajo
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportación de un espacio de trabajo{#export-a-workspace}

Puede exportar un espacio de trabajo como archivo de imagen .png o exportar los datos desde determinadas ventanas a un archivo de Excel (.xls o .xlsx).

## Exportación de espacios de trabajo como archivos PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Puede guardar una instantánea de un espacio de trabajo en formato de gráfico de red portátil (`.png` archivos). Las siguientes opciones de color están disponibles al guardar espacios de trabajo como `.png` archivos:

* **El fondo** negro copia el espacio de trabajo como se muestra.
* **El fondo** blanco copia los elementos del espacio de trabajo en color y los muestra en un fondo blanco.
* **El fondo blanco (blanco y negro)** copia los elementos del espacio de trabajo en escala de grises y los muestra en un fondo blanco.

**Para exportar un espacio de trabajo como archivo .png**

En el menú de la barra de título de un espacio de trabajo, haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

Aparecerá el cuadro de diálogo [!UICONTROL Save Image As] .

Vaya al directorio en el que desea guardar el archivo, cambie el nombre del archivo si es necesario y haga clic en **[!UICONTROL Save]**.

## Exportar datos del espacio de trabajo a Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Al exportar un espacio de trabajo a Excel, el Área de trabajo de datos exporta datos de ciertas visualizaciones, leyendas de dimensión y valor y anotaciones de texto a un nuevo libro de Excel con una visualización por hoja de cálculo.

Para exportar espacios de trabajo y ventanas individuales a Microsoft Excel, deben cumplirse los siguientes requisitos:

* Microsoft Excel debe estar instalado en el mismo equipo que el Área de trabajo de datos.
* La cuenta de usuario en la que se está ejecutando el proceso de Área de trabajo de datos debe tener permiso para acceder a Microsoft Excel.

>[!NOTE]
>
>* Al exportar datos como archivos de Excel, se abre una nueva instancia de Excel. Para obtener más información sobre este proceso, consulte [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Aunque el Área de trabajo de datos admite más de 256 columnas y 65.536 filas de datos, las versiones de Microsoft Excel anteriores a la versión 8.0 no lo hacen.
>



Si se cumplen estos requisitos, Área de trabajo de datos inicia automáticamente Microsoft Excel y exporta los datos a un nuevo libro de Excel. Los datos no se exportan desde las visualizaciones siguientes: gráficos, exploradores de rutas, mapas de procesos, gráficos de dispersión y globos.

## Aplicar títulos personalizados {#section-a332e157554546cb8e88922a8d7a4fa2}

A menos que haya especificado un título Personalizado para la ventana del [!UICONTROL Export] menú, se utilizará el nombre de la hoja de cálculo [!UICONTROL Export title] (por ejemplo, Tabla de ciudad).

1. Haga clic con el botón derecho en el borde superior de la ventana y haga clic en el **[!UICONTROL Custom title]** campo.
1. Escriba el título que desea aplicar a la ventana.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Si introduce un guión (-) en el [!UICONTROL Custom title] campo, esta visualización no se exporta con el espacio de trabajo.

Al exportar el espacio de trabajo a Excel, la hoja de cálculo que contiene los datos de esta ventana recibe el nombre del título especificado en lugar del título del [!UICONTROL Export title] campo.

## Exportación de un espacio de trabajo o una barra lateral a Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Para exportar datos del espacio de trabajo a un archivo nuevo[!DNL .xls]o[!DNL .xlsx]**

1. En la barra de título del espacio de trabajo, haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Especifique si desea exportar el espacio de trabajo, la barra lateral o ambos.

## Exportar a un archivo de Excel de plantilla {#section-814772929ca64cf6b92b89d3fdd02302}

Puede exportar datos de su espacio de trabajo a un archivo de Excel de plantilla (`.xls` o `.xlsx`). El uso de un archivo de plantilla puede reducir la cantidad de tiempo que emplea en dar formato a los datos cada vez que se exporta el espacio de trabajo.

>[!NOTE]
>
>Este archivo de plantilla debe ser un archivo `.xls` o `.xlsx` , no un `.xlt` archivo.

Cuando se exportan los datos, las fichas existentes en la plantilla (cada una representa una visualización) se vuelven a rellenar con los datos más recientes del espacio de trabajo, mientras que las ventanas nuevas que no estén presentes en la plantilla como hojas con fichas se ignoran. Las demás hojas con fichas del archivo de plantilla permanecen sin cambios.

Además, si tiene una macro definida en el archivo de Excel de la plantilla que desea ejecutar automáticamente cuando se genere el informe, asigne a la macro el nombre &quot;VSExport&quot;.

Supongamos que desea utilizar los datos de campaña exportados desde una visualización de tabla en un gráfico circular en otra hoja con fichas en un archivo de Excel y desea actualizar esta información cada semana. Puede utilizar una plantilla para no tener que volver a crear las referencias de la hoja con fichas de la tabla a la hoja con fichas del gráfico circular cada vez que desee actualizar los datos. Los datos de la tabla se actualizan tras la exportación, lo que actualiza automáticamente el gráfico circular.

**Para exportar datos del espacio de trabajo a una plantilla[!DNL .xls]o un archivo[!DNL .xlsx]**

1. Haga clic con el botón secundario en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Especifique si desea exportar un espacio de trabajo, una barra lateral o ambos.

   Se abre el [!UICONTROL Select a template worksheet] cuadro de diálogo.

1. Realice uno de los siguientes pasos según corresponda:

   * Si está utilizando un archivo `.xls` de plantilla:

      1. Busque y seleccione el `.xls` archivo de plantilla.
      1. Haga clic en **[!UICONTROL Open]**.
   * Si está utilizando un archivo `.xlsx` de plantilla:

      1. Vaya a la ubicación del archivo de plantilla. No se muestra el nombre del `.xlsx` archivo.
      1. En el [!UICONTROL File name] campo, escriba `.xlsx` y haga clic en **[!UICONTROL Open]**. Todos los nombres `.xlsx` de archivo se muestran en la lista de archivos.

      1. Seleccione el `.xlsx` archivo de plantilla.
      1. Haga clic en **[!UICONTROL Open]**.


