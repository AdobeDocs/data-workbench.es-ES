---
description: Para todos los idiomas, Report Server 6.0 y versiones posteriores requieren el archivo "insight.zbin" copiado en la carpeta raíz del servidor de informes.
title: Actualizar el servidor de informes con un archivo de idioma (archivo .zbin)
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 9%

---

# Actualizar el servidor de informes con un archivo de idioma (archivo .zbin){#update-report-server-with-a-language-file-zbin-file}

Para todos los idiomas, Report Server 6.0 y versiones posteriores requieren el archivo &quot;insight.zbin&quot; copiado en la carpeta raíz del servidor de informes.

Actualice los archivos de idioma del servidor de informes:

1. Agregue el archivo renombrado &quot;insight.zbin&quot; al directorio raíz de ReportServer.
1. El archivo de configuración del servidor de informes (reportserver.cfg) requiere ajustes de fuente para lenguajes de byte doble. Por ejemplo, el chino requiere la adición de fuentes utilizando SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Se debe pasar un parámetro para Report Server 6.0 en la línea de comandos para la localización, por ejemplo:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Si no se especifica una configuración regional, el servidor de informes usará el idioma predeterminado inglés.

   Siga los pasos para iniciar ReportServer como un servicio con los parámetros de configuración regional:

   1. Inicie un símbolo del sistema como administrador.
   1. Vaya a la carpeta de instalación de ReportServer.
   1. Escriba el siguiente comando para iniciar el servicio:

      * Para inglés: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Para chino: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Para verificar si ReportServer se está ejecutando con los parámetros correctos:

   1. Abra el Administrador de servicios de Windows.
   1. Haga clic con el botón derecho en [!DNL Adobe Insight Report Server - Properties].

   La ruta al ejecutable contiene los parámetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
