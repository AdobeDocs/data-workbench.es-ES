---
description: Pasos para reenviar informes por correo electrónico.
title: Reenvío de informes por correo electrónico
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Reenvío de informes por correo electrónico{#resending-reports-by-email}

{{eol}}

Pasos para reenviar informes por correo electrónico.

Si la variable **[!UICONTROL Allow Report Regeneration]** en el [!DNL Report.cfg] está definido como [!DNL True], cuando realice cambios en un [!DNL Report.cfg] y guarde ese archivo en el servidor, Report Server vuelve a generar automáticamente los informes de ese conjunto. No vuelve a enviar los informes por correo electrónico.

1. En el [!DNL Reports] , seleccione la subcarpeta (ficha o subdirectorio desplegable) del conjunto de informes que desea reenviar.
1. Haga clic en **[!UICONTROL Report.cfg]**. Los parámetros de la variable [!DNL Report.cfg] para este conjunto de informes.
1. Cambie el **[!UICONTROL Start Date]** para el momento futuro en el que desea que se envíen los informes.
1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL Report.cfg (modified)]** en la parte superior de los parámetros y haga clic en **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Los informes de este conjunto se regeneran y se reenvían por correo electrónico a los destinatarios especificados.
