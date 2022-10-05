---
description: Sensor automatiza la adquisición de datos de su canal de Internet eliminando la mayor parte de la mano de obra humana tradicionalmente implicada en la recopilación de datos.
title: ¿Cómo funciona el proceso de recopilación de datos?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# ¿Cómo funciona el proceso de recopilación de datos?{#how-does-the-data-collection-process-work}

{{eol}}

Sensor automatiza la adquisición de datos de su canal de Internet eliminando la mayor parte de la mano de obra humana tradicionalmente implicada en la recopilación de datos.

En muchos casos, usar [!DNL Sensor] puede simplificar enormemente el proceso de administración de datos.

Los grandes sitios de Internet, extranet e intranet de hoy a menudo se ejecutan en una matriz de servidores web. Los registros y los datos producidos pueden ser muy grandes y engorrosos de administrar. Por ejemplo: si el sitio ejecuta 30 servidores web, normalmente uno de los empleados (o los empleados del proveedor de servicios externalizados) extraerá y consolidará cada archivo de registro en cada uno de los 30 servidores y, a continuación, ejecutará informes sobre ellos. Instalación [!DNL Sensor] en cada uno de los servidores web automatiza todo este proceso, reduciendo sus gastos y haciendo que los datos estén disponibles en tiempo real.

Para automatizar este proceso, [!DNL Sensor] recopila información sin procesar sobre el tráfico en un sitio web directamente desde cada servidor web. Los datos sin procesar que [!DNL Sensor] captura se denomina datos de evento y es similar al tipo de datos que registra el servidor web en sus archivos de registro.

Para capturar estos datos, instrumental dentro de [!DNL Sensor] registra información sobre cada solicitud HTTP que procesa el servidor web. [!DNL Sensor] luego almacena en búfer la información para protegerla contra fallos de red y transmite de forma segura la información a través de HTTP/S a la variable [!DNL data workbench server] que especifique.

Después de la [!DNL data workbench server] recibe los datos, procesa y almacena los archivos de registro en archivos muy comprimidos [!DNL .vsl] archivos de formato, lo que le permite mantener fácilmente grandes cantidades de datos en hardware económico.

Para obtener información sobre los campos de datos de evento recopilados por [!DNL Sensor] en [!DNL .vsl] archivos, consulte [Campos de registro de datos de evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
