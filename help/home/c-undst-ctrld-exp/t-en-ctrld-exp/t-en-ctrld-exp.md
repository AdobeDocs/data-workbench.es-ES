---
description: Para habilitar la experimentación controlada, alguien con acceso de administrador a su web o servidores de aplicaciones debe modificar el parámetro ExpFile en el archivo de configuración del sensor (generalmente denominado usando txlogd.conf) en cada servidor web o de aplicaciones del clúster web en el que está instalado un sensor.
solution: Analytics
title: Habilitar experimento controlado
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Habilitar experimento controlado{#enabling-controlled-experimentation}

Para habilitar la experimentación controlada, alguien con acceso de administrador a su web o servidores de aplicaciones debe modificar el parámetro ExpFile en el archivo de configuración del sensor (generalmente denominado usando txlogd.conf) en cada servidor web o de aplicaciones del clúster web en el que está instalado un sensor.

Además, se pueden modificar otros dos parámetros de este archivo para implementar una herramienta de prueba (parámetro ExpCookieURL ) o para reasignar grandes secciones de su sitio web (parámetro ExpPartialMatch ). Este capítulo proporciona más información sobre estos parámetros.

**Para editar el archivo txlogd.conf**

Si tiene acceso de administrador, complete los siguientes pasos. Si no tiene acceso de administrador, póngase en contacto con el arquitecto del sistema para solicitar los cambios, proporcionándoles los siguientes pasos.

1. Vaya a la [!DNL Sensor] carpeta de instalación en un servidor de aplicaciones o web de su clúster web en el que [!DNL Sensor] está instalado.
1. Abra el [!DNL Sensor] archivo de configuración (normalmente, con el nombre [!DNL txlogd.conf]) con un editor de texto y edite el archivo como se indica en [Modificación del parámetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   (Y opcionalmente en [Modificación del parámetro ExpCookieURL (opcional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) y [Modificación del parámetro ExpPartialMatch (opcional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Guarde y cierre el archivo.
1. Repita este procedimiento para cada servidor de aplicaciones o web de su clúster web en el que [!DNL Sensor] está instalado.
