---
description: El portal de informes utiliza la información de un archivo de configuración llamado global.asa para inicializar las sesiones de usuario.
solution: Analytics
title: Editar el archivo de configuración de sesión
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar el archivo de configuración de sesión{#edit-the-session-configuration-file}

El portal de informes utiliza la información de un archivo de configuración llamado global.asa para inicializar las sesiones de usuario.

Al instalar [!DNL Report Portal], debe editar este archivo como se indica. El [!DNL global.asa] archivo reside en \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>No cambie ningún otro parámetro en este archivo de configuración.

1. En el equipo en el que se está ejecutando IIS, abra el [!DNL global.asa] archivo en un editor de texto como Bloc de notas.
1. Opcional. Para permitir que los usuarios accedan [!DNL Report Portal] sin autenticación, cambie el valor del parámetro Session(&quot;In&quot;) a true. El valor predeterminado es false, que autentica a todos los usuarios que intentan obtener acceso a él [!DNL Report Portal].
1. Si [!DNL Report Portal] está instalado en una unidad que no sea la unidad C, cambie el valor del parámetro Session(&quot;Drive&quot;) a la ubicación correcta de la unidad.
1. Para el parámetro Session(&quot;DBPath&quot;), cambie el valor para reflejar la ruta a la base de datos que contiene la información necesaria para autenticar a [!DNL Report Portal] los usuarios. No incluya la letra de unidad, pero asegúrese de incluir una barra diagonal final.

   Ejemplo: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Guarde el archivo.
1. Para verificar que los [!DNL Report Portal] archivos se han instalado correctamente y se puede acceder a ellos a través del directorio virtual designado, abra la siguiente página en el explorador:

   http://*YourServerAddress*/*YourPortalName*

   Ejemplo: [!DNL http://localhost/VisualReportPortal]

   Si los [!DNL Report Portal] ASP se han instalado correctamente, debería ver la página de inicio de sesión del portal. Si no ve esta página, compruebe que los ASP estén activados en su IIS y las asignaciones de directorio virtual.

