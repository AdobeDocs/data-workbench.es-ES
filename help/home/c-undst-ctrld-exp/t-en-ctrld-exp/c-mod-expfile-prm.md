---
description: El parámetro ExpFile apunta a la ubicación del archivo de configuración del experimento, que define el experimento.
solution: Analytics
title: Modificación del parámetro ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Modificación del parámetro ExpFile{#modifying-the-expfile-parameter}

El parámetro ExpFile apunta a la ubicación del archivo de configuración del experimento, que define el experimento.

La configuración de este parámetro le permite ejecutar experimentos. Para ver los pasos para crear el archivo de configuración del experimento, consulte [Configuración e implementación del experimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

A continuación se muestra un ejemplo del parámetro ExpFile:

```
ExpFile /home/experiment.txt
```

Esta ficha delimita el archivo de texto ( [!DNL .txt]) se puede encontrar en cualquier lugar del [!DNL Sensor] carpeta y puede tener cualquier nombre conveniente.

Asegúrese de registrar la ubicación del directorio de experimentos y el nombre del archivo de configuración que especifique porque necesita guardar el archivo de configuración del experimento (que se describirá más adelante en esta guía) con este nombre y en este directorio.

>[!NOTE]
>
>Si no establece este parámetro de forma idéntica en cada equipo del clúster web en el que [!DNL Sensor] está instalado, la experimentación controlada no funciona.

Esta entrada se puede preconfigurar y permanecer en el [!DNL Sensor] archivo de configuración de forma continua sin efectos adversos. Si el nombre del archivo de configuración del experimento especificado no se encuentra en [!DNL Sensor] o está en blanco (es decir, existe pero no tiene contenido), [!DNL Sensor] no realiza el experimento, registra un evento de error en el servidor HTTP y sigue funcionando normalmente en todos los demás aspectos.
