---
description: Instrucciones detalladas para instalar una DPU de Insight Server y configurarla para uso administrativo.
solution: Insight
title: Procedimientos de instalación para una DPU de Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procedimientos de instalación para una DPU de Insight Server{#installation-procedures-for-an-insight-server-dpu}

Instrucciones detalladas para instalar una DPU de Insight Server y configurarla para uso administrativo.

Para instalar y configurar una [!DNL Insight Server] DPU, debe completar las siguientes tareas en orden:

1. Instale los archivos del [!DNL Insight Server] programa. Consulte [Instalación de los archivos](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)de programa de Insight Server.
1. Download and install the [!DNL Insight Server] digital certificate. Consulte [Descarga e instalación de certificados](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitales.
1. Compruebe la configuración del puerto en el [!DNL Communications.cfg] archivo. Consulte [Comprobación de la configuración](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)del puerto.
1. Modifique el [!DNL Access Control.cfg] archivo para permitir el acceso administrativo a [!DNL Insight Server] desde [!DNL Insight]. Consulte [Actualización del archivo](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)de control de acceso.
1. Modifique el [!DNL server.address] archivo para definir la ubicación de red del servidor. Consulte [Definición de la ubicación](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)de red del servidor.
1. (Opcional) Modifique el [!DNL Disk Files.cfg] archivo para especificar dónde se almacenan los datos procesados. Consulte [Configuración de la ubicación del conjunto de datos (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Instale los perfiles y los archivos de búsqueda. Consulte [Instalación de perfiles y archivos](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)de búsqueda.
1. Establezca los parámetros de utilización de memoria de Microsoft Windows.
1. Regístrese [!DNL Insight Server] como un servicio de Windows. Consulte [Registro de Insight Server como un servicio](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)de Windows.
