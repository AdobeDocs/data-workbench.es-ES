---
description: La geografía de Data Workbench admite proyecciones de latitud-longitud y proyecciones de Universal Transverse Mercator (UTM) para todas las fuentes de capa de imagen de terreno.
title: Especificación de la información de proyección para imágenes de terreno
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Especificación de la información de proyección para imágenes de terreno{#specifying-projection-information-for-terrain-images}

{{eol}}

La geografía de Data Workbench admite proyecciones de latitud-longitud y proyecciones de Universal Transverse Mercator (UTM) para todas las fuentes de capa de imagen de terreno.

La información de proyección es necesaria para los mapas de bits sin proyectar e imágenes generales, no proyectados. Puede especificar información de proyección para imágenes con información de proyección incrustada, aunque normalmente no es necesaria, ya que los parámetros de la proyección se determinan automáticamente a partir de datos geodésicos incrustados en la propia imagen. Las secciones siguientes proporcionan detalles sobre cómo especificar estos formatos de proyección en la variable [!DNL Terrain Images.cfg] archivo.
