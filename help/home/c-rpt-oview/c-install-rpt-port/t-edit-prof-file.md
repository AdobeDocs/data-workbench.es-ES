---
description: Para especificar los perfiles que desea que estén disponibles en el portal de informes, debe configurar el archivo profiles.xml.
title: Edición del archivo Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Edición del archivo Profiles.xml{#edit-the-profiles-xml-file}

{{eol}}

Para especificar los perfiles que desea que estén disponibles en el portal de informes, debe configurar el archivo profiles.xml.

La variable [!DNL profiles.xml] reside en la carpeta que ha designado para la salida. De forma predeterminada, reside en la carpeta \*PortalName*\PortalFiles\Output .

**Para agregar nombres de perfil al archivo profiles.xml**

1. En el equipo en el que se está ejecutando IIS, abra el [!DNL profiles.xml] en un editor de texto como Bloc de notas.
1. Agregar un elemento de perfil y una etiqueta para cada [!DNL Profile] en su portal, como en el siguiente ejemplo:

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
