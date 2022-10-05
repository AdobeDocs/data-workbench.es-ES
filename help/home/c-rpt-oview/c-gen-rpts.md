---
description: Genere informes procesando espacios de trabajo y especificándolos como informes.
title: Generación de informes
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Generación de informes{#generating-reports}

{{eol}}

Genere informes procesando espacios de trabajo y especificándolos como informes.

[!DNL Report] genera los informes en el intervalo definido en la variable [!DNL Every] en el [!DNL Report.cfg] archivo (como [!DNL "day],&quot; que procesa el informe diariamente) y se basa en el otro [!DNL Report.cfg] configuración del archivo.

Durante la generación de informes, el porcentaje completado se muestra en la variable [!DNL Reports] debajo de la miniatura para ese informe en particular. If [!DNL Report] encuentra un problema durante la generación de informes, el mensaje de error más reciente se muestra en la variable [!DNL Reports] en la carpeta del conjunto de informes. If [!DNL Report] si encuentra un error para un informe en particular, continúa procesando los demás informes del conjunto.

Puede generar los informes en un conjunto de informes en cualquiera de los formatos siguientes o en todos ellos utilizando la variable [!DNL Report Types] en el [!DNL Report.cfg] archivo:

* Archivo Excel de Microsoft ( [!DNL .xls] o [!DNL .xlsx])
* Archivo gráfico de red portátil ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Junto con los tipos de salida especificados, [!DNL Report] crea un [!DNL .xml] con el mismo nombre que el informe. Esta *`<report name>`* El archivo .xml contiene la descripción del informe que se muestra en la Data Workbench en la variable [!DNL Reports] debajo de la miniatura del informe. Esto hace que la descripción esté disponible para usar al distribuir los informes a través de un portal de informes. Para obtener información sobre la variable [!DNL Report Portal], consulte [Uso del portal de informes](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Si redefine una métrica interna, el sistema se comporta de forma inesperada debido al valor incorrecto. Los informes no se generarán a menos que una métrica indique el 100%. Se recomienda no cambiar las definiciones de métricas.
