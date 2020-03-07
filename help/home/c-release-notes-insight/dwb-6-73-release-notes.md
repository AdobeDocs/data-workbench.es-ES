---
description: Nuevas funciones y correcciones en Área de trabajo de datos 6.73.
title: Notas de la versión de Área de trabajo de datos 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.73 Release Notes{#data-workbench-release-notes}

Nuevas funciones y correcciones en Área de trabajo de datos 6.73.

## Data Workbench 6.73 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Nuevas funciones y correcciones en Área de trabajo de datos 6.73.

## Correcciones {#section-160baf6ea04c45a993777ee4260691ed}

* Se ha corregido un problema del área de trabajo que causaba que los usuarios no pudieran firmar contenido en algunos hardwares de alta resolución y altos PPI.
* Se ha corregido un problema en el servidor por el que faltaba Correo electrónico en los nombres de archivo de archivado al utilizar el inicio de sesión de IMS.
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

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* La estación de trabajo de área de trabajo de datos versión 6.73 no se conecta a los servidores de área de trabajo de datos versión 6.61 o posterior. El motivo es que las versiones anteriores del servidor utilizan una forma débil de cifrado no admitida en la versión 6.73. Para habilitar la compatibilidad con versiones anteriores

   1. Anule la lista de filtros SSL predeterminados en el servidor con una lista de cifrado fuerte admitida por OpenSSL versión 1.0.1h. Para omitir, agregue la clave &quot;Cifradores SSL&quot; en los archivos &quot;Communications.cfg&quot; disponibles en los directorios &quot;Componentes&quot; y &quot;Componentes para servidores de procesamiento&quot;. Por ejemplo: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Asegúrese de que la clave se encuentra en el mismo nivel que el puerto SSL. Para obtener más información, consulte Configuración de [comunicaciones](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Coloque el último archivo trust_ca_cert.pem en los servidores del servidor 6.61 y anteriores. Esta configuración se aplica a todas las versiones de Workstation 6.7x.

Consulte las notas [archivadas de la versión](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) de Área de trabajo de datos 5.3 a 5.52.
