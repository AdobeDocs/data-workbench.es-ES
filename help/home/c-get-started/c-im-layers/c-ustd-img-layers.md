---
description: Información conceptual sobre las capas de imágenes.
solution: Analytics
title: Acerca de las capas de imágenes
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Acerca de las capas de imágenes{#about-imagery-layers}

Información conceptual sobre las capas de imágenes.

## Tipos de capas de imágenes {#section-891cbf61e8334690bd203a2bb9761b25}

Puede ver los siguientes tipos de capas de imágenes en el área de trabajo de datos:

* **[!UICONTROL Terrain image layer]::**Este tipo de capa muestra imágenes de terreno de la Tierra, sobre las que se pueden mostrar datos geográficos. La visualización del globo en es un ejemplo de una capa de imagen del terreno. Consulte[Uso de capas](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)de imagen de terreno.

* **[!UICONTROL Element point layer]::**Este tipo de capa muestra un punto en el globo para cada elemento de una dimensión. Consulte[Uso de capas](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)de puntos de elementos.

* **[!UICONTROL Vector layer]::**Este tipo de capa muestra datos vectoriales (arte lineal) en el globo. Consulte[Uso de capas](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)vectoriales.

* **[!UICONTROL Presentation layer]** Comente y aclare visualizaciones usando una superposición de presentación. Añada globos de texto, flechas, imágenes y codificación por colores para resaltar y aclarar los datos, y luego compártalos con otras personas.

En el área de trabajo de datos, puede seleccionar qué capas desea mostrar para una tarea de análisis concreta.

## Capas de perfil geográfico {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

El [!DNL Geography] perfil le proporciona un conjunto de capas de imágenes predeterminadas, que se almacenan en la carpeta Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]::**Esta capa de imagen de terreno crea un mapa 3D del mundo, que es lo que se muestra al agregar la visualización de globo a un espacio de trabajo. Cuando esta capa no está seleccionada, el globo no está visible pero las demás capas siguen mostrándose. El[!DNL Blue Marble 2km.layer]archivo hace referencia al[!DNL Blue Marble 2km.tsi]archivo.

* **[!UICONTROL Zip Points]::**Esta capa de punto de elemento le permite asignar ubicaciones en el conjunto de datos mediante un código postal de Estados Unidos. El archivo de[!DNL Zip Points.txt]búsqueda (proporcionado por Adobe) contiene una lista de todos los códigos postales de Estados Unidos y la latitud y longitud de cada código postal. El[!DNL Zip Points.layer]archivo hace referencia al[!DNL Zip Points.txt]archivo y al[!DNL Zipcode.dim]archivo y contiene los parámetros de configuración necesarios para mostrar las ubicaciones en el globo. Cada elemento de la dimensión Código postal ([!DNL Zipcode.dim]) que defina dentro del conjunto de datos se asigna en el globo usando la latitud y longitud enumeradas para ese código postal en el archivo de[!DNL Zip Points.txt]búsqueda.

   Para obtener información sobre la definición de dimensiones, consulte la Guía *de configuración de* conjuntos de datos.

* **[!UICONTROL Boundaries]::**Esta capa vectorial proporciona las principales fronteras políticas mundiales, como los países, así como los límites de las características físicas naturales de la Tierra, como lagos e islas. El[!DNL Boundaries.layer]archivo hace referencia a uno o varios de los[!DNL mwcoast.vec],[!DNL mwisland.vec],[!DNL mwlake.vec],[!DNL mwnation.vec],[!DNL mwriver.vec],[!DNL mwstate.vec],[!DNL US states.vec]y[!DNL world boundaries.vec]archivos.

* **[!UICONTROL IP Coordinates]::**Esta capa de puntos de elemento utiliza puntos dinámicos para permitirle asignar ubicaciones en el conjunto de datos mediante direcciones IP. El[!DNL IP Coordinates.layer]archivo hace referencia a la dimensión Coordenadas ([!DNL Coordinates.dim]) y especifica la métrica Visitantes como métrica que se utilizará para determinar el tamaño de los puntos del globo para cada coordenada.

El perfil [!UICONTROLNL geográfico] u otros perfiles de la instalación pueden contener capas de imágenes adicionales que Adobe proporcionó o que su empresa creó.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

Puede crear nuevas capas de imágenes copiando el tipo adecuado de archivo de capa incluido en el [!DNL Geography] perfil en cualquier carpeta Profiles\*profile name*\Maps y, a continuación, cambiando el nombre y editando el archivo según corresponda. Todas las capas nuevas deben cumplir los siguientes requisitos:

* El [!DNL .layer] archivo debe ajustarse al formato de uno de los tipos de capas admitidos.
* El [!DNL .layer] archivo debe hacer referencia a los archivos de dimensión y búsqueda adecuados, si es necesario.
* El archivo de búsqueda al que se hace referencia también debe almacenarse en el directorio de instalación del servidor de Área de trabajo de datos y su ruta de acceso debe especificarse con precisión en el [!DNL .layer] archivo.

Para obtener más información sobre el formato y los parámetros de cada tipo de archivo de capa y sus archivos asociados, consulte la sección de este capítulo correspondiente al tipo de capa correspondiente.
