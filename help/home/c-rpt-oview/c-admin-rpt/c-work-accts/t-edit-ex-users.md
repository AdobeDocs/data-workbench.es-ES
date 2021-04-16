---
description: Pasos para editar cuentas de usuario existentes.
title: Edición de usuarios existentes
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# Edición de usuarios existentes{#editing-existing-users}

Pasos para editar cuentas de usuario existentes.

1. En [!DNL Report Portal], haga clic en la pestaña **[!UICONTROL Admin]**. Aparece la página [!DNL Admin].

   ![](assets/report_admintag2.png)

1. Haga clic en la carta que representa la primera letra del nombre de la cuenta que desea editar. Por ejemplo, si desea editar la cuenta &quot;Marketing&quot;, haga clic en la letra &quot;M&quot;.

   Se muestra una lista de los nombres de las cuentas que comienzan por esa carta.

1. Seleccione el nombre de cuenta que desea editar y luego haga clic en el botón **[!UICONTROL select]** . Aparece la página [!DNL Edit Account Info].

   ![Información sobre los pasos](assets/rptPort_scrn_AdminTab_editUser.png)

1. Cambie solo los campos de esta página que deban actualizarse. La tabla siguiente proporciona descripciones de cada uno de estos campos:

   | En este campo . . . | Especifique . . . |
   |---|---|
   | email | La dirección de correo electrónico del usuario. |
   | contraseña antigua | La contraseña actual, que es necesaria para continuar con la edición de una cuenta de administrador o al restablecer la contraseña de una cuenta de no administrador. |
   | nueva contraseña | La nueva contraseña que el usuario debe proporcionar al iniciar sesión en [!DNL Report Portal]. |
   | confirmar contraseña | La nueva contraseña que el usuario debe proporcionar al iniciar sesión en [!DNL Report Portal]. |
   | acceso a perfiles | Los perfiles a los que puede acceder este usuario (por ejemplo, ProductSales). Para permitir el acceso a varios perfiles, separe los nombres por comas. Si el usuario puede acceder a todos los perfiles asociados con [!DNL Report Portal], escriba &quot;ALL&quot;. |
   | acceso a pestañas | Las pestañas a las que puede acceder este usuario (por ejemplo, [!DNL Admin]). Para permitir el acceso a varias pestañas, separe los nombres con comas. Si el usuario puede acceder a todas las pestañas en [!DNL Report Portal], escriba &quot;ALL&quot;. Este campo, junto con el campo de tipo de cuenta, es muy útil para definir los derechos de acceso de grupo. |
   | tipo de cuenta | Si esta cuenta es para un individuo o un grupo. Las cuentas individuales permiten a los usuarios restablecer sus contraseñas, mientras que los grupos no lo hacen. Un administrador es la única persona capaz de restablecer la contraseña de una cuenta de grupo. |
   | status | Indica si esta cuenta está activa o inactiva. El valor predeterminado está activo. Para desactivar una cuenta de usuario, seleccione **[!UICONTROL inactive]**. |
   | admin | Si se permite al usuario crear, actualizar y eliminar cuentas de usuario, así como editar las notas asociadas a cada informe. La configuración predeterminada es false. Para que sea un usuario administrador, seleccione true. |
   | fecha de caducidad | La fecha, en formato MM/DD/AAAA, hasta la cual se permite al usuario utilizar [!DNL Report Portal]. |

1. Haga clic en **[!UICONTROL update]**.
