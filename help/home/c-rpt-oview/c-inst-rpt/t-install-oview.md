---
description: Pasos para instalar y configurar el software de Report Server.
title: Información general de instalación
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 8%

---

# Información general de instalación{#installation-overview}

Pasos para instalar y configurar el software de Report Server.

Las siguientes tareas deben completarse en orden:

1. Instale los archivos de programa de Report Server.
1. Descargue e instale el certificado digital del servidor de informes. Consulte [Descarga e instalación del certificado digital](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
1. Configure la conexión entre el servidor de informes y el servidor de Data Workbench (InsightServer64.exe). Consulte [Configuración de la conexión con Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c).
1. Actualizar el servidor de informes con un archivo de idioma (archivo .zbin).

   Consulte [Actualizar el servidor de informes con un archivo de idioma (archivo .zbin)](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b). 1. Actualice el archivo de control de acceso en el equipo del servidor de Data Workbench para permitir que Report Server acceda al servidor de Data Workbench. Consulte [Habilitación del acceso a Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc).
1. Edite el archivo de comunicaciones en el equipo maestro de servidor de Data Workbench para mostrar el estado de Report Server en la interfaz [!DNL Master Server Detailed Status]. Consulte [Configuración de Insight Server para mostrar el estado del servidor para el informe](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8).
1. Registre el informe como un servicio de Windows. Consulte [Registro del informe como servicio de Windows](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6).
