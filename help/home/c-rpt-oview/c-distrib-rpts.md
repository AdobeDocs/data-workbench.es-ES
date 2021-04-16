---
description: Una vez generados los informes, Report distribuye los informes en el conjunto en función de la configuración de su archivo Report.cfg.
title: Distribución de informes
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Distribución de informes{#distributing-reports}

Una vez generados los informes, Report distribuye los informes en el conjunto en función de la configuración de su archivo Report.cfg.

[!DNL Report] permite distribuir los informes en un conjunto mediante los siguientes métodos:

* **Correo electrónico:** para distribuir informes como archivos,  [!DNL .png] archivos o miniaturas de Excel por correo electrónico (en línea o como archivos adjuntos), especifique los parámetros de Informe de correo en el  [!DNL Report.cfg] archivo del conjunto de informes. Todos los informes de ese conjunto se envían por correo electrónico en un mensaje a los destinatarios especificados.

* **Directorio compartido:** para distribuir informes como archivos,  [!DNL .png] archivos o miniaturas de Excel a un directorio compartido, especifique el directorio en el parámetro Raíz de salida en el  [!DNL Report.cfg] archivo del conjunto de informes.

* **Portal de informes:** un portal de informes permite ver informes a través del explorador web. El [!DNL Report Portal] de Adobe muestra los informes generados como archivos de Excel o [!DNL .png], pero no los generados como miniaturas ( [!DNL .jpg]). Para distribuir informes a un portal, especifique la raíz del documento del servidor web utilizado para el portal en el parámetro Output Root del archivo [!DNL Report.cfg] del conjunto de informes. Para obtener más información sobre la instalación y el uso de [!DNL Report Portal], consulte [Uso del portal de informes](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Para leer el resultado que admite actualmente [!DNL Report], debe tener una aplicación capaz de mostrar los informes en los formatos deseados. Por ejemplo, para ver archivos [!DNL .xlsx], debe tener Microsoft Excel 2007 o posterior.

También puede utilizar una combinación de estas opciones de generación y distribución. Por ejemplo, si configura el parámetro [!DNL Report Types] para generar un conjunto de informes como archivos de Excel y [!DNL .png] y luego establece los parámetros [!DNL Mail Report]y [!DNL Output Root], todos los informes de ese conjunto se distribuyen al directorio de salida especificado (tal vez para verlo en un portal) y se envían por correo electrónico a los destinatarios.

Para ver los pasos para configurar los conjuntos de informes, consulte [Uso de conjuntos de informes](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Para obtener más información sobre los parámetros específicos de [!DNL Report.cfg], consulte [Parámetros de Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
