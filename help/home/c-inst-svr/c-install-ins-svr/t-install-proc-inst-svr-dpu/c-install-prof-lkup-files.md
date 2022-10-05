---
description: Los perfiles y archivos de búsqueda que Adobe ha desarrollado para su aplicación en particular son perfiles internos que proporcionan las métricas, dimensiones y espacios de trabajo que permiten el análisis del conjunto de datos.
title: Instalación de perfiles y archivos de búsqueda
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# Instalación de perfiles y archivos de búsqueda{#installing-profiles-and-lookup-files}

{{eol}}

Los perfiles y archivos de búsqueda que Adobe ha desarrollado para su aplicación en particular son perfiles internos que proporcionan las métricas, dimensiones y espacios de trabajo que permiten el análisis del conjunto de datos.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, estos perfiles no deben cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

Adobe distribuye los archivos de perfil y búsqueda de la aplicación como un [!DNL .zip] archivo. Cada archivo zip recibe el nombre de la aplicación cuyo perfil y archivos de búsqueda contiene. (Por ejemplo, [!DNL Site52.zip] contiene los archivos de perfil del sitio v5.2.) La variable [!DNL .zip] contiene dos carpetas ( [!DNL Lookups] y [!DNL Profiles]).

>[!NOTE]
>
>Si todavía no tiene el archivo de instalación que contiene los perfiles y los archivos de búsqueda de la aplicación, descárguelos del sitio FTP de Adobe antes de empezar.

Debe instalar el perfil y sus archivos de búsqueda en la variable [!DNL Insight Server] máquina en la que se procesa y ejecuta el perfil del conjunto de datos. Si está ejecutando un [!DNL Insight Server] , debe instalar los archivos en el servidor maestro. Para obtener información sobre los perfiles de conjuntos de datos, consulte la *Guía de configuración de conjuntos de datos*.

**Para instalar perfiles para la aplicación de Adobe**

1. Abra el [!DNL Profiles] de [!DNL .zip] archivo proporcionado por Adobe.

1. Copie todas las carpetas dentro de la [!DNL Profiles] en la carpeta [!DNL .zip] a [!DNL Profiles] en su [!DNL Insight Server] directorio de instalación. Desea terminar con [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>* carpetas en su [!DNL Insight Server] como se muestra en el siguiente ejemplo. Los nombres reales de perfil pueden diferir.

   ![](assets/win_installprofiles.png)

1. Vaya a la  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* carpeta en el directorio donde instaló [!DNL Insight Server] y busque la variable [!DNL profile.cfg] en este directorio.

   >[!NOTE]
   >
   >Si va a instalar perfiles por primera vez, puede utilizar el perfil de muestra proporcionado como perfil de conjunto de datos. Puede encontrar la variable [!DNL profile.cfg] (puede llamarse algo como [!DNL profile.cfg.offline]) para el perfil de muestra dentro de la variable [!DNL Profiles\Sample] en su [!DNL Insight Server] directorio de instalación.

1. Abra el [!DNL profile.cfg] con un editor de texto como Bloc de notas y haga lo siguiente:

   1. Añada entradas para los perfiles internos en el vector Directorios . Los nombres de perfil corresponden a los nombres de los directorios que ha copiado en la [!DNL Profiles] en la carpeta [!DNL Insight Server] máquina.

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
      >La variable *serverCommonName* que especifique para el Nombre común en la sección [!DNL profile.cfg] corresponde al nombre común del servidor para la variable [!DNL Insight Server] equipo en el que está procesando y ejecutando el perfil del conjunto de datos. Para obtener instrucciones para actualizar [!DNL profile.cfg] para que el perfil del conjunto de datos se ejecute en un [!DNL Insight Server] clúster, consulte [Clústeres de Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Guarde el archivo. Asegúrese de guardar el archivo como [!DNL profile.cfg] si su nombre es distinto.

**Para instalar los archivos de búsqueda para la aplicación de Adobe**

1. Abra el [!DNL Lookups] de [!DNL .zip] archivo proporcionado por Adobe.

1. Copie todas las carpetas dentro de la [!DNL Lookups] en la carpeta [!DNL .zip] a [!DNL Lookups] en su [!DNL Insight Server] directorio de instalación. Desea terminar con [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>* carpetas en su [!DNL Insight Server] como se muestra en el siguiente ejemplo. Los nombres reales de perfil pueden diferir.

   ![](assets/win_installLookups.png)
