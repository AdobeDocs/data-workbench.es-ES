---
description: La funcionalidad de transformación se ejecuta en un equipo FSU de Insight Server para permitir la exportación de datos de origen de registro para su uso por otras aplicaciones.
title: Configuración de la transformación
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configuración de la transformación{#configuring-transform}

La funcionalidad de transformación se ejecuta en un equipo FSU de Insight Server para permitir la exportación de datos de origen de registro para su uso por otras aplicaciones.

[!DNL Transform] puede leer  [!DNL .vsl] archivos, archivos de registro, archivos XML y datos ODBC y exportar los datos como  [!DNL .vsl] archivos, archivos de texto o archivos de texto delimitados que pueden utilizar las rutinas de carga del almacén de datos, las agencias de auditoría u otros destinos. La extracción y transformación de datos se puede realizar de forma continua o programada. Cada FSU [!DNL Insight Server] que proporcione el resultado de los datos de evento alterados debe ejecutar [!DNL Transform].

>[!NOTE]
>
>Normalmente, [!DNL Transform] se instala en una [!DNL Insight Server] FSU. Sin embargo, la implementación puede requerir la instalación en una DPU [!DNL Insight Server]. Para obtener más información, póngase en contacto con el Adobe.

Para obtener información sobre los requisitos del sistema para instalar, configurar y operar [!DNL Transform], consulte el documento *Minimum System Requirements*.

Adobe distribuye la funcionalidad [!DNL Transform] como un perfil dentro del archivo [!DNL .zip] para el paquete de versión [!DNL Insight Server]. El perfil [!DNL Transform] es un perfil interno que proporciona funcionalidad adicional a [!DNL Insight Server]. Al igual que con todos los demás perfiles internos proporcionados por Adobe, el perfil no debe cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

El perfil consta de los siguientes archivos:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un archivo de inclusión de conjunto de datos de procesamiento de registros

Todos estos archivos se encuentran en la carpeta [!DNL Dataset] del perfil.

**Para instalar el  [!DNL Transform] perfil en[!DNL Insight Server]**

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado [!DNL Insight] y ha establecido una conexión entre [!DNL Insight] y el [!DNL Insight Server] en el que está instalando [!DNL Transform]. Si no lo ha hecho, consulte la * [!DNL Insight] Guía del usuario*.

1. Abra el archivo [!DNL .zip] para el paquete de versión [!DNL Insight Server] y abra la carpeta [!DNL Profiles] dentro de ese archivo [!DNL .zip].
1. Copie la carpeta [!DNL Transform] a la carpeta [!DNL Profiles] en el directorio de instalación de [!DNL Insight Server]. Desea terminar con una carpeta [!DNL ...\Profiles\Transform] en su [!DNL Insight Server] como se muestra en el siguiente ejemplo.

   ![Información sobre los pasos](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si ha seguido todos los pasos para instalar [!DNL Insight Server] (consulte [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), es posible que ya tenga una carpeta [!DNL Transform] en el directorio Perfiles.

1. Siga estos pasos para actualizar el archivo [!DNL profile.cfg] del perfil con el que desea utilizar [!DNL Transform]. El conjunto de datos vuelve a procesarse tras completar estos pasos.

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparece la ventana [!DNL profile.cfg].

   1. En la ventana [!DNL profile.cfg], haga clic con el botón derecho en **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para añadir el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL Transform]
   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
