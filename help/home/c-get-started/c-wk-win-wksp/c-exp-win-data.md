---
description: Puede exportar los datos de ciertas ventanas a un archivo de Excel (.xls o .xlsx) o a un archivo de valores separados por tabuladores (.tsv).
solution: Analytics
title: Exportar datos de ventana
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportar datos de ventana{#export-window-data}

Puede exportar los datos de ciertas ventanas a un archivo de Excel (.xls o .xlsx) o a un archivo de valores separados por tabuladores (.tsv).

Los datos no se exportan desde gráficos, navegadores de rutas, mapas de procesos, gráficos de dispersión y globos.

## Exportar datos de ventana a Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Para exportar datos de ventana individuales a Microsoft Excel, deben cumplirse los siguientes requisitos:

* Microsoft Excel debe estar instalado en el mismo equipo que el Área de trabajo de datos.
* La cuenta de usuario en la que se está ejecutando el proceso de Área de trabajo de datos debe tener permiso para acceder a Microsoft Excel.
* Al exportar datos como archivos de Excel, se abre una nueva instancia de Excel.
* Aunque el Área de trabajo de datos admite más de 256 columnas y 65.536 filas de datos, las versiones de Microsoft Excel anteriores a la versión 8.0 no lo hacen.

Si se cumplen estos requisitos, Área de trabajo de datos inicia automáticamente Microsoft Excel y exporta los datos a un nuevo libro de Excel cuando selecciona la opción de **[!UICONTROL Export To Excel]** menú.

**Para exportar datos de ventana a un archivo .xls o .xlsx**

Haga clic con el botón derecho en el borde superior de la ventana y haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel abre un nuevo libro que contiene los datos exportados. A menos que haya proporcionado un título personalizado (como se describe en la sección siguiente), este libro se nombra con el [!DNL Export title] (Tabla de días en el ejemplo anterior).

## Aplicar títulos personalizados {#section-2a6559df812a470685e43923b7b9024e}

Si se proporciona un título personalizado para una ventana (mediante el [!DNL Custom title] campo del [!DNL Export] menú), la hoja de cálculo a la que el Área de trabajo de datos exporta los datos se nombra con este título personalizado en lugar del título del [!DNL Export title] campo (Tabla de días en el ejemplo anterior).

**Aplicar un título personalizado a una visualización**

1. Haga clic con el botón derecho en el borde superior de la ventana y haga clic en el **[!UICONTROL Custom title]** campo.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Cuando exporta la visualización a Excel, la hoja de cálculo que contiene los datos de esta ventana recibe el nombre del título especificado en lugar del título del [!DNL Export title] campo.

## Exportar datos de ventana a un archivo TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Para exportar una ventana a un archivo .tsv**

Haga clic con el botón derecho en el borde superior de la ventana y haga clic en **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. Aparecerá el cuadro de diálogo [!DNL Save Window] .
1. Vaya al directorio en el que desea guardar el archivo. Cambie el nombre del archivo si es necesario y haga clic en **[!UICONTROL Save]**.

