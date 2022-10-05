---
description: Cada ficha o subficha de la superficie de trabajo corresponde a un tipo concreto de información, como Paneles, Actividad, Adquisición, etc.
title: Personalización de una pestaña de superficie de trabajo
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
exl-id: 529c6d8d-fc42-4c2b-a111-b8eea4665d8b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 4%

---

# Personalización de una pestaña de superficie de trabajo{#customize-a-worktop-tab}

{{eol}}

Cada ficha o subficha de la superficie de trabajo corresponde a un tipo concreto de información, como Paneles, Actividad, Adquisición, etc.

Por ejemplo, la variable [!DNL Acquisition] puede contener espacios de trabajo que proporcionen datos sobre dominios de referencia, motores de búsqueda y campañas.

Cada ficha que aparece en la [!DNL Worktop] corresponde a una carpeta de *nombre del perfil de trabajo*\Workspaces carpeta dentro del directorio de instalación de la Data Workbench. El orden de las pestañas en la [!DNL Worktop] está controlado por [!DNL order.txt] en la misma carpeta. Por ejemplo, si tiene una subcarpeta de adquisición en la carpeta Workspaces y, a continuación, agrega Adquisición como la primera entrada en la [!DNL order.txt] archivo, [!DNL Acquisition] es la primera pestaña de la [!DNL Worktop] y todo lo que se encuentra en esa subcarpeta se muestra en la [!DNL Acquisition] pestaña .

>[!NOTE]
>
>Para obtener información sobre cómo usar la variable [!DNL order.txt] para personalizar el menú de la ventana del espacio de trabajo, consulte [Personalización de menús](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894).
