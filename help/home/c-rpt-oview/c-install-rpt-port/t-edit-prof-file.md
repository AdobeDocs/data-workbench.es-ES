---
description: Para especificar los perfiles que desea que estén disponibles en el portal de informes, debe configurar el archivo profile.xml.
solution: Analytics
title: Editar el archivo Profiles.xml
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar el archivo Profiles.xml{#edit-the-profiles-xml-file}

Para especificar los perfiles que desea que estén disponibles en el portal de informes, debe configurar el archivo profile.xml.

El [!DNL profiles.xml] archivo reside en la carpeta que ha designado para la salida. De forma predeterminada, reside en \*PortalName*\PortalFiles\Output folder.

**Para agregar nombres de perfil al archivo profile.xml**

1. En el equipo en el que se está ejecutando IIS, abra el [!DNL profiles.xml] archivo en un editor de texto como Bloc de notas.
1. Agregue un elemento de perfil y una etiqueta para cada uno [!DNL Profile] de ellos en el portal, como en el siguiente ejemplo:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Guarde y cierre el archivo.
