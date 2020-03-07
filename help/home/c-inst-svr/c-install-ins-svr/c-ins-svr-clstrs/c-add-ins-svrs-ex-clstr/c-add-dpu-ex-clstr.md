---
description: Normalmente, desea agregar una DPU de Insight Server a un clúster existente cuando la cantidad de datos que desea procesar y hacer accesible para los usuarios de Insight e Report exceda la capacidad de la configuración actual del clúster.
solution: Insight
title: Adición de una DPU de Insight Server a un clúster existente
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adición de una DPU de Insight Server a un clúster existente{#adding-an-insight-server-dpu-to-an-existing-cluster}

Normalmente, desea agregar una DPU de Insight Server a un clúster existente cuando la cantidad de datos que desea procesar y hacer accesible para los usuarios de Insight e Report exceda la capacidad de la configuración actual del clúster.

## Actualización de los archivos de configuración en el servidor maestro {#section-7c9a23754a994d73b722d53f999f0e82}

En [!DNL Insight], abra el [!DNL Server Files Manager] para el maestro [!DNL Insight Server] (generalmente un [!DNL Insight Server] FSU) y haga lo siguiente para cada DPU que desee agregar al clúster:

1. Edite el archivo de dirección en el archivo maestro [!DNL Insight Server] para incluir el nombre y la dirección del nuevo DPU, tal como se describe en [Adición de los servidores de perspectiva de procesamiento al archivo](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)de direcciones. Agregue el nombre y la dirección del nuevo DPU al grupo en el que [!DNL Insight Servers] se muestra la lista actual del clúster.

1. Edite el archivo de control de acceso en el maestro [!DNL Insight Server] para incluir la dirección IP del nuevo DPU, tal como se describe en [Actualización del archivo de control de acceso para un clúster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalación de la nueva DPU de Insight Server {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Esta tarea solo se aplica a Windows de 32 bits.

1. Copie los siguientes directorios de uno de los DPU actuales del clúster en el nuevo DPU:

   * [!DNL Insight Server] directorio de instalación/bin/
   * [!DNL Insight Server] directorio de instalación/Certificados/
   * [!DNL Insight Server] directorio de instalación/Componentes/

1. Descargue e instale el certificado digital para el nuevo DPU como se describe en [Descarga e instalación de certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitales.
1. Establezca los parámetros de utilización de la memoria de Windows en el nuevo DPU.
1. Regístrese [!DNL Insight Server] como un servicio de Windows en el nuevo equipo DPU, tal como se describe en [Registro de Insight Server como un servicio](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)de Windows.

1. Compruebe los registros de seguimiento para asegurarse de que el DPU se está sincronizando con el maestro [!DNL Insight Server].
1. Repita los pasos del 1 al 6 para cada DPU adicional que agregue al clúster.

## Adición de la nueva DPU de Insight Server a los servidores de procesamiento del perfil de dataset {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Si el nuevo DPU procesa el mismo conjunto de datos que los demás DPU del clúster, agregue el nombre común del nuevo DPU al [!DNL profile.cfg] archivo principal [!DNL Insight Server] como se describe en [Especificación de los servidores de procesamiento en Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
