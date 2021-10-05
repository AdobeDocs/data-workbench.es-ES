---
description: Información para generar informes como archivos de Excel.
title: Generación de informes como archivos de Microsoft Excel
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 4%

---

# Generación de informes como archivos de Microsoft Excel{#generating-reports-as-microsoft-excel-files}

Información para generar informes como archivos de Excel.

Deben cumplirse los siguientes requisitos:

* Microsoft Excel debe estar instalado en el mismo equipo que [!DNL Report Server].
* La cuenta de usuario en la que se está ejecutando el proceso [!DNL Report Server] debe tener permiso para acceder a Microsoft Excel.

   >[!NOTE]
   >
   >
   >
   >
   >    * Cuando se generan informes como archivos de Excel, se abre una nueva instancia de Excel. Para obtener más información sobre este proceso, consulte [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Aunque el área de trabajo de datos admite más de 256 columnas y 65.536 filas de datos, Microsoft Excel no lo admite.


Si se cumplen estos requisitos, [!DNL Report Server] inicia automáticamente Microsoft Excel y genera datos de ciertas visualizaciones, leyendas de dimensiones y valores y anotaciones de texto en un nuevo libro de Excel con una visualización por hoja de cálculo.

>[!NOTE]
>
>Los datos no se exportan desde gráficos, navegadores de rutas, mapas de procesos, gráficos de puntos y globos.

A menos que haya especificado un [!DNL Custom Title] para la visualización, el tipo de ventana (por ejemplo, Tabla de película) se usa como nombre de hoja de cálculo.

Para obtener más información sobre cómo especificar [!DNL Custom Titles] para visualizaciones, consulte la [Guía del cliente de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=es).

## Uso de un archivo de plantilla {#section-40ab11916f464b1a88214ab969da6751}

También puede generar un informe como archivo de Excel utilizando un archivo de plantilla de Excel ( [!DNL .xls] o [!DNL .xlsx]). El uso de un archivo de plantilla puede reducir la cantidad de tiempo que se invierte en dar formato a los datos cada vez que se genera el informe.

Este archivo de plantilla debe ser un archivo [!DNL .xls] o [!DNL .xlsx], no un archivo [!DNL .xlt].

Puede elegir definir una plantilla para cada informe individual, una plantilla genérica para todos los informes o una combinación de ambos. Estos dos elementos no se excluyen mutuamente, por lo que puede definir una plantilla genérica y luego definir plantillas específicas también.

Para generar un informe con una plantilla genérica que utilice para todos los informes, debe especificar el nombre de ese archivo de Excel en el parámetro Plantilla de Excel predeterminada del [!DNL Report.cfg] para ese archivo del conjunto de informes y, a continuación, colocar el archivo de plantilla en la misma carpeta que el [!DNL Report.cfg] para ese conjunto de informes (*directorio de instalación del Data Workbench*\*NombreDePerfil*\Reports\*ReportSetName*). Para obtener información sobre este parámetro, consulte [Parámetros de Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Para generar un informe con una plantilla específica para un informe, debe asignar al archivo de Excel el mismo nombre que el archivo del espacio de trabajo del informe ( [!DNL .vw]) y, a continuación, colocar el archivo de plantilla en la misma carpeta que el archivo del espacio de trabajo del informe ( [!DNL .vw]).

Cuando se genera el informe, las fichas existentes en la plantilla (cada una de las cuales representa una visualización) se rellenan con los datos más recientes del informe, mientras que las ventanas nuevas que no estén presentes en la plantilla como hojas de cálculo se ignoran. Las demás hojas con pestañas del archivo de plantilla no cambian.

Además, si tiene una macro definida en la plantilla del archivo de Excel que desea ejecutar automáticamente cuando se genere el informe, asigne un nombre a la macro &quot;VSExport&quot;.
