---
description: El portal de informes utiliza la información de un archivo de configuración llamado global.asa para inicializar las sesiones de usuario.
title: Edición del archivo de configuración de sesión
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Edición del archivo de configuración de sesión{#edit-the-session-configuration-file}

{{eol}}

El portal de informes utiliza la información de un archivo de configuración llamado global.asa para inicializar las sesiones de usuario.

Al instalar [!DNL Report Portal], debe editar este archivo como se indica. La variable [!DNL global.asa] reside en la carpeta \*PortalName*\PortalASP\.

>[!NOTE]
>
>No cambie ningún otro parámetro en este archivo de configuración.

1. En el equipo en el que se está ejecutando IIS, abra el [!DNL global.asa] en un editor de texto como Bloc de notas.
1. Opcional. Para permitir el acceso de los usuarios [!DNL Report Portal] sin autenticación, cambie el valor del parámetro Session(&quot;In&quot;) a true. El valor predeterminado es false, que autentica a todos los usuarios que intentan acceder a [!DNL Report Portal].
1. Si su [!DNL Report Portal] se instala en una unidad distinta de la unidad C, cambie el valor del parámetro Session(&quot;Drive&quot;) a la ubicación correcta de la unidad.
1. Para el parámetro Session(&quot;DBPath&quot;), cambie el valor para reflejar la ruta a la base de datos que contiene la información necesaria para autenticarse [!DNL Report Portal] usuarios. No incluya la letra de unidad, pero asegúrese de incluir una barra diagonal.

   Ejemplo: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Guarde el archivo.
1. Para verificar que la variable [!DNL Report Portal] Los archivos se han instalado correctamente y se puede acceder a ellos a través del directorio virtual designado, abra la siguiente página en el explorador:

   https://*YourServerAddress*/*YourPortalName*

   Ejemplo: [!DNL https://localhost/VisualReportPortal]

   Si la variable [!DNL Report Portal] Los ASP se han instalado correctamente, debería ver la página de inicio de sesión del portal. Si no ve esta página, verifique que los ASP estén habilitados en su IIS y verifique dos veces las asignaciones de directorios virtuales.
