---
description: Puede que desee agregar una FSU de Insight Server a un clúster existente si desea almacenar datos de origen en un servidor de archivos adicional o si desea configurar una copia de seguridad para el servidor maestro de Insight Server.
title: Añadir una FSU de Insight Server a un clúster existente
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Añadir una FSU de Insight Server a un clúster existente{#adding-an-insight-server-fsu-to-an-existing-cluster}

Puede que desee agregar una FSU de Insight Server a un clúster existente si desea almacenar datos de origen en un servidor de archivos adicional o si desea configurar una copia de seguridad para el servidor maestro de Insight Server.

Para agregar una [!DNL Insight Server] FSU a un clúster existente, debe realizar los siguientes procedimientos:

1. [Actualización de los archivos de configuración en el servidor maestro](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Instalación de la nueva FSU de Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configuración de la nueva FSU de Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Actualización de los archivos de configuración en el servidor maestro {#section-b5f21f2edb35493da4475de2cdeefca1}

En [!DNL Insight], abra [!DNL Server Files Manager] para su [!DNL Insight Server] maestro (normalmente una [!DNL Insight Server] FSU) y haga lo siguiente para cada FSU que desee agregar al clúster:

1. Edite el archivo de direcciones en el [!DNL Insight Server] maestro para incluir el nombre y la dirección de la nueva FSU, tal como se describe en [Añadir los servidores de perspectiva de procesamiento al archivo de direcciones](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Agregue el nombre y la dirección de la nueva FSU al grupo en el que se muestra la [!DNL Insight Servers] actual de su clúster.

1. Edite el archivo de control de acceso en el [!DNL Insight Server] maestro para incluir la dirección IP de la nueva FSU, tal como se describe en [Actualización del archivo de control de acceso para un clúster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalación de la nueva FSU de Insight Server {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. En su FSU actual, haga un archivo zip del directorio de instalación [!DNL Insight Server] y copie el archivo en la nueva FSU.
1. Descomprima el archivo en la ubicación donde desee colocar el software [!DNL Insight Server].
1. Descargue e instale el certificado digital para la nueva FSU tal como se describe en [Descarga e instalación de certificados digitales](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Establezca los parámetros de utilización de la memoria de Windows en la nueva FSU.
1. Cambie el nombre del archivo [!DNL .address] para que refleje el nombre de la FSU tal como se describe en [Definición de la ubicación de red del servidor](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Si la estructura de la unidad en la nueva FSU es diferente a la de la FSU principal, debe editar el archivo [!DNL Disk Files.cfg].

   1. Abra el archivo [!DNL Disk Files.cfg] en la nueva FSU.
   1. Actualice la configuración para que coincida con las unidades de la FSU principal como se describe en [Monitorización del espacio de datos del conjunto de datos](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Guarde el archivo localmente y en el servidor.

1. Registre [!DNL Insight Server] como un servicio de Windows en el nuevo equipo FSU tal como se describe en [Registro de Insight Server como un servicio de Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Repita los pasos del 1 al 6 para cada FSU adicional que agregue al clúster.

## Configuración de la nueva FSU de Insight Server {#section-c39334c5bd754d5b98d41ad094333108}

Los siguientes procedimientos proporcionan instrucciones para tareas de configuración específicas. Siga las instrucciones adecuadas para la implementación de la nueva FSU.

**Para configurar la FSU para el almacenamiento de datos de origen**

Si la nueva FSU almacena datos de origen adicionales para el conjunto de datos que se ejecuta en el clúster, debe completar el proceso de configuración del servidor de archivos tal como se describe en Configuración de una [!DNL Insight Server] unidad de servidor de archivos en el capítulo Archivo de configuración de procesamiento de registros de la *Guía de configuración del conjunto de datos*.

**Para hacer a la nueva FSU la copia de seguridad para la  [!DNL Insight Server] FSU maestra**

Si desea que la nueva FSU sea la copia de seguridad para el maestro [!DNL Insight Server] (que sirve como FSU para el clúster), debe modificar el archivo de sincronización en la nueva FSU (copia de seguridad) para que se sincronice con la FSU maestra.

1. En la [!DNL Insight Server] FSU de copia de seguridad, utilice el [!DNL Server Files Manager] para copiar el archivo [!DNL Synchronize.cfg] en la carpeta [!DNL Components for Processing Servers] a la carpeta [!DNL Components].

1. Abra el archivo [!DNL Synchronize.cfg] (en la carpeta [!DNL Components]) en [!DNL Insight].

1. Busque el objeto SynchronizeDir que especifica la ubicación del directorio Componentes. Puede haber varios directorios de sincronización enumerados en Directorios, por lo que puede que necesite ver el contenido de muchos de ellos (haciendo clic en el número de servidor) para encontrar el servidor deseado).
1. Edite la entrada SynchronizeDir y añada una segunda entrada SynchronizeDir como se muestra en el ejemplo siguiente.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Guarde el archivo modificado con un nombre nuevo como [!DNL FSU_Synchronize.cfg] para no confundirlo con los archivos [!DNL Synchronize.cfg] de las DPU del clúster.

1. Utilice [!DNL Server Files Manager] para guardar la copia local del archivo renombrado en el servidor. La FSU de copia de seguridad descarga los archivos en los directorios identificados de la FSU maestra [!DNL Insight Server] y recupera dinámicamente copias actualizadas de estos archivos de la FSU maestra [!DNL Insight Server] cuando cambian.
