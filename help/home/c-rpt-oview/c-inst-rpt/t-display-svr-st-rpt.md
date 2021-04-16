---
description: La interfaz Estado detallado de Data Workbench resulta útil para solucionar errores u otros problemas con los equipos Servidor de Data Workbench y Servidor de informes que son clientes de Data Workbench Server.
title: Visualización del estado del servidor de informes
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Visualización del estado del servidor de informes{#displaying-report-server-status}

La interfaz Estado detallado de Data Workbench resulta útil para solucionar errores u otros problemas con los equipos Servidor de Data Workbench y Servidor de informes que son clientes de Data Workbench Server.

Para ver el estado del informe en la interfaz [!DNL Master Server Detailed Status], debe agregar un servidor de estado de informe al vector [!DNL Servers] en el archivo [!DNL Communications.cfg] del servidor de Data Workbench. El siguiente procedimiento describe cómo agregar el servidor de estado de informes al archivo [!DNL Communications.cfg]:

Para obtener más información sobre las interfaces [!DNL Detailed Status], consulte el capítulo Interfaces administrativas de la *Guía del usuario de la Data Workbench*.

**Para agregar un[!DNL Report Status Server]**

1. Vaya a la carpeta Componentes en el directorio donde instaló el servidor de Data Workbench (InsightServer64.exe).

   Ejemplo: [!DNL C:\Adobe\Server\Components]
1. Abra [!DNL Communications.cfg] en un editor de texto como el Bloc de notas.
1. Busque el vector [!DNL Servers] y añada el servidor de estado de informes a este vector como se indica en el siguiente fragmento de archivo.

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

1. Actualice el recuento de elementos para el vector [!DNL Servers] (es decir, aumente el valor de los elementos en uno) como se resalta en el fragmento de archivo del paso anterior.
1. Guarde el archivo.
