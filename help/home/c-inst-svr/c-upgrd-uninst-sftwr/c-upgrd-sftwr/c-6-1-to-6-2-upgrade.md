---
description: Actualización de los componentes del servidor para las Datas Workbench 6.2 y 6.2.2.
title: Actualización del servidor DWB de 6.1 a 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# Actualización del servidor DWB: de 6.1 a 6.2{#dwb-server-upgrade-to}

{{eol}}

Actualización de los componentes del servidor para las Datas Workbench 6.2 y 6.2.2.

## Problemas de actualización para 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* El perfil de atribución está configurado para que los usuarios que hayan implementado el perfil SC de Adobe utilicen la fuente de datos de Analytics (SC/Insight). De forma predeterminada, los eventos de marketing y conversión se emplean como interacciones predeterminadas evaluadas en los modelos basados en reglas. Consulte [Implementación del perfil de atribución](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) para obtener más información.
* Si no utiliza las configuraciones predeterminadas, compruebe que los usuarios del perfil de Adobe SC que actualicen a la Data Workbench 6.2 [!DNL x-bot_id] en la variable [!DNL SC Fields.cfg] se está descodificando correctamente y que la variable [!DNL x-bot_id] aparece correctamente en la lista [!DNL Decoding Instructions.cfg] y [!DNL Exclude Hit.cfg] archivos. Esto solo será un problema si ha modificado el archivo de configuración desde la configuración predeterminada.
* Si ha eliminado campos no utilizados en el [!DNL Dataset > Log Processing > SC Fields.cfg] para el perfil SC de Adobe, deberá actualizarlo para dar cabida a los valores de campo actualizados utilizados para el perfil de atribución (consulte [Implementación del perfil de atribución](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Problemas de actualización para la versión 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* La variable **[!UICONTROL Browsers]** y **[!UICONTROL Operating Systems]** los archivos de búsqueda no se actualizarán dentro del archivo heredado **[!UICONTROL Traffic]** perfil (por ejemplo, [!DNL Lookups\Traffic\Browsers.txt)]. En su lugar, la configuración de la variable **[!UICONTROL Traffic]** utilizará el paquete DeviceAtlas ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) para proporcionar esta información de configuración.
* La versión 6.2.1 de Área de trabajo de datos será la última que ofrecerá la descarga de la aplicación del cliente de 32 bits. A partir de entonces, las siguientes descargas de la aplicación del cliente serán de 64 bits y también requerirán Windows 7 o una versión posterior. Las limitaciones de memoria de la aplicación de 32 bits quedan corregidas con la aplicación de 64 bits, a partir de la versión 6.1.

>[!NOTE]
>
>La versión de 32 bits de la aplicación cliente de Data Workbench puede experimentar posibles problemas relacionados con las limitaciones de memoria al ejecutar modelos predictivos mediante las funciones de agrupación en clúster y puntuación.
