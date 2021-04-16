---
description: Para que el tablero pueda funcionar, debe permitirle acceder a SQL Server.
title: Configuración de SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Configuración de SQL Server{#configuring-the-sql-server}

Para que el tablero pueda funcionar, debe permitirle acceder a SQL Server.

1. Abra SQL Management Studio como administrador.
1. Agregue un nuevo inicio de sesión haciendo clic con el botón derecho en **[!UICONTROL Logins]** y seleccionando **[!UICONTROL New Login]**.
1. Introduzca el nombre de identidad del grupo de aplicaciones completo.

   De forma predeterminada, la identidad del grupo de aplicaciones recibe el nombre del grupo de aplicaciones. Si elige `dashboard`, la identidad se llamará `IIS AppPool\dashboard`. 1. Seleccione **[!UICONTROL Server Roles]** y marque la función **[!UICONTROL dbcreator]**.
1. Haga clic en **[!UICONTROL OK]** para agregar el nuevo usuario.
