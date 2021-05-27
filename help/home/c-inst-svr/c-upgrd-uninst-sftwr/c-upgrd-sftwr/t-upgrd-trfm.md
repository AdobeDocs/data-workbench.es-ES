---
description: Pasos para actualizar la carpeta Transform .
title: Actualización de transformación
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Actualización de transformación{#upgrading-transform}

Pasos para actualizar la carpeta Transform .

1. Abra el archivo [!DNL .zip] para el paquete de versión [!DNL Insight Server] y abra la carpeta [!DNL Profiles] dentro de ese archivo [!DNL .zip].
1. Copie la carpeta [!DNL Transform] a la carpeta [!DNL Profiles] en el directorio de instalación de [!DNL Insight Server]. Al hacerlo, se sobrescribe la carpeta [!DNL Transform] existente.
1. Para cada perfil que hereda el perfil [!DNL Transform], confirme que el archivo [!DNL profile.cfg] tiene una entrada &quot;Transformar&quot; en el vector Directorios.
El reprocesamiento de datos comienza después de la sincronización del perfil.
