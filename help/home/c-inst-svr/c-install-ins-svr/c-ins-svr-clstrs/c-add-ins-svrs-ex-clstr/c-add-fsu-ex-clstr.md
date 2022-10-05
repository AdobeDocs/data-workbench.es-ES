---
description: Puede que desee agregar una FSU de Insight Server a un clúster existente si desea almacenar datos de origen en un servidor de archivos adicional o si desea configurar una copia de seguridad para el servidor maestro de Insight Server.
title: Añadir una FSU de Insight Server a un clúster existente
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Añadir una FSU de Insight Server a un clúster existente{#adding-an-insight-server-fsu-to-an-existing-cluster}

{{eol}}

Puede que desee agregar una FSU de Insight Server a un clúster existente si desea almacenar datos de origen en un servidor de archivos adicional o si desea configurar una copia de seguridad para el servidor maestro de Insight Server.

Para agregar un [!DNL Insight Server] La FSU a un clúster existente debe realizar los siguientes procedimientos:

1. [Actualización de los archivos de configuración en el servidor maestro](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Instalación de la nueva FSU de Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configuración de la nueva FSU de Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Actualización de los archivos de configuración en el servidor maestro {#section-b5f21f2edb35493da4475de2cdeefca1}

En [!DNL Insight], abra el [!DNL Server Files Manager] para el maestro [!DNL Insight Server] (normalmente una [!DNL Insight Server] FSU) y haga lo siguiente para cada FSU que desee agregar al clúster:

1. Edite el archivo de dirección en el maestro [!DNL Insight Server] incluir el nombre y la dirección de la nueva FSU, tal como se describe en [Adición de los servidores de perspectiva de procesamiento al archivo de direcciones](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Añada el nombre y la dirección de la nueva FSU al grupo en el que se encuentra la [!DNL Insight Servers] se muestran.

1. Edición del archivo de control de acceso en el maestro [!DNL Insight Server] incluir la dirección IP de la nueva FSU, tal como se describe en [Actualización del archivo de control de acceso para un clúster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalación de la nueva FSU de Insight Server {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. En su FSU actual, cree un archivo zip de la variable [!DNL Insight Server] directorio de instalación y copie el archivo en la nueva FSU.
1. Descomprima el archivo en la ubicación en la que desee colocar la variable [!DNL Insight Server] software.
1. Descargue e instale el certificado digital para la nueva FSU, tal como se describe en [Descarga e instalación de certificados digitales](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Establezca los parámetros de utilización de la memoria de Windows en la nueva FSU.
1. Cambie el nombre del [!DNL .address] para reflejar el nombre de la FSU como se describe en [Definición de la ubicación de red del servidor](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Si la estructura de la unidad de la nueva FSU es diferente a la de la FSU principal, debe editar la variable [!DNL Disk Files.cfg] archivo.

   1. Abra el [!DNL Disk Files.cfg] en la nueva FSU.
   1. Actualice la configuración para que coincida con las unidades de la FSU principal como se describe en [Monitorización del espacio de datos del conjunto de datos](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Guarde el archivo localmente y en el servidor.

1. Registro [!DNL Insight Server] como servicio de Windows en el nuevo equipo FSU, tal como se describe en [Registro de Insight Server como un servicio de Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Repita los pasos del 1 al 6 para cada FSU adicional que agregue al clúster.

## Configuración de la nueva FSU de Insight Server {#section-c39334c5bd754d5b98d41ad094333108}

Los siguientes procedimientos proporcionan instrucciones para tareas de configuración específicas. Siga las instrucciones adecuadas para la implementación de la nueva FSU.

**Para configurar la FSU para el almacenamiento de datos de origen**

Si la nueva FSU almacena datos de origen adicionales para el conjunto de datos que se ejecuta en el clúster, debe completar el proceso de configuración del servidor de archivos como se describe en Configuración de un [!DNL Insight Server] Unidad de servidor de archivos en el capítulo Archivo de configuración de procesamiento de registros de la sección *Guía de configuración de conjuntos de datos*.

**Para hacer a la nueva FSU la copia de seguridad para el maestro [!DNL Insight Server] FSU**

Si desea que la nueva FSU sea la copia de seguridad para el maestro [!DNL Insight Server] (que sirve como FSU para el clúster), debe modificar el archivo de sincronización en la nueva FSU (copia de seguridad) para que se sincronice con la FSU maestra.

1. En la copia de seguridad [!DNL Insight Server] FSU, usar la variable [!DNL Server Files Manager] para copiar el [!DNL Synchronize.cfg] en el [!DNL Components for Processing Servers] a la [!DNL Components] carpeta.

1. Abra el [!DNL Synchronize.cfg] (en la variable [!DNL Components] carpeta) en [!DNL Insight].

1. Busque el objeto SynchronizeDir que especifica la ubicación del directorio Componentes. Puede haber varios directorios de sincronización enumerados en Directorios, por lo que puede que necesite ver el contenido de muchos de ellos (haciendo clic en el número de servidor) para encontrar el servidor deseado).
1. Edite la entrada SynchronizeDir y añada una segunda entrada SynchronizeDir como se muestra en el ejemplo siguiente.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Guarde el archivo modificado con un nombre nuevo como [!DNL FSU_Synchronize.cfg] para que no se confunda con el [!DNL Synchronize.cfg] archivos en las DPU del clúster.

1. Utilice la variable [!DNL Server Files Manager] para guardar la copia local del archivo renombrado en el servidor. La FSU de copia de seguridad descarga los archivos de los directorios identificados del maestro [!DNL Insight Server] FSU y recupera dinámicamente copias actualizadas de estos archivos del maestro [!DNL Insight Server] FSU cuando cambian.
