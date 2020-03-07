---
description: El directorio Dataset incluye archivos adicionales que son necesarios para el funcionamiento del software o proporcionan funcionalidad adicional para la implementación de Adobe.
solution: Analytics
title: Otros archivos
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Otros archivos{#other-files}

El directorio Dataset incluye archivos adicionales que son necesarios para el funcionamiento del software o proporcionan funcionalidad adicional para la implementación de Adobe.

* **[!DNL Client.cfg:]** El [!DNL Client.cfg] archivo del directorio Dataset del [!DNL Base] perfil es necesario para el funcionamiento del software. No elimine ni modifique ninguno de los parámetros del [!DNL Client.cfg] archivo.

* **[!DNL Cluster.cfg:]** El [!DNL Cluster.cfg] archivo del directorio Dataset del [!DNL Base] perfil es necesario para el funcionamiento del software. En el [!DNL Cluster.cfg] archivo, debe modificar solo el parámetro Normalizar servidor si está configurando un conjunto de datos para que se procese en un clúster de servidores del área de trabajo de datos. Para obtener instrucciones sobre cómo modificar el parámetro Normalizar servidor, consulte [Creación de un servidor de normalización centralizado para un clúster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]y[!DNL Insight Transform Mode.cfg]:**Si utiliza la funcionalidad de transformación, tiene dos archivos de configuración adicionales, Área de trabajo de datos[!DNL Transform.cfg]y Área de trabajo de datos[!DNL TransformMode.cfg], en el directorio Conjunto de datos del[!DNL Transform]perfil. Para obtener información sobre estos archivos y sus parámetros, consulte[Transformar funcionalidad](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Archivo **PAServer.cfg** . Si desea enviar trabajos de clúster de Predictive Analytics a los servidores de Insight, deberá configurar el [!DNL PAServer.cfg] archivo para gestionar los envíos de clúster del lado del servidor.
El perfil personalizado debe heredar el [!DNL PAServer.cfg] del perfil de Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Establezca un *servidor* maestro en este archivo y guarde el [!DNL PAServer.cfg] en el sitio de implementación.   >
   >
   >
   ```>
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```  >
   >



