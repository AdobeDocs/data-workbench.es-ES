---
description: El paso final es ejecutar el tablero por primera vez para permitirle que se inicialice.
title: Inicialización del panel
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# Inicialización del panel{#initializing-the-dashboard}

{{eol}}

El paso final es ejecutar el tablero por primera vez para permitirle que se inicialice.

1. Abra un explorador web e introduzca la dirección URL del sitio recién implementado (por ejemplo, https://localhost/dashboard).
1. La conexión por primera vez configurará las tablas de la base de datos, por lo que puede experimentar un ligero retraso.
1. Las credenciales de inicio de sesión inicial son:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. En su primer inicio de sesión, vaya a **[!UICONTROL User]** > **[!UICONTROL Account Settings]** y seleccione **[!UICONTROL Change Password]** para cambiar la contraseña de administrador.

La instalación del panel ya ha finalizado. Si aún no lo ha hecho, utilice las instrucciones detalladas en la sección Preparación de la Data Workbench de esta guía para configurar la comunicación con los servidores de Data Workbench y administrar usuarios y grupos.

>[!NOTE]
>
>Los registros de error y auditoría del panel se encuentran en la [!DNL logs] dentro de la ruta de instalación.

>[!NOTE]
>
>Si necesita cambiar la identidad del grupo de aplicaciones a una cuenta diferente, asegúrese de conceder acceso a la base de datos y dar a la identidad acceso de lectura y escritura a la [!DNL logs] en la ruta de instalación.

>[!NOTE]
>
>Si alguna vez necesita cambiar la cadena de conexión de la base de datos, edite el valor utilizando la variable **[!UICONTROL IIS Management Console]**.
