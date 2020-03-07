---
description: Para todos los idiomas, el servidor de informes 6.0 y posterior requiere que el archivo "insight.zbin" se copie en la carpeta raíz del servidor de informes.
solution: Analytics
title: Actualizar el servidor de informes con un archivo de idioma (archivo .zbin)
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Actualizar el servidor de informes con un archivo de idioma (archivo .zbin){#update-report-server-with-a-language-file-zbin-file}

Para todos los idiomas, el servidor de informes 6.0 y posterior requiere que el archivo &quot;insight.zbin&quot; se copie en la carpeta raíz del servidor de informes.

Actualice los archivos de idioma del servidor de informes:

1. Agregue el archivo renombrado &quot;insight.zbin&quot; al directorio raíz de ReportServer.
1. El archivo de configuración del servidor de informes (reportserver.cfg) requiere la configuración de fuentes para los idiomas de doble byte. Por ejemplo, el chino requiere la adición de fuentes mediante SimSun:

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
   >Si no se especifica una configuración regional, el servidor de informes elige de forma predeterminada el inglés.

   Siga los pasos para iniciar ReportServer como un servicio con los parámetros de configuración regional:

   1. Inicie un símbolo del sistema como administrador.
   1. Vaya a la carpeta de instalación de ReportServer.
   1. Escriba el siguiente comando para iniciar el servicio:

      * En inglés: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Para chino: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Para verificar si ReportServer se está ejecutando con los parámetros correctos:

   1. Abra el Administrador de servicios de Windows.
   1. Haga clic con el botón secundario [!DNL Adobe Insight Report Server - Properties].
   La ruta de acceso al archivo ejecutable contendrá los parámetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

