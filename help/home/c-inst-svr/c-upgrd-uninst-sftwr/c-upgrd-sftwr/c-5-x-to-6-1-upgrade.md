---
description: Siga estos pasos para actualizar a Data Workbench v6.1 desde la instalación de Insight v5.5x.
title: Actualización de Data Workbench de 5.5 a 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 1%

---

# Actualización de Data Workbench de 5.5 a 6.1{#data-workbench-to-upgrade}

Siga estos pasos para actualizar a Data Workbench v6.1 desde la instalación de Insight v5.5x.

**Paso 1**:  [Actualización del servidor](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Paso 2**:  [Actualización del servidor de informes](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Paso 3**:  [Actualización del cliente](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Los componentes de servidor, servidor de informes y cliente se actualizan para que se ejecuten en sistemas operativos Windows de 64 bits.

## Actualización del servidor {#section-08bd6fe3da8740fcb19688e8cac6f223}

Siga estos pasos para actualizar los componentes **[!UICONTROL Server v6.1]**:

1. Con el perfil **[!UICONTROL Software and Docs]**, abra el espacio de trabajo **[!UICONTROL Start Here]** y descargue todos los paquetes de servidor necesarios en una carpeta local.

   * Descargue las carpetas zip **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** y extraiga todos los archivos.

      El paquete **[!UICONTROL Server]** incluye carpetas **[!UICONTROL Lookup]** y **[!UICONTROL Profile]** con los archivos de búsqueda **[!UICONTROL Base]** y **[!UICONTROL Transform]** que se van a agregar y reemplazar para actualizar el servidor.

   * Descargue nuevas carpetas **[!UICONTROL Profiles]**.
   * Descargar carpetas **[!UICONTROL Lookup]** actualizadas.
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

1. Si utiliza **[!UICONTROL DeviceAtlas]**, deberá [actualizar el paquete](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) ubicado en la carpeta [!DNL Server\Lookups].
1. Configure [!DNL Directories] en el archivo [!DNL Profile.cfg] para asegurarse de que el vector se actualice para reflejar el número de elementos para cada perfil.

   Por ejemplo, para habilitar el perfil **[!UICONTROL Predictive Analytics]** deberá actualizar esta configuración.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure y guarde el archivo [!DNL PAServer.cfg] para actualizar la función de Predictive Analytics.

   Si desea enviar trabajos de Predictive Analytics a los servidores, deberá configurar el archivo [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] para administrar los envíos de clúster del lado del servidor.

   El perfil personalizado debe heredar la configuración del perfil de configuración de Predictive Analytics, lo que le permite configurar y guardar el [!DNL PAServer.cfg] en función de la implementación del sitio.

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

1. (opcional) Modifique el archivo de configuración del servidor de informes para que admita caracteres de bits dobles.

   Actualmente, Data Workbench admite inglés (-en-us) y chino (-zh-cn). Debe configurar una fuente para que admita caracteres de byte único y doble:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   El sistema operativo Windows también debe tener instaladas las fuentes enumeradas.

1. Configurar [!DNL Report Server v6.1].

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

## Actualización de cliente {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Antes de actualizar a **[!UICONTROL Client v6.1]**, el administrador debe actualizar primero a **[!UICONTROL Server v6.1.]**

1. Inicie [!DNL Insight.exe] pero NO se conecte a ningún perfil.
1. Edite el archivo [!DNL Insight.cfg] para no actualizar el software automáticamente.

   ```
   Update Software = bool: false
   ```

1. Conéctese al perfil **[!UICONTROL Software and Docs]** (softdocs).
1. Descargar [!DNL Software\Insight Client\v6.10].
1. (opcional) Modifique [!DNL insight.cfg] para que admita caracteres de bits dobles.

   Actualmente, Data Workbench admite inglés y chino simplificado. Seleccione fuentes para admitir ambos idiomas:

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Salga del cliente.
1. Copie los archivos del paquete de cliente **v6.1** descargado en la carpeta [!DNL Install] .

   >[!NOTE]
   >
   >El archivo [!DNL Insight.zbin] de la carpeta de instalación es un archivo de copia de seguridad que se utiliza para la localización y debe estar presente en el directorio de instalación. Este archivo u otros [!DNL .zbin] archivos se utilizarán según la configuración de línea de comandos que se pase al iniciar.
   >
   >Por ejemplo, para iniciar Chino simplificado, cree un acceso directo que pase en la configuración de la línea de comandos.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Si desea iniciar en inglés (predeterminado), no es necesario ningún cambio en la línea de comandos.

1. Inicie [!DNL Insight.exe] para inglés o el acceso directo que ha creado para otro idioma.
1. Conéctese a su perfil y permita que el cliente se sincronice con el servidor.
1. (opcional) Para utilizar el IME, realice estos cambios en el archivo [!DNL Insight.cfg]:

   ```
   Localized IME = bool: true
   ```

   El Editor de métodos de entrada (IME) permite introducir caracteres internacionales.

1. (opcional) Edite el archivo [!DNL Insight.cfg] para actualizar automáticamente el software:

   ```
   Update Software = bool: true
   ```

   Consulte las instrucciones para implementar el IME.
1. Reinicie de nuevo después de la sincronización de perfiles para utilizar el archivo [!DNL .zbin] más reciente.

La instalación del cliente ya ha finalizado.
