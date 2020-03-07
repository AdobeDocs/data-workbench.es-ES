---
description: Instrucciones para agregar el archivo visual_sciences.dll a la ruta de la biblioteca java de Tomcat.
title: Modificación de la ruta de biblioteca Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificación de la ruta de biblioteca Java{#modify-the-java-library-path}

Instrucciones para agregar el archivo visual_sciences.dll a la ruta de la biblioteca java de Tomcat.

1. En el servidor Windows, vaya al directorio de instalación de Tomcat. (Tomcat > bin)
1. En la carpeta bin, ejecute Tomcat9w.exe (administrador de servicio de demonio común).

En la ficha Java, en Opciones de Java, agregue una nueva línea:

```
-Djava.library.path=C:\Sensor directory
```

Donde C:\Sensor directory is the directory containing the visual_sciences.dll archivo.
