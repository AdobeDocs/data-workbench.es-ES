---
description: Pasos para actualizar la carpeta Transform.
solution: Insight
title: Actualización de transformación
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Actualización de transformación{#upgrading-transform}

Pasos para actualizar la carpeta Transform.

1. Abra el [!DNL .zip] archivo del paquete de [!DNL Insight Server] versión y abra la [!DNL Profiles] carpeta dentro de ese [!DNL .zip] archivo.
1. Copie la [!DNL Transform] carpeta en la [!DNL Profiles] carpeta del directorio [!DNL Insight Server] de instalación. Al hacer esto, se sobrescribe la [!DNL Transform] carpeta existente.
1. Para cada perfil que hereda el [!DNL Transform] perfil, confirme que el [!DNL profile.cfg] archivo tiene una entrada &quot;Transformar&quot; en el vector Directorios.
El reprocesamiento de datos comienza después de la sincronización del perfil.
