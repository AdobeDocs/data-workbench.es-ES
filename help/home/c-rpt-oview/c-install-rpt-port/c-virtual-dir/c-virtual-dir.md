---
description: Para configurar el portal de informes, debe asignar sus archivos de aplicación a directorios virtuales.
title: Asignación de páginas del portal de informes a los directorios virtuales
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# Asignación de páginas del portal de informes a los directorios virtuales{#map-the-report-portal-pages-to-virtual-directories}

{{eol}}

Para configurar el portal de informes, debe asignar sus archivos de aplicación a directorios virtuales.

Un directorio virtual define la dirección que los clientes del explorador utilizan para localizar un recurso físico en el servidor de aplicaciones IIS. Para acceder a [!DNL Report Portal], los clientes dirigen sus exploradores al directorio virtual que usted asigna al portal.

El nombre del directorio virtual al que se asigna [!DNL Report Portal] debe coincidir con el nombre que utilizó para la carpeta VSVirtualPortalName en el paso 3 de la sección anterior. Por ejemplo, si desea utilizar &quot;Portal&quot; como nombre de su [!DNL Report Portal], debe asignar los archivos del portal a un directorio virtual denominado &quot;Portal&quot;. El siguiente ejemplo muestra el URI que los clientes usarían para acceder a un [!DNL Report Portal] asignado al directorio virtual [!DNL VisualReportPortal] en un servidor llamado myWebServer:

[!DNL https://myWebServer/VisualReportPortal]

Los siguientes procedimientos describen cómo asignar [!DNL Report Portal] a un directorio virtual en IIS 5.0, 6.0 y 7.0 o superior.

Siga el conjunto de procedimientos para la versión de IIS que esté utilizando:

* [Asignación del portal de informes a un directorio virtual (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Asignación del portal de informes a un directorio virtual (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Edición del archivo de configuración de sesión](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
