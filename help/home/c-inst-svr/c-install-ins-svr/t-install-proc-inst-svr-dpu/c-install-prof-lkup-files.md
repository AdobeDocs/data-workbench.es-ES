---
description: Los perfiles y archivos de búsqueda que Adobe ha desarrollado para su aplicación en particular son perfiles internos que proporcionan las métricas, dimensiones y espacios de trabajo que permiten el análisis del conjunto de datos.
title: Instalación de perfiles y archivos de búsqueda
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Instalación de perfiles y archivos de búsqueda{#installing-profiles-and-lookup-files}

Los perfiles y archivos de búsqueda que Adobe ha desarrollado para su aplicación en particular son perfiles internos que proporcionan las métricas, dimensiones y espacios de trabajo que permiten el análisis del conjunto de datos.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, estos perfiles no deben cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

Adobe distribuye los archivos de perfil y búsqueda de la aplicación como un archivo [!DNL .zip]. Cada archivo zip recibe el nombre de la aplicación cuyo perfil y archivos de búsqueda contiene. (Por ejemplo, [!DNL Site52.zip] contiene los archivos de perfil del sitio v5.2.) El archivo [!DNL .zip] contiene dos carpetas ( [!DNL Lookups] y [!DNL Profiles]).

>[!NOTE]
>
>Si todavía no tiene el archivo de instalación que contiene los perfiles y los archivos de búsqueda de la aplicación, descárguelos del sitio FTP de Adobe antes de empezar.

Debe instalar el perfil y sus archivos de búsqueda en el equipo [!DNL Insight Server] en el que procesa y ejecuta el perfil del conjunto de datos. Si está ejecutando un clúster [!DNL Insight Server], debe instalar los archivos en el servidor maestro. Para obtener información sobre los perfiles de conjuntos de datos, consulte la *Guía de configuración de conjuntos de datos*.

**Para instalar perfiles para la aplicación de Adobe**

1. Abra la carpeta [!DNL Profiles] del archivo [!DNL .zip] que le proporcionó el Adobe.

1. Copie todas las carpetas de la carpeta [!DNL Profiles] del archivo [!DNL .zip] a la carpeta [!DNL Profiles] en el directorio de instalación de [!DNL Insight Server]. Desea terminar con las carpetas  [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]* en su [!DNL Insight Server] como se muestra en el siguiente ejemplo. Los nombres reales de perfil pueden diferir.

   ![](assets/win_installprofiles.png)

1. Vaya a la carpeta  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* en el directorio donde instaló [!DNL Insight Server] y busque el archivo [!DNL profile.cfg] en este directorio.

   >[!NOTE]
   >
   >Si va a instalar perfiles por primera vez, puede utilizar el perfil de muestra proporcionado como perfil de conjunto de datos. Puede encontrar el archivo [!DNL profile.cfg] (puede llamarse algo así como [!DNL profile.cfg.offline]) para el perfil de muestra dentro de la carpeta [!DNL Profiles\Sample] en su directorio de instalación [!DNL Insight Server].

1. Abra el archivo [!DNL profile.cfg] utilizando un editor de texto como el Bloc de notas y haga lo siguiente:

   1. Añada entradas para los perfiles internos en el vector Directorios . Los nombres de perfil corresponden a los nombres de los directorios que copió en la carpeta [!DNL Profiles] del equipo [!DNL Insight Server].

   1. Actualice el número de directorios según corresponda.
   1. Agregue el nombre común del servidor a la línea Nombre común de este archivo, como se indica a continuación:

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
      >El *serverCommonName* que especifique para el Nombre común en el archivo [!DNL profile.cfg] corresponde al nombre común del servidor para el equipo [!DNL Insight Server] en el que está procesando y ejecutando el perfil del conjunto de datos. Para obtener instrucciones para actualizar [!DNL profile.cfg] de modo que el perfil del conjunto de datos se ejecute en un clúster [!DNL Insight Server], consulte [Clústeres de Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Guarde el archivo. Asegúrese de guardar el archivo como [!DNL profile.cfg] si tiene un nombre diferente.

**Para instalar los archivos de búsqueda para la aplicación de Adobe**

1. Abra la carpeta [!DNL Lookups] del archivo [!DNL .zip] que le proporcionó el Adobe.

1. Copie todas las carpetas de la carpeta [!DNL Lookups] del archivo [!DNL .zip] a la carpeta [!DNL Lookups] en el directorio de instalación de [!DNL Insight Server]. Desea terminar con las carpetas  [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]* en su [!DNL Insight Server] como se muestra en el siguiente ejemplo. Los nombres reales de perfil pueden diferir.

   ![](assets/win_installLookups.png)
