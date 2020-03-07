---
description: El paso final es ejecutar el tablero por primera vez para permitirle inicializarlo.
solution: Analytics
title: Inicialización del tablero
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inicialización del tablero{#initializing-the-dashboard}

El paso final es ejecutar el tablero por primera vez para permitirle inicializarlo.

1. Abra un navegador web e introduzca la URL en el sitio recientemente implementado (por ejemplo, http://localhost/dashboard).
1. La conexión por primera vez configurará las tablas de la base de datos, por lo que puede experimentar un ligero retraso.
1. Las credenciales de inicio de sesión iniciales son:

* **[!UICONTROL Username]**: admin
* **[!UICONTROL Password]**: password

1. En el primer inicio de sesión, vaya a **[!UICONTROL User]** > **[!UICONTROL Account Settings]** y seleccione **[!UICONTROL Change Password]** para cambiar la contraseña de administrador.
>La instalación del tablero ya se ha completado. Si aún no lo ha hecho, siga las instrucciones detalladas en >
><!-->
>Preparación del trabajo de datos>
>-->
>nch de esta guía para configurar la comunicación con los servidores del área de trabajo de datos y para administrar usuarios y grupos. >
>>[!NOTE]
>>
>>Los registros de errores y auditoría del tablero se encuentran en el [!DNL logs] directorio dentro de la ruta de instalación.
>[!NOTE]
Si necesita cambiar la identidad del grupo de aplicaciones a una cuenta diferente, asegúrese de conceder acceso a la base de datos y dar a la identidad acceso de lectura y escritura a la carpeta de la ruta de instalación en la [!DNL logs] carpeta.
>[!NOTE]
Si alguna vez necesita cambiar la cadena de conexión de la base de datos, simplemente edite el valor usando el **[!UICONTROL IIS Management Console]**.
>
>
>
