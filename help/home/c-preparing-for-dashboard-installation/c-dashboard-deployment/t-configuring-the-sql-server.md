---
description: Antes de que el tablero pueda funcionar, debe permitirle el acceso a SQL Server.
solution: Analytics
title: Configuración de SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de SQL Server{#configuring-the-sql-server}

Antes de que el tablero pueda funcionar, debe permitirle el acceso a SQL Server.

1. Abra SQL Management Studio como administrador.
1. Agregue un nuevo inicio de sesión haciendo clic con el botón secundario **[!UICONTROL Logins]** y seleccionando **[!UICONTROL New Login]**.
1. Introduzca el nombre de identidad completo del grupo de aplicaciones.

   De forma predeterminada, la identidad del grupo de aplicaciones recibe el nombre del grupo de aplicaciones. Si elige `dashboard`, se le asignará un nombre a la identidad `IIS AppPool\dashboard`. 1. Seleccione **[!UICONTROL Server Roles]** y compruebe la **[!UICONTROL dbcreator]** función.
1. Click **[!UICONTROL OK]** to add the new user.
