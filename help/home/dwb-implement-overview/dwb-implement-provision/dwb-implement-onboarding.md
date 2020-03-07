---
description: Siga estos pasos para iniciar el proceso de integración de Adobe Data Workbench (DWB), un componente de Adobe Analytics Premium (AAP).
title: Instrucciones básicas de integración para los servicios administrados de DWB
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Instrucciones básicas de integración para los servicios administrados de DWB{#basic-onboarding-instructions-for-dwb-managed-services}

Siga estos pasos para iniciar el proceso de integración de Adobe Data Workbench (DWB), un componente de Adobe Analytics Premium (AAP).

Estas instrucciones de incorporación están destinadas a los clientes que implementan Área de trabajo de datos con un único grupo de informes que utiliza los servicios gestionados de Adobe sin servicios de consultoría. Si es un nuevo cliente de AAP que implementa DWB, el equipo de integración de Adobe será su contacto inicial. Si actualiza desde el estándar de Adobe Analytics o desde una versión anterior de DWB, un administrador de éxito de clientes de Adobe le ayudará.

## Información de integración: Lo que necesitamos de usted {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe se pondrá en contacto con usted para:

* Identifique un usuario principal para DWB a fin de generar un certificado específico para ese usuario en el directorio de red. El usuario principal también actuará como la persona que interactúe con el Servicio de atención al cliente de Adobe.
* Identifique el grupo de informes que se va a cargar en DWB.

A continuación, los equipos de Adobe Digital Marketing tomarán su información para crear perfiles, configurar cuentas y enviar un archivo de configuración para DWB.

**Tareas de integración de Adobe**

* El Servicio de atención al cliente de Adobe crea una cuenta con licencia de DWB. El Servicio de atención al cliente de Adobe genera un certificado DWB para el usuario principal.
* El Servicio de atención al cliente de Adobe define al usuario principal como un &quot;usuario de asistencia técnica&quot;, la persona identificada para las llamadas admitidas y la resolución de problemas.
* El Servicio de atención al cliente de Adobe carga el paquete de software en el portal de software y licencia de DWB (perfil SoftDocs/Software and Docs) para descargarlo en su organización.
* El equipo de Adobe TechOps prepara los entornos de producción y desarrollo y sus perfiles (por contrato) para DWB.
* El equipo de Adobe TechOps configura fuentes de datos y scripts de administración de perfiles.
* El equipo de TechOps de Adobe crea y envía el archivo de configuración de DWB (Insight.cfg) al equipo de integración de Adobe responsable de las tareas de integración asociadas con su organización.

Tras personalizar las fuentes de datos y generar credenciales, certificados y una configuración de perfil, el Servicio de atención al cliente de Adobe enviará el archivo de configuración y las credenciales para dar el siguiente paso.

## Acceso a los archivos de instalación personalizados {#section-26962bf57fef435dbd1c5486d4b6f688}

Recibirá estos archivos de configuración del Servicio de atención al cliente de Adobe para instalar la estación de trabajo DWB en el equipo cliente.

* Su archivo de configuración DWB personalizado (Insight.cfg)

   Este archivo de configuración del equipo cliente incluirá conexiones a los servidores DWB administrados.

* Las credenciales de inicio de sesión del portal de licencias para descargar el Asistente para la instalación de DWB y el certificado requerido (archivo .pem) con el nombre del usuario principal.

**Descargar archivos de configuración adicionales**

1. Vaya a: license.visualsciences.com para descargar el certificado de licencia y el ejecutable del Asistente para la instalación de DWB.
1. Introduzca su organización (Nombre de cuenta), el nombre del usuario principal y la contraseña que ha recibido del Servicio de atención al cliente de Adobe y, a continuación, haga clic en iniciar sesión.

   >[!NOTE]
   >
   >Es posible que el explorador le pida que presente un certificado digital en este momento. Si es así, haga clic en Cancelar para cerrar el cuadro de diálogo.

1. Busque el certificado emitido para su instancia de Adobe Data Workbench (`<PrimaryUser>`.pem) en la sección Descargas y descargue.
1. Busque el instalador del cliente estándar en la sección de descargas para descargar el Asistente para la instalación de DWB (archivo InsightSetup-x.xx.exe).
1. Después de recibir y descargar archivos del Servicio de atención al cliente de Adobe, ejecute el Asistente para la instalación de DWB para instalar el software de la estación de trabajo en el equipo cliente.

>[!NOTE]
El Asistente para la instalación de DWB lo guiará por la instalación de la estación de trabajo cliente de DWB y le ayudará a localizar los archivos Insight.cfg y `<PrimaryUser>`.pem para colocarlos en las carpetas requeridas. El archivo Insight.cfg reside con el archivo Insight.exe en la estación de trabajo cliente instalada. El archivo `<PrimaryUser>`.pem reside en la carpeta Certificates con el archivo trust_ca_cert.pem. Todos los archivos de certificado y configuración deben estar presentes para que DWB funcione.

Para obtener más información, consulte el Asistente para la configuración de [DWB](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html).

## Conexión a los servidores DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Los servidores administrados se identifican en el archivo Insight.cfg que recibe del Servicio de atención al cliente de Adobe y que reside en la estación de trabajo del cliente. Adobe TechOps configurará sus servidores y el Servicio de atención al cliente de Adobe agregará referencias a estos servidores y perfiles administrados al archivo Insight.cfg antes de enviárselo. (Se completará la configuración de conexiones con el servidor en el paso 12 de la documentación del Asistente para configuración de DWB).

>[!NOTE]
En el espacio de trabajo Configuración de estación de trabajo de la estación de trabajo cliente DWB, podrá ver los servidores y perfiles conectados.

**Adobe Managed Services**

・ Adobe TechOps administra la infraestructura, incluyendo la red, el centro de datos, los servidores y el almacenamiento. La supervisión de la infraestructura y la respuesta a las alertas se realizan las 24 horas del día, los 7 días de la semana para las alertas que requieren la acción de TechOps. Para otras alertas, TechOps notificará al Servicio de atención al cliente de Adobe que debe coordinarse con usted.

・ Adobe TechOps realizará actualizaciones de mantenimiento y firmware para sus servidores administrados. Para el mantenimiento que causa downtime, recibirá notificaciones de la ventana de mantenimiento del Servicio de atención al cliente con al menos dos semanas de anticipación. Adobe TechOps atenderá las necesidades inmediatas lo antes posible. La notificación dependerá de la urgencia y se resolverá una vez que se conozca el calendario.

・ Adobe TechOps configura una tarea programada para administrar automáticamente los datos. Los datos de fuentes analíticas se mueven a DWB para su procesamiento y transformación todas las tardes a partir de las 21:00, hora del grupo de informes.

・ Adobe TechOps procesará otros servicios gestionados de Adobe, como copias de seguridad de datos, cuentas de FTP, archivo de datos y transferencia de datos cuando sea necesario.

・ Adobe TechOps configurará el clúster de producción principal para que contenga tres meses de datos móviles que se restablecerán y se reprocesarán mensualmente. Las actualizaciones de las búsquedas (Geografía, DeviceAtlas, Clasificaciones estándar) también se producirán como parte de la tarea de reprocesamiento. De forma predeterminada, la tarea se ejecuta el primer viernes de cada mes. Si es necesario, el Servicio de atención al cliente puede modificar la programación.

Para obtener más información, póngase en contacto con el Servicio de atención al cliente de [Adobe](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
