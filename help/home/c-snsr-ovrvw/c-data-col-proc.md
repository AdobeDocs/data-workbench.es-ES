---
description: Sensor automatiza la adquisición de datos de su canal de Internet eliminando la mayor parte de la mano de obra humana tradicionalmente implicada en la recopilación de datos.
solution: Analytics
title: ¿Cómo funciona el proceso de recopilación de datos?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---


# ¿Cómo funciona el proceso de recopilación de datos?{#how-does-the-data-collection-process-work}

Sensor automatiza la adquisición de datos de su canal de Internet eliminando la mayor parte de la mano de obra humana tradicionalmente implicada en la recopilación de datos.

En muchos casos, el uso [!DNL Sensor] puede simplificar enormemente el proceso de gestión de datos.

Los grandes sitios de Internet, extranet e intranet de hoy en día suelen ejecutarse en una matriz de servidores Web. Los registros y datos producidos pueden ser muy grandes y complicados de administrar. Por ejemplo: si el sitio está ejecutando 30 servidores Web, normalmente uno de los empleados (o empleados de proveedores de servicio externos) extraerá y consolidará cada archivo de registro en cada uno de los 30 servidores y luego ejecutará informes en ellos. La instalación [!DNL Sensor] en cada uno de los servidores Web automatiza todo este proceso, reduciendo los gastos y haciendo que los datos estén disponibles en tiempo real.

Para automatizar este proceso, [!DNL Sensor] recopila información sin procesar sobre el tráfico en un sitio web directamente desde cada servidor web. Los datos sin procesar que [!DNL Sensor] captura se denominan datos de evento y son similares al tipo de datos que el servidor web registra en sus archivos de registro.

Para capturar estos datos, la instrumentación dentro [!DNL Sensor] registra información sobre cada solicitud HTTP que procesa el servidor web. [!DNL Sensor] a continuación almacena en búfer la información para protegerla contra fallos de red y transmite la información de forma segura mediante HTTP/S al [!DNL data workbench server] que especifique.

Después de que el [!DNL data workbench server] usuario recibe los datos, procesa y almacena los archivos de registro en archivos de formato [!DNL .vsl] muy comprimidos, lo que le permite mantener fácilmente grandes cantidades de datos en hardware económico.

Para obtener información sobre los campos de datos de evento recopilados por [!DNL Sensor] en [!DNL .vsl] archivos, consulte Campos [de registro de datos de](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)Evento.
