---
description: La interfaz Estado detallado del área de trabajo de datos resulta útil para solucionar errores u otros problemas con el servidor del área de trabajo de datos y los equipos del servidor de informes que son clientes del servidor del área de trabajo de datos.
solution: Analytics
title: Visualización del estado del servidor de informes
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualización del estado del servidor de informes{#displaying-report-server-status}

La interfaz Estado detallado del área de trabajo de datos resulta útil para solucionar errores u otros problemas con el servidor del área de trabajo de datos y los equipos del servidor de informes que son clientes del servidor del área de trabajo de datos.

Para ver el estado del informe en la [!DNL Master Server Detailed Status] interfaz, debe agregar un servidor de estado del informe al [!DNL Servers] vector en el archivo [!DNL Communications.cfg] del servidor del área de trabajo de datos. El siguiente procedimiento describe cómo agregar el servidor de estado de informes al [!DNL Communications.cfg] archivo:

Para obtener más información sobre [!DNL Detailed Status] las interfaces, consulte el capítulo Interfaces administrativas de la Guía *del usuario de Área de trabajo de* datos.

**Para agregar un[!DNL Report Status Server]**

1. Vaya a la carpeta Componentes del directorio en el que instaló el servidor del área de trabajo de datos (InsightServer64.exe).

   Ejemplo: [!DNL C:\Adobe\Server\Components]
1. Abra [!DNL Communications.cfg] en un editor de texto como Bloc de notas.
1. Localice el [!DNL Servers] vector y agregue el servidor de estado de informes a este vector como se resalta en el siguiente fragmento de archivo.

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

1. Actualice el recuento de elementos del [!DNL Servers] vector (es decir, incremente el valor de los elementos en uno) tal como se resaltó en el fragmento de archivo en el paso anterior.
1. Guarde el archivo.
