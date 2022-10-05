---
description: Pasos para actualizar la carpeta Transform .
title: Actualización de transformación
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Actualización de transformación{#upgrading-transform}

{{eol}}

Pasos para actualizar la carpeta Transform .

1. Abra el [!DNL .zip] para [!DNL Insight Server] libere el paquete y abra el [!DNL Profiles] carpeta dentro de [!DNL .zip] archivo.
1. Copie el [!DNL Transform] a la [!DNL Profiles] en su [!DNL Insight Server] directorio de instalación. Al hacer esto, se sobrescribe la [!DNL Transform] carpeta.
1. Para cada perfil que hereda la variable [!DNL Transform] , confirme que la variable [!DNL profile.cfg] tiene una entrada &quot;Transformar&quot; en el vector Directorios.
El reprocesamiento de datos comienza después de la sincronización del perfil.
