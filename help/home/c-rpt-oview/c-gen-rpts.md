---
description: Genere informes procesando espacios de trabajo y especificándolos como informes.
title: Generación de informes
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Generación de informes{#generating-reports}

Genere informes procesando espacios de trabajo y especificándolos como informes.

[!DNL Report] genera los informes en el intervalo establecido en el  [!DNL Every] parámetro del  [!DNL Report.cfg] archivo (por ejemplo,  [!DNL "day]&quot;, que procesa el informe diariamente) y en función de los demás ajustes del  [!DNL Report.cfg] archivo.

Durante la generación de informes, el porcentaje completado se muestra en la pestaña [!DNL Reports] debajo de la miniatura de ese informe en particular. Si [!DNL Report] encuentra un problema durante la generación del informe, el mensaje de error más reciente se muestra en la pestaña [!DNL Reports] de la carpeta del conjunto de informes. Si [!DNL Report] encuentra un error para un informe en particular, continúa procesando los demás informes del conjunto.

Puede generar los informes en un conjunto de informes en cualquiera de los formatos siguientes o en todos ellos utilizando el parámetro [!DNL Report Types] del archivo [!DNL Report.cfg]:

* Archivo de Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx])
* Archivo gráfico de red portátil ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Junto con los tipos de salida especificados, [!DNL Report] crea un archivo [!DNL .xml] con el mismo nombre que el informe. Este archivo *`<report name>`*.xml contiene la descripción del informe que se muestra en la Data Workbench en la pestaña [!DNL Reports] debajo de la miniatura del informe. Esto hace que la descripción esté disponible para usar al distribuir los informes a través de un portal de informes. Para obtener más información sobre [!DNL Report Portal], consulte [Uso del portal de informes](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Si redefine una métrica interna, el sistema se comporta de forma inesperada debido al valor incorrecto. Los informes no se generarán a menos que una métrica indique el 100%. Se recomienda no cambiar las definiciones de métricas.
