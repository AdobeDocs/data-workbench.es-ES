---
description: La funcionalidad de transformación se ejecuta en un equipo FSU de Insight Server para permitir la exportación de datos de origen de registro para su uso por otras aplicaciones.
title: Configuración de la transformación
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configuración de la transformación{#configuring-transform}

{{eol}}

La funcionalidad de transformación se ejecuta en un equipo FSU de Insight Server para permitir la exportación de datos de origen de registro para su uso por otras aplicaciones.

[!DNL Transform] se puede leer [!DNL .vsl] archivos, archivos de registro, archivos XML y datos ODBC y exportar los datos como [!DNL .vsl] archivos, archivos de texto o archivos de texto delimitados que se pueden utilizar en rutinas de carga del almacén de datos, agencias de auditoría u otros destinos. La extracción y transformación de datos se puede realizar de forma continua o programada. Cada [!DNL Insight Server] La FSU que proporciona resultados de datos de eventos alterados debe ejecutarse [!DNL Transform].

>[!NOTE]
>
>Normalmente, [!DNL Transform] está instalado en un [!DNL Insight Server] FSU. Sin embargo, la implementación puede requerir la instalación en un [!DNL Insight Server] DPU Para obtener más información, póngase en contacto con el Adobe.

Para obtener información sobre los requisitos del sistema para instalar, configurar y operar [!DNL Transform], consulte la *Requisitos mínimos del sistema* documento.

Adobe distribuye el [!DNL Transform] como un perfil dentro de la función [!DNL .zip] para [!DNL Insight Server] paquete de versión. La variable [!DNL Transform] perfil es un perfil interno que proporciona funcionalidad adicional a [!DNL Insight Server]. Al igual que con todos los demás perfiles internos proporcionados por Adobe, el perfil no debe cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

El perfil consta de los siguientes archivos:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* un archivo de inclusión de conjunto de datos de procesamiento de registros

Todos estos archivos se encuentran en la [!DNL Dataset] para el perfil.

**Para instalar el [!DNL Transform] perfil en[!DNL Insight Server]**

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado [!DNL Insight] y establece una conexión entre [!DNL Insight] y [!DNL Insight Server] en el que está instalando [!DNL Transform]. Si no lo ha hecho, consulte el [!DNL Insight] Guía del usuario*.

1. Abra el [!DNL .zip] para [!DNL Insight Server] libere el paquete y abra el [!DNL Profiles] carpeta dentro de [!DNL .zip] archivo.
1. Copie el [!DNL Transform] a la [!DNL Profiles] en su [!DNL Insight Server] directorio de instalación. Desea terminar con un [!DNL ...\Profiles\Transform] en su [!DNL Insight Server] como se muestra en el siguiente ejemplo.

   ![Información sobre los pasos](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Si ha seguido todos los pasos para instalar [!DNL Insight Server] (consulte [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), ya puede tener un [!DNL Transform] en el directorio Profiles .

1. Siga estos pasos para actualizar el [!DNL profile.cfg] para el perfil con el que desea utilizar [!DNL Transform]. El conjunto de datos vuelve a procesarse tras completar estos pasos.

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La variable [!DNL profile.cfg] se abre.

   1. En el [!DNL profile.cfg]ventana, clic con el botón derecho **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para añadir el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL Transform]
   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
