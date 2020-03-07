---
description: Un servidor de procesamiento de Insight es idéntico a un servidor maestro de Insight Server excepto por el contenido de su directorio Components.
solution: Insight
title: Instalación y configuración de los servidores de perspectiva de procesamiento
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalación y configuración de los servidores de perspectiva de procesamiento{#installing-and-configuring-the-processing-insight-servers}

Un servidor de procesamiento de Insight es idéntico a un servidor maestro de Insight Server excepto por el contenido de su directorio Components.

El directorio Componentes de un proceso [!DNL Insight Server] contiene un conjunto especial de archivos configurados específicamente para su procesamiento [!DNL Insight Servers]. Estos archivos se derivan del directorio Componentes para Servidores de Procesamiento del maestro [!DNL Insight Server].

Al instalar un procesamiento [!DNL Insight Server], se hace lo siguiente para configurar el directorio Componentes:

1. Elimine el directorio Componentes original del proceso [!DNL Insight Server].
1. Cambie el nombre del directorio Componentes para servidores de procesamiento a Componentes.
1. Modifique el [!DNL Synchronize.cfg] directorio Componentes para que señale al maestro [!DNL Insight Server].

**Para instalar y configurar un procesamiento[!DNL Insight Server]**

1. Instale los [!DNL Insight Server] archivos de programa como se describe en [Instalación de los archivos](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)de programa de Insight Server. Asegúrese de duplicar la estructura de directorio que se utilizó en el maestro [!DNL Insight Server]. Por ejemplo, si [!DNL Insight Server] está instalado [!DNL C:\Adobe\Server] en el maestro [!DNL Insight Server], debe instalarlo [!DNL C:\Adobe\Server] también en el procesamiento [!DNL Insight Servers] .
1. Instale el certificado digital emitido por Adobe para este procesamiento en particular [!DNL Insight Server]. Consulte [Descarga e instalación de certificados](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) digitales para obtener instrucciones.
1. Con el Explorador de Windows, haga lo siguiente en el procesamiento [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. Cambie el nombre de la [!DNL Components for Processing Servers] carpeta a Componentes.

1. Con un editor de texto como Bloc de notas, abra el [!DNL Synchronize.cfg] archivo en el directorio Componentes del proceso [!DNL Insight Server].
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
1. Inicie el [!DNL Insight Server] como se describe en [Registro de Insight Server como un servicio](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)de Windows.

   Ha completado la instalación del [!DNL Insight Server] clúster. A continuación, configure el perfil del conjunto de datos para que se ejecute en el clúster como se describe en la siguiente sección.

