---
description: Siga estos pasos para actualizar a Data Workbench v6.1 desde la instalación de Data Workbench v6.0x.
title: Actualización de Data Workbench de 6.0 a 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 1%

---

# Actualización de Data Workbench de 6.0 a 6.1{#data-workbench-to-upgrade}

Siga estos pasos para actualizar a Data Workbench v6.1 desde la instalación de Data Workbench v6.0x.

**Paso 1**:  [Actualización del servidor](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Paso 2**:  [Actualización del servidor de informes](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Paso 3**:  [Actualización de cliente](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Los componentes de servidor, servidor de informes y cliente se actualizan para que se ejecuten en sistemas operativos Windows de 64 bits.

## Actualización del servidor {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Siga estos pasos para actualizar los componentes **[!UICONTROL Server v6.1]**:

1. Con el perfil **[!UICONTROL Software and Docs]**, abra el espacio de trabajo **[!UICONTROL Start Here]** y descargue todos los paquetes de servidor necesarios en una carpeta local.

   * Descargue las carpetas zip **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** y extraiga todos los archivos.

      El paquete del servidor incluye carpetas **[!UICONTROL Lookup]** y **[!UICONTROL Profile]** con perfiles **[!UICONTROL Base]** y **[!UICONTROL Transform]** para actualizar el servidor.

      * Descargue las carpetas **[!UICONTROL Profiles]** .
      * Descargue las carpetas **[!UICONTROL Lookup]** .
      * Descargue el paquete **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** .
      * Descargue los archivos **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** y **[!UICONTROL Dashboard]** adicionales que necesite para su sistema.

1. Detenga el servicio **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. Desde el paquete **[!UICONTROL Server]** descargado:

   1. Reemplace la carpeta [!DNL Server\Bin] para actualizar los [!DNL InsightServer64.exe] y los archivos de soporte.

   1. Reemplace la carpeta [!DNL Server\Profiles]. Puede sobrescribir todos los archivos.
   1. Actualice la carpeta [!DNL Server\Lookups]. Desea añadir los archivos recién descargados a los archivos personalizados que ya se encuentran en la carpeta .
   1. Reemplace la carpeta [!DNL Server\Software] para actualizar [!DNL Insight.exe] y [!DNL ReportServer.exe]
   1. Actualice la carpeta [!DNL Server\Scripts] para actualizar [!DNL TnTSend.exe].

1. Si utiliza **[!UICONTROL DeviceAtlas]**, deberá [actualizar el paquete](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) ubicado en la carpeta [!DNL Server\Lookups].

1. Configure el archivo [!DNL Profile.cfg] para asegurarse de que el vector se actualice para reflejar el número de elementos para cada perfil.

   Por ejemplo, para habilitar el perfil **[!UICONTROL Predictive Analytics]** deberá actualizar esta configuración.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure y guarde el archivo PAServer.cfg para la función Análisis predictivo .

   Si desea enviar trabajos de Predictive Analytics a los servidores, deberá configurar el archivo [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] para administrar los envíos de clúster del lado del servidor.

   El perfil personalizado debe heredar la configuración del perfil de configuración de Predictive Analytics, lo que le permite configurar y guardar el archivo [!DNL PAServer.cfg] en función de la implementación del sitio.

1. Defina las **[!UICONTROL Log Source ID]**.

   El **[!UICONTROL Recording of Rows per Log Source]** se agregó en **[!UICONTROL v6.04]** y se definió en el archivo [!DNL Log Processing.cfg] del perfil personalizado agregando un **[!UICONTROL Log Source ID]** con nombre único.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Si no tiene definido el ID de fuente de registro, obtendrá el siguiente error:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Como el [!DNL EventMessages.dll] se ha actualizado, es necesario que cancele el registro y, a continuación, registre el **[!UICONTROL Adobe Insight Server]** en todo el clúster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Inicie el servicio **[!UICONTROL Adobe Insight Server]** en todo el clúster.

La instalación del servidor ya ha finalizado.

## Actualización del servidor de informes {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Antes de actualizar a **[!UICONTROL Report Server v6.1]**, primero debe actualizar a **[!UICONTROL Server v6.1]**.

1. Usando el perfil **[!UICONTROL Software and Docs]** , descargue **[!UICONTROL v6.1]** del paquete **[!UICONTROL Report Server]** en una carpeta local.

1. Copie **[!UICONTROL Report Server 6.1]** del paquete descargado y reemplace los paquetes de perfil.

   >[!NOTE]
   >
   >El archivo [!DNL Insight.zbin] de la carpeta [!DNL install] es un archivo de copia de seguridad utilizado para la localización y debe estar presente en el directorio [!DNL install]. Este archivo u otros [!DNL .zbin] archivos se utilizarán según la configuración de línea de comandos que se pase al iniciar.

1. (opcional) Actualmente, Data Workbench admite inglés (-en-us) y chino (-zh-cn). Debe configurar una fuente para que admita caracteres de byte único y doble:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   El sistema operativo Windows también debe tener instaladas las fuentes enumeradas.

1. Configure [!DNL Report Server v6.1] para la localización.

   1. Detenga el servicio **[!UICONTROL Adobe Insight Report Server]**.
   1. Inicie un símbolo del sistema como &quot;Administrador&quot;.
   1. Vaya a la carpeta [!DNL install] del servidor de informes.
   1. Elimine el servicio Servidor de informes con el siguiente comando:

      ```
      ReportServer.exe /unregserver
      ```

   1. Inicie el servicio en función de la configuración de idioma:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Para comprobar que el servidor de informes se está ejecutando con la configuración correcta, abra **[!UICONTROL Windows Service Manager]** y haga clic con el botón derecho **[!UICONTROL Adobe Insight Report Server - Properties]**. La ruta al ejecutable mostrará la configuración actualizada de la línea de comandos.

La instalación del servidor de informes ya ha finalizado.

## Actualización del cliente {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Antes de actualizar a **[!UICONTROL Client v6.1]**, el administrador debe actualizar primero a **[!UICONTROL Insight Server v6.1.]**

1. Inicie [!DNL Insight.exe] pero no se conecte a ningún perfil.
1. Edite el archivo [!DNL Insight.cfg].

   ```
   Update Software = bool: true
   ```

1. Conéctese a su perfil.

   Permita que el cliente se sincronice con el servidor y su cliente se actualizará con los perfiles de cliente, ejecutables y archivos de configuración v6.1 más recientes.

   >[!NOTE]
   >
   >El archivo [!DNL Insight.zbin] de la carpeta [!DNL install] es un archivo de copia de seguridad que se utiliza para la localización y que debe estar presente. Este archivo u otros [!DNL .zbin] archivos se utilizarán según la configuración de línea de comandos que se pase al iniciar.

   Consulte [configuración de idiomas localizados](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) para añadir el archivo [!DNL insight.zbin] necesario para la configuración localizada.

**Configuración de cliente adicional**

Antes de configurar [!DNL Insight.exe] y los archivos de soporte, debe salir de la aplicación cliente.

Para instalar chino simplificado:

1. Cree un acceso directo que pase la configuración de la línea de comandos al archivo [!DNL Insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para que admita caracteres de fuente de byte único y doble.

   Actualmente, Data Workbench admite inglés y chino simplificado. Puede seleccionar fuentes para admitir ambos idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   El sistema operativo Windows también debe tener instaladas las fuentes solicitadas.

1. Inicie el acceso directo que ha creado para sincronizar perfiles y el archivo actualizado . [!DNL zbin] archivo.

Para utilizar el Editor de métodos de entrada (IME).

IME permite introducir caracteres internacionales.

1. Actualice el archivo [!DNL Insight.cfg] con esta configuración:

   ```
   Localized IME = bool: true
   ```

1. Inicie el acceso directo que ha creado para sincronizar perfiles y el archivo [!DNL .zbin] actualizado.

La instalación del cliente ya ha finalizado.
