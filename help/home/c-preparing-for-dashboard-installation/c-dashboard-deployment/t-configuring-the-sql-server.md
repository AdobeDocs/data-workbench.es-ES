---
description: Para que el tablero pueda funcionar, debe permitirle acceder a SQL Server.
title: Configuración de SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Configuración de SQL Server{#configuring-the-sql-server}

{{eol}}

Para que el tablero pueda funcionar, debe permitirle acceder a SQL Server.

1. Abra SQL Management Studio como administrador.
1. Agregue un nuevo inicio de sesión haciendo clic con el botón derecho **[!UICONTROL Logins]** y seleccionar **[!UICONTROL New Login]**.
1. Introduzca el nombre de identidad del grupo de aplicaciones completo.

   De forma predeterminada, la identidad del grupo de aplicaciones recibe el nombre del grupo de aplicaciones. Si elige `dashboard`, se llamará a la identidad `IIS AppPool\dashboard`. 1. Seleccione **[!UICONTROL Server Roles]** y compruebe el **[!UICONTROL dbcreator]** función.
1. Haga clic en **[!UICONTROL OK]** para agregar el nuevo usuario.
