---
description: Información conceptual sobre capas de imágenes.
title: Información sobre las capas de imágenes
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# Información sobre las capas de imágenes{#about-imagery-layers}

{{eol}}

Información conceptual sobre capas de imágenes.

## Tipos de capas de imágenes {#section-891cbf61e8334690bd203a2bb9761b25}

Puede ver los siguientes tipos de capas de imágenes en la Data Workbench:

* **[!UICONTROL Terrain image layer]:** Este tipo de capa muestra imágenes de terreno de la Tierra, sobre las que se pueden visualizar datos geográficos. La visualización del globo terráqueo en es un ejemplo de una capa de imagen del terreno. Consulte [Uso de capas de imagen del terreno](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Este tipo de capa muestra un punto del globo para cada elemento de una dimensión. Consulte [Uso de capas de punto de elementos](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Este tipo de capa muestra datos vectoriales (arte lineal) en el globo. Consulte [Uso de capas vectoriales](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Comente y aclare visualizaciones usando una superposición de presentación. Añada globos de texto, flechas, imágenes y codificación por colores para resaltar y aclarar los datos, y luego compártalos con otras personas.

En Data Workbench, puede seleccionar cuál de estas capas desea mostrar para una tarea de análisis determinada.

## Capas de perfil de geografía {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

La variable [!DNL Geography] profile le proporciona un conjunto de capas de imágenes predeterminadas, que se almacenan en la carpeta Profiles\Geography\Maps dentro del directorio de instalación del servidor de Data Workbench:

* **[!UICONTROL Blue Marble 2km]:** Esta capa de imagen de terreno crea un mapa 3D del mundo, que es lo que se muestra al agregar la visualización del globo a un espacio de trabajo. Cuando no se selecciona esta capa, el globo no es visible, pero las demás capas siguen mostrándose. La variable [!DNL Blue Marble 2km.layer] hace referencia al [!DNL Blue Marble 2km.tsi] archivo.

* **[!UICONTROL Zip Points]:** Esta capa de puntos de elemento le permite asignar ubicaciones en el conjunto de datos mediante un código postal de Estados Unidos. La variable [!DNL Zip Points.txt] el archivo de búsqueda (proporcionado por Adobe) contiene una lista de todos los códigos postales de Estados Unidos y la latitud y longitud de cada código postal. La variable [!DNL Zip Points.layer] hace referencia al [!DNL Zip Points.txt] y [!DNL Zipcode.dim] y contiene los parámetros de configuración necesarios para mostrar las ubicaciones en el globo. Cada elemento de la dimensión Código postal ( [!DNL Zipcode.dim]) que define dentro de su conjunto de datos está asignado en el globo utilizando la latitud y longitud enumeradas para ese código postal en la variable [!DNL Zip Points.txt] archivo de búsqueda.

   Para obtener información sobre la definición de dimensiones, consulte la *Guía de configuración de conjuntos de datos*.

* **[!UICONTROL Boundaries]:** Esta capa vectorial proporciona las principales fronteras políticas mundiales, como los países, así como los límites de las características físicas naturales de la Tierra, como lagos e islas. La variable [!DNL Boundaries.layer] hace referencia a una o más de las [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]y [!DNL world boundaries.vec] archivos.

* **[!UICONTROL IP Coordinates]:** Esta capa de puntos de elemento utiliza puntos dinámicos para permitirle asignar ubicaciones en el conjunto de datos mediante direcciones IP. La variable [!DNL IP Coordinates.layer] hace referencia a la dimensión Coordenadas ( [!DNL Coordinates.dim]) y especifica la métrica Visitantes como la métrica que se utilizará para determinar el tamaño de los puntos del globo para cada coordenada.

Su [!UICONTROL NL Geography] perfil u otros perfiles de la instalación pueden contener capas de imágenes adicionales que proporcionan los Adobes o que la empresa ha creado.

## Crear una nueva capa {#section-b5313773316c4e0fa748f7376a8e7f0b}

Puede crear nuevas capas de imágenes copiando el tipo apropiado de archivo de capa incluido en el [!DNL Geography] perfil en cualquier carpeta Profiles\*nombre de perfil*\Mapas y, a continuación, cambie el nombre del archivo y edítelo según corresponda. Todas las capas nuevas deben cumplir los siguientes requisitos:

* La variable [!DNL .layer] debe cumplir el formato de uno de los tipos de capa admitidos.
* La variable [!DNL .layer] debe hacer referencia a los archivos de dimensión y búsqueda adecuados, si es necesario.
* El archivo de búsqueda al que se hace referencia también debe almacenarse dentro del directorio de instalación del servidor de Data Workbench y su ruta debe especificarse con precisión en la variable [!DNL .layer] archivo.

Para obtener más información sobre el formato y los parámetros de cada tipo de archivo de capa y sus archivos asociados, consulte la sección de este capítulo para obtener el tipo de capa correspondiente.
