---
description: Para conectarse a un servidor de Data Workbench, Report Server debe tener permiso para acceder a dicho servidor.
title: Habilitar el acceso al servidor de Data Workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Habilitar el acceso al servidor de Data Workbench{#enabling-access-to-the-data-workbench-server}

Para conectarse a un servidor de Data Workbench, Report Server debe tener permiso para acceder a dicho servidor.

Para conceder acceso a un servidor de Data Workbench, agregue el nombre común del servidor de informes (según se asigna en el certificado digital del servidor de informes) al archivo de control de acceso del servidor.

>[!NOTE]
>
>Cuando se trabaja en un entorno agrupado, Report Server debe configurarse para acceder al servidor maestro de Data Workbench a fin de evitar problemas de sincronización. En Data Workbench puede ver información sobre los servidores de procesamiento del clúster mediante el elemento de menú [!DNL Related Servers] del [!DNL Servers Manager]. Para obtener más información sobre [!DNL Servers Manager], consulte el capítulo Interfaces administrativas de la *Guía del usuario de la Data Workbench*.

En el siguiente procedimiento se describe cómo agregar manualmente el servidor de informes al archivo de control de acceso en un servidor de Data Workbench. Para actualizar el archivo de control de acceso de esta forma, debe tener acceso al sistema de archivos en el equipo en el que esté instalado el servidor de Data Workbench.

También puede actualizar el archivo de control de acceso del servidor utilizando el [!DNL Server Files Manager] en Data Workbench. Para ello, el cliente de Data Workbench debe tener privilegios de administrador en el servidor.

Para obtener más información sobre [!DNL Server Files Manager], consulte el capítulo Interfaces administrativas de la *Guía del usuario de la Data Workbench*.

**Para configurar el acceso a un servidor de Data Workbench**

1. Vaya a la carpeta Control de acceso en el directorio donde instaló el servidor de Data Workbench (InsightServer64.exe).

   Ejemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra [!DNL Access Control.cfg] en un editor de texto como el Bloc de notas.
1. Busque el [!DNL Report Server AccessGroup] y añada el nombre común [!DNL Report Server’s] a este grupo tal como se indica en el siguiente fragmento de archivo. (Escriba el nombre común exactamente como aparece en el certificado digital [!DNL Report Server’s]).

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Guarde el archivo.
