---
description: En el portal de informes, puede ver los informes generados por el servidor de informes como archivos de Excel (.xls o .xlsx) o .png .
title: Configuración de los archivos de Report.cfg
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Configuración de los archivos de Report.cfg{#configuring-report-cfg-files}

{{eol}}

En el portal de informes, puede ver los informes generados por el servidor de informes como archivos de Excel (.xls o .xlsx) o .png .

Para mostrar un conjunto de informes en la variable [!DNL Report Portal], debe configurar los siguientes parámetros en la variable [!DNL Report.cfg] para ese conjunto de informes:

* En el **[!UICONTROL Output Root]** , especifique la raíz del documento del servidor web utilizado para su portal.
* En el **[!UICONTROL Report Types]** especifique Excel, png o miniatura como los tipos de informe que desea generar.

When [!DNL Report Server] genera los informes en los formatos especificados, coloca esos archivos en la raíz del documento del servidor web, que es donde durante la instalación se configura la variable [!DNL Report Portal] para acceder a los informes.

Para obtener más información sobre la variable [!DNL Report.cfg] parámetros, consulte [Parámetros de Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
