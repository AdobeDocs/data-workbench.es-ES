---
description: El parámetro ExpFile apunta a la ubicación del archivo de configuración del experimento, que define el experimento.
solution: Insight,Analytics
title: Modificación del parámetro ExpFile
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificación del parámetro ExpFile{#modifying-the-expfile-parameter}

El parámetro ExpFile apunta a la ubicación del archivo de configuración del experimento, que define el experimento.

La configuración de este parámetro le permite ejecutar experimentos. Para ver los pasos para crear el archivo de configuración del experimento, consulte [Configuración e implementación del experimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

A continuación se muestra un ejemplo del parámetro ExpFile:

```
ExpFile /home/experiment.txt
```

Este archivo de texto delimitado por tabuladores ( [!DNL .txt]) puede ubicarse en cualquier lugar de la [!DNL Sensor] carpeta y puede tener cualquier nombre conveniente.

Asegúrese de registrar la ubicación del directorio de experimentos y el nombre del archivo de configuración que especifique, ya que debe guardar el archivo de configuración del experimento (que se describirá más adelante en esta guía) con este nombre y en este directorio.

>[!NOTE]
>
>Si no establece este parámetro de forma idéntica en cada equipo del clúster web en el que se haya instalado un [!DNL Sensor] equipo, la experimentación controlada no funcionará.

Esta entrada puede preconfigurarse y permanecer en el archivo de configuración de forma continua sin ningún efecto adverso. [!DNL Sensor] Si el nombre del archivo de configuración del experimento especificado no se encuentra en [!DNL Sensor] o está en blanco (es decir, existe pero no tiene contenido), [!DNL Sensor] no realiza el experimento, registra un evento de error en el servidor HTTP y sigue funcionando normalmente en todos los demás aspectos.
