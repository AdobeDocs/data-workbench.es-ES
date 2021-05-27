---
description: Pasos para reenviar informes por correo electrónico.
title: Reenvío de informes por correo electrónico
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Reenvío de informes por correo electrónico{#resending-reports-by-email}

Pasos para reenviar informes por correo electrónico.

Si el parámetro **[!UICONTROL Allow Report Regeneration]** del archivo [!DNL Report.cfg] está establecido en [!DNL True], cuando realice cambios en un archivo [!DNL Report.cfg] y lo vuelva a guardar en el servidor, Report Server volverá a generar automáticamente los informes de ese conjunto. No vuelve a enviar los informes por correo electrónico.

1. En la pestaña [!DNL Reports], seleccione la subcarpeta (pestaña o subdirectorio desplegable) del conjunto de informes que desea reenviar.
1. Haga clic en **[!UICONTROL Report.cfg]**. Se muestran los parámetros de [!DNL Report.cfg] para este conjunto de informes.
1. Cambie el parámetro **[!UICONTROL Start Date]** a la hora futura en la que desea que se envíen los informes.
1. Guarde el archivo haciendo clic con el botón derecho en **[!UICONTROL Report.cfg (modified)]** en la parte superior de los parámetros y haciendo clic en **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Los informes de este conjunto se regeneran y se reenvían por correo electrónico a los destinatarios especificados.
