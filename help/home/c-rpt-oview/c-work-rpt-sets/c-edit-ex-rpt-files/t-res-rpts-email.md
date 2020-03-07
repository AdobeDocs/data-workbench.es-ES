---
description: Pasos para reenviar informes por correo electrónico.
solution: Analytics
title: Reenvío de informes por correo electrónico
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Reenvío de informes por correo electrónico{#resending-reports-by-email}

Pasos para reenviar informes por correo electrónico.

Si el **[!UICONTROL Allow Report Regeneration]** parámetro del [!DNL Report.cfg] archivo está establecido en [!DNL True], al realizar cambios en un [!DNL Report.cfg] archivo y guardarlo de nuevo en el servidor, el servidor de informes vuelve a generar automáticamente los informes de ese conjunto. No vuelve a enviar los informes por correo electrónico.

1. En la [!DNL Reports] ficha, seleccione la subcarpeta (ficha o subdirectorio desplegable) del conjunto de informes que desee reenviar.
1. Haga clic en **[!UICONTROL Report.cfg]**. Se muestran los parámetros del [!DNL Report.cfg] conjunto de informes.
1. Cambie el **[!UICONTROL Start Date]** parámetro a la hora futura en la que desee que se envíen los informes.
1. Para guardar el archivo, haga clic con el botón derecho **[!UICONTROL Report.cfg (modified)]** en la parte superior de los parámetros y haga clic en **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Los informes de este conjunto se regeneran y se envían por correo electrónico a los destinatarios especificados.
