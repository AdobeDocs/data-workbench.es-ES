---
description: Para especificar los perfiles que desea que estén disponibles en el portal de informes, debe configurar el archivo profiles.xml.
title: Edición del archivo Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Edición del archivo Profiles.xml{#edit-the-profiles-xml-file}

Para especificar los perfiles que desea que estén disponibles en el portal de informes, debe configurar el archivo profiles.xml.

El archivo [!DNL profiles.xml] reside en la carpeta que ha designado para la salida. De forma predeterminada, reside en \*PortalName*\PortalFiles\Output folder.

**Para agregar nombres de perfil al archivo profiles.xml**

1. En el equipo en el que se está ejecutando IIS, abra el archivo [!DNL profiles.xml] en un editor de texto como el Bloc de notas.
1. Agregue un elemento de perfil y una etiqueta para cada [!DNL Profile] en el portal, como en el siguiente ejemplo:

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
