---
description: Un servidor de procesamiento de Insight es idéntico al servidor maestro de Insight Server, excepto el contenido de su directorio Componentes.
title: Instalación y configuración del procesamiento de Master Insight Server
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Instalación y configuración del procesamiento de Master Insight Server{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

Un servidor de procesamiento de Insight es idéntico al servidor maestro de Insight Server, excepto el contenido de su directorio Componentes.

El directorio Componentes de un procesamiento [!DNL Insight Server] contiene un conjunto especial de archivos que están configurados específicamente para su procesamiento [!DNL Insight Servers]. Estos archivos se derivan del directorio Componentes para servidores de procesamiento del directorio maestro [!DNL Insight Server].

Al instalar un procesamiento [!DNL Insight Server], haga lo siguiente para configurar su directorio Componentes :

1. Eliminar el directorio de componentes original en el procesamiento [!DNL Insight Server].
1. Cambie el nombre del directorio Componentes para servidores de procesamiento a Componentes.
1. Modifique el [!DNL Synchronize.cfg] en el directorio Componentes para que apunte al maestro [!DNL Insight Server].

**Para instalar y configurar un procesamiento[!DNL Insight Server]**

1. Instale el [!DNL Insight Server] archivos de programa como se describe en [Instalación de los archivos de programa de Insight Server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Asegúrese de duplicar la estructura de directorio que se utilizó en el maestro [!DNL Insight Server]. Por ejemplo, si [!DNL Insight Server] está instalado en [!DNL C:\Adobe\Server] en el patrón [!DNL Insight Server], debe instalarlo en [!DNL C:\Adobe\Server] en el proceso [!DNL Insight Servers] también.
1. Instale el certificado digital emitido por el Adobe para este procesamiento en particular [!DNL Insight Server]. Consulte [Descarga e instalación de certificados digitales](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) para obtener instrucciones.
1. Con el Explorador de Windows, haga lo siguiente en el procesamiento [!DNL Insight Server]:

   1. Elimine el **[!UICONTROL Components]** carpeta.
   1. Cambiar el nombre de [!DNL Components for Processing Servers] a Componentes.

1. Con un editor de texto como Bloc de notas, abra [!DNL Synchronize.cfg] en el directorio Componentes del procesamiento [!DNL Insight Server].
1. Añadir la dirección IP del maestro (principal) [!DNL Insight Server] a la segunda línea de este archivo como se muestra en el siguiente fragmento de archivo. No edite nada más en este archivo.

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
1. Inicie el [!DNL Insight Server] tal como se describe en [Registro de Insight Server como un servicio de Windows](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Ya ha completado la instalación de su [!DNL Insight Server] clúster. A continuación, configure el perfil del conjunto de datos para que se ejecute en el clúster como se describe en la siguiente sección.
