---
description: Nuevas funciones y correcciones en la Data Workbench 6.73.
title: Notas de la versión de Data Workbench 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 26%

---

# Notas de la versión de Data Workbench 6.73{#data-workbench-release-notes}

Nuevas funciones y correcciones en la Data Workbench 6.73.

## Correcciones {#section-160baf6ea04c45a993777ee4260691ed}

* Se ha corregido un problema del área de trabajo que causaba que los usuarios no pudieran firmar contenido en algunos hardwares de alta resolución y altos PPI.
* Se ha corregido un problema en el servidor en el que faltaba Correo electrónico en los nombres de archivo al usar el inicio de sesión de IMS.
* Se ha actualizado OpenSSL a la versión 1.1.0h, que incluye varias correcciones de vulnerabilidad y nuevos cifrados SSL.
* Se han actualizado las bibliotecas de código abierto enumeradas a continuación a las últimas versiones estables

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Se ha agregado un registro de errores para los casos en los que el número de filas de los archivos de la búsqueda supera el máximo admitido, que es de 357 913 908 filas.

## Problema conocido {#section-f2cb932f6225457a872fb916a78df89a}

* La versión 6.73 de la estación de trabajo de Data Workbench no se conecta a las versiones 6.61 y anteriores de los Servidores de Data Workbench. El motivo es que las versiones anteriores de los servidores utilizan una forma débil de cifrados no compatibles con la versión 6.73. Para habilitar la compatibilidad con versiones anteriores

   1. Anule la lista de cifrados SSL predeterminados en el servidor con una lista de cifrados segura compatible con OpenSSL versión 1.0.1h. Para anular, añada la clave &quot;Cifradores SSL&quot; en los archivos &quot;Communications.cfg&quot; disponibles en los directorios &quot;Componentes&quot; y &quot;Componentes para servidores de procesamiento&quot;. Por ejemplo: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Asegúrese de que la clave se coloca en el mismo nivel que el puerto SSL. Para obtener más información, consulte [Configuración de comunicaciones](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Coloque el último archivo trust_ca_cert.pem en el servidor 6.61 y en servidores anteriores. Esta configuración se aplica a todas las versiones de Workstation 6.7x.

Consulte [notas de versiones archivadas](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) para ver las Datas Workbench 5.3 a 5.52.
