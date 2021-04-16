---
description: Cuando configura un perfil de conjunto de datos para que se ejecute en un clúster de Insight Server, todos los equipos del clúster comparten todos los archivos de configuración del conjunto de datos para ese perfil.
title: Configuración de un Perfil para ejecutar en un clúster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configuración de un Perfil para ejecutar en un clúster{#configuring-a-profile-to-run-on-a-cluster}

Cuando configura un perfil de conjunto de datos para que se ejecute en un clúster de Insight Server, todos los equipos del clúster comparten todos los archivos de configuración del conjunto de datos para ese perfil.

Por lo tanto, las entradas de los parámetros de estos archivos deben aplicarse a todos los [!DNL Insight Servers] del clúster. Por ejemplo, las ubicaciones de los archivos de registro que se van a leer, los archivos de búsqueda que [!DNL Insight Server] utilizará y la ubicación de la salida de datos [!DNL Insight Server] debe ser la misma en todos los equipos del clúster.

Puede realizar todas las tareas de configuración en el [!DNL Insight Server] maestro del clúster, que es el [!DNL Insight Server] que utiliza para editar sus archivos de configuración. Todos los cambios guardados en el archivo de configuración realizados en el [!DNL Insight Server] maestro se sincronizan automáticamente con los archivos del [!DNL Insight Servers] de procesamiento del clúster.

Para ejecutar un perfil de conjunto de datos en un clúster [!DNL Insight Server], debe realizar los siguientes procesos en el orden enumerado:

1. [Determinación de qué servidores de Insight procesan datos de evento](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Especificación de los servidores de procesamiento en Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Si es necesario) [Modificación de los archivos de configuración del conjunto de datos para el perfil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinación de qué servidores de Insight procesan datos de evento {#section-59b8e3f2b34f49739d544c8740a62fba}

No es necesario que todos los [!DNL Insight Servers] en los datos de evento de proceso del clúster. Puede designar una [!DNL Insight Server] del clúster como unidad de servidor de archivos que almacene los archivos de origen (archivos de registro y VSL) y sirva los archivos a todas las unidades de procesamiento de datos (servidores de procesamiento) del clúster. Esta configuración proporciona las ventajas de un único repositorio de datos de evento y aprovecha la potencia de procesamiento de todos los servidores de procesamiento del clúster. Los servidores de procesamiento dividen los archivos de datos entre ellos y garantizan que el mismo archivo no se procese más de una vez.

Para obtener más información sobre la designación de un [!DNL Insight Server] para que se ejecute como unidad de servidor de archivos, consulte el capítulo Archivo de configuración de procesamiento de registros de la *Guía de configuración de conjuntos de datos*.

Si decide almacenar los archivos de datos de origen en cada uno de los servidores de procesamiento en lugar de en una sola unidad de servidor de archivos, debe dividir los archivos equitativamente entre los servidores de procesamiento. No almacene todos los archivos de origen del conjunto de datos en cada uno de los servidores de procesamiento. Si hay varias copias del mismo archivo disponibles para varios servidores de procesamiento, los datos se leen varias veces (una vez por cada equipo) y distorsionan los datos.

Para obtener ayuda para determinar qué [!DNL Insight Servers] debe procesar los archivos de registro, póngase en contacto con el consultor de Adobe.

## Especificación de los servidores de procesamiento en Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

En el archivo [!DNL profile.cfg], especifique los servidores de procesamiento que procesan los datos del perfil.

**Para acceder al archivo profile.cfg**

Puede acceder al archivo de configuración de perfil utilizando [!DNL Profile Manager] en [!DNL Insight].

1. Mientras trabaja en el perfil del conjunto de datos, abra [!DNL Profile Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**, o abriendo el espacio de trabajo de Administración de perfiles en la pestaña [!DNL Admin] .

1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.

1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparece la ventana de configuración de perfil.

**Para agregar los servidores de procesamiento**

1. En el archivo [!DNL profile.cfg], haga clic en **[!UICONTROL Profile]** y, a continuación, haga clic en **[!UICONTROL Processing Servers]** para mostrar su contenido.

1. Haga clic con el botón derecho en **[!UICONTROL Processing Servers]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. En el parámetro Nombre común , escriba el nombre común del primer servidor de procesamiento del clúster. Por ejemplo: [!DNL server1.mycompany.com]
1. Repita los pasos 2 y 3 hasta que haya agregado los nombres comunes de todos los servidores de procesamiento del clúster.

   >[!NOTE]
   >
   >Si el [!DNL Insight Server] maestro procesa los datos, también debe agregarlos.

1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Haga clic con el botón derecho en la marca de verificación de la columna [!DNL User] junto a [!DNL profile.cfg]. Haga clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modificación de los archivos de configuración del conjunto de datos para el perfil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Para modificar los archivos de configuración del conjunto de datos**

Si necesita realizar cambios en los archivos de configuración del conjunto de datos ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], archivos de inclusión de conjuntos de datos, [!DNL Log Processing Mode.cfg], etc.), hágalo solo en el [!DNL Insight Server] maestro.

1. Acceda a los archivos que desea modificar:

   Para obtener instrucciones para acceder a los archivos, consulte la *Guía de configuración del conjunto de datos*.
1. Haga los cambios. Consulte la *Guía de configuración del conjunto de datos* para obtener más información sobre los parámetros dentro de los archivos de configuración.
1. Guarde el archivo.

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. Haga clic con el botón derecho en la marca de verificación de la columna [!DNL User] junto al nombre del archivo.
   1. Haga clic en **[!UICONTROL Save to]** y seleccione el perfil deseado.

>[!NOTE]
>
>[!DNL Insight] los usuarios que acceden a un perfil de conjunto de datos que se ejecuta en un clúster solo identifican al maestro  [!DNL Insight Server] en el archivo de  [!DNL Insight] configuración (  [!DNL insight.cfg]). Desde la perspectiva del usuario [!DNL Insight], solo se puede acceder al perfil en un [!DNL Insight Server] (el [!DNL Insight Server] maestro); sin embargo, las solicitudes de consulta de los analistas se pueden dirigir a cualquiera de los [!DNL Insight Servers] del clúster.

Un clúster [!DNL Insight Server] permite el almacenamiento centralizado de [!DNL .vsl] archivos de registro (desde [!DNL Sensor]) en una sola máquina [!DNL Insight Server] llamada Unidad de Servidor de Archivos (FSU). Para obtener información sobre la instalación de una FSU, consulte [Procedimientos de instalación de una FSU de Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Para obtener información sobre la configuración de una FSU, consulte la *Guía de configuración de conjuntos de datos*.
