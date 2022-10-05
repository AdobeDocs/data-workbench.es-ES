---
description: El producto del panel requiere una licencia proporcionada por Adobe ClientCare.
title: Añadir clave de licencia del panel
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Añadir clave de licencia del panel{#add-dashboard-license-key}

{{eol}}

El producto del panel requiere una licencia proporcionada por Adobe ClientCare.

1. Apertura **[!UICONTROL SQL Management Studio]** como administrador.
1. Abra la base de datos creada por el panel (por ejemplo, thinclientdb).
1. Haga clic con el botón derecho en el **[!UICONTROL Configuration]** tabla y haga clic en **[!UICONTROL Edit Top 200 Rows]**.
1. Busque la **[!UICONTROL licenseKey]** e introduzca la clave proporcionada por Adobe ClientCare en la variable **[!UICONTROL Value]** para abrir el Navegador.
1. Reinicie el **[!UICONTROL Application Pool]** en el **[!UICONTROL IIS Manager Console]**.
