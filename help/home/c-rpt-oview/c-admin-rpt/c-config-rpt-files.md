---
description: En el portal de informes, puede ver los informes generados por el servidor de informes como archivos de Excel (.xls o .xlsx) o .png .
title: Configuración de los archivos de Report.cfg
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Configuración de los archivos de Report.cfg{#configuring-report-cfg-files}

En el portal de informes, puede ver los informes generados por el servidor de informes como archivos de Excel (.xls o .xlsx) o .png .

Para mostrar un conjunto de informes en [!DNL Report Portal], debe configurar los siguientes parámetros en el archivo [!DNL Report.cfg] para ese conjunto de informes:

* En el parámetro **[!UICONTROL Output Root]**, especifique la raíz del documento del servidor web utilizado para su portal.
* En el parámetro **[!UICONTROL Report Types]**, especifique Excel, png y/o miniatura como los tipos de informe que desee generar.

Cuando [!DNL Report Server] genera los informes en los formatos especificados, coloca esos archivos en la raíz del documento del servidor web, que es donde durante la instalación configura el [!DNL Report Portal] para acceder a los informes.

Para obtener más información sobre los parámetros específicos de [!DNL Report.cfg], consulte [Parámetros de Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
