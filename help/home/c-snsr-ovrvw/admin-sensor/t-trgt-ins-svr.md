---
description: Para cambiar el servidor de Data Workbench con el que se comunica un sensor (el servidor de destino), debe editar el archivo txlogd.conf en cada uno de los servidores web en los que está instalado Sensor.
title: Cambio del destino del servidor de Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Cambio del destino del servidor de Data Workbench{#changing-the-target-data-workbench-server}

{{eol}}

Para cambiar el servidor de Data Workbench con el que se comunica un sensor (el servidor de destino), debe editar el archivo txlogd.conf en cada uno de los servidores web en los que está instalado Sensor.

**Para cambiar a target[!DNL data workbench server]**

1. Detenga el servidor de destino original y el nuevo servidor de destino.
1. Copiar el más actual [!DNL .vsl] desde el servidor de destino original al nuevo servidor de destino. Cuando reinicie el nuevo servidor de destino en un paso posterior, esto provocará todas las [!DNL Sensor] datos que se anexarán al actual [!DNL .vsl] en lugar de crear un nuevo [!DNL .vsl] archivo. Para ello, complete los siguientes pasos:

   1. En el servidor de destino original, vaya a la [!DNL \Logs] en la carpeta [!DNL data workbench server] directorio de instalación.

   1. Copiar el más actual [!DNL .vsl] en la carpeta .
   1. En el nuevo servidor de destino, vaya a la [!DNL \Logs] en la carpeta [!DNL data workbench server] directorio de instalación y pegue el [!DNL .vsl] a esta carpeta.

1. En uno de los servidores web en los que [!DNL Sensor] está instalado, abra y edite el [!DNL txlogd.conf] archivo. Para ello, complete los siguientes pasos:

   1. Vaya a la [!DNL Sensor] directorio de instalación y abra [!DNL txlogd.conf] en un editor de texto.

   1. Busque el parámetro ServerAddress y cámbielo para que refleje la dirección del nuevo servidor de destino.
   1. Guarde y cierre el archivo.

1. Repita los pasos del 2 al 3 en todos los servidores web restantes en los que [!DNL Sensor] está instalado.
1. Reinicie el servidor de destino original (si todavía está por utilizar) y el nuevo servidor de destino.
1. Los datos empezarán a transmitirse al nuevo servidor de destino que haya especificado.
