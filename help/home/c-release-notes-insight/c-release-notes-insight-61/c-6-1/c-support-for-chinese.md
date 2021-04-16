---
description: La aplicación cliente de Data Workbench ahora es compatible con el chino simplificado.
title: Localización de chino simplificado
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# Localización de chino simplificado{#simplified-chinese-localization}

La aplicación cliente de Data Workbench ahora es compatible con el chino simplificado.

**Para instalar chino** simplificado:

Antes de configurar [!DNL Insight.exe] y los archivos de soporte, debe salir de la aplicación cliente.

1. Cree un acceso directo que pase la configuración de la línea de comandos al archivo [!DNL insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para que admita caracteres de fuente de byte único y doble.

   Actualmente, Data Workbench admite inglés y chino simplificado. Puede seleccionar fuentes para admitir ambos idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Reiniciar [!DNL Insight.exe].

