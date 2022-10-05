---
description: Una vez generados los informes, Report distribuye los informes en el conjunto en función de la configuración de su archivo Report.cfg.
title: Distribución de informes
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Distribución de informes{#distributing-reports}

{{eol}}

Una vez generados los informes, Report distribuye los informes en el conjunto en función de la configuración de su archivo Report.cfg.

[!DNL Report] permite distribuir los informes en un conjunto mediante los siguientes métodos:

* **Correo electrónico:** Para distribuir informes como archivos de Excel, [!DNL .png] archivos, o miniaturas por correo electrónico (en línea o como archivos adjuntos), especifique los parámetros de informe de correo en el informe del conjunto de informes [!DNL Report.cfg] archivo. Todos los informes de ese conjunto se envían por correo electrónico en un mensaje a los destinatarios especificados.

* **Directorio compartido:** Para distribuir informes como archivos de Excel, [!DNL .png] archivos, o miniaturas a un directorio compartido, especifique el directorio en el parámetro Raíz de salida en el parámetro [!DNL Report.cfg] archivo.

* **Portal de informes:** Un portal de informes permite ver informes a través del explorador web. Adobe [!DNL Report Portal] muestra los informes generados como Excel o [!DNL .png] archivos, pero no los generados como miniaturas ( [!DNL .jpg]). Para distribuir informes a un portal, especifique la raíz del documento del servidor web utilizado para el portal en el parámetro Raíz de salida del grupo de informes [!DNL Report.cfg] archivo. Para obtener más información sobre cómo instalar y usar [!DNL Report Portal], consulte [Uso del portal de informes](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Para leer la salida que admite actualmente [!DNL Report], debe tener una aplicación capaz de mostrar los informes en los formatos deseados. Por ejemplo, para ver [!DNL .xlsx] debe tener Microsoft Excel 2007 o posterior.

También puede utilizar una combinación de estas opciones de generación y distribución. Por ejemplo, si establece la variable [!DNL Report Types] para generar un conjunto de informes como Excel y [!DNL .png] y, a continuación, establezca la variable [!DNL Mail Report]y [!DNL Output Root] , todos los informes de ese conjunto se distribuyen al directorio de salida especificado (tal vez para verlo en un portal) y se envían por correo electrónico a los destinatarios.

Para ver los pasos para configurar los grupos de informes, consulte [Uso de los conjuntos de informes](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Para obtener más información sobre la variable [!DNL Report.cfg] parámetros, consulte [Parámetros de Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
