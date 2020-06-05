---
description: El paso final es ejecutar el panel por primera vez para permitirle inicializarlo.
solution: Analytics
title: Inicialización del Panel
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Inicialización del Panel{#initializing-the-dashboard}

El paso final es ejecutar el panel por primera vez para permitirle inicializarlo.

1. Abra un navegador web e introduzca la URL en el sitio recientemente implementado (por ejemplo, http://localhost/dashboard).
1. La conexión por primera vez configurará las tablas de la base de datos, por lo que puede experimentar un ligero retraso.
1. Las credenciales de inicio de sesión iniciales son:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. En el primer inicio de sesión, vaya a **[!UICONTROL User]** > **[!UICONTROL Account Settings]** y seleccione **[!UICONTROL Change Password]** para cambiar la contraseña del administrador.

La instalación del panel ya ha finalizado. Si aún no lo ha hecho, utilice las instrucciones detalladas en la sección Preparación del área de trabajo de datos de esta guía para configurar la comunicación con los servidores del área de trabajo de datos y administrar usuarios y grupos.

>[!NOTE]
>
>Los registros de errores de Panel y auditoría se encuentran en el [!DNL logs] directorio dentro de la ruta de instalación.

>[!NOTE]
>
>Si necesita cambiar la identidad del grupo de aplicaciones a una cuenta diferente, asegúrese de conceder acceso a la base de datos y dar a la identidad acceso de lectura y escritura a la carpeta de la ruta de instalación en la [!DNL logs] carpeta.

>[!NOTE]
>
>Si alguna vez necesita cambiar la cadena de conexión de la base de datos, simplemente edite el valor usando el **[!UICONTROL IIS Management Console]**.
