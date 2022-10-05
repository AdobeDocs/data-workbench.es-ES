---
description: Siga estos pasos para actualizar a la Data Workbench v6.4.
title: Actualizar la versión 6.3 a la versión 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Actualizar la versión 6.3 a la versión 6.4{#upgrading-to}

{{eol}}

Siga estos pasos para actualizar a la Data Workbench v6.4.

## Requisitos de actualización y Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Siga estos requisitos y recomendaciones al actualizar a la Data Workbench 6.4.

>[!IMPORTANT]
>
>Se recomienda utilizar los archivos de configuración predeterminados recién instalados y personalizarlos, en lugar de mover archivos de una instalación anterior, con estas excepciones:

* **Agregar** ***Procesos excluidos*** para *Protección de extremo de MS System Center en servidores Windows 2012* para los siguientes ejecutables:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Esto habilitará derechos de lista de permitidos para estos ejecutables de interfaz.

* **Actualice el *Trust_ca_cert.pem* certificado en los servidores**.
* **Reorganización de perfiles de atribución**.

   * La variable *Atribución* se cambió el nombre de la carpeta a ***Atribución - Premium*** (se encuentra en la instalación predeterminada en *Perfiles*\*Atribución - Premium*).

   * La variable *Premium* se eliminó el perfil y el espacio de trabajo se movió al nuevo ***Atribución - Premium*** carpeta.

* **Actualizar *Attribution-Premium* configuración**. Si tiene perfiles personalizados con ajustes de parámetros que anulan el valor predeterminado *Adobe SC* perfil, debe actualizar los campos personalizados en estos archivos de configuración:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Debido a esta reorganización, deseará eliminar la *Atribución* y *Premium* carpetas de la instalación del servidor.

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

* **Actualizar archivos Meta.cfg personalizados** (si es necesario).

   La variable **[!DNL Meta.cfg]** archivos en **[!DNL Base\Context and AdobeSC\Context]** las carpetas se han actualizado en esta versión.

   Si anula la variable **meta.cfg** durante la instalación, la copia de perfil debe actualizarse con estos parámetros y la variable **vector de metadatos** introducido correctamente:

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

* **Definir permisos del servidor de informes** para generar informes de Microsoft Excel en servidores Windows 2012.

   1. Establezca el permiso de la carpeta raíz (**[!DNL E:\ReportServer\]**) a *Todos = control total*.

   1. Cree las carpetas siguientes con los permisos adecuados:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Si ejecuta el Servidor de informes en Windows Server 2012, necesita tener instalado Windows Server 2012 R2.

   1. Asigne &quot;SYSTEM&quot; como propietario de estas carpetas.

* **Agregue fuentes al servidor de informes.** En el **[!DNL ReportServer.cfg]**añadir estas fuentes (para todos los idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Actualice su versión de Microsoft Excel ** (si es necesario).

   Con el lanzamiento de la Data Workbench 6.4, se ha interrumpido la compatibilidad con Excel 2007. Además, como la Data Workbench solo se ejecuta en Microsoft Windows para la arquitectura de 64 bits, se recomienda instalar también una versión de 64 bits de Microsoft Excel.

* **Arquitectura de 64 bits** necesario para la instalación de Workstation (Client).
* **Ejecutar el Asistente para configuración de Workstation**.

   Instale la nueva versión de la estación de trabajo (cliente) descargando e iniciando ***InsightSetup.exe*** y siga las instrucciones de configuración. El asistente de configuración instalará los archivos en una nueva ubicación de forma predeterminada:

   Los archivos de programa ahora se guardan de forma predeterminada en:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Los archivos de datos (perfiles, certificados, registros de seguimiento y archivos de usuario) ahora se guardan de forma predeterminada en:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Añadir fuentes a la estación de trabajo**.

   En el **[!DNL Insight.cfg]** , añada estas fuentes (para todos los idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
