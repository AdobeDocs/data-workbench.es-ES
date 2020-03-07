---
description: Genere informes procesando espacios de trabajo y especificándolos como informes.
solution: Analytics
title: Generación de informes
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generación de informes{#generating-reports}

Genere informes procesando espacios de trabajo y especificándolos como informes.

[!DNL Report] genera los informes en el intervalo establecido en el [!DNL Every] parámetro del [!DNL Report.cfg] archivo (por ejemplo, [!DNL "day]&quot;, que procesa el informe diariamente) y en función de la otra configuración del [!DNL Report.cfg] archivo.

Durante la generación de informes, el porcentaje completado se muestra en la ficha situada debajo de la miniatura de ese informe en particular. [!DNL Reports] Si [!DNL Report] encuentra un problema durante la generación de informes, el mensaje de error más reciente se muestra en la ficha [!DNL Reports] de la carpeta del conjunto de informes. Si [!DNL Report] encuentra un error en un informe en particular, continúa procesando los demás informes del conjunto.

Puede generar los informes en un conjunto de informes en cualquiera de los siguientes formatos o en todos ellos utilizando el [!DNL Report Types] parámetro del [!DNL Report.cfg] archivo:

* Archivo de Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx])
* Archivo gráfico de red portátil ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Junto con los tipos de salida especificados, [!DNL Report] crea un [!DNL .xml] archivo con el mismo nombre que el informe. Este archivo *`<report name>`*.xml contiene la descripción del informe que se muestra en el área de trabajo de datos en la [!DNL Reports] ficha debajo de la miniatura del informe. Esto hace que la descripción esté disponible para su uso al distribuir los informes a través de un portal de informes. Para obtener más información sobre el [!DNL Report Portal], consulte [Uso del portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)de informes.

>[!NOTE]
>
>Si redefine una métrica interna, el sistema se comporta de forma inesperada debido al valor incorrecto. Los informes no se generarán a menos que una métrica indique el 100 %. Se recomienda no cambiar las definiciones de métricas.
