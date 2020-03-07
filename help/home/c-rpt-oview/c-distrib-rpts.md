---
description: Una vez generados los informes, Report distribuye los informes del conjunto en función de la configuración de su archivo Report.cfg.
solution: Analytics
title: Distribución de informes
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribución de informes{#distributing-reports}

Una vez generados los informes, Report distribuye los informes del conjunto en función de la configuración de su archivo Report.cfg.

[!DNL Report] permite distribuir los informes en un conjunto mediante los siguientes métodos:

* **Correo electrónico:** Para distribuir informes como archivos de Excel, archivos [!DNL .png] o miniaturas por correo electrónico (en línea o como archivos adjuntos), especifique los parámetros de Informe de correo en el [!DNL Report.cfg] archivo del conjunto de informes. Todos los informes de ese conjunto se envían por correo electrónico en un mensaje a los destinatarios especificados.

* **Directorio compartido:** Para distribuir informes como archivos de Excel, archivos [!DNL .png] o miniaturas a un directorio compartido, especifique el directorio en el parámetro Raíz de salida en el [!DNL Report.cfg] archivo del conjunto de informes.

* **Portal de informes:** Un portal de informes permite ver los informes a través del explorador Web. Adobe [!DNL Report Portal] muestra los informes generados como Excel o [!DNL .png] archivos, pero no los generados como miniaturas ( [!DNL .jpg]). Para distribuir informes a un portal, especifique la raíz del documento del servidor Web utilizado para el portal en el parámetro Raíz de salida en el [!DNL Report.cfg] archivo del conjunto de informes. Para obtener más información sobre la instalación y el uso [!DNL Report Portal], consulte [Uso del portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)de informes.

>[!NOTE]
>
>Para leer el resultado que actualmente admite [!DNL Report], debe tener una aplicación capaz de mostrar los informes en los formatos deseados. Por ejemplo, para ver [!DNL .xlsx] archivos, debe tener Microsoft Excel 2007 o posterior.

También puede utilizar una combinación de estas opciones de generación y distribución. Por ejemplo: si configura el [!DNL Report Types] parámetro para generar un conjunto de informes como Excel y [!DNL .png] archivos, y luego configura los parámetros [!DNL Mail Report]y [!DNL Output Root] , todos los informes de ese conjunto se distribuyen al directorio de salida especificado (tal vez para que se vean en un portal) y se envían por correo electrónico a los destinatarios.

Para ver los pasos para configurar los conjuntos de informes, consulte [Uso de conjuntos](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)de informes. Para obtener más información sobre los [!DNL Report.cfg] parámetros específicos, consulte Parámetros [de Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
