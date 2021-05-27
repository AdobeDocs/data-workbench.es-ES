---
description: Los usuarios deben tener una cuenta válida y proporcionar un nombre de cuenta y una contraseña cuando accedan al portal de informes.
title: Definición de cuentas adicionales
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Definición de cuentas adicionales

Los usuarios deben tener una cuenta válida y proporcionar un nombre de cuenta y una contraseña cuando accedan al portal de informes.

De forma predeterminada, la autenticación de usuario está habilitada en [!DNL Report Portal].

La lista de cuentas válidas para [!DNL Report Portal] se mantiene en el archivo de base de datos, [!DNL portal.mdb]. [!DNL Report Portal] se instala con una cuenta con privilegios administrativos:

* Nombre de la cuenta: prueba
* Contraseña: usuario

>[!NOTE]
>
>Por motivos de seguridad, Adobe recomienda cambiar la contraseña de esta cuenta después de instalar [!DNL Report Portal].

Para agregar cuentas de usuario a [!DNL Report Portal] o cambiar información relacionada con cuentas existentes, utilice la pestaña [!DNL Admin] en la interfaz de usuario [!DNL Report Portal].

Cada vez que agrega una cuenta nueva o edita una existente, se envía un correo electrónico de confirmación como se especifica en el archivo [!DNL email.asp] de la carpeta \*PortalName*\PortalASP. Para obtener más información, consulte [Editar el archivo Email.asp](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Para ver los pasos para agregar usuarios adicionales, consulte [Trabajo con cuentas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Opcionalmente, puede deshabilitar la autenticación de usuarios y permitir el acceso anónimo a [!DNL Report Portal]. Para ver los pasos necesarios para ello, consulte la información sobre el parámetro Session(&quot;In&quot;) en [Edit the Session Configuration File](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
