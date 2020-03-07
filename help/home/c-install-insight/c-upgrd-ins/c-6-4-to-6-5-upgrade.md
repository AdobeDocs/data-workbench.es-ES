---
description: Siga estos pasos para actualizar a Área de trabajo de datos v6.5.
title: Actualización de 6.4 a 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Upgrading 6.4 to 6.5{#upgrading-to}

Siga estos pasos para actualizar a Área de trabajo de datos v6.5.

## Requisitos y recomendaciones de actualización {#section-8704a9ac358246cd81233dd0982d534f}

Siga estos requisitos y recomendaciones al actualizar a Área de trabajo de datos 6.5.

* Los cambios en el **[!DNL Components for Processing Servers\Communications.cfg]** archivo requieren que actualice este archivo para la versión DWB 6.5. Se eliminaron *las entradas SourceListServer*, *SegmentExportServer* y *NormalizeServer* . (Los DPU no deben ejecutar *source list*, exportar ** segmentos ni *normalizar servidores*. )

* Las visualizaciones de Correlación, Tabla de correlación, Tabla de asociación, Matriz de asociación, Puntuación de tendencia y Atribución de mejor ajuste ahora son visualizaciones de varios pasos.

   Cuando haya más de una visualización de varios pasos en un espacio de trabajo, el servidor de informes no podrá generar informes de forma predeterminada con el error:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evite este error actualizando el [!DNL ReportServer.cfg] archivo o agregue esta línea al archivo existente en la sección *Informes* .

   ```
   Max Multipass Per Slice = int: n
   ```

   donde n es el número máximo de visualizaciones de varios pasos admitidas por el servidor de informes en un espacio de trabajo.

