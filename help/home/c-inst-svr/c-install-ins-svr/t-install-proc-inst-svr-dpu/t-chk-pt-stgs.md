---
description: De forma predeterminada, Insight Server escucha en los puertos 80 (para HTTP) y 443 (para HTTPS).
title: Comprobación de la configuración del puerto
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# Comprobación de la configuración del puerto{#checking-the-port-settings}

{{eol}}

De forma predeterminada, Insight Server escucha en los puertos 80 (para HTTP) y 443 (para HTTPS).

Si estos puertos ya están asignados por otro proceso en el equipo en el que ha instalado [!DNL Insight Server], utilice el siguiente procedimiento para cambiar [!DNL Insight Server’s] asignaciones de puerto.

**Para cambiar las asignaciones de puerto**

1. Vaya a la [!DNL Components] carpeta en el directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Components]

1. Abra el [!DNL Communications.cfg] en un editor de texto como Bloc de notas.
1. Busque las entradas Puerto y Puerto SSL , como se muestra a continuación:

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. Si estos no son los puertos que desea [!DNL Insight Server] para usar, cambie las asignaciones de puerto y, a continuación, guarde y cierre el archivo.
