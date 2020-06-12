---
description: Siga estos pasos para actualizar a Área de trabajo de datos v6.4.
title: Actualización de 6.3 a 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---


# Upgrading 6.3 to 6.4{#upgrading-to}

Siga estos pasos para actualizar a Área de trabajo de datos v6.4.

## Requisitos y recomendaciones de actualización {#section-8704a9ac358246cd81233dd0982d534f}

Siga estos requisitos y recomendaciones al actualizar a Área de trabajo de datos 6.4.

>[!IMPORTANT]
>
>Se recomienda utilizar los archivos de configuración predeterminados recién instalados y personalizarlos, en lugar de mover archivos de una instalación anterior, con las siguientes excepciones:

* **Añadir** procesos ****** excluidos para la protección de extremo de System Center de *MS en servidores* Windows 2012 para los siguientes ejecutables:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Esto habilitará los derechos de lista permitida para estos ejecutables de interfaz.

* **Actualice el certificado *Trust_ca_cert.pem*en los servidores**.
* **Reorganización de los Perfiles** de atribución.

   * Se cambió el nombre de la carpeta *Atribución* a ***Atribución - Premium*** (se encuentra en la instalación predeterminada en *Perfiles*\*Atribución - Premium*).

   * Se eliminó el perfil *Premium* y el espacio de trabajo se movió a la nueva carpeta ***Atribución - Premium*** .

* **Actualice la configuración *de Atribución-Premium***. Si tiene perfiles personalizados con parámetros que anulan el perfil predeterminado de *Adobe SC* , deberá actualizar los campos personalizados en estos archivos de configuración:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Debido a esta reorganización, querrá quitar las carpetas antiguas *Atribución* y *Premium* de la instalación del servidor.

   **Cambiar esta configuración**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   a esta configuración:

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **Actualice los archivos** Meta.cfg personalizados (si es necesario).

   Los **[!DNL Meta.cfg]** archivos de **[!DNL Base\Context and AdobeSC\Context]** las carpetas se han actualizado en esta versión.

   Si anula el archivo **meta.cfg** durante la instalación, la copia de perfil debe actualizarse con estos parámetros y el vector **de** metadatos especificado correctamente:

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **Establezca los permisos** del servidor de informes para generar informes de Microsoft Excel en servidores de Windows 2012.

   1. Establezca el permiso de la carpeta raíz (**[!DNL E:\ReportServer\]**) en *Todos = control* total.

   1. Cree las siguientes carpetas con los permisos correspondientes:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Si está ejecutando el servidor de informes en Windows Server 2012, debe tener instalado Windows Server 2012 R2.

   1. Asigne &quot;SYSTEM&quot; como propietario de estas carpetas.

* **Añada las fuentes al servidor de informes.** En el archivo **[!DNL ReportServer.cfg]***, agregue estas fuentes (para todos los idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Actualice su versión de Microsoft Excel ** (si es necesario).

   Con el lanzamiento de Área de trabajo de datos 6.4, la compatibilidad con Excel 2007 se ha interrumpido. Además, dado que Área de trabajo de datos solo se ejecuta en Microsoft Windows para la arquitectura de 64 bits, se recomienda instalar una versión de 64 bits de Microsoft Excel.

* **Se requiere una arquitectura** de 64 bits para la instalación de Workstation (cliente).
* **Ejecute el Asistente** de configuración de estación de trabajo.

   Instale la nueva versión de la estación de trabajo (cliente) descargando e iniciando ***InsightSetup.exe*** y siguiendo las instrucciones de configuración. El asistente de configuración instalará los archivos en una nueva ubicación de forma predeterminada:

   Los archivos Programa ahora se guardan de forma predeterminada en:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Los archivos de datos (perfiles, certificados, registros de seguimiento y archivos de usuario) ahora se guardan de forma predeterminada en:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Añada las fuentes a la estación de trabajo**.

   En el **[!DNL Insight.cfg]** archivo, agregue estas fuentes (para todos los idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

