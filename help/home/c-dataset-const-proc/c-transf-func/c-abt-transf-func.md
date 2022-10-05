---
description: La funcionalidad de transformación (Transform) se ejecuta en un equipo de servidor de Data Workbench para permitir la exportación de datos de origen de registro para su uso en otras aplicaciones.
title: Acerca de la funcionalidad de transformación
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Acerca de la funcionalidad de transformación{#about-transformation-functionality}

{{eol}}

La funcionalidad de transformación (Transform) se ejecuta en un equipo de servidor de Data Workbench para permitir la exportación de datos de origen de registro para su uso en otras aplicaciones.

[!DNL Transform] se puede leer [!DNL .vsl] archivos, archivos de registro, archivos XML y datos ODBC y exportar los datos como [!DNL .vsl] archivos, archivos de texto o archivos de texto delimitados que se pueden utilizar mediante rutinas de carga de DataWarehouse, agencias de auditoría u otros destinos. La extracción y transformación de datos se puede realizar de forma continua o programada.

>[!NOTE]
>
>Normalmente, [!DNL Transform] está configurado en una FSU del servidor de Data Workbench. Sin embargo, la implementación puede requerir configuración en una DPU del servidor de Data Workbench. Para obtener más información, póngase en contacto con el Adobe.

Puede ver la información de uso de la memoria para [!DNL Transform] en la interfaz Estado detallado . Para obtener más información, consulte el capítulo Interfaces administrativas del *Guía del usuario de Data Workbench*.

La función de exportación de segmentos proporciona otro medio para exportar datos desde una aplicación de Adobe. [!DNL Transform] permite exportar datos sin procesar a un destino externo, pero la función de exportación de segmentos permite generar datos procesados desde el conjunto de datos y requiere que los datos exportados se definan como una dimensión en el conjunto de datos. Para obtener más información sobre la exportación de segmentos, consulte la *Guía del usuario de Data Workbench*.
