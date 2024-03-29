---
description: Instrucciones detalladas para instalar una DPU de Insight Server y configurarla para uso administrativo.
title: Procedimientos de instalación para una DPU de Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Procedimientos de instalación para una DPU de Insight Server{#installation-procedures-for-an-insight-server-dpu}

{{eol}}

Instrucciones detalladas para instalar una DPU de Insight Server y configurarla para uso administrativo.

Para instalar y configurar un [!DNL Insight Server] DPU, debe completar las siguientes tareas en orden:

1. Instale el [!DNL Insight Server] archivos de programa. Consulte [Instalación de los archivos de programa de Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Descargue e instale el [!DNL Insight Server] certificado digital. Consulte [Descarga e instalación de certificados digitales](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Compruebe la configuración del puerto en el [!DNL Communications.cfg] archivo. Consulte [Comprobación de la configuración del puerto](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifique el [!DNL Access Control.cfg] para permitir el acceso administrativo a [!DNL Insight Server] from [!DNL Insight]. Consulte [Actualización del archivo de control de acceso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifique el [!DNL server.address] para definir la ubicación de red del servidor. Consulte [Definición de la ubicación de red del servidor](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Opcional) Modifique el [!DNL Disk Files.cfg] para especificar dónde se almacenan los datos procesados. Consulte [Configuración de la ubicación del conjunto de datos (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Instale los perfiles y los archivos de búsqueda. Consulte [Instalación de perfiles y archivos de búsqueda](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Establezca los parámetros de utilización de memoria de Microsoft Windows.
1. Registro [!DNL Insight Server] como servicio de Windows. Consulte [Registro de Insight Server como un servicio de Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
