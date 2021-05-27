---
description: Debe supervisar regularmente el espacio en disco disponible para que todos los equipos de Report Server sigan funcionando al nivel más alto posible.
title: Monitorización del espacio en disco
uuid: 590c8239-d20e-470e-b633-7785b75daaa6
exl-id: 0debd601-494f-4d4e-9452-c4d32678dc95
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Monitorización del espacio en disco{#monitoring-disk-space}

Debe supervisar regularmente el espacio en disco disponible para que todos los equipos de Report Server sigan funcionando al nivel más alto posible.

Cada máquina [!DNL Report Server] almacena los siguientes tipos de datos:

* Datos del sistema operativo
* Datos de informes
* Datos del sistema

>[!NOTE]
>
>Los consultores de Adobe pueden evaluar su situación de uso para ayudarlo a proyectar la cantidad de almacenamiento de datos que su aplicación de software de Adobe genera y requiere. Para solicitar dicha evaluación, póngase en contacto con los servicios de consultoría de Adobe.

* [Monitorización del espacio de datos del informe](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-ad0a63f3a6824e68acd675da0b6c5c23)
* [Copia de seguridad del sistema operativo, los informes y los datos del sistema](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-b5efb132ca5d4ee69a8608f9b4ab245b)

## Monitorización del espacio de datos del informe {#section-ad0a63f3a6824e68acd675da0b6c5c23}

**Frecuencia recomendada:** cada 5-10 minutos

Asegúrese de proporcionar suficiente espacio en disco para acomodar los informes en la carpeta [!DNL Reports] dentro del directorio de instalación [!DNL Report].

## Copia de seguridad del sistema operativo, los informes y los datos del sistema {#section-b5efb132ca5d4ee69a8608f9b4ab245b}

**Frecuencia recomendada:** Diario

Los datos de informes, sistemas y sistemas operativos deben ser respaldados de forma regular y diligente utilizando los sistemas normales de backup y recuperación ante desastres de su empresa.
