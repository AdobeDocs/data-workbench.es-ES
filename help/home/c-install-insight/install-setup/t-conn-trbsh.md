---
description: Si Insight no puede conectarse a los servidores de Insight mediante la configuración especificada, aparecerá un nodo rojo en el Administrador de servidores.
title: Resolución de problemas de conexión
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Resolución de problemas de conexión{#connection-troubleshooting}

Si Insight no puede conectarse a los servidores de Insight mediante la configuración especificada, aparecerá un nodo rojo en el Administrador de servidores.

Esto puede ocurrir, por ejemplo, si configura la conexión de forma incorrecta o si no tiene permiso para ver el [!DNL Insight Server’s] estado.

**Para determinar por qué Insight no puede establecer una conexión**

1. Haga clic con el botón secundario en el nodo rojo del servidor y haga clic en **[!UICONTROL Detailed Status]**.
1. En la [!DNL Detailed Status] interfaz, haga clic en **[!UICONTROL Network Connections]** y expanda los elementos numerados. El [!DNL Status] parámetro proporciona información sobre por qué Insight no puede establecer una conexión:

   * Un código de estado en los 500 indica un error de configuración.
   * El código de estado 403 normalmente indica que no tiene permiso para ver el estado del servidor.

Puede ver información de estado adicional en el [!DNL insight.log] archivo. Este archivo de registro se encuentra en la [!DNL Trace] carpeta del directorio donde instaló Insight. Para ver el archivo, ábralo en un editor de texto como Bloc de notas.

Si necesita ayuda para comprender la información del [!DNL insight.log] archivo, póngase en contacto con el administrador del sistema. Si necesita más ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe.
