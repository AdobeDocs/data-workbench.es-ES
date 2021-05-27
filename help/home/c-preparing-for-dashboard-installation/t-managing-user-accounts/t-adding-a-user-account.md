---
description: Añadir una cuenta de usuario
title: Añadir una cuenta de usuario
uuid: c322eeaa-a3f4-41e8-b38c-dd892ec29a87
exl-id: c99f3189-4d89-443a-be5b-84352c4ec6e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# Añadir una cuenta de usuario{#adding-a-user-account}

1. Haga clic en **[!UICONTROL Add User]** para que aparezca el mensaje **[!UICONTROL New User]**.

   ![](assets/add_user_account.png)

1. Rellene los campos necesarios para completar el formulario.
   1. **[!UICONTROL Username]**: Introduzca el nombre de usuario.
   1. **[!UICONTROL Password]**: Escriba una contraseña de más de 6 caracteres.
   1. **[!UICONTROL Confirm Password]**: Vuelva a introducir la contraseña.
   1. **[!UICONTROL Authentication Method]**: seleccione una opción en la lista desplegable.

      | **Forms** | De forma predeterminada, el panel almacena la cuenta de usuario y se autentica internamente. |
      |---|---|
      | **LDAP** | Seleccione esta opción si el usuario se va a autenticar mediante LDAP. (El usuario ya debe existir en el directorio ). |
      | **Windows** | Seleccione si se va a autenticar al usuario mediante la autenticación de Windows (el usuario debe existir ya en el directorio de Windows). |

1. **[!UICONTROL Assigned Groups]**: Elija entre el grupo Administradores predeterminado y cualquier otro grupo que se haya creado. En este momento no se requiere ningún grupo y la pertenencia al grupo del usuario se puede modificar en cualquier momento.
1. Una vez configurado correctamente el formulario, haga clic en **[!UICONTROL Add User]** para agregar el usuario al sistema.

   Si la operación se ha realizado correctamente, verá un mensaje que indicará que se ha creado el usuario.
