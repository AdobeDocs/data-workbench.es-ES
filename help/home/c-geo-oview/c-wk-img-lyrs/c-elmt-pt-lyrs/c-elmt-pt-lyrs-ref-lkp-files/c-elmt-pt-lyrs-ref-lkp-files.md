---
description: Al crear una capa de punto de elemento que haga referencia a un archivo de búsqueda para obtener datos de latitud y longitud, la ubicación del punto se obtiene recuperando cada elemento y su latitud y longitud asociadas del archivo de búsqueda.
title: Definición de capas de punto de elementos que hacen referencia a archivos de búsqueda
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Definición de capas de punto de elementos que hacen referencia a archivos de búsqueda{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

Al crear una capa de punto de elemento que haga referencia a un archivo de búsqueda para obtener datos de latitud y longitud, la ubicación del punto se obtiene recuperando cada elemento y su latitud y longitud asociadas del archivo de búsqueda.

En lugar de usar un archivo de búsqueda, puede usar la variable [!DNL Dynamic Points] , que incrusta la latitud y longitud de una ubicación en el nombre de cada elemento de una dimensión. Consulte [Definición de capas de puntos de elementos mediante puntos dinámicos](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Para definir una capa de punto de elemento que haga referencia a un archivo de búsqueda, debe crear o tener ya disponible lo siguiente:

* **Una dimensión** definida en la variable [!DNL Transformation.cfg] o un archivo de inclusión de conjunto de datos de transformación. Para obtener información sobre los archivos de configuración de transformación, consulte la *Guía de configuración de conjuntos de datos*.

* **Un archivo de búsqueda** que contienen los datos utilizados para trazar cada punto de datos. Este archivo debe contener al menos tres columnas de datos por cada punto de datos: la clave, la longitud y la latitud. Para obtener más información sobre el formato requerido del archivo de búsqueda, consulte [Formato del archivo de búsqueda de puntos de elemento](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Un archivo de capa** que especifica la ubicación del archivo de búsqueda e identifica la dimensión y métrica relacionadas, así como los nombres de columna de clave, longitud y latitud en el archivo de búsqueda. Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato de archivo de capa de punto de elemento](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>La variable [!DNL Zip Points.layer] , que se proporciona con la variable [!DNL Geography] perfil, es una capa de punto de elemento que identifica el [!DNL Zipcode.dim] archivo, la variable [!DNL Sessions.metric] archivo, la variable [!DNL Zip Points.txt] archivo de búsqueda y nombres de las columnas clave, longitud, latitud y nombre del archivo de búsqueda.
