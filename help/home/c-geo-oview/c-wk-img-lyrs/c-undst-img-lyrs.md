---
description: Información conceptual sobre las capas de perfil Geografía, los tipos de capas de imágenes y la creación de nuevas capas.
solution: Analytics
title: Explicación de las capas de imágenes
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de las capas de imágenes{#understanding-imagery-layers}

Información conceptual sobre las capas de perfil Geografía, los tipos de capas de imágenes y la creación de nuevas capas.

## Tipos de capas de imágenes {#section-ce25364651a04cd1b83f9ac7c231fa41}

El área de trabajo de datos [!DNL Geography] permite ver los siguientes tipos de capas de imágenes en el área de trabajo de datos:

* **Capa de imagen de terreno:** Este tipo de capa muestra imágenes de terreno de la Tierra, sobre las que se pueden mostrar datos geográficos. La visualización de globo en el área de trabajo de datos es un ejemplo de una capa de imagen de terreno. Consulte [Uso de capas](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)de imagen de terreno.

* **Capa de punto de elemento:** Este tipo de capa muestra un punto en el globo para cada elemento de una dimensión. Consulte [Uso de capas](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)de puntos de elementos.

* **Capa vectorial:** Este tipo de capa muestra datos vectoriales (arte lineal) en el globo. Consulte [Uso de capas](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)vectoriales.

En el área de trabajo de datos, puede seleccionar qué capas desea mostrar para una tarea de análisis concreta.

## Capas de perfil geográfico {#section-4d9fb9b357764493a4d97d2b4068bb67}

El [!DNL Geography] perfil le proporciona un conjunto de capas de imágenes predeterminadas, que se almacenan en la carpeta Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Mármol azul 2 km:** Esta capa de imagen de terreno crea un mapa 3D del mundo, que es lo que se muestra al agregar la visualización de globo a un espacio de trabajo. Cuando esta capa no está seleccionada, el globo no está visible pero las demás capas siguen mostrándose. El [!DNL Blue Marble 2km.layer] archivo hace referencia al [!DNL Blue Marble 2km.tsi] archivo.

   Para obtener información sobre el trabajo con la visualización de globos, consulte la Guía del usuario *de Área de trabajo de datos*.

* **Puntos postales:** Esta capa de punto de elemento le permite asignar ubicaciones en el conjunto de datos mediante un código postal de Estados Unidos. El archivo de [!DNL Zip Points.txt] búsqueda (proporcionado por Adobe) contiene una lista de todos los códigos postales de Estados Unidos y la latitud y longitud de cada código postal. El [!DNL Zip Points.layer] archivo hace referencia al [!DNL Zip Points.txt] archivo y al [!DNL Zipcode.dim] archivo y contiene los parámetros de configuración necesarios para mostrar las ubicaciones en el globo. Cada elemento de la dimensión Código postal ( [!DNL Zipcode.dim]) que defina dentro del conjunto de datos se asigna en el globo usando la latitud y longitud enumeradas para ese código postal en el archivo de [!DNL Zip Points.txt] búsqueda.

   Para obtener información sobre la definición de dimensiones, consulte la Guía de configuración de *conjuntos de datos.*

* **Límites:** Esta capa vectorial proporciona las principales fronteras políticas mundiales, como los países, así como los límites de las características físicas naturales de la Tierra, como lagos e islas. El [!DNL Boundaries.layer] archivo hace referencia a uno o varios de los [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]y [!DNL world boundaries.vec] archivos.

* **Coordenadas IP:** Esta capa de puntos de elemento utiliza puntos dinámicos para permitirle asignar ubicaciones en el conjunto de datos mediante direcciones IP. El [!DNL IP Coordinates.layer] archivo hace referencia a la dimensión Coordenadas ( [!DNL Coordinates.dim]) y especifica la métrica Visitantes como métrica que se utilizará para determinar el tamaño de los puntos del globo para cada coordenada.

Su perfil [!DNL Geography] u otros perfiles de la instalación pueden contener capas de imágenes adicionales que Adobe proporcionó o que su empresa creó.

## Creación de nuevas capas {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Puede crear nuevas capas de imágenes copiando el tipo adecuado de archivo de capa incluido en el [!DNL Geography] perfil en cualquier carpeta Profiles\*profile name*\Maps y, a continuación, cambiando el nombre y editando el archivo según corresponda. Todas las capas nuevas deben cumplir los siguientes requisitos:

* El [!DNL .layer] archivo debe ajustarse al formato de uno de los tipos de capas admitidos.
* El [!DNL .layer] archivo debe hacer referencia a los archivos de dimensión y búsqueda adecuados, si es necesario.
* El archivo de búsqueda al que se hace referencia también debe almacenarse en el directorio de instalación del servidor del área de trabajo de datos y su ruta de acceso debe especificarse con precisión en el [!DNL .layer] archivo.

Para obtener más información sobre el formato y los parámetros de cada tipo de archivo de capa y sus archivos asociados, consulte la sección de este capítulo correspondiente al tipo de capa correspondiente.
