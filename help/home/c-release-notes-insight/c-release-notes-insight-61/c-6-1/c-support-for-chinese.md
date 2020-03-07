---
description: La aplicación cliente del área de trabajo de datos ahora admite chino simplificado.
solution: Analytics
title: Localización de chino simplificado
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Localización de chino simplificado{#simplified-chinese-localization}

La aplicación cliente del área de trabajo de datos ahora admite chino simplificado.

**Para instalar chino** simplificado:

Antes de configurar [!DNL Insight.exe] y admitir archivos, debe salir de la aplicación cliente.

1. Cree un acceso directo que pase la configuración de la línea de comandos al [!DNL insight.exe] archivo.

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para admitir caracteres de fuente de byte único y doble.

   Actualmente, el área de trabajo de datos admite inglés y chino simplificado. Puede seleccionar fuentes para admitir ambos idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Reiniciar [!DNL Insight.exe].

