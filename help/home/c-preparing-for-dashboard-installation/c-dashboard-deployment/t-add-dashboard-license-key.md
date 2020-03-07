---
description: El producto de tablero requiere una licencia proporcionada por Adobe ClientCare.
solution: Analytics
title: Agregar clave de licencia del tablero
topic: Data workbench
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Agregar clave de licencia del tablero{#add-dashboard-license-key}

El producto de tablero requiere una licencia proporcionada por Adobe ClientCare.

1. Open **[!UICONTROL SQL Management Studio]** as an Administrator.
1. Abra la base de datos creada por el tablero (por ejemplo, thinclientdb).
1. Haga clic con el botón secundario en la **[!UICONTROL Configuration]** tabla y haga clic en **[!UICONTROL Edit Top 200 Rows]**.
1. Busque el **[!UICONTROL licenseKey]** campo e introduzca la clave proporcionada por Adobe ClientCare en la **[!UICONTROL Value]** columna.
1. Reinicie el **[!UICONTROL Application Pool]** en la **[!UICONTROL IIS Manager Console]**.
