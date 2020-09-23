---
description: De forma predeterminada, Insight Server escribe su conjunto de datos (temp.db) en la misma unidad que los archivos programa de Insight Server.
solution: Analytics
title: Configuración de la ubicación del conjunto de datos (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---


# Configuración de la ubicación del conjunto de datos (temp.db){#configuring-the-location-of-the-dataset-temp-db}

De forma predeterminada, Insight Server escribe su conjunto de datos (temp.db) en la misma unidad que los archivos programa de Insight Server.

Por ejemplo, si instala [!DNL Insight Server] en la unidad C, escribe el conjunto de datos en la unidad C.

Si desea [!DNL Insight Server] mantener el conjunto de datos en una unidad diferente, o si la cantidad de datos que espera recopilar requiere el uso de varias unidades, debe actualizar el [!DNL Disk Files.cfg] archivo para especificar dónde desea [!DNL Insight Server] escribir el [!DNL temp.db] archivo.

**Para configurar la ubicación de temp.db**

1. Vaya a la [!DNL Components] carpeta del directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Components]

1. Abra el [!DNL Disk Files.cfg] archivo en un editor de texto como Bloc de notas.

   De forma predeterminada, este archivo contiene una sola entrada en la estructura Archivos de disco, como se muestra a continuación.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Para cambiar la ubicación de [!DNL temp.db], modifique la definición de Archivos de disco. El siguiente ejemplo ilustra cómo editaría la configuración para distribuir el [!DNL temp.db] archivo entre las unidades C, D y E:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Tenga en cuenta el uso de las barras invertidas de doble en los nombres de archivo anteriores. En los archivos [!DNL Insight Server] de configuración, el carácter de barra invertida es un carácter de escape. Se utiliza para expresar secuencias de control especiales (por ejemplo, \t para un carácter de tabulación) en el texto. Para representar un carácter de barra invertida real, debe escribir la barra invertida dos veces (por ejemplo, \\) para anular la función de escape. Esto solo se aplica cuando se editan archivos de configuración en un editor de texto como Bloc de notas.

