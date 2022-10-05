---
description: Si Insight no puede conectarse a los servidores de Insight mediante la configuración especificada, aparecerá un nodo rojo en el Administrador de servidores.
title: Resolución de problemas de conexión
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Resolución de problemas de conexión{#connection-troubleshooting}

{{eol}}

Si Insight no puede conectarse a los servidores de Insight mediante la configuración especificada, aparecerá un nodo rojo en el Administrador de servidores.

Esto puede ocurrir, por ejemplo, si configura la conexión incorrectamente o no tiene permiso para ver la variable [!DNL Insight Server’s] estado.

**Para determinar por qué Insight no puede establecer una conexión**

1. Haga clic con el botón derecho en el nodo de servidor rojo y, a continuación, haga clic en **[!UICONTROL Detailed Status]**.
1. En el [!DNL Detailed Status] interfaz, haga clic en **[!UICONTROL Network Connections]** y expanda los elementos numerados. La variable [!DNL Status] proporciona información sobre por qué Insight no puede establecer una conexión:

   * Un código de estado en los años 500 indica un error de configuración.
   * El código de estado 403 normalmente indica que no tiene permiso para ver el estado del servidor.

Puede ver información de estado adicional en la [!DNL insight.log] archivo. Este archivo de registro se encuentra en la variable [!DNL Trace] en el directorio donde instaló Insight. Para ver el archivo, ábralo en un editor de texto como el Bloc de notas.

Si necesita asistencia para comprender la información de la sección [!DNL insight.log] , póngase en contacto con el administrador del sistema. Si necesita más ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe.
