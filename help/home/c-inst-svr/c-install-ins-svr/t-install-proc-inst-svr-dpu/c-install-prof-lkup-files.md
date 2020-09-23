---
description: Los perfiles y archivos de búsqueda que Adobe ha desarrollado para una aplicación en particular son perfiles internos que proporcionan las métricas, dimensiones y espacios de trabajo que permiten la análisis de su conjunto de datos.
solution: Analytics
title: Instalación de perfiles y archivos de búsqueda
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---


# Instalación de perfiles y archivos de búsqueda{#installing-profiles-and-lookup-files}

Los perfiles y archivos de búsqueda que Adobe ha desarrollado para una aplicación en particular son perfiles internos que proporcionan las métricas, dimensiones y espacios de trabajo que permiten la análisis de su conjunto de datos.

Al igual que todos los demás perfiles internos proporcionados por el Adobe, estos perfiles no deben modificarse. Toda la personalización debe producirse en el conjunto de datos o en perfiles específicos de funciones u otros perfiles que cree.

Adobe distribuye los archivos de perfil y búsqueda de la aplicación como un [!DNL .zip] archivo. Cada archivo zip recibe el nombre de la aplicación cuyo perfil y archivos de búsqueda contiene. (Por ejemplo, [!DNL Site52.zip] contiene los archivos de perfil para el sitio v5.2.) El [!DNL .zip] archivo contiene dos carpetas ( [!DNL Lookups] y [!DNL Profiles]).

>[!NOTE]
>
>Si todavía no tiene el archivo de instalación que contiene los perfiles y los archivos de búsqueda de la aplicación, descárguelos del sitio FTP de Adobe antes de comenzar.

Debe instalar el perfil y sus archivos de búsqueda en el [!DNL Insight Server] equipo en el que procesa y ejecuta el perfil del conjunto de datos. Si está ejecutando un [!DNL Insight Server] clúster, debe instalar los archivos en el servidor maestro. Para obtener información sobre los perfiles de conjuntos de datos, consulte la Guía *de configuración de* conjuntos de datos.

**Para instalar perfiles para la aplicación Adobe**

1. Abra la [!DNL Profiles] carpeta del [!DNL .zip] archivo proporcionado por Adobe.

1. Copie todas las carpetas de la [!DNL Profiles] carpeta del [!DNL .zip] archivo en la [!DNL Profiles] carpeta del directorio [!DNL Insight Server] de instalación. Desea terminar con  [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* carpetas en el [!DNL Insight Server] ejemplo siguiente. Los nombres de perfiles reales pueden diferir.

   ![](assets/win_installprofiles.png)

1. Vaya a la carpeta&lt; [!DNL Profiles\]*>[!DNL dataset profile name]del* directorio donde instaló [!DNL Insight Server] y busque el [!DNL profile.cfg] archivo en este directorio.

   >[!NOTE]
   >
   >Si va a instalar perfiles por primera vez, puede utilizar el perfil de muestra proporcionado como perfil de conjunto de datos. Puede encontrar el [!DNL profile.cfg] archivo (puede llamarse algo así como [!DNL profile.cfg.offline]) para el perfil Ejemplo dentro de la [!DNL Profiles\Sample] carpeta en el directorio [!DNL Insight Server] de instalación.

1. Abra el [!DNL profile.cfg] archivo con un editor de texto como Bloc de notas y haga lo siguiente:

   1. Añada entradas para los perfiles internos en el vector Directorios. Los nombres de los perfiles corresponden a los nombres de los directorios que ha copiado en la [!DNL Profiles] carpeta del [!DNL Insight Server] equipo.

   1. Actualice el número de directorios según corresponda.
   1. Añada el nombre común del servidor a la línea Nombre común de este archivo, como se indica a continuación:

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >El *serverCommonName* que especifique para el Nombre común en el [!DNL profile.cfg] archivo corresponde al nombre común del servidor para el [!DNL Insight Server] equipo en el que está procesando y ejecutando el perfil de conjunto de datos. Para obtener instrucciones sobre cómo actualizar [!DNL profile.cfg] para que el perfil del conjunto de datos se ejecute en un [!DNL Insight Server] clúster, consulte Clústeres [de](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)Insight Server.

1. Guarde el archivo. Asegúrese de guardar el archivo como [!DNL profile.cfg] si su nombre fuera diferente.

**Para instalar los archivos de búsqueda de la aplicación Adobe**

1. Abra la [!DNL Lookups] carpeta del [!DNL .zip] archivo proporcionado por Adobe.

1. Copie todas las carpetas de la [!DNL Lookups] carpeta del [!DNL .zip] archivo en la [!DNL Lookups] carpeta del directorio [!DNL Insight Server] de instalación. Desea terminar con  [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* carpetas en el [!DNL Insight Server] ejemplo siguiente. Los nombres de perfiles reales pueden diferir.

   ![](assets/win_installLookups.png)

