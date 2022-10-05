---
description: Instrucciones para agregar el archivo visual_sciences.dll a la ruta de biblioteca Java de Tomcat.
title: Modificación de la ruta de biblioteca Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# Modificación de la ruta de biblioteca Java{#modify-the-java-library-path}

{{eol}}

Instrucciones para agregar el archivo visual_sciences.dll a la ruta de biblioteca Java de Tomcat.

1. En el servidor Windows, vaya al directorio de instalación de Tomcat. (Tomcat > bin)
1. En la carpeta bin, ejecute Tomcat9w.exe (administrador de servicio del demonio común).

En la pestaña Java , en Opciones de Java, agregue una línea nueva:

```
-Djava.library.path=C:\Sensor directory
```

Donde C:\Sensor directory is the directory containing the visual_sciences.dll archivo.
