---
description: Cada ficha o subficha de la superficie de trabajo corresponde a un tipo concreto de información, como Paneles, Actividad, Adquisición, etc.
title: Personalización de una pestaña de superficie de trabajo
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
exl-id: 529c6d8d-fc42-4c2b-a111-b8eea4665d8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 4%

---

# Personalización de una pestaña de superficie de trabajo{#customize-a-worktop-tab}

Cada ficha o subficha de la superficie de trabajo corresponde a un tipo concreto de información, como Paneles, Actividad, Adquisición, etc.

Por ejemplo, la pestaña [!DNL Acquisition] puede contener espacios de trabajo que proporcionen datos sobre dominios de referencia, motores de búsqueda y campañas.

Cada ficha que aparece en [!DNL Worktop] corresponde a una carpeta de la carpeta *nombre del perfil de trabajo*\Workspaces dentro del directorio de instalación de la Data Workbench. El orden de las pestañas en [!DNL Worktop] está controlado por el archivo [!DNL order.txt] en esa misma carpeta. Por ejemplo, si tiene una subcarpeta Acquisition en la carpeta Workspaces y luego agrega Acquisition como primera entrada en el archivo [!DNL order.txt], [!DNL Acquisition] es la primera pestaña en la [!DNL Worktop] y todo lo que hay en esa subcarpeta aparece en la pestaña [!DNL Acquisition].

>[!NOTE]
>
>Para obtener información sobre el uso del archivo [!DNL order.txt] para personalizar el menú de la ventana del espacio de trabajo, consulte [Personalización de menús](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894).
