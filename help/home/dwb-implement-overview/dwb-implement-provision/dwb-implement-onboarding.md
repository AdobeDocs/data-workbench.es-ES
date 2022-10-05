---
description: Siga estos pasos para iniciar el proceso de incorporación para la Data Workbench de Adobe (DWB), un componente de Adobe Analytics Premium (AAP).
title: Instrucciones básicas de integración para los servicios administrados de DWB
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Instrucciones básicas de integración para los servicios administrados de DWB{#basic-onboarding-instructions-for-dwb-managed-services}

{{eol}}

Siga estos pasos para iniciar el proceso de incorporación para la Data Workbench de Adobe (DWB), un componente de Adobe Analytics Premium (AAP).

Estas instrucciones de incorporación están destinadas a los clientes que implementan la Data Workbench con un único grupo de informes mediante servicios administrados por Adobe sin servicios de consultoría. Si es un nuevo cliente de AAP que implementa DWB, el equipo de incorporación de Adobe será su contacto inicial. Si actualiza desde Adobe Analytics Standard o desde una versión anterior de DWB, le ayudará un gestor de éxito de los clientes de Adobe.

## Información de incorporación: Lo que necesitamos de ti {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe se pondrá en contacto con usted para:

* Identifique a un usuario principal para que DWB genere un certificado específicamente para ese usuario en el directorio de red. El usuario principal también actuará como la persona de punto para interactuar con el Servicio de atención al cliente de Adobe.
* Identifique el grupo de informes que se cargará en DWB.

Los equipos de marketing digital de Adobe tomarán su información para crear perfiles, establecer cuentas y enviar un archivo de configuración para DWB.

**Tareas de incorporación de Adobe**

* El Servicio de atención al cliente de Adobe crea una cuenta con licencia de DWB. El Servicio de atención al cliente de Adobe genera un certificado DWB para el usuario principal.
* El Servicio de atención al cliente de Adobe define el usuario principal como un &quot;usuario admitido&quot;, la persona identificada para las llamadas admitidas y la resolución de problemas.
* El Servicio de atención al cliente de Adobe carga el paquete de software en el portal de software y licencias de DWB (perfil SoftDocs/Software and Docs) para descargarlo en su organización.
* El equipo de TechOps de Adobe prepara los entornos de producción y desarrollo y sus perfiles (por contrato) para DWB.
* El equipo de TechOps de Adobe configura fuentes de datos y scripts de administración de perfiles.
* El equipo de TechOps de Adobe crea y envía el archivo de configuración de DWB (Insight.cfg) al equipo de incorporación de Adobe responsable de las tareas de integración asociadas con su organización.

Después de personalizar las fuentes de datos y de generar credenciales, certificados y una configuración de perfil, el Servicio de atención al cliente de Adobe enviará el archivo de configuración y las credenciales para dar el siguiente paso.

## Acceso a los archivos de instalación personalizados {#section-26962bf57fef435dbd1c5486d4b6f688}

Recibirá estos archivos de configuración del Servicio de atención al cliente de Adobe para instalar la estación de trabajo de DWB en su equipo cliente.

* Su archivo de configuración personalizado de DWB (Insight.cfg)

   Este archivo de configuración en el equipo cliente incluirá conexiones a los servidores DWB administrados.

* Credenciales de inicio de sesión para el portal de licencias para descargar el asistente de configuración de DWB y el certificado requerido (archivo .pem) con el nombre del usuario principal.

**Descargar archivos de configuración adicionales**

1. Vaya a: license.visualsciences.com para descargar el certificado de licencia y el ejecutable del Asistente para configuración de DWB.
1. Introduzca su organización (Nombre de cuenta), el nombre del usuario principal y la contraseña que recibió del Servicio de atención al cliente de Adobe y, a continuación, haga clic en iniciar sesión.

   >[!NOTE]
   >
   >Es posible que el explorador le pida que presente un certificado digital en este momento. Si es así, haga clic en Cancelar para cerrar el cuadro de diálogo.

1. Busque el certificado emitido para la instancia de Data Workbench de Adobe (`<PrimaryUser>`.pem) en la sección Descargas y descargue.
1. Busque el instalador del cliente estándar en la sección Descargas para descargar el asistente de configuración de DWB (archivo InsightSetup-x.xx.exe).
1. Después de recibir y descargar archivos del Servicio de atención al cliente de Adobe, ejecute el Asistente para configuración de DWB para instalar el software de la estación de trabajo en el equipo cliente.

>[!NOTE]
El Asistente de configuración de DWB lo guiará a través de la instalación de la estación de trabajo cliente de DWB y ayudará a localizar Insight.cfg y `<PrimaryUser>`archivos .pem para colocarlos en las carpetas requeridas. El archivo Insight.cfg reside con el archivo Insight.exe en la estación de trabajo cliente instalada. La variable `<PrimaryUser>`El archivo .pem reside en la carpeta Certificados con el archivo trust_ca_cert.pem. Todos los archivos de certificado y configuración deben estar presentes para que DWB funcione.

Para obtener más información, consulte la [Asistente de configuración de DWB](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html).

## Conexión a los servidores DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Sus servidores administrados se identifican en el archivo Insight.cfg que recibe del Servicio de atención al cliente de Adobe y reside en su estación de trabajo cliente. Adobe TechOps configurará sus servidores y el Servicio de atención al cliente de Adobe agregará referencias a estos servidores y perfiles administrados al archivo Insight.cfg antes de enviárselo. (Se completará la configuración de conexiones al servidor en el paso 12 de la documentación del Asistente para la configuración de DWB).

>[!NOTE]
En el espacio de trabajo Configuración de Workstation en la estación de trabajo cliente DWB, podrá ver sus servidores y perfiles conectados.

**Adobe Managed Services**

・ TechOps de Adobe administra la infraestructura, que incluye la red, el centro de datos, los servidores y el almacenamiento de información. La supervisión de la infraestructura y la respuesta a las alertas se realizan las 24 horas del día, los 7 días de la semana para las alertas que requieran acciones de TechOps. Para otras alertas, TechOps notificará al Servicio de atención al cliente de Adobe que se coordine con usted.

・ TechOps de Adobe realizará actualizaciones de mantenimiento y firmware para sus servidores administrados. Para el mantenimiento que cause downtime, recibirá notificaciones de ventana de mantenimiento del Servicio de atención al cliente con al menos dos semanas de anticipación. Los TechOps de Adobe abordarán las necesidades inmediatas lo antes posible. La notificación dependerá de la urgencia y se resolverá una vez que se conozca la programación.

・ Adobe TechOps configura una tarea programada para administrar automáticamente los datos. Los datos de fuentes de Analytics se mueven a DWB para su procesamiento y transformación todas las noches a partir de las 21:00, hora del grupo de informes.

・ Adobe TechOps procesará otros servicios administrados de Adobe, como backups de datos, cuentas FTP, archiving de datos y transferencia de datos cuando sea necesario.

・ Adobe TechOps configurará el clúster de producción principal para que contenga tres meses de datos móviles que se restablecerán y reprocesarán mensualmente. Las actualizaciones de las búsquedas (Geografía, DeviceAtlas, Clasificaciones estándar) también se producirán como parte de la tarea de reprocesamiento. De forma predeterminada, la tarea se ejecuta el primer viernes de cada mes. Si es necesario, el Servicio de atención al cliente puede modificar la programación.

Para obtener más información, póngase en contacto con [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
