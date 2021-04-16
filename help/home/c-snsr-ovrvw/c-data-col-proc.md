---
description: Sensor automatiza la adquisición de datos de su canal de Internet eliminando la mayor parte de la mano de obra humana tradicionalmente implicada en la recopilación de datos.
title: ¿Cómo funciona el proceso de recopilación de datos?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# ¿Cómo funciona el proceso de recopilación de datos?{#how-does-the-data-collection-process-work}

Sensor automatiza la adquisición de datos de su canal de Internet eliminando la mayor parte de la mano de obra humana tradicionalmente implicada en la recopilación de datos.

En muchos casos, el uso de [!DNL Sensor] puede simplificar enormemente el proceso de administración de datos.

Los grandes sitios de Internet, extranet e intranet de hoy a menudo se ejecutan en una matriz de servidores web. Los registros y los datos producidos pueden ser muy grandes y engorrosos de administrar. Por ejemplo: si el sitio ejecuta 30 servidores web, normalmente uno de los empleados (o los empleados del proveedor de servicios externalizados) extraerá y consolidará cada archivo de registro en cada uno de los 30 servidores y, a continuación, ejecutará informes sobre ellos. La instalación de [!DNL Sensor] en cada uno de los servidores web automatiza todo este proceso, reduciendo sus gastos y haciendo que los datos estén disponibles en tiempo real.

Para automatizar este proceso, [!DNL Sensor] recopila información sin procesar sobre el tráfico en un sitio web directamente desde cada servidor web. Los datos sin procesar que captura [!DNL Sensor] se denominan datos de evento y son similares al tipo de datos que el servidor web registra en sus archivos de registro.

Para capturar estos datos, la instrumentación dentro de [!DNL Sensor] registra información sobre cada solicitud HTTP que procesa el servidor web. [!DNL Sensor] a continuación, almacena en búfer la información para protegerla contra fallos de red y transmite de forma segura la información mediante HTTP/S a la  [!DNL data workbench server] que especifique.

Una vez que [!DNL data workbench server] recibe los datos, procesa y almacena sus archivos de registro en archivos de formato [!DNL .vsl] altamente comprimidos, lo que le permite mantener fácilmente grandes cantidades de datos en hardware económico.

Para obtener información sobre los campos de datos de evento recopilados por [!DNL Sensor] en los archivos [!DNL .vsl], consulte [Campos de registro de datos de evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
