---
description: Actualización de componentes de servidor para Área de trabajo de datos 6.2 y 6.2.2.
title: Actualización del servidor DWB 6.1 a 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Actualización del servidor DWB: 6.1 a 6.2{#dwb-server-upgrade-to}

Actualización de componentes de servidor para Área de trabajo de datos 6.2 y 6.2.2.

## Problemas de actualización para 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* El perfil de atribución está configurado para que los usuarios que hayan implementado el perfil de Adobe SC empleen la fuente de datos de Analytics (SC/Insight). De forma predeterminada, los eventos de marketing y conversión se emplean como interacciones predeterminadas evaluadas en los modelos basados en reglas. Consulte [Implementación del perfil](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html) de atribución para obtener información adicional.
* Para los usuarios del perfil de Adobe SC que actualicen a Área de trabajo de datos 6.2, si no utiliza las configuraciones predeterminadas, compruebe que el [!DNL x-bot_id] valor del [!DNL SC Fields.cfg] archivo se descodifica correctamente y que el [!DNL x-bot_id] campo aparece correctamente en los archivos [!DNL Decoding Instructions.cfg] y [!DNL Exclude Hit.cfg] . Esto sólo será un problema si ha modificado el archivo de configuración desde la configuración predeterminada.
* Si ha eliminado los campos no utilizados del [!DNL Dataset > Log Processing > SC Fields.cfg] archivo para el perfil de Adobe SC, deberá actualizarlos para dar cabida a los valores de campo actualizados utilizados para el perfil de atribución (consulte [Implementación del perfil](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)de atribución).

## Problemas de actualización para 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Los archivos **[!UICONTROL Browsers]** y **[!UICONTROL Operating Systems]** de búsqueda no se actualizarán dentro del **[!UICONTROL Traffic]** perfil heredado (por ejemplo, [!DNL Lookups\Traffic\Browsers.txt)]. Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* La versión 6.2.1 de Área de trabajo de datos será la última que ofrecerá la descarga de la aplicación del cliente de 32 bits. A partir de entonces, las siguientes descargas de la aplicación del cliente serán de 64 bits y también requerirán Windows 7 o una versión posterior. Las limitaciones de memoria de la aplicación de 32 bits quedan corregidas con la aplicación de 64 bits, a partir de la versión 6.1.

>[!NOTE]
>
>La versión de 32 bits de la aplicación cliente de Área de trabajo de datos puede experimentar problemas potenciales relacionados con las limitaciones de memoria al ejecutar modelos predictivos mediante las funciones de clúster y puntuación.

