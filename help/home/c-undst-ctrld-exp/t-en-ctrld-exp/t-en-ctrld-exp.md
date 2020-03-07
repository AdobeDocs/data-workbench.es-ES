---
description: Para habilitar la experimentación controlada, alguien con acceso de administrador a sus servidores Web o de aplicaciones debe modificar el parámetro ExpFile en el archivo de configuración de Sensor (generalmente denominado mediante txlogd.conf) en cada servidor Web o de aplicaciones del clúster Web en el que esté instalado un Sensor.
solution: Insight,Analytics
title: Habilitar experimentación controlada
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Habilitar experimentación controlada{#enabling-controlled-experimentation}

Para habilitar la experimentación controlada, alguien con acceso de administrador a sus servidores Web o de aplicaciones debe modificar el parámetro ExpFile en el archivo de configuración de Sensor (generalmente denominado mediante txlogd.conf) en cada servidor Web o de aplicaciones del clúster Web en el que esté instalado un Sensor.

Además, se pueden modificar otros dos parámetros de este archivo para implementar una herramienta de prueba (parámetro ExpCookieURL) o para reasignar grandes secciones del sitio web (parámetro ExpPartialMatch). Este capítulo proporciona más información sobre estos parámetros.

**Para editar el archivo txlogd.conf**

Si tiene acceso de administrador, complete los siguientes pasos. Si no dispone de acceso de administrador, póngase en contacto con el arquitecto del sistema para solicitar los cambios, proporcionándoles los siguientes pasos.

1. Vaya a la carpeta de instalación de un servidor Web o de aplicaciones del clúster Web en el que se haya instalado un [!DNL Sensor] [!DNL Sensor] servidor.
1. Abra el [!DNL Sensor] archivo de configuración (normalmente denominado mediante [!DNL txlogd.conf]) con un editor de texto y edite el archivo como se indica en [Modificación del parámetro](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

   (Y, opcionalmente, en la [modificación del parámetro ExpCookieURL (opcional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) y en la [modificación del parámetro ExpPartialMatch (opcional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e)).

1. Guarde y cierre el archivo.
1. Repita este procedimiento para cada servidor Web o de aplicaciones del clúster Web en el que [!DNL Sensor] esté instalado un servidor.
