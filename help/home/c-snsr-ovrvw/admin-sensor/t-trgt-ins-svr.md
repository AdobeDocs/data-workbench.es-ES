---
description: Para cambiar el servidor de Data Workbench con el que se comunica un sensor (el servidor de destino), debe editar el archivo txlogd.conf en cada uno de los servidores web en los que está instalado Sensor.
title: Cambio del destino del servidor de Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Cambio del destino del servidor de Data Workbench{#changing-the-target-data-workbench-server}

Para cambiar el servidor de Data Workbench con el que se comunica un sensor (el servidor de destino), debe editar el archivo txlogd.conf en cada uno de los servidores web en los que está instalado Sensor.

**Para cambiar a target[!DNL data workbench server]**

1. Detenga el servidor de destino original y el nuevo servidor de destino.
1. Copie el archivo [!DNL .vsl] más actual desde el servidor de destino original al nuevo servidor de destino. Cuando reinicie el nuevo servidor de destino en un paso posterior, esto hará que todos los datos nuevos [!DNL Sensor] se adjunten al archivo [!DNL .vsl] actual en lugar de crear un nuevo archivo [!DNL .vsl]. Para ello, complete los siguientes pasos:

   1. En el servidor de destino original, vaya a la carpeta [!DNL \Logs] en el directorio de instalación [!DNL data workbench server].

   1. Copie el archivo [!DNL .vsl] más actual de la carpeta.
   1. En el nuevo servidor de destino, vaya a la carpeta [!DNL \Logs] en el directorio de instalación [!DNL data workbench server] y pegue el archivo [!DNL .vsl] en esta carpeta.

1. En uno de los servidores web en los que está instalado [!DNL Sensor], abra y edite el archivo [!DNL txlogd.conf]. Para ello, complete los siguientes pasos:

   1. Vaya al directorio de instalación [!DNL Sensor] y abra el archivo [!DNL txlogd.conf] en un editor de texto.

   1. Busque el parámetro ServerAddress y cámbielo para que refleje la dirección del nuevo servidor de destino.
   1. Guarde y cierre el archivo.

1. Repita los pasos del 2 al 3 en todos los servidores web restantes en los que está instalado [!DNL Sensor].
1. Reinicie el servidor de destino original (si todavía está por utilizar) y el nuevo servidor de destino.
1. Los datos empezarán a transmitirse al nuevo servidor de destino que haya especificado.
