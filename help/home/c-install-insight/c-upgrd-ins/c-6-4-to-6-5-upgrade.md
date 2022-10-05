---
description: Siga estos pasos para actualizar a la Data Workbench v6.5.
title: Actualizar la versión 6.4 a la versión 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%

---

# Actualizar la versión 6.4 a la versión 6.5{#upgrading-to}

{{eol}}

Siga estos pasos para actualizar a la Data Workbench v6.5.

## Requisitos de actualización y Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Siga estos requisitos y recomendaciones al actualizar a la Data Workbench 6.5.

* Cambios en la **[!DNL Components for Processing Servers\Communications.cfg]** requiere que actualice este archivo para la versión de DWB 6.5. La variable *SourceListServer*, *SegmentExportServer* y *NormalizeServer* se eliminaron las entradas. ( El DPU no debería estar en ejecución *sourcelist*, *exportación de segmentos* o *normalizar servidores*. )

* Las visualizaciones de acorde de correlación, matriz de correlación, acorde de asociación, matriz de asociación, puntuación de tendencia y atribución de mejor ajuste ahora son visualizaciones de varios pasos.

   Cuando hay más de una visualización de varios pasos en un espacio de trabajo, Report Server no generará informes de forma predeterminada con el error:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evite este error actualizando su [!DNL ReportServer.cfg] o agregue esta línea al archivo existente en el *Informes* para obtener más información.

   ```
   Max Multipass Per Slice = int: n
   ```

   donde n es el número máximo de visualizaciones de varios pasos compatibles con Report Server en un espacio de trabajo.
