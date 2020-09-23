---
description: Instrucciones detalladas para instalar una DPU de Insight Server y configurarla para uso administrativo.
solution: Analytics
title: Procedimientos de instalación para una DPU de Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---


# Procedimientos de instalación para una DPU de Insight Server{#installation-procedures-for-an-insight-server-dpu}

Instrucciones detalladas para instalar una DPU de Insight Server y configurarla para uso administrativo.

Para instalar y configurar un [!DNL Insight Server] DPU, debe completar las siguientes tareas en orden:

1. Instale los archivos de [!DNL Insight Server] programa. See [Installing the Insight Server Program Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Download and install the [!DNL Insight Server] digital certificate. See [Downloading and Installing the Digital Certificates](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Compruebe la configuración del puerto en el [!DNL Communications.cfg] archivo. See [Checking the Port Settings](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifique el [!DNL Access Control.cfg] archivo para permitir el acceso administrativo a [!DNL Insight Server] desde [!DNL Insight]. See [Updating the Access Control File](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifique el [!DNL server.address] archivo para definir la ubicación de red del servidor. See [Defining the Server&#39;s Network Location](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Opcional) Modifique el [!DNL Disk Files.cfg] archivo para especificar dónde se almacenan los datos procesados. See [Configuring the Location of the Dataset (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Instale los perfiles y los archivos de búsqueda. See [Installing Profiles and Lookup Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Establezca los parámetros de utilización de memoria de Microsoft Windows.
1. Regístrese [!DNL Insight Server] como un servicio de Windows. See [Registering Insight Server as a Windows Service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
