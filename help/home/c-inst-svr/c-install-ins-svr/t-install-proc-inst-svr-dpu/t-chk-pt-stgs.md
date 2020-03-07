---
description: De forma predeterminada, Insight Server escucha en los puertos 80 (para HTTP) y 443 (para HTTPS).
solution: Insight
title: Comprobación de la configuración del puerto
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comprobación de la configuración del puerto{#checking-the-port-settings}

De forma predeterminada, Insight Server escucha en los puertos 80 (para HTTP) y 443 (para HTTPS).

Si estos puertos ya están asignados por otro proceso en el equipo en el que ha instalado [!DNL Insight Server], utilice el siguiente procedimiento para cambiar las asignaciones [!DNL Insight Server’s] de puertos.

**Cambio de las asignaciones de puertos**

1. Vaya a la [!DNL Components] carpeta del directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Components]

1. Abra el [!DNL Communications.cfg] archivo en un editor de texto como Bloc de notas.
1. Ubique las entradas Puerto y Puerto SSL, como se muestra a continuación:

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

1. Si estos no son los puertos que desea [!DNL Insight Server] utilizar, cambie las asignaciones de puertos y, a continuación, guarde y cierre el archivo.
