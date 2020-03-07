---
description: Para conectarse a un servidor del área de trabajo de datos, el servidor de informes debe tener permiso de acceso a dicho servidor.
solution: Analytics
title: Habilitación del acceso al servidor de Área de trabajo de datos
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Habilitación del acceso al servidor de Área de trabajo de datos{#enabling-access-to-the-data-workbench-server}

Para conectarse a un servidor del área de trabajo de datos, el servidor de informes debe tener permiso de acceso a dicho servidor.

Para otorgar acceso a un servidor del área de trabajo de datos, agregue el nombre común del servidor de informes (como se asigna en el certificado digital del servidor de informes) al archivo de control de acceso del servidor.

>[!NOTE]
>
>Cuando se trabaja en un entorno agrupado, el servidor de informes debe configurarse para acceder al servidor maestro del área de trabajo de datos a fin de evitar problemas de sincronización. En el área de trabajo de datos puede ver información sobre los servidores de procesamiento del clúster mediante el elemento de [!DNL Related Servers] menú de la [!DNL Servers Manager]. Para obtener más información sobre el [!DNL Servers Manager], consulte el capítulo Interfaces administrativas de la Guía *del usuario del área de trabajo de* datos.

El siguiente procedimiento describe cómo agregar manualmente el servidor de informes al archivo de control de acceso en un servidor del área de trabajo de datos. Para actualizar el archivo de control de acceso de este modo, debe tener acceso al sistema de archivos en el equipo en el que está instalado el servidor del área de trabajo de datos.

También puede actualizar el archivo de control de acceso del servidor mediante el uso de [!DNL Server Files Manager] en el área de trabajo de datos. Para ello, el cliente del área de trabajo de datos debe tener privilegios administrativos en el servidor.

Para obtener más información sobre el [!DNL Server Files Manager], consulte el capítulo Interfaces administrativas de la Guía *del usuario del área de trabajo de* datos.

**Para configurar el acceso a un servidor del área de trabajo de datos**

1. Vaya a la carpeta Control de acceso del directorio en el que instaló el servidor del área de trabajo de datos (InsightServer64.exe).

   Ejemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra [!DNL Access Control.cfg] en un editor de texto como Bloc de notas.
1. Busque el [!DNL Report Server AccessGroup] y agregue un nombre [!DNL Report Server’s] común a este grupo como se resalta en el siguiente fragmento de archivo. (Escriba el nombre común tal como aparece en el certificado [!DNL Report Server’s] digital).

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
