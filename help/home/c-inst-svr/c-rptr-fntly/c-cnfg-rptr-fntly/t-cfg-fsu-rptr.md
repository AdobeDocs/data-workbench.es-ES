---
description: Instrucciones para instalar y configurar una FSU de Insight Server para su uso con Repeater.
solution: Analytics
title: Configuración de una FSU de Insight Server para el repetidor
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---


# Configuración de una FSU de Insight Server para el repetidor{#configuring-an-insight-server-fsu-for-repeater}

Instrucciones para instalar y configurar una FSU de Insight Server para su uso con Repeater.

Complete las siguientes tareas en orden. Después de cada paso se anotan todas las excepciones o cambios que debe realizar para que la [!DNL Insight Server] FSU pueda utilizarse como servidor repetidor.

1. Instale los archivos de [!DNL Insight Server] programa como se describe en [Instalación de Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Dado que el equipo en el que se instalan estos archivos se utiliza para ejecutar Repeater, resulta útil asignar al directorio de instalación un nombre descriptivo como [!DNL D:\Adobe\Repeater].

1. Instale el certificado [!DNL Insight Server] digital como se describe en [Descarga e instalación de certificados](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitales.

   Después de iniciar sesión en el servidor de licencias de Adobe, recuerde buscar el nombre del certificado que coincida con el nombre común del servidor del equipo repetidor designado.

1. Compruebe la configuración del puerto en el [!DNL Communications.cfg] archivo como se describe en [Comprobación de la configuración](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)del puerto.

   Si los puertos asignados (puerto y puerto SSL) son utilizados por otro proceso que se ejecuta en el mismo equipo, debe cambiar las asignaciones de puerto a un par no utilizado.

1. Si es necesario, cambie el directorio de registro de los datos que se van a recopilar y almacenar en este equipo. [!DNL Sensor] Para obtener instrucciones, consulte [Supervisión del espacio](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)de datos de Evento.
1. Modifique el [!DNL Access Control.cfg] archivo para permitir el acceso administrativo a [!DNL Insight Server] desde [!DNL Insight] , tal como se describe en [Actualización del archivo](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)Control de acceso.
1. Modifique el [!DNL server.address] archivo para definir la ubicación de red del servidor tal como se define en [Definición de la ubicación](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)de red del servidor.
1. Configure los parámetros de utilización de la memoria de Windows.
1. Regístrese [!DNL Insight Server] como un servicio de Windows tal como se describe en [Registro de Insight Server como un servicio](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)de Windows.
