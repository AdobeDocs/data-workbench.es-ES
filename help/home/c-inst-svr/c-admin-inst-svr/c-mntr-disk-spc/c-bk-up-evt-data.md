---
description: Se debe realizar un backup diario de los datos de evento utilizando los sistemas de backup normales de su empresa y los procedimientos de recuperación ante desastres.
title: Copia de seguridad de datos de evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# Copia de seguridad de datos de evento{#backing-up-event-data}

Se debe realizar un backup diario de los datos de evento utilizando los sistemas de backup normales de su empresa y los procedimientos de recuperación ante desastres.

**Frecuencia recomendada:** Diario

[!DNL Insight Server] comienza los nuevos archivos de registro a las 12:00 AM GMT diariamente. Adobe recomienda realizar copias de seguridad de los archivos de registro todos los días poco después de las 12:00 AM GMT para poder capturar todos los datos del día anterior. Por ejemplo, la copia de seguridad de todos los archivos de registro a las 12:05 AM GMT del 15 de diciembre captura todos los datos del 14 de diciembre. [!DNL Insight Server] no necesita detenerse durante las copias de seguridad de los archivos de registro, y todas las funcionalidades permanecen disponibles.

## Copia de seguridad de datos de integración, sistema operativo, salida y sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frecuencia recomendada:** Diario

La integración, el sistema operativo, la salida y los datos del sistema deben realizarse con regularidad y diligencia utilizando los sistemas normales de backup y recuperación ante desastres de su empresa.
