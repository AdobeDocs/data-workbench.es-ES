---
description: Se debe realizar una copia de seguridad diaria de los datos de eventos mediante los sistemas de backup normales de la empresa y los procedimientos de recuperación ante desastres.
solution: Insight
title: Copia de seguridad de datos de eventos
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copia de seguridad de datos de eventos{#backing-up-event-data}

Se debe realizar una copia de seguridad diaria de los datos de eventos mediante los sistemas de backup normales de la empresa y los procedimientos de recuperación ante desastres.

**Frecuencia recomendada:** Diario

[!DNL Insight Server] comienza los nuevos archivos de registro a las 12:00 AM GMT diariamente. Adobe recomienda que realice una copia de seguridad de los archivos de registro todos los días poco después de las 12:00 GMT para poder capturar todos los datos del día anterior. Por ejemplo, la copia de seguridad de todos los archivos de registro a las 12:05 GMT del 15 de diciembre captura todos los datos del 14 de diciembre. [!DNL Insight Server] no necesita detenerse durante las copias de seguridad de los archivos de registro y toda la funcionalidad permanece disponible.

## Copia de seguridad de datos de integración, sistema operativo, salida y sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frecuencia recomendada:** Diario

La integración, el sistema operativo, la salida y los datos del sistema deben respaldarse de manera regular y diligente utilizando los sistemas normales de backup y recuperación ante desastres de su empresa.
