---
description: Un servidor de Insight de procesamiento es idéntico a un servidor de Insight maestro, excepto por el contenido de su directorio Componentes.
title: Instalación y configuración del procesamiento de Master Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Instalación y configuración del procesamiento de Master Insight Server{#installing-and-configuring-the-processing-insight-servers}

Un servidor de Insight de procesamiento es idéntico a un servidor de Insight maestro, excepto por el contenido de su directorio Componentes.

El directorio Componentes de un [!DNL Insight Server] de procesamiento contiene un conjunto especial de archivos que están configurados específicamente para procesar [!DNL Insight Servers]. Estos archivos se derivan del directorio Componentes para servidores de procesamiento del [!DNL Insight Server] maestro.

Cuando instale un [!DNL Insight Server] de procesamiento, haga lo siguiente para configurar su directorio Componentes:

1. Elimine el directorio de componentes original en el [!DNL Insight Server] de procesamiento.
1. Cambie el nombre del directorio Componentes para servidores de procesamiento a Componentes.
1. Modifique [!DNL Synchronize.cfg] en el directorio Componentes para que apunte al [!DNL Insight Server] maestro.

**Para instalar y configurar un procesamiento[!DNL Insight Server]**

1. Instale los archivos de programa [!DNL Insight Server] como se describe en [Instalación de los archivos de programa de Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Asegúrese de duplicar la estructura de directorio que se utilizó en el [!DNL Insight Server] maestro. Por ejemplo, si [!DNL Insight Server] está instalado en [!DNL C:\Adobe\Server] en el [!DNL Insight Server] maestro, también debe instalarlo en [!DNL C:\Adobe\Server] en el [!DNL Insight Servers] de procesamiento.
1. Instale el certificado digital emitido por el Adobe para este procesamiento en particular [!DNL Insight Server]. Consulte [Descarga e instalación de certificados digitales](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) para obtener instrucciones.
1. Con el Explorador de Windows, haga lo siguiente en el procesamiento [!DNL Insight Server]:

   1. Elimine la carpeta **[!UICONTROL Components]**.
   1. Cambie el nombre de la carpeta [!DNL Components for Processing Servers] a Componentes.

1. Con un editor de texto como el Bloc de notas, abra el archivo [!DNL Synchronize.cfg] en el directorio Componentes del [!DNL Insight Server] de procesamiento.
1. Agregue la dirección IP del maestro (principal) [!DNL Insight Server] a la segunda línea de este archivo como se muestra en el siguiente fragmento de archivo. No edite nada más en este archivo.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Guarde el archivo.
1. Inicie [!DNL Insight Server] tal como se describe en [Registro de Insight Server como un servicio de Windows](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Ya ha completado la instalación del clúster [!DNL Insight Server]. A continuación, configure el perfil del conjunto de datos para que se ejecute en el clúster como se describe en la siguiente sección.
