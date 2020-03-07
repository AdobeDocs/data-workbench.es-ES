---
description: Utilice Workstation para administrar los usuarios de Área de trabajo de datos.
title: Autoaprovisionamiento de usuarios
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Autoaprovisionamiento de usuarios{#self-provisioning-of-users}

Utilice Workstation para administrar los usuarios de Área de trabajo de datos.

Puede utilizar Workstation para conectarse al servidor de Área de trabajo de datos configurando el certificado requerido de Adobe. Este certificado ayuda tanto en la comunicación SSL como en la autorización para utilizar los recursos y características con licencia. En la autenticación basada en certificados, debe adquirir y configurar varios certificados para utilizar la estación de trabajo en varios equipos. Además, Adobe administra las asignaciones y los derechos de los usuarios y debe ponerse en contacto con Adobe para obtener nuevos certificados o revocación de certificados.

A partir de DWB 6.7, la estación de trabajo admite la autenticación de usuarios mediante el nombre de usuario y la contraseña.

Aunque la autenticación/autorización basada en certificados seguirá funcionando para su configuración, se recomienda migrar a la autenticación basada en credenciales más reciente. En el nuevo enfoque, los usuarios de Workstation se autentican a sí mismos a través del Sistema de administración de identidades de Adobe (IMS). Antes de poder utilizar la estación de trabajo, el administrador de la organización debe darle acceso a las funciones a través de la Consola [de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) administración.

El nuevo modelo de autenticación y aprovisionamiento de usuarios ayuda a:

* Autoaprovisionamiento de usuarios y grupos a través de la Consola de administración. No es necesario que se ponga en contacto con Adobe para agregar, quitar o modificar derechos de licencia para los usuarios.
* Acceso a Workstation desde varios equipos sin perder el estado de configuración mediante el inicio de sesión con credenciales. La caché local se elimina al cerrar sesión, el perfil actual se cierra y el perfil de configuración se activa.

## Primeros pasos

Antes de comenzar, póngase en contacto con Adobe para agregar su organización en Admin Console. Según los servicios que haya adquirido, Adobe le proporcionará la organización. Por ejemplo: las organizaciones pueden tener acceso al servicio de atribución o a las compilaciones beta, o a ambas. Una vez configurada una organización, el administrador de la organización puede agregar usuarios y grupos. Consulte [Administrar usuarios y productos](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) de Experience Cloud en Experience Cloud para obtener más información. El administrador de la organización también puede configurar restricciones de uso para distintos usuarios en función de sus funciones. Por ejemplo, los usuarios que no sean de la versión preliminar no necesitan acceder a las compilaciones beta.

Cada usuario aprovisionado agregado a esta organización a través de la Consola de administración tendrá acceso para utilizar el Área de trabajo de datos. Los subservicios solo se pueden habilitar o deshabilitar para cada usuario en función del acceso al producto. Cuando se actualiza un usuario de un certificado a IMS, todos los datos locales se copian en el nuevo directorio de usuarios de IMS.

>[!NOTE]
>
>Una sesión dura 6 horas en el servidor y 23 horas en el cliente, a menos que se actualice el autentificador de acceso. Cuando se actualiza el token, puede usar Client sin volver a iniciar sesión.

El administrador debe crear al menos una configuración de nivel de producto en Admin Console antes de dar acceso a cualquier usuario.

El indicador booleano **Usar IMS** se puede agregar a [!DNL Insight.cfg] la opción de reserva al modo de certificado. Para obtener información sobre la configuración del control de acceso para los usuarios de IMS, consulte [Actualización del archivo](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)de control de acceso.

## Resolución de conflictos

Cuando un usuario ha iniciado sesión en varios equipos con la misma cuenta de IMS en el mismo perfil y está en modo sin conexión en uno de los equipos, `.conflict` puede que se forme un formulario y que una ventana emergente le informe. Esto ocurre cuando hay una diferencia en el contenido con cualquier archivo (espacios de trabajo, dimensiones, filtros, etc.) sincronizado en ambos equipos en [!DNL User\Profile\] en servidor y cliente. Se creará una copia de seguridad en el `.conflict` archivo y no se perderán datos. Un indicador booleano en [!DNL Insight.cfg] le permite deshabilitar esta ventana emergente de conflicto.

Marca: Notificaciones de conflictos

Esto es aplicable a espacios de trabajo, métricas, dimensiones, etc. en la carpeta de usuario.
