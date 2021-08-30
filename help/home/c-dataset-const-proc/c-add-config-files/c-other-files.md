---
description: El directorio Dataset incluye archivos adicionales que son necesarios para el funcionamiento del software o proporcionan funcionalidad adicional para la implementación del Adobe.
title: Otros archivos
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Otros archivos{#other-files}

El directorio Dataset incluye archivos adicionales que son necesarios para el funcionamiento del software o proporcionan funcionalidad adicional para la implementación del Adobe.

* **[!DNL Client.cfg:]** El  [!DNL Client.cfg] archivo dentro del directorio Dataset para el  [!DNL Base] perfil es necesario para el funcionamiento del software. No elimine ni modifique ninguno de los parámetros del archivo [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** El  [!DNL Cluster.cfg] archivo dentro del directorio Dataset para el  [!DNL Base] perfil es necesario para el funcionamiento del software. En el archivo [!DNL Cluster.cfg], debe modificar solo el parámetro Normalize Server si está configurando un conjunto de datos para que se procese en un clúster de servidores de Data Workbench. Para obtener instrucciones para modificar el parámetro Normalize Server, consulte [Creación de un Servidor de Normalización Centralizado para un Clúster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]y  [!DNL Insight Transform Mode.cfg]:** si utiliza la funcionalidad de transformación, tiene dos archivos de configuración adicionales, Data Workbench  [!DNL Transform.cfg] y Data Workbench  [!DNL TransformMode.cfg], en el directorio Dataset del  [!DNL Transform] perfil. Para obtener información sobre estos archivos y sus parámetros, consulte [Funcionalidad de transformación](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* El archivo **PAServer.cfg**. Si desea enviar trabajos de agrupación en clúster de Predictive Analytics a servidores de Insight, deberá configurar el archivo [!DNL PAServer.cfg] para gestionar los envíos de clúster del lado del servidor.
El perfil personalizado debe heredar el [!DNL PAServer.cfg] del perfil de Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Establezca un *Master Server* en este archivo y guarde el [!DNL PAServer.cfg] en el sitio de implementación.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
