---
description: Instrucciones para instalar y configurar una FSU de Insight Server para usar con el repetidor.
title: Configuración de una FSU de Insight Server para el repetidor
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Configuración de una FSU de Insight Server para el repetidor{#configuring-an-insight-server-fsu-for-repeater}

Instrucciones para instalar y configurar una FSU de Insight Server para usar con el repetidor.

Complete las siguientes tareas en orden. Las excepciones o cambios que debe realizar para que la FSU [!DNL Insight Server] pueda utilizarse como servidor repetidor se anotan después de cada paso.

1. Instale los archivos de programa [!DNL Insight Server] como se describe en [Instalación de Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Dado que el equipo en el que se instalan estos archivos se utiliza para ejecutar el repetidor, resulta útil dar al directorio de instalación un nombre descriptivo como [!DNL D:\Adobe\Repeater].

1. Instale el certificado digital [!DNL Insight Server] como se describe en [Descarga e instalación de certificados digitales](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Una vez que haya iniciado sesión en el servidor de licencias de Adobe, recuerde buscar el nombre del certificado que coincida con el nombre común del servidor del equipo repetidor designado.

1. Compruebe la configuración del puerto en el archivo [!DNL Communications.cfg] como se describe en [Comprobación de la configuración del puerto](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Si los puertos asignados (puerto y puerto SSL) son utilizados por otro proceso que se ejecuta en el mismo equipo, debe cambiar las asignaciones de puerto a un par no utilizado.

1. Si es necesario, cambie el directorio de registro para que los datos [!DNL Sensor] se recopilen y almacenen en este equipo. Para obtener instrucciones, consulte [Monitorización del espacio de datos del evento](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Modifique el archivo [!DNL Access Control.cfg] para permitir el acceso administrativo a [!DNL Insight Server] desde [!DNL Insight] como se describe en [Actualización del archivo de control de acceso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifique el archivo [!DNL server.address] para definir la ubicación de red del servidor tal como se define en [Definición de la ubicación de red del servidor](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Establezca los parámetros de utilización de la memoria de Windows.
1. Registre [!DNL Insight Server] como un servicio de Windows como se describe en [Registro de Insight Server como un servicio de Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
