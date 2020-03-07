---
description: Pasos para editar cuentas de usuario existentes.
solution: Analytics
title: Edición de usuarios existentes
topic: Data workbench
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Edición de usuarios existentes{#editing-existing-users}

Pasos para editar cuentas de usuario existentes.

1. En la [!DNL Report Portal], haga clic en la **[!UICONTROL Admin]** ficha. Aparece la [!DNL Admin] página.

   ![](assets/report_admintag2.png)

1. Haga clic en la carta que representa la primera letra del nombre de la cuenta que desee editar. Por ejemplo, si desea editar la cuenta &quot;Marketing&quot;, haga clic en la letra &quot;M&quot;.

   Se muestra una lista de los nombres de cuenta que comienzan con esa letra.

1. Seleccione el nombre de la cuenta que desee editar y haga clic en el **[!UICONTROL select]** botón. Aparece la [!DNL Edit Account Info] página.

   ![Información sobre los pasos](assets/rptPort_scrn_AdminTab_editUser.png)

1. Cambie solo los campos de esta página que deban actualizarse. La tabla siguiente proporciona descripciones de cada uno de estos campos:

   | En este campo . . . | Especifique . . . |
   |---|---|
   | email | La dirección de correo electrónico del usuario. |
   | contraseña antigua | La contraseña actual, que es necesaria para continuar al editar una cuenta de administrador o al restablecer la contraseña para una cuenta que no es de administrador. |
   | nueva contraseña | La nueva contraseña que debe proporcionar el usuario al iniciar sesión en [!DNL Report Portal]. |
   | confirmar contraseña | La nueva contraseña que debe proporcionar el usuario al iniciar sesión en [!DNL Report Portal]. |
   | acceso a perfiles | Los perfiles a los que se permite acceder este usuario (por ejemplo, ProductSales). Para permitir el acceso a varios perfiles, separe los nombres por comas. Si el usuario tiene permiso para acceder a todos los perfiles asociados con [!DNL Report Portal], escriba &quot;ALL&quot;. |
   | acceso a ficha | Las fichas a las que este usuario puede acceder (por ejemplo, [!DNL Admin]). Para permitir el acceso a varias fichas, separe los nombres por comas. Si el usuario puede acceder a todas las fichas del [!DNL Report Portal], escriba &quot;ALL&quot;. Este campo, junto con el campo de tipo de cuenta, es muy útil para definir derechos de acceso de grupo. |
   | tipo de cuenta | Indica si esta cuenta es para un individuo o un grupo. Las cuentas individuales permiten a los usuarios restablecer sus contraseñas, mientras que los grupos no. Un administrador es la única persona capaz de restablecer la contraseña de una cuenta de grupo. |
   | status | Indica si esta cuenta está activa o inactiva. El valor predeterminado está activo. Para desactivar una cuenta de usuario, seleccione **[!UICONTROL inactive]**. |
   | admin | Si se debe permitir que este usuario cree, actualice y elimine cuentas de usuario, así como editar las notas asociadas con cada informe. La configuración predeterminada es false. Para convertir este usuario en administrador, seleccione true. |
   | fecha de caducidad | La fecha, en formato MM/DD/AAAA, hasta la cual se permite el uso de este usuario [!DNL Report Portal]. |

1. Haga clic en **[!UICONTROL update]**.
