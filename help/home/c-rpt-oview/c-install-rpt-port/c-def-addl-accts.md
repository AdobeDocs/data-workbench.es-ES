---
description: Los usuarios deben tener una cuenta válida y proporcionar un nombre de cuenta y una contraseña cuando accedan al portal de informes.
solution: Analytics
title: Definir cuentas adicionales
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir cuentas adicionales{#define-additional-accounts}

Los usuarios deben tener una cuenta válida y proporcionar un nombre de cuenta y una contraseña cuando accedan al portal de informes.

De forma predeterminada, la autenticación de usuarios está habilitada en [!DNL Report Portal].

La lista de cuentas válidas para [!DNL Report Portal] se mantiene en el archivo de base de datos, [!DNL portal.mdb]. [!DNL Report Portal] se instala con una cuenta con privilegios administrativos:

* Nombre de la cuenta: test
* Contraseña: user

>[!NOTE]
>
>Por motivos de seguridad, Adobe recomienda cambiar la contraseña de esta cuenta después de la instalación [!DNL Report Portal].

Para agregar cuentas de usuario [!DNL Report Portal] o cambiar información relacionada con cuentas existentes, utilice la [!DNL Admin] ficha de la interfaz de [!DNL Report Portal] usuario.

Cada vez que agrega una cuenta nueva o edita una existente, se envía un correo electrónico de confirmación como se especifica en el archivo [!DNL email.asp] de la carpeta \*PortalName*\PortalASP. Para obtener más información, consulte [Editar el archivo](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)Email.asp.

Para ver los pasos para agregar usuarios adicionales, consulte [Uso de cuentas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Opcionalmente, puede desactivar la autenticación de usuarios y permitir el acceso anónimo a [!DNL Report Portal]. Para ver los pasos a seguir, consulte la información sobre el parámetro Session(&quot;In&quot;) en [Editar el archivo](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)de configuración de sesión.

