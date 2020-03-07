---
description: Puede visualizar datos de varios perfiles en un solo tablero.
solution: Analytics
title: Selecciones entre perfiles
topic: Data workbench
uuid: e9377bcf-8de9-4952-a81a-863216f25fb7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Selecciones entre perfiles{#cross-profile-selections}

Puede visualizar datos de varios perfiles en un solo tablero.

En algunos casos, las selecciones de una visualización también se pueden aplicar a visualizaciones de otro perfil. Por ejemplo, si crea visualizaciones a partir de un perfil **[!UICONTROL Call Center]** y un **[!UICONTROL Website Traffic]** perfil en un tablero, puede seleccionar un mes objetivo para que los datos de todas las visualizaciones se segmenten simultáneamente en ese mes, a pesar de ser conjuntos de datos completamente diferentes.

Cuando existen visualizaciones de varios perfiles en un tablero, puede realizar una selección en una visualización si la dimensión de la visualización también existe en todos los demás perfiles representados en la pantalla. Sin embargo, las selecciones se desactivarán si no se encuentra una dimensión globalmente en todas las demás visualizaciones de la pantalla y los usuarios verán un **[!UICONTROL Selections Disabled]** mensaje.

![](assets/selection_disabled.png)

>[!NOTE]
>
>Aunque las dimensiones pueden compartir el mismo nombre en varios perfiles, es posible que no tengan el mismo significado. Es importante investigar cada dimensión para determinar si es apropiado utilizarla para realizar selecciones en varios perfiles.

