---
description: Se debe realizar una copia de seguridad diaria de los datos de evento mediante los sistemas de backup normales de la compañía y los procedimientos de recuperación ante desastres.
solution: Analytics
title: Copia de seguridad de datos de evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---


# Copia de seguridad de datos de evento{#backing-up-event-data}

Se debe realizar una copia de seguridad diaria de los datos de evento mediante los sistemas de backup normales de la compañía y los procedimientos de recuperación ante desastres.

**Frecuencia recomendada:** Diario

[!DNL Insight Server] comienza los nuevos archivos de registro a las 12:00 AM GMT diariamente. Adobe recomienda que realice una copia de seguridad de los archivos de registro todos los días poco después de las 12:00 AM GMT para poder capturar todos los datos del día anterior. Por ejemplo, la copia de seguridad de todos los archivos de registro a las 12:05 GMT del 15 de diciembre captura todos los datos del 14 de diciembre. [!DNL Insight Server] no necesita detenerse durante las copias de seguridad de los archivos de registro y toda la funcionalidad permanece disponible.

## Copia de seguridad de datos de integración, sistema operativo, salida y sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frecuencia recomendada:** Diario

La integración, el sistema operativo, la salida y los datos del sistema deben respaldarse de manera regular y diligente utilizando los sistemas normales de backup y recuperación ante desastres de su compañía.
