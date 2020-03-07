---
description: Al crear una capa de punto de elemento que hace referencia a un archivo de búsqueda para obtener datos de latitud y longitud, la ubicación del punto se obtiene recuperando cada elemento y su latitud y longitud asociadas del archivo de búsqueda.
solution: Analytics
title: Definición de capas de punto de elementos que hacen referencia a archivos de búsqueda
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definición de capas de punto de elementos que hacen referencia a archivos de búsqueda{#defining-element-point-layers-referencing-lookup-files}

Al crear una capa de punto de elemento que hace referencia a un archivo de búsqueda para obtener datos de latitud y longitud, la ubicación del punto se obtiene recuperando cada elemento y su latitud y longitud asociadas del archivo de búsqueda.

En lugar de utilizar un archivo de búsqueda, puede utilizar la [!DNL Dynamic Points] funcionalidad, que incrusta la latitud y la longitud de una ubicación en el nombre de cada elemento de una dimensión. Consulte [Definición de Capas de Puntos de Elementos mediante Puntos](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)Dinámicos.

Para definir una capa de punto de elemento que haga referencia a un archivo de búsqueda, debe crear o tener ya disponible lo siguiente:

* **Una dimensión** definida en el archivo [!DNL Transformation.cfg] o un conjunto de datos de transformación incluye un archivo. Para obtener información sobre los archivos de configuración de transformación, consulte la Guía *de configuración de* Dataset.

* **Archivo** de búsqueda que contiene los datos utilizados para trazar cada punto de datos. Este archivo debe contener al menos tres columnas de datos por cada punto de datos: la llave, la longitud y la latitud. Para obtener más información sobre el formato requerido del archivo de búsqueda, consulte Formato [de archivo de búsqueda de puntos de](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)elementos.

* **Archivo** de capa que especifica la ubicación del archivo de búsqueda e identifica la dimensión y métrica relacionadas, así como los nombres de columna de clave, longitud y latitud en el archivo de búsqueda. Para obtener más información sobre el formato requerido del archivo de capa, consulte Formato [de archivo de capa de punto de](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)elemento.

>[!NOTE]
>
>El [!DNL Zip Points.layer] archivo, proporcionado con el [!DNL Geography] perfil, es una capa de punto de elemento que identifica el [!DNL Zipcode.dim] archivo, el [!DNL Sessions.metric] [!DNL Zip Points.txt] archivo, el archivo de búsqueda y los nombres de las columnas clave, longitud, latitud y nombre del archivo de búsqueda.

