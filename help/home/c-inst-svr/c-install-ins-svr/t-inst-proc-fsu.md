---
description: Las instrucciones para instalar una FSU de Insight Server y configurarla para uso administrativo son muy similares a las para instalar y configurar una DPU de Insight Server.
solution: Insight
title: Procedimientos de instalación de una FSU de Insight Server
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procedimientos de instalación de una FSU de Insight Server{#installation-procedures-for-an-insight-server-fsu}

Las instrucciones para instalar una FSU de Insight Server y configurarla para uso administrativo son muy similares a las para instalar y configurar una DPU de Insight Server.

Para *MS System Center Endpoint Protection* en servidores Windows 2012, estos ejecutables deben agregarse a los procesos **excluidos:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Para instalar y configurar una [!DNL Insight Server] FSU, debe completar las siguientes tareas:

1. Instale los archivos del [!DNL Insight Server] programa.
1. Instale el certificado [!DNL Insight Server] digital.
1. Compruebe la configuración del puerto en el [!DNL Communications.cfg] archivo.
1. Modifique el [!DNL Access Control.cfg] archivo para permitir el acceso administrativo a [!DNL the Server] desde [!DNL the Client].
1. Modifique el [!DNL server.address] archivo para definir la ubicación de red del servidor.
1. Configure los parámetros de utilización de la memoria de Windows tal como se describe.
1. Regístrese [!DNL Insight Server] como un servicio de Windows como se describe.

   Para obtener instrucciones sobre cómo configurar fuentes de datos, permisos y comunicaciones para un [!DNL Insight Server] FSU, consulte la Guía *de configuración de* Dataset.

