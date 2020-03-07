---
description: La funcionalidad de transformación se ejecuta en un equipo FSU de Insight Server para permitir la exportación de datos de origen de registro para su uso en otras aplicaciones.
solution: Insight
title: Configuración de la transformación
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configuración de la transformación{#configuring-transform}

La funcionalidad de transformación se ejecuta en un equipo FSU de Insight Server para permitir la exportación de datos de origen de registro para su uso en otras aplicaciones.

[!DNL Transform] Puede leer [!DNL .vsl] archivos, archivos de registro, archivos XML y datos ODBC y exportar los datos como [!DNL .vsl] archivos, archivos de texto o archivos de texto delimitados que pueden utilizar las rutinas de carga del almacén de datos, agencias de auditoría u otros destinos. La extracción y transformación de datos se puede realizar de forma continua o programada. Cada [!DNL Insight Server] FSU que proporciona la salida de los datos de eventos alterados debe ejecutarse [!DNL Transform].

>[!NOTE]
>
>Normalmente, [!DNL Transform] se instala en una [!DNL Insight Server] FSU. Sin embargo, su implementación puede requerir la instalación en un [!DNL Insight Server] DPU. Para obtener más información, póngase en contacto con Adobe.

Para obtener información sobre los requisitos del sistema para la instalación, configuración y funcionamiento [!DNL Transform], consulte el documento Requisitos ** mínimos del sistema.

Adobe distribuye la [!DNL Transform] funcionalidad como un perfil dentro del [!DNL .zip] archivo para el paquete de la [!DNL Insight Server] versión. El [!DNL Transform] perfil es un perfil interno que proporciona funcionalidad adicional a [!DNL Insight Server]. Al igual que con todos los demás perfiles internos proporcionados por Adobe, el perfil no debe modificarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

El perfil consta de los siguientes archivos:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un conjunto de datos de procesamiento de registros incluye un archivo

Todos estos archivos se encuentran en la [!DNL Dataset] carpeta del perfil.

**Para instalar el[!DNL Transform]perfil en[!DNL Insight Server]**

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado [!DNL Insight] y establecido una conexión entre [!DNL Insight] y el [!DNL Insight Server] en el que está instalando [!DNL Transform]. Si no lo ha hecho, consulte la * [!DNL Insight] Guía del usuario*.

1. Abra el [!DNL .zip] archivo del paquete de [!DNL Insight Server] versión y abra la [!DNL Profiles] carpeta dentro de ese [!DNL .zip] archivo.
1. Copie la [!DNL Transform] carpeta en la [!DNL Profiles] carpeta del directorio [!DNL Insight Server] de instalación. Desea terminar con una [!DNL ...\Profiles\Transform] carpeta en el [!DNL Insight Server] ejemplo siguiente.

   ![Información sobre los pasos](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si ha seguido todos los pasos para la instalación [!DNL Insight Server] (consulte [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), es posible que ya tenga una [!DNL Transform] carpeta en el directorio Perfiles.

1. Siga los pasos siguientes para actualizar el [!DNL profile.cfg] archivo del perfil con el que desea utilizar [!DNL Transform]. El conjunto de datos se reprocesa una vez completados estos pasos.

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

   1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparecerá la [!DNL profile.cfg] ventana.

   1. En la [!DNL profile.cfg]ventana, haga clic con el botón derecho **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para agregar el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL Transform]
   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL profile.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

