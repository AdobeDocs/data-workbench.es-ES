---
description: En el portal de informes, puede ver los informes generados por el servidor de informes como archivos de Excel (.xls o .xlsx) o .png.
solution: Analytics
title: Configuración de los archivos de Report.cfg
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de los archivos de Report.cfg{#configuring-report-cfg-files}

En el portal de informes, puede ver los informes generados por el servidor de informes como archivos de Excel (.xls o .xlsx) o .png.

Para mostrar un conjunto de informes en el [!DNL Report Portal], debe configurar los siguientes parámetros en el [!DNL Report.cfg] archivo para ese conjunto de informes:

* En el **[!UICONTROL Output Root]** parámetro, especifique la raíz del documento del servidor web utilizado para el portal.
* En el **[!UICONTROL Report Types]** parámetro, especifique Excel, png y/o miniatura como los tipos de informes que desee generar.

Cuando [!DNL Report Server] genera los informes en los formatos especificados, coloca esos archivos en la raíz del documento del servidor Web, que es donde durante la instalación se configura el [!DNL Report Portal] para acceder a los informes.

Para obtener más información sobre los [!DNL Report.cfg] parámetros específicos, consulte Parámetros [de Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
