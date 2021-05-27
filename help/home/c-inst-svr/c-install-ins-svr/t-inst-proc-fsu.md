---
description: Las instrucciones para instalar una FSU de Insight Server y configurarla para uso administrativo son muy similares a las para instalar y configurar una DPU de Insight Server.
title: Procedimientos de instalación de una FSU de Insight Server
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procedimientos de instalación de una FSU de Insight Server{#installation-procedures-for-an-insight-server-fsu}

Las instrucciones para instalar una FSU de Insight Server y configurarla para uso administrativo son muy similares a las para instalar y configurar una DPU de Insight Server.

Para *MS System Center Endpoint Protection* en servidores Windows 2012, estos ejecutables deben agregarse a los **Procesos excluidos:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Para instalar y configurar una FSU [!DNL Insight Server], debe completar las siguientes tareas:

1. Instale los archivos de programa [!DNL Insight Server].
1. Instale el certificado digital [!DNL Insight Server].
1. Compruebe la configuración del puerto en el archivo [!DNL Communications.cfg].
1. Modifique el archivo [!DNL Access Control.cfg] para permitir acceso administrativo a [!DNL the Server] desde [!DNL the Client].
1. Modifique el archivo [!DNL server.address] para definir la ubicación de red del servidor.
1. Establezca los parámetros de utilización de la memoria de Windows como se describe.
1. Registre [!DNL Insight Server] como un servicio de Windows como se describe.

   Para obtener instrucciones sobre la configuración de fuentes de datos, permisos y comunicaciones para una FSU [!DNL Insight Server], consulte la *Guía de configuración de conjuntos de datos*.
