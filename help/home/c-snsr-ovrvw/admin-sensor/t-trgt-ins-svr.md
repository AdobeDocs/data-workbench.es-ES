---
description: Para cambiar el servidor del área de trabajo de datos con el que se comunica un sensor (el servidor destinatario), debe editar el archivo txlogd.conf en cada uno de los servidores Web en los que está instalado Sensor.
solution: Analytics
title: Cambio del destino del servidor de Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---


# Cambio del destino del servidor de Data Workbench{#changing-the-target-data-workbench-server}

Para cambiar el servidor del área de trabajo de datos con el que se comunica un sensor (el servidor destinatario), debe editar el archivo txlogd.conf en cada uno de los servidores Web en los que está instalado Sensor.

**Para cambiar a destinatario[!DNL data workbench server]**

1. Detenga el servidor de destinatario original y el nuevo servidor de destinatario.
1. Copie el [!DNL .vsl] archivo más reciente del servidor de destinatario original al nuevo servidor de destinatario. Al reiniciar el nuevo servidor de destinatario en un paso posterior, todos los datos nuevos [!DNL Sensor] se anexan al [!DNL .vsl] archivo existente actual en lugar de crear un nuevo [!DNL .vsl] archivo. Para ello, complete los siguientes pasos:

   1. En el servidor de destinatario original, vaya a la [!DNL \Logs] carpeta del directorio [!DNL data workbench server] de instalación.

   1. Copie el [!DNL .vsl] archivo más reciente de la carpeta.
   1. En el nuevo servidor de destinatario, vaya a la [!DNL \Logs] carpeta del directorio de instalación [!DNL data workbench server] y pegue el [!DNL .vsl] archivo en esta carpeta.

1. En uno de los servidores web en los que [!DNL Sensor] está instalado, abra y edite el [!DNL txlogd.conf] archivo. Para ello, complete los siguientes pasos:

   1. Vaya al directorio de instalación [!DNL Sensor] y abra el [!DNL txlogd.conf] archivo en un editor de texto.

   1. Busque el parámetro ServerAddress y cámbielo para que refleje la dirección del nuevo servidor de destinatario.
   1. Guarde y cierre el archivo.

1. Repita los pasos del 2 al 3 en todos los servidores Web restantes en los que [!DNL Sensor] esté instalado.
1. Reinicie el servidor de destinatario original (si aún no se ha utilizado) y el nuevo servidor de destinatario.
1. Los datos empezarán a transmitirse al nuevo servidor de destinatario que haya especificado.
