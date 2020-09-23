---
description: Cuando configura un perfil de conjunto de datos para que se ejecute en un clúster de Insight Server, todos los equipos del clúster comparten todos los archivos de configuración de conjunto de datos para ese perfil.
solution: Analytics
title: Configuración de un Perfil para ejecutar en un clúster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---


# Configuración de un Perfil para ejecutar en un clúster{#configuring-a-profile-to-run-on-a-cluster}

Cuando configura un perfil de conjunto de datos para que se ejecute en un clúster de Insight Server, todos los equipos del clúster comparten todos los archivos de configuración de conjunto de datos para ese perfil.

Por lo tanto, las entradas para los parámetros de estos archivos deben ser aplicables a todos [!DNL Insight Servers] los del clúster. Por ejemplo, las ubicaciones de los archivos de registro que se van a leer, los archivos de búsqueda que se van a utilizar [!DNL Insight Server]y la ubicación de la salida de datos por [!DNL Insight Server] deben ser las mismas en todos los equipos del clúster.

Se realizan todas las tareas de configuración en el maestro del clúster [!DNL Insight Server], que es el [!DNL Insight Server] que se utiliza para editar los archivos de configuración. Todos los cambios guardados en el archivo de configuración realizados en el maestro [!DNL Insight Server] se sincronizan automáticamente con los archivos del procesamiento [!DNL Insight Servers] en el clúster.

Para ejecutar un perfil de conjunto de datos en un [!DNL Insight Server] clúster, debe realizar los siguientes procesos en el orden indicado:

1. [Determinación de los servidores de perspectiva que procesan los datos de Evento](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Especificación de los servidores de procesamiento en Perfil.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Si es necesario) [Modificación de los archivos de configuración del conjunto de datos para el Perfil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinación de los servidores de perspectiva que procesan los datos de Evento {#section-59b8e3f2b34f49739d544c8740a62fba}

No es necesario que todos los datos [!DNL Insight Servers] del evento de procesos del clúster. Puede designar uno [!DNL Insight Server] en el clúster como una unidad de servidor de archivos que almacene los archivos de origen (archivos de registro y VSL) y sirva los archivos a todas las unidades de procesamiento de datos (servidores de procesamiento) del clúster. Esta configuración proporciona las ventajas de un único repositorio de datos de evento y aprovecha la potencia de procesamiento de todos los servidores de procesamiento del clúster. Los servidores de procesamiento dividen los archivos de datos entre ellos y garantizan que el mismo archivo no se procesa más de una vez.

Para obtener más información sobre cómo designar un [!DNL Insight Server] para que se ejecute como una unidad de servidor de archivos, consulte el capítulo Archivo de configuración de procesamiento de registros de la Guía *de configuración de* conjuntos de datos.

Si decide almacenar los archivos de datos de origen en cada uno de los servidores de procesamiento en lugar de en una sola unidad de servidor de archivos, debe dividir los archivos de forma equitativa entre los servidores de procesamiento. No almacene todos los archivos de origen del conjunto de datos en cada uno de los servidores de procesamiento. Si hay varias copias del mismo archivo disponibles para varios servidores de procesamiento, los datos se leen varias veces (una por cada equipo) y distorsionan los datos.

Para obtener ayuda para determinar qué archivos de registro [!DNL Insight Servers] deben procesarse, póngase en contacto con Adobe Consulting.

## Especificación de los servidores de procesamiento en Perfil.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

En el [!DNL profile.cfg] archivo, especifique los servidores de procesamiento que procesan los datos del perfil.

**Para acceder al archivo perfil.cfg**

Puede acceder al archivo de configuración de perfil mediante la [!DNL Profile Manager] parte [!DNL Insight].

1. Mientras trabaja en el perfil del conjunto de datos, abra el  haciendo clic con el botón secundario en un espacio de trabajo y haciendo clic en [!DNL Profile Manager] > **[!UICONTROL Admin]** > **[!UICONTROL Profile]** , o bien abriendo el espacio de trabajo de Administración de Perfiles en la **[!UICONTROL Profile Manager]**[!DNL Admin] ficha.

1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparece la ventana de configuración de perfil.

**Para agregar los servidores de procesamiento**

1. En el [!DNL profile.cfg] archivo, haga clic en **[!UICONTROL Profile]** y, a continuación, haga clic en **[!UICONTROL Processing Servers]** para mostrar su contenido.

1. Haga clic con el botón derecho **[!UICONTROL Processing Servers]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. En el parámetro Nombre común, escriba el nombre común del primer servidor de procesamiento del clúster. Por ejemplo: [!DNL server1.mycompany.com]
1. Repita los pasos 2 y 3 hasta que haya agregado los nombres comunes de todos los servidores de procesamiento del clúster.

   >[!NOTE]
   >
   >Si el maestro [!DNL Insight Server] procesa los datos, debe agregarlos también.

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Haga clic con el botón secundario en la marca de verificación de la [!DNL User] columna situada junto a [!DNL profile.cfg]. Haga clic **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modificación de los archivos de configuración del conjunto de datos para el Perfil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Para modificar los archivos de configuración del conjunto de datos**

Si necesita realizar cambios en los archivos de configuración del conjunto de datos ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], archivos de inclusión de conjuntos de datos, [!DNL Log Processing Mode.cfg], etc.), hágalo sólo en el maestro [!DNL Insight Server].

1. Acceda a los archivos que desea modificar:

   Para obtener instrucciones sobre cómo acceder a los archivos, consulte la Guía *de configuración de* Dataset.
1. Haga los cambios. Consulte la Guía *de configuración de* Dataset para obtener más información sobre los parámetros dentro de los archivos de configuración.
1. Guarde el archivo.

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. Haga clic con el botón secundario en la marca de verificación de la [!DNL User] columna situada junto al nombre del archivo.
   1. Haga clic **[!UICONTROL Save to]** y seleccione el perfil que desee.

>[!NOTE]
>
>[!DNL Insight] los usuarios que acceden a un perfil de conjunto de datos que se ejecuta en un clúster identifican únicamente al maestro [!DNL Insight Server] en el archivo de [!DNL Insight] configuración ( [!DNL insight.cfg]). Desde el punto de vista del [!DNL Insight] usuario, el perfil sólo puede accederse a uno [!DNL Insight Server] (el maestro [!DNL Insight Server]); sin embargo, las solicitudes de consulta de los analistas se pueden dirigir a cualquiera de los [!DNL Insight Servers] del clúster.

Un [!DNL Insight Server] clúster permite el almacenamiento centralizado de archivos de [!DNL .vsl] registro (desde [!DNL Sensor]) en un solo [!DNL Insight Server] equipo llamado File Server Unit (FSU). Para obtener información sobre la instalación de una FSU, consulte Procedimientos [de instalación de una FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)de Insight Server. Para obtener información sobre la configuración de una FSU, consulte la Guía *de configuración de* Dataset.
