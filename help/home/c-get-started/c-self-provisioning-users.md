---
description: Utilice Workstation para administrar los usuarios de su Data Workbench.
title: Autoaprovisionamiento de usuarios
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Autoaprovisionamiento de usuarios{#self-provisioning-of-users}

{{eol}}

Utilice Workstation para administrar los usuarios de su Data Workbench.

Puede utilizar Workstation para conectarse al Servidor de Data Workbench configurando el certificado requerido desde el Adobe. Este certificado ayuda tanto en la comunicación SSL como en la autorización para utilizar los recursos y las funciones con licencia. En la autenticación basada en certificados, debe adquirir y configurar varios certificados para usar la estación de trabajo en varios equipos. Además, el aprovisionamiento de usuarios y las autorizaciones se administran mediante Adobe y debe ponerse en contacto con el Adobe para obtener nuevos certificados o revocación de certificados.

A partir de DWB 6.7, la estación de trabajo admite la autenticación de usuarios mediante el nombre de usuario y la contraseña.

Aunque la autenticación/autorización basada en certificados seguirá funcionando para su configuración, se recomienda migrar a la autenticación basada en credenciales más reciente. En el enfoque más reciente, los usuarios de la estación de trabajo se autentican mediante el sistema Identity Management de Adobe (IMS). Antes de poder utilizar la estación de trabajo, es necesario que se les conceda acceso a las funciones a través de la variable [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es) por el administrador de la organización.

El nuevo modelo de autenticación y aprovisionamiento de usuarios ayuda en:

* Autoaprovisionamiento de usuarios y grupos a través del Admin Console. No es necesario ponerse en contacto con Adobe para agregar, quitar o modificar derechos de licencia para usuarios.
* Acceder a la estación de trabajo desde varios equipos sin perder el estado de configuración al iniciar sesión con credenciales. La caché local se elimina al cerrar la sesión, el perfil actual se cierra y el perfil de configuración se activa.

## Primeros pasos

Antes de empezar, póngase en contacto con Adobe para agregar su organización al Admin Console. En función de los servicios que haya adquirido, los Adobes le proporcionarán la organización. Por ejemplo, las organizaciones pueden tener acceso al servicio de atribución o a las compilaciones beta, o a ambas. Una vez configurada la organización, el administrador de la organización puede agregar usuarios y grupos. Consulte [Administración de usuarios y productos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) en Experience Cloud para obtener más información. El administrador de la organización también puede configurar restricciones de uso para distintos usuarios según sus funciones. Por ejemplo, los usuarios que no sean versiones anteriores no necesitan acceder a las versiones beta.

Cada usuario aprovisionado añadido a esta organización a través del Admin Console tendrá acceso para utilizar la Data Workbench . Los subservicios solo se pueden habilitar o deshabilitar para cada usuario en función del acceso a su producto. Cuando se actualiza un usuario de un certificado a IMS, todos los datos locales se copian en el nuevo directorio de usuario de IMS.

>[!NOTE]
>
>Una sesión dura 6 horas en el servidor y 23 horas en el cliente a menos que se actualice el token de acceso. Cuando se actualiza el token, puede utilizar Client sin iniciar sesión de nuevo.

El administrador debe crear al menos una configuración de nivel de producto en el Admin Console antes de conceder acceso a cualquier usuario.

El indicador booleano **Usar IMS** se puede agregar a [!DNL Insight.cfg] para volver al modo de certificado. Para obtener información sobre la configuración del control de acceso para los usuarios de IMS, consulte [Actualización del archivo de control de acceso](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Resolución de conflictos

Cuando un usuario ha iniciado sesión en varios equipos con la misma cuenta de IMS en el mismo perfil y está en modo sin conexión en uno de los equipos, una `.conflict` y una ventana emergente le informará. Esto ocurre cuando hay una diferencia en el contenido con cualquier archivo (espacios de trabajo, dimensiones, filtros, etc.) sincronizados en ambos equipos en [!DNL User\Profile\] en servidor y cliente . Se creará una copia de seguridad en el `.conflict` y no se perderán datos. Un indicador booleano en [!DNL Insight.cfg] le permite desactivar esta ventana emergente de conflicto.

Indicador: Notificaciones de conflictos

Esto es aplicable a espacios de trabajo, métricas, dimensiones, etc. en la carpeta de usuario.
