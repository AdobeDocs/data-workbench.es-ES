---
description: Nuevas funciones, correcciones y problemas conocidos en la Data Workbench 6.7.
title: Notas de la versión de Data Workbench 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 34%

---

# Notas de la versión de Data Workbench 6.7{#data-workbench-release-notes}

Nuevas funciones, correcciones y problemas conocidos en la Data Workbench 6.7.

## Notas de la versión de Data Workbench 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Nuevas funciones, correcciones y problemas conocidos en la Data Workbench 6.7.

## Nuevas funciones de la versión 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Nuevo modelo de autenticación para la estación de trabajo del Data Workbench (integración con IMS)**

Ahora, la estación de trabajo del Data Workbench admite la autenticación de usuarios mediante nombres de usuario y contraseñas. Con este nuevo método, los administradores pueden crear y gestionar sus propias cuentas de usuario, lo que elimina la necesidad de ponerse en contacto con el servicio de atención al cliente.

Para obtener más información, consulte [ Autoaprovisionamiento de usuarios](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html).

**Búsqueda de archivos planos**

Ahora, la estación de trabajo del Data Workbench admite la autenticación de usuarios mediante nombres de usuario y contraseñas. Con este nuevo método, los administradores pueden crear y gestionar sus propias cuentas de usuario, lo que elimina la necesidad de ponerse en contacto con el servicio de atención al cliente.

Antes, la búsqueda de archivos planos cargaba todo el archivo en búferes en memoria, lo que sobrecargaba el uso de la memoria y ocasionaba problemas de rendimiento para otros subsistemas. Ahora, es posible asignar y almacenar en caché los archivos en la memoria en Windows, lo que optimiza el uso de memoria al establecer *Memory Mapped Lookup Files* en  true  en [!DNL MemorySettings.cfg].

Para obtener más información, consulte [ Autoaprovisionamiento de usuarios](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html).

**Uso de memoria**

Ahora se puede deshabilitar el uso de grandes páginas al establecer *Use Large Pages* en false en [!DNL MemorySettings.cfg]. Consulte [ Supervisión del uso de la memoria ](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) para obtener más información.

**Cifrados de seguridad**

Se ha añadido compatibilidad con ECDHE y DHE.

Compatibilidad con Email en [!DNL User List.cfg]

Se agregó compatibilidad con el atributo Correo electrónico en [!DNL User List.cfg]. Para obtener más información, consulte [Administración de usuarios de los miembros del grupo](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html).

**Menú Ayuda**

Ahora, en el menú Ayuda se muestra un acceso directo al directorio de certificados abiertos.

**`TargetBulkUpload`exportar**

Se proporcionarán direcciones URL al final del archivo de seguimiento de la exportación y el archivo `targetbulkuploadexportname.log.completed`  para efectuar un seguimiento del registro de lotes atascados.

Se ha proporcionado un nuevo archivo, [!DNL TargetBulkUpload.cfg] , para configurar el intervalo de tiempo de espera máximo (en minutos). El archivo se encuentra en [!DNL Server\Admin\Export\].

## Correcciones {#section-160baf6ea04c45a993777ee4260691ed}

* Se ha corregido un problema en el cual la dimensión Pulsación de campaña mostraba valores inflados.
* Se ha corregido un problema con la generación de archivos de Excel desde el servidor de informes.
* El cifrado RC4 ahora está desactivado de forma predeterminada.
* Se ha corregido un problema que hacía que la estación de trabajo de Data Workbench se bloqueara al agregar un elemento de dimensión a una tabla de leyenda de valores.
* Se ha corregido un problema con la Data Workbench a AAM exportaciones que estaba causando tiempos de espera.
* Se ha corregido un problema que hacía que la estación de trabajo de la Data Workbench se bloqueara cuando un usuario sin un nivel de acceso suficiente guardaba el espacio de trabajo en Servidor.
* Se ha corregido un problema con el formato de fecha en [!DNL report.cfg], que era incorrecto o no estaba localizado.
* Se ha corregido un problema por el que las filas de productos y móviles de la fuente AVRO mostraban información confusa.
* Se ha corregido un problema que impedía ordenar archivos `*.1cd` y `*.1ad` en [!DNL order.txt].

* La opción Enviar al servidor se ha deshabilitado para el algoritmo de Maximización de expectativas al ejecutar la agrupación en clúster.
* Se ha corregido un problema con el ejecutable `TargetBulkUpload` que se demoraba y no se ejecutaba completamente.

## Problemas conocidos {#section-d76322bdac5043f087ab303dc68b8fff}

* Al cerrar la sesión, se limpia el archivo [!DNL user cache.db].
* No se admiten las direcciones de correo electrónico de usuario IMS que contienen caracteres &quot;+&quot; o &quot;%&quot;.
* El usuario no puede cerrar la sesión durante un error en el estado de la conexión. Como solución alternativa, cierre la sesión en modo sin conexión.
* La ventana de inicio de sesión de IMS no se procesa correctamente en algunos hardware con alta resolución y altos PPI. Para solucionarlo, haga clic con el botón derecho en [!DNL Insight.exe] y vaya a **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**, y marque la casilla **[!UICONTROL Override high DPI scaling behavior]**.

## Requisitos de actualización  {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Actualice [!DNL trust_ca_cert.pem] en los servidores de Insight que forman parte del paquete de compilación.
1. Actualice el certificado del servidor y del servidor de informes descargando nuevos certificados de [https://aap.adobe.com](https://aap.adobe.com).
1. Para actualizar automáticamente Workstation y Report Server, actualice manualmente [!DNL trust_ca_cert.pem] para ambos descargándolos del servidor de licencias.
1. La función de actualización automática del sensor requiere la versión 5.0 para comunicarse con Insight Server versión 6.70. Además, el [!DNL trust_ca_cert.pem] del sensor debe actualizarse manualmente descargándola del servidor de licencias.

## Actualizaciones del sistema {#section-c1b4949ea734440aa62658ac313261db}

Los nuevos archivos incluyen:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Los archivos actualizados incluyen:

1. [!DNL trust_ca_cert.pem] para todos los componentes.
1. [!DNL Access Control.cfg] para admitir la configuración de IMS.
1. [!DNL Base\Context\meta.cfg] para admitir los formatos Fecha de inicio y Fecha de finalización en  [!DNL Report.cfg]

1. Adiciones a [!DNL Insight.cfg] para admitir el proxy para la autenticación IMS:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Consulte [notas de versiones archivadas](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) para ver las Datas Workbench 5.3 a 5.52.
