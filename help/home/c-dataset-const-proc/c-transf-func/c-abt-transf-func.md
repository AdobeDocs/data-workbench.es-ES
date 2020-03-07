---
description: La funcionalidad de transformación (Transform) se ejecuta en un equipo de servidor del área de trabajo de datos para permitir la exportación de datos de origen de registro para su uso en otras aplicaciones.
solution: Analytics
title: Acerca de la funcionalidad de transformación
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acerca de la funcionalidad de transformación{#about-transformation-functionality}

La funcionalidad de transformación (Transform) se ejecuta en un equipo de servidor del área de trabajo de datos para permitir la exportación de datos de origen de registro para su uso en otras aplicaciones.

[!DNL Transform] Puede leer [!DNL .vsl] archivos, archivos de registro, archivos XML y datos ODBC y exportar los datos como [!DNL .vsl] archivos de texto, archivos de texto o archivos de texto delimitados que pueden utilizar las rutinas de carga, agencias de auditoría u otros destinos de DataWarehouse. La extracción y transformación de datos se puede realizar de forma continua o programada.

>[!NOTE]
>
>Normalmente, [!DNL Transform] se configura en una FSU de servidor del área de trabajo de datos. Sin embargo, la implementación puede requerir configuración en una DPU del servidor del área de trabajo de datos. Para obtener más información, póngase en contacto con Adobe.

Puede ver la información de uso de memoria para [!DNL Transform] en la interfaz Estado detallado. Para obtener más información, consulte el capítulo Interfaces administrativas de la Guía *del usuario de Área de trabajo de* datos.

La función de exportación de segmentos proporciona otro medio para exportar datos desde una aplicación de Adobe. [!DNL Transform] le permite exportar datos sin procesar a un destino externo, pero la función de exportación de segmentos le permite generar datos procesados desde el conjunto de datos y requiere que los datos exportados se definan como una dimensión en el conjunto de datos. Para obtener más información sobre la exportación de segmentos, consulte la Guía del usuario *del área de trabajo de datos*.
