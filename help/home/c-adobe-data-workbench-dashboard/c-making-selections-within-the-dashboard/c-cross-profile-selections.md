---
description: Puede visualizar datos de varios perfiles en un solo tablero.
title: Selecciones entre perfiles
uuid: e9377bcf-8de9-4952-a81a-863216f25fb7
exl-id: a14400bf-64e3-44be-b9ab-d8a9ded406ae
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%

---

# Selecciones entre perfiles{#cross-profile-selections}

Puede visualizar datos de varios perfiles en un solo tablero.

En algunos casos, las selecciones de una visualización también se pueden aplicar a las visualizaciones de otro perfil. Por ejemplo, si crea visualizaciones a partir de un perfil **[!UICONTROL Call Center]**y un perfil **[!UICONTROL Website Traffic]** en un tablero, puede seleccionar un mes objetivo para que los datos de todas las visualizaciones se segmenten simultáneamente en ese mes, a pesar de ser conjuntos de datos completamente diferentes.

Cuando existen visualizaciones de varios perfiles en un tablero, puede realizar una selección en una visualización si la dimensión de esa visualización también existe en todos los demás perfiles representados en la pantalla. Sin embargo, las selecciones se deshabilitarán si una dimensión no se encuentra globalmente en todas las demás visualizaciones de la pantalla y los usuarios verán un mensaje **[!UICONTROL Selections Disabled]**.

![](assets/selection_disabled.png)

>[!NOTE]
>
>Aunque las dimensiones pueden compartir el mismo nombre en varios perfiles, es posible que no tengan el mismo significado. Es importante investigar cada dimensión para determinar si es apropiado utilizarla para realizar selecciones en varios perfiles.
