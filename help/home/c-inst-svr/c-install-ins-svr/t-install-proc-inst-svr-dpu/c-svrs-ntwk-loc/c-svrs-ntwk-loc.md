---
description: Los clientes de Insight Server (Informe e Insight) utilizan nombres comunes para hacer referencia a los servidores de Insight.
title: Definición de la ubicación de red del servidor
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# Definición de la ubicación de red del servidor{#defining-the-server-s-network-location}

{{eol}}

Los clientes de Insight Server (Informe e Insight) utilizan nombres comunes para hacer referencia a los servidores de Insight.

Por ejemplo, al conectarse [!DNL Insight] o [!DNL Report] a un [!DNL Insight Server], puede identificar el servidor por su nombre común (por ejemplo, [!DNL Server.MyCompany.com]). Internamente, el cliente resuelve el nombre común en una dirección IP numérica antes de enviar una solicitud al servidor.

Para resolver nombres comunes en direcciones IP, [!DNL Insight Server’s] los clientes utilizan un archivo de búsqueda local denominado el archivo de dirección. El archivo de dirección enumera los nombres comunes de [!DNL Insight Servers] instalado en su organización e identifica sus direcciones IP numéricas. Un cliente recibe automáticamente una copia del archivo de dirección cuando abre un perfil en la variable [!DNL Insight Server].

Cuando un cliente envía una solicitud a un [!DNL Insight Server], intenta resolver el nombre común del servidor a través del archivo de dirección. Si el archivo de dirección identifica una dirección IP para el servidor solicitado, el cliente envía la solicitud a la dirección especificada. Si la dirección no está definida (por ejemplo, el archivo de dirección no define el nombre común del servidor), la solicitud falla. De forma opcional, puede configurar clientes para que resuelvan las direcciones a través del mecanismo normal del servicio de nombres de dominio (DNS) del entorno operativo si no se define un nombre en el archivo de direcciones del cliente. Para obtener instrucciones, consulte el parámetro Principal en la sección [Tabla Parámetros de NetworkLocation](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) en la siguiente sección.
