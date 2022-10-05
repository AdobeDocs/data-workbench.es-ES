---
description: El directorio Dataset incluye archivos adicionales que son necesarios para el funcionamiento del software o proporcionan funcionalidad adicional para la implementación del Adobe.
title: Otros archivos
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Otros archivos{#other-files}

{{eol}}

El directorio Dataset incluye archivos adicionales que son necesarios para el funcionamiento del software o proporcionan funcionalidad adicional para la implementación del Adobe.

* **[!DNL Client.cfg:]** La variable [!DNL Client.cfg] dentro del directorio de conjunto de datos para la variable [!DNL Base] para el funcionamiento del software. No elimine ni modifique ninguno de los parámetros de la sección [!DNL Client.cfg] archivo.

* **[!DNL Cluster.cfg:]** La variable [!DNL Cluster.cfg] dentro del directorio de conjunto de datos para la variable [!DNL Base] para el funcionamiento del software. En el [!DNL Cluster.cfg] , debe modificar solo el parámetro Normalize Server si está configurando un conjunto de datos para que se procese en un clúster de servidores de Data Workbench. Para obtener instrucciones para modificar el parámetro Normalize Server, consulte [Creación de un Servidor de Normalización Centralizado para un Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]y [!DNL Insight Transform Mode.cfg]:** Si utiliza la funcionalidad de transformación, tiene dos archivos de configuración adicionales, Data Workbench [!DNL Transform.cfg] y Data Workbench [!DNL TransformMode.cfg], en el directorio del conjunto de datos para la variable [!DNL Transform] perfil. Para obtener información sobre estos archivos y sus parámetros, consulte [Funcionalidad de transformación](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* La variable **PAServer.cfg** archivo. Si desea enviar trabajos de agrupación en clúster de Predictive Analytics a servidores de Insight, deberá configurar la variable [!DNL PAServer.cfg] para administrar los envíos de clustering del lado del servidor.
El perfil personalizado debe heredar el [!DNL PAServer.cfg] del perfil de Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Configure un *Servidor maestro* en este archivo y guarde la variable [!DNL PAServer.cfg] al sitio de implementación.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
