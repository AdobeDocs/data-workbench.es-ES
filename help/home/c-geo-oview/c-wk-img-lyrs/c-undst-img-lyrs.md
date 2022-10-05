---
description: Información conceptual sobre las capas de perfil de Geografía, tipos de capas de imágenes y creación de nuevas capas.
title: Explicación de las capas de imágenes
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Explicación de las capas de imágenes{#understanding-imagery-layers}

{{eol}}

Información conceptual sobre las capas de perfil de Geografía, tipos de capas de imágenes y creación de nuevas capas.

## Tipos de capas de imágenes {#section-ce25364651a04cd1b83f9ac7c231fa41}

Área de trabajo de datos [!DNL Geography] permite ver los siguientes tipos de capas de imágenes en data workbench:

* **Capa de imagen del terreno:** Este tipo de capa muestra imágenes de terreno de la Tierra, sobre las que se pueden visualizar datos geográficos. La visualización del globo terráqueo en Data Workbench es un ejemplo de una capa de imagen de terreno. Consulte [Uso de capas de imagen del terreno](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Capa de punto de elemento:** Este tipo de capa muestra un punto del globo para cada elemento de una dimensión. Consulte [Uso de capas de punto de elementos](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Capa vectorial:** Este tipo de capa muestra datos vectoriales (arte lineal) en el globo. Consulte [Uso de capas vectoriales](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

En Data Workbench, puede seleccionar cuál de estas capas desea mostrar para una tarea de análisis determinada.

## Capas de perfil de geografía {#section-4d9fb9b357764493a4d97d2b4068bb67}

La variable [!DNL Geography] profile le proporciona un conjunto de capas de imágenes predeterminadas, que se almacenan en la carpeta Profiles\Geography\Maps dentro del directorio de instalación del servidor de Data Workbench:

* **Mármol azul a 2 km:** Esta capa de imagen de terreno crea un mapa 3D del mundo, que es lo que se muestra al agregar la visualización del globo a un espacio de trabajo. Cuando no se selecciona esta capa, el globo no es visible, pero las demás capas siguen mostrándose. La variable [!DNL Blue Marble 2km.layer] hace referencia al [!DNL Blue Marble 2km.tsi] archivo.

   Para obtener información sobre cómo trabajar con la visualización del globo, consulte la *Guía del usuario de Data Workbench*.

* **Puntos postales:** Esta capa de puntos de elemento le permite asignar ubicaciones en el conjunto de datos mediante un código postal de Estados Unidos. La variable [!DNL Zip Points.txt] el archivo de búsqueda (proporcionado por Adobe) contiene una lista de todos los códigos postales de Estados Unidos y la latitud y longitud de cada código postal. La variable [!DNL Zip Points.layer] hace referencia al [!DNL Zip Points.txt] y [!DNL Zipcode.dim] y contiene los parámetros de configuración necesarios para mostrar las ubicaciones en el globo. Cada elemento de la dimensión Código postal ( [!DNL Zipcode.dim]) que define dentro de su conjunto de datos está asignado en el globo utilizando la latitud y longitud enumeradas para ese código postal en la variable [!DNL Zip Points.txt] archivo de búsqueda.

   Para obtener información sobre la definición de dimensiones, consulte la *Guía de configuración de conjuntos de datos.*

* **Límites:** Esta capa vectorial proporciona las principales fronteras políticas mundiales, como los países, así como los límites de las características físicas naturales de la Tierra, como lagos e islas. La variable [!DNL Boundaries.layer] hace referencia a una o más de las [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]y [!DNL world boundaries.vec] archivos.

* **Coordenadas IP:** Esta capa de puntos de elemento utiliza puntos dinámicos para permitirle asignar ubicaciones en el conjunto de datos mediante direcciones IP. La variable [!DNL IP Coordinates.layer] hace referencia a la dimensión Coordenadas ( [!DNL Coordinates.dim]) y especifica la métrica Visitantes como la métrica que se utilizará para determinar el tamaño de los puntos del globo para cada coordenada.

Su [!DNL Geography] perfil u otros perfiles de la instalación pueden contener capas de imágenes adicionales que proporcionan los Adobes o que la empresa ha creado.

## Creación de nuevas capas {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Puede crear nuevas capas de imágenes copiando el tipo apropiado de archivo de capa incluido en el [!DNL Geography] perfil en cualquier carpeta Profiles\*nombre de perfil*\Mapas y, a continuación, cambie el nombre del archivo y edítelo según corresponda. Todas las capas nuevas deben cumplir los siguientes requisitos:

* La variable [!DNL .layer] debe cumplir el formato de uno de los tipos de capa admitidos.
* La variable [!DNL .layer] debe hacer referencia a los archivos de dimensión y búsqueda adecuados, si es necesario.
* El archivo de búsqueda al que se hace referencia también debe almacenarse en el directorio de instalación del servidor de Data Workbench, y su ruta debe especificarse con precisión en la variable [!DNL .layer] archivo.

Para obtener más información sobre el formato y los parámetros de cada tipo de archivo de capa y sus archivos asociados, consulte la sección de este capítulo para obtener el tipo de capa correspondiente.
