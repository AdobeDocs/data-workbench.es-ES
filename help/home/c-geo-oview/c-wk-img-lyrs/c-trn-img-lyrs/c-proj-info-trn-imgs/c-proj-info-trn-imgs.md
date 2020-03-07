---
description: Área de trabajo de datos Geografía admite proyecciones de latitud y longitud y proyecciones de Universal Transverse Mercator (UTM) para todos los orígenes de capas de imagen de terreno.
solution: Analytics
title: Especificación de la información de proyección para imágenes de terreno
topic: Data workbench
uuid: 4a476192-e749-4187-b64e-9794f39b0019
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Especificación de la información de proyección para imágenes de terreno{#specifying-projection-information-for-terrain-images}

Área de trabajo de datos Geografía admite proyecciones de latitud y longitud y proyecciones de Universal Transverse Mercator (UTM) para todos los orígenes de capas de imagen de terreno.

La información de proyección es necesaria para los mapas de bits sin proyección y las imágenes generales, no proyectadas. Puede especificar información de proyección para imágenes con información de proyección incrustada, aunque normalmente no es necesaria porque los parámetros de la proyección se determinan automáticamente a partir de datos geodésicos incrustados en la propia imagen. Las siguientes secciones proporcionan detalles sobre cómo especificar estos formatos de proyección en el [!DNL Terrain Images.cfg] archivo.
