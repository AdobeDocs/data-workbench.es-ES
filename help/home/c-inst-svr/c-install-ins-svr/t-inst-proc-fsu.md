---
description: Las instrucciones para instalar una FSU de Insight Server y configurarla para uso administrativo son muy similares a las para instalar y configurar una DPU de Insight Server.
title: Procedimientos de instalación de una FSU de Insight Server
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procedimientos de instalación de una FSU de Insight Server{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

Las instrucciones para instalar una FSU de Insight Server y configurarla para uso administrativo son muy similares a las para instalar y configurar una DPU de Insight Server.

Para *Protección de extremo de MS System Center* en los servidores de Windows 2012, estos ejecutables deben agregarse al **Procesos excluidos:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Para instalar y configurar un [!DNL Insight Server] FSU, debe completar las siguientes tareas:

1. Instale el [!DNL Insight Server] archivos de programa.
1. Instale el [!DNL Insight Server] certificado digital.
1. Compruebe la configuración del puerto en el [!DNL Communications.cfg] archivo.
1. Modifique el [!DNL Access Control.cfg] para permitir el acceso administrativo a [!DNL the Server] from [!DNL the Client].
1. Modifique el [!DNL server.address] para definir la ubicación de red del servidor.
1. Establezca los parámetros de utilización de la memoria de Windows como se describe.
1. Registro [!DNL Insight Server] como un servicio de Windows como se describe.

   Para obtener instrucciones sobre la configuración de fuentes de datos, permisos y comunicaciones para un [!DNL Insight Server] FSU, consulte la *Guía de configuración de conjuntos de datos*.
