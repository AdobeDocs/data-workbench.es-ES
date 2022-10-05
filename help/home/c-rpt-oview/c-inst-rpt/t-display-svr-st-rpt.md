---
description: La interfaz Estado detallado de Data Workbench resulta útil para solucionar errores u otros problemas con los equipos Servidor de Data Workbench y Servidor de informes que son clientes de Data Workbench Server.
title: Visualización del estado del servidor de informes
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Visualización del estado del servidor de informes{#displaying-report-server-status}

{{eol}}

La interfaz Estado detallado de Data Workbench resulta útil para solucionar errores u otros problemas con los equipos Servidor de Data Workbench y Servidor de informes que son clientes de Data Workbench Server.

Para ver el estado del informe en la variable [!DNL Master Server Detailed Status] , debe agregar un servidor de estado de informes al [!DNL Servers] vector en el servidor de Data Workbench [!DNL Communications.cfg] archivo. El siguiente procedimiento describe cómo agregar el servidor de estado de informes al [!DNL Communications.cfg] archivo:

Para obtener más información, consulte [!DNL Detailed Status] , consulte el capítulo Interfaces administrativas de la sección *Guía del usuario de Data Workbench*.

**Para agregar un[!DNL Report Status Server]**

1. Vaya a la carpeta Componentes en el directorio donde instaló el servidor de Data Workbench (InsightServer64.exe).

   Ejemplo: [!DNL C:\Adobe\Server\Components]
1. Apertura [!DNL Communications.cfg] en un editor de texto como el Bloc de notas.
1. Busque la variable [!DNL Servers] y agregue el servidor de estado de informes a este vector como se indica en el siguiente fragmento de archivo.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Actualizar el recuento de elementos para la variable [!DNL Servers] vectorial (es decir, aumente el valor de los elementos en uno) tal y como se indica en el fragmento de archivo del paso anterior.
1. Guarde el archivo.
