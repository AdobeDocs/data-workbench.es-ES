---
description: El producto del panel requiere una licencia proporcionada por Adobe ClientCare.
title: Añadir clave de licencia del panel
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Añadir clave de licencia del panel{#add-dashboard-license-key}

El producto del panel requiere una licencia proporcionada por Adobe ClientCare.

1. Abra **[!UICONTROL SQL Management Studio]** como administrador.
1. Abra la base de datos creada por el panel (por ejemplo, thinclientdb).
1. Haga clic con el botón derecho en la tabla **[!UICONTROL Configuration]** y haga clic en **[!UICONTROL Edit Top 200 Rows]**.
1. Busque el campo **[!UICONTROL licenseKey]** e introduzca la clave proporcionada por Adobe ClientCare en la columna **[!UICONTROL Value]**.
1. Reinicie **[!UICONTROL Application Pool]** en **[!UICONTROL IIS Manager Console]**.
