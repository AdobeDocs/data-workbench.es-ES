---
description: Puede exportar un espacio de trabajo como archivo de imagen .png o exportar los datos de ciertas ventanas a un archivo de Excel (.xls o .xlsx).
title: Exportación de un espacio de trabajo
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exportación de un espacio de trabajo{#export-a-workspace}

{{eol}}

Puede exportar un espacio de trabajo como archivo de imagen .png o exportar los datos de ciertas ventanas a un archivo de Excel (.xls o .xlsx).

## Exportación de espacios de trabajo como archivos PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Puede guardar una instantánea de un espacio de trabajo en formato de gráfico de red portátil (`.png` archivos). Las siguientes opciones de color están disponibles al guardar espacios de trabajo como `.png` archivos:

* **Fondo negro** copia el espacio de trabajo como se muestra.
* **Fondo blanco** copia los elementos del espacio de trabajo en color y los muestra en un fondo blanco.
* **Fondo blanco (B&amp;W)** copia los elementos del espacio de trabajo en escala de grises y los muestra en un fondo blanco.

**Exportación de un espacio de trabajo como archivo .png**

En el menú de barra de título de un espacio de trabajo, haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

Aparece el cuadro de diálogo [!UICONTROL Save Image As].

Vaya al directorio en el que desea guardar el archivo, cambie el nombre del archivo si es necesario y haga clic en **[!UICONTROL Save]**.

## Exportar datos de espacio de trabajo a Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Al exportar un espacio de trabajo a Excel, la Data Workbench exporta datos de ciertas visualizaciones, leyendas de dimensiones y valores y anotaciones de texto a un nuevo libro de Excel con una visualización por hoja de cálculo.

Para exportar espacios de trabajo y ventanas individuales a Microsoft Excel, se deben cumplir los siguientes requisitos:

* Microsoft Excel debe estar instalado en el mismo equipo que la Data Workbench.
* La cuenta de usuario en la que se está ejecutando el proceso de Data Workbench debe tener permiso para acceder a Microsoft Excel.

>[!NOTE]
>
>* Al exportar datos como archivos de Excel, se abre una nueva instancia de Excel. Para obtener más información sobre este proceso, consulte [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
>* Aunque la Data Workbench admite más de 256 columnas y 65.536 filas de datos, las versiones de Microsoft Excel anteriores a la versión 8.0 no lo hacen.
>


Si se cumplen estos requisitos, la Data Workbench inicia automáticamente Microsoft Excel y exporta los datos a un nuevo libro de Excel. Los datos no se exportan desde las visualizaciones siguientes: gráficos, exploradores de rutas, mapas de procesos, gráficos de puntos y globos.

## Aplicar títulos personalizados {#section-a332e157554546cb8e88922a8d7a4fa2}

A menos que haya especificado un título personalizado para la ventana de la [!UICONTROL Export] , el [!UICONTROL Export title] La lista (por ejemplo, Tabla de ciudad) se utiliza como nombre de hoja de cálculo.

1. Haga clic con el botón derecho en el borde superior de la ventana y, a continuación, haga clic en **[!UICONTROL Custom title]** campo .
1. Escriba el título que desea aplicar a la ventana.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Si introduce un guión (-) en la variable [!UICONTROL Custom title] , esta visualización no se exporta con el espacio de trabajo.

Cuando exporta el espacio de trabajo a Excel, la hoja de cálculo que contiene los datos de esta ventana recibe un nombre usando el título especificado en lugar del título en la variable [!UICONTROL Export title] campo .

## Exportación de un espacio de trabajo o una barra lateral a Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Para exportar datos de Workspace a una nueva [!DNL .xls] o [!DNL .xlsx] file**

1. En la barra de título del espacio de trabajo, haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Especifique si desea exportar el espacio de trabajo, la barra lateral o ambos.

## Exportación a un archivo de Excel de plantilla {#section-814772929ca64cf6b92b89d3fdd02302}

Puede exportar datos en el espacio de trabajo a una plantilla Archivo Excel (`.xls` o `.xlsx`). El uso de un archivo de plantilla puede reducir la cantidad de tiempo que se invierte en dar formato a los datos cada vez que se exporta el espacio de trabajo.

>[!NOTE]
>
>Este archivo de plantilla debe ser `.xls` o `.xlsx` archivo, no un `.xlt` archivo.

Cuando se exportan los datos, las fichas existentes en la plantilla (cada una de las cuales representa una visualización) se rellenan con los datos más recientes del espacio de trabajo, mientras que las ventanas nuevas que no están presentes en la plantilla como hojas de cálculo se ignoran. Las demás hojas con pestañas del archivo de plantilla no cambian.

Además, si tiene una macro definida en la plantilla del archivo de Excel que desea ejecutar automáticamente cuando se genere el informe, asigne un nombre a la macro &quot;VSExport&quot;.

Supongamos que desea utilizar datos de campaña exportados desde una visualización de tabla en un gráfico circular de otra hoja con pestañas en un archivo de Excel y desea actualizar esta información cada semana. Puede utilizar una plantilla para no tener que volver a crear las referencias de la hoja con fichas de la tabla a la hoja con fichas del gráfico circular cada vez que desee actualizar los datos. Los datos de la tabla se actualizan tras la exportación, lo que actualiza automáticamente el gráfico circular.

**Para exportar datos de Workspace a una plantilla [!DNL .xls] o [!DNL .xlsx] file**

1. Haga clic con el botón derecho en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Especifique si desea exportar un espacio de trabajo, una barra lateral o ambos.

   La variable [!UICONTROL Select a template worksheet] se abre.

1. Complete uno de los siguientes pasos según corresponda:

   * Si está utilizando un `.xls` archivo de plantilla:

      1. Buscar y seleccionar la plantilla `.xls` archivo.
      1. Haga clic en **[!UICONTROL Open]**.
   * Si está utilizando un `.xlsx` archivo de plantilla:

      1. Vaya a la ubicación del archivo de plantilla. La variable `.xlsx` no se muestra el nombre del archivo.
      1. En el [!UICONTROL File name] campo, tipo `.xlsx` y haga clic en **[!UICONTROL Open]**. Todo `.xlsx` los nombres de archivo se muestran en la lista de archivos.

      1. Seleccione la plantilla `.xlsx` archivo.
      1. Haga clic en **[!UICONTROL Open]**.
