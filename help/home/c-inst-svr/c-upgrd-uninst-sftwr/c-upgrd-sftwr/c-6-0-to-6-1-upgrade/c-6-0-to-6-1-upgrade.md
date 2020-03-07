---
description: Siga estos pasos para actualizar a la versión 6.1 del área de trabajo de datos desde la instalación v6.0x del área de trabajo de datos.
solution: Analytics
title: Actualización del área de trabajo de datos 6.0 a 6.1
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Actualización del área de trabajo de datos 6.0 a 6.1{#data-workbench-to-upgrade}

Siga estos pasos para actualizar a la versión 6.1 del área de trabajo de datos desde la instalación v6.0x del área de trabajo de datos.

**Paso 1**: Actualización [del servidor](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Paso 2**: Actualización [del servidor de informes](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Paso 3**: Actualización [del cliente](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Los componentes de servidor, servidor de informes y cliente se actualizan para ejecutarse en sistemas operativos Windows de 64 bits.

## Actualización del servidor {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Siga estos pasos para actualizar los **[!UICONTROL Server v6.1]** componentes:

1. Con el **[!UICONTROL Software and Docs]** perfil, abra el **[!UICONTROL Start Here]** espacio de trabajo y descargue todos los paquetes de servidor necesarios en una carpeta local.

   * Descargue **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** carpetas zip y extraiga todos los archivos.

      El paquete Servidor incluye **[!UICONTROL Lookup]** y **[!UICONTROL Profile]** carpetas con **[!UICONTROL Base]** y **[!UICONTROL Transform]** perfiles para actualizar el servidor.

      * Descargue las **[!UICONTROL Profiles]** carpetas.
      * Descargue las **[!UICONTROL Lookup]** carpetas.
      * Descargue el **[!UICONTROL Report Server]** paquete \ **[!UICONTROL v6.1]** .
      * Descargue archivos adicionales **[!UICONTROL Sensor]****[!UICONTROL Documentation]**, y **[!UICONTROL Dashboard]** archivos según sea necesario para su sistema.

1. Detenga el **[!UICONTROL Adobe Insight Server]** servicio.

   ![](assets/install_server_download1.png)

1. Del paquete descargado **[!UICONTROL Server]** :

   1. Reemplace la [!DNL Server\Bin] carpeta para actualizar los archivos [!DNL InsightServer64.exe] y los archivos auxiliares.

   1. Reemplace la [!DNL Server\Profiles] carpeta. Puede sobrescribir todos los archivos.
   1. Actualice la [!DNL Server\Lookups] carpeta. Desea agregar los archivos recién descargados a los archivos personalizados que ya se encuentran en la carpeta.
   1. Reemplazar la [!DNL Server\Software] carpeta que se va a actualizar [!DNL Insight.exe] y [!DNL ReportServer.exe]
   1. Actualice la [!DNL Server\Scripts] carpeta que desea actualizar [!DNL TnTSend.exe].

1. Si utiliza **[!UICONTROL DeviceAtlas]**, deberá [actualizar el paquete](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) ubicado en la [!DNL Server\Lookups] carpeta.

1. Configure el [!DNL Profile.cfg] archivo para asegurarse de que el vector se actualiza para reflejar el número de elementos de cada perfil.

   Por ejemplo, para habilitar el **[!UICONTROL Predictive Analytics]** perfil deberá actualizar esta configuración.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure y guarde el archivo PAServer.cfg para la función Análisis predictivo.

   Si desea enviar trabajos de Predictive Analytics a los servidores, deberá configurar el [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] archivo para administrar los envíos de clúster del lado del servidor.

   El perfil personalizado debe heredar la configuración del perfil de configuración de Predictive Analytics, permitiéndole configurar y guardar el [!DNL PAServer.cfg] archivo en función de la implementación del sitio.

1. Defina las **[!UICONTROL Log Source ID]**.

   El **[!UICONTROL Recording of Rows per Log Source]** se agregó **[!UICONTROL v6.04]** y definió en el [!DNL Log Processing.cfg] archivo del perfil personalizado agregando un nombre exclusivo **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Si no tiene definida la ID de origen de registro, obtendrá el siguiente error:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Dado que el [!DNL EventMessages.dll] se ha actualizado, es necesario anular el registro y, a continuación, registrarlo **[!UICONTROL Adobe Insight Server]** en todo el clúster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Inicie el **[!UICONTROL Adobe Insight Server]** servicio en todo el clúster.

La instalación del servidor ha finalizado.

## Actualización del servidor de informes {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Antes de actualizar a **[!UICONTROL Report Server v6.1]**, primero debe actualizar a **[!UICONTROL Server v6.1]**.

1. Con el **[!UICONTROL Software and Docs]** perfil, descargue **[!UICONTROL v6.1]** del **[!UICONTROL Report Server]** paquete a una carpeta local.

1. Copie **[!UICONTROL Report Server 6.1]** del paquete descargado y reemplace los paquetes de perfil.

   >[!NOTE]
   >
   >El [!DNL Insight.zbin] archivo de la [!DNL install] carpeta es un archivo de copia de seguridad utilizado para la localización y debe estar presente en el [!DNL install] directorio. Este archivo u otros [!DNL .zbin] archivos se utilizarán en función de la configuración de la línea de comandos que se pase al iniciar.

1. (opcional) El área de trabajo de datos admite actualmente inglés (-en-us) y chino (-zh-cn). Debe definir una fuente para admitir caracteres de byte único y doble:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   El sistema operativo Windows también debe tener instaladas las fuentes enumeradas.

1. Configurar [!DNL Report Server v6.1] la localización.

   1. Detenga el **[!UICONTROL Adobe Insight Report Server]** servicio.
   1. Inicie un símbolo del sistema como &quot;Administrador&quot;.
   1. Vaya a la [!DNL install] carpeta Servidor de informes.
   1. Elimine el servicio Servidor de informes con el siguiente comando:

      ```
      ReportServer.exe /unregserver
      ```

   1. Inicie el servicio según la configuración de idioma:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Para verificar que el servidor de informes se está ejecutando con la configuración correcta, abra **[!UICONTROL Windows Service Manager]** y haga clic con el botón derecho **[!UICONTROL Adobe Insight Report Server - Properties]**. La ruta al archivo ejecutable mostrará la configuración de la línea de comandos actualizada.

La instalación del servidor de informes ya se ha completado.

## Actualización del cliente {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Antes de realizar la actualización a **[!UICONTROL Client v6.1]**, el administrador debe actualizar primero a **[!UICONTROL Insight Server v6.1.]**

1. Inicie [!DNL Insight.exe] pero no se conecte a ningún perfil.
1. Edite el [!DNL Insight.cfg] archivo.

   ```
   Update Software = bool: true
   ```

1. Conéctese a su perfil.

   Permita que el cliente se sincronice con el servidor y se actualizará el cliente con los perfiles de cliente, ejecutables y archivos de configuración v6.1 más recientes.

   >[!NOTE]
   >
   >El [!DNL Insight.zbin] archivo de la [!DNL install] carpeta es un archivo de copia de seguridad que se utiliza para la localización y que debe estar presente. Este archivo u otros [!DNL .zbin] archivos se utilizarán en función de la configuración de la línea de comandos que se pase al iniciar.

   Consulte [Configuración de idiomas](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) localizados para agregar un [!DNL insight.zbin] archivo necesario para la configuración localizada.

**Configuración de cliente adicional**

Antes de configurar [!DNL Insight.exe] y admitir archivos, debe salir de la aplicación cliente.

Para instalar el chino simplificado:

1. Cree un acceso directo que pase la configuración de la línea de comandos al [!DNL Insight.exe] archivo.

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para admitir caracteres de fuente de byte único y doble.

   Actualmente, el área de trabajo de datos admite inglés y chino simplificado. Puede seleccionar fuentes para admitir ambos idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   El sistema operativo Windows también debe tener instaladas las fuentes solicitadas.

1. Inicie el método abreviado que ha creado para sincronizar perfiles y la actualización. [!DNL zbin] archivo.

Para utilizar el Editor de métodos de entrada (IME).

IME le permite introducir caracteres internacionales.

1. Actualice el [!DNL Insight.cfg] archivo con esta configuración:

   ```
   Localized IME = bool: true
   ```

1. Inicie el acceso directo que ha creado para sincronizar perfiles y el [!DNL .zbin] archivo actualizado.

La instalación del cliente se ha completado.
