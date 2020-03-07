---
description: Siga estos pasos para actualizar a la versión 6.1 del área de trabajo de datos desde la instalación de Insight v5.5x.
solution: Analytics
title: Actualización de Área de trabajo de datos 5.5 a 6.1
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Actualización de Área de trabajo de datos 5.5 a 6.1{#data-workbench-to-upgrade}

Siga estos pasos para actualizar a la versión 6.1 del área de trabajo de datos desde la instalación de Insight v5.5x.

**Paso 1**: Actualización [del servidor](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Paso 2**: Actualización [del servidor de informes](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Paso 3**: Actualización [del cliente](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Los componentes de servidor, servidor de informes y cliente se actualizan para ejecutarse en sistemas operativos Windows de 64 bits.

## Actualización del servidor {#section-08bd6fe3da8740fcb19688e8cac6f223}

Siga estos pasos para actualizar los **[!UICONTROL Server v6.1]** componentes:

1. Con el **[!UICONTROL Software and Docs]** perfil, abra el **[!UICONTROL Start Here]** espacio de trabajo y descargue todos los paquetes de servidor necesarios en una carpeta local.

   * Descargue **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** carpetas zip y extraiga todos los archivos.

      El **[!UICONTROL Server]** paquete incluye **[!UICONTROL Lookup]** y **[!UICONTROL Profile]** carpetas con los archivos de búsqueda **[!UICONTROL Base]** y **[!UICONTROL Transform]** búsqueda que se van a agregar y reemplazar para actualizar el servidor.

   * Descargar nuevas **[!UICONTROL Profiles]** carpetas.
   * Descargar **[!UICONTROL Lookup]** carpetas actualizadas.
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
1. Configure [!DNL Directories] en el [!DNL Profile.cfg] archivo para asegurarse de que el vector se actualiza para reflejar el número de elementos de cada perfil.

   Por ejemplo, para habilitar el **[!UICONTROL Predictive Analytics]** perfil deberá actualizar esta configuración.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure y guarde el [!DNL PAServer.cfg] archivo para actualizar la función Análisis predictivo.

   Si desea enviar trabajos de Predictive Analytics a los servidores, deberá configurar el [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] archivo para administrar los envíos de clúster del lado del servidor.

   El perfil personalizado debe heredar la configuración del perfil de configuración de Predictive Analytics, lo que le permitirá configurar y guardar la configuración en función de la implementación del [!DNL PAServer.cfg] sitio.

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

1. (opcional) Modifique el archivo de configuración del servidor de informes para admitir caracteres de doble byte.

   Actualmente, el área de trabajo de datos admite inglés (-en-us) y chino (-zh-cn). Debe definir una fuente para admitir caracteres de byte único y doble:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   El sistema operativo Windows también debe tener instaladas las fuentes enumeradas.

1. Configurar [!DNL Report Server v6.1].

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
>Antes de realizar la actualización a **[!UICONTROL Client v6.1]**, el administrador debe actualizar primero a **[!UICONTROL Server v6.1.]**

1. Iniciar [!DNL Insight.exe] pero NO conectar con ningún perfil.
1. Edite el [!DNL Insight.cfg] archivo para no actualizar el software automáticamente.

   ```
   Update Software = bool: false
   ```

1. Conéctese al **[!UICONTROL Software and Docs]** perfil (softdocs).
1. Descargar [!DNL Software\Insight Client\v6.10].
1. (opcional) Modificar [!DNL insight.cfg] para admitir caracteres de doble byte.

   Actualmente, el área de trabajo de datos admite inglés y chino simplificado. Seleccione las fuentes para admitir ambos idiomas:

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Salga del cliente.
1. Copie los archivos del paquete de cliente descargado **v6.1** en la [!DNL Install] carpeta.

   >[!NOTE]
   >
   >El [!DNL Insight.zbin] archivo de la carpeta de instalación es un archivo de copia de seguridad utilizado para la localización y debe estar presente en el directorio de instalación. Este archivo u otros [!DNL .zbin] archivos se utilizarán en función de la configuración de la línea de comandos que se pase al iniciar.
   >
   >Por ejemplo, para iniciar Chino simplificado, cree un acceso directo que pase en la configuración de la línea de comandos.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Si desea iniciar en inglés (predeterminado), no es necesario realizar ningún cambio en la línea de comandos.

1. Inicie [!DNL Insight.exe] para inglés o el acceso directo que ha creado para otro idioma.
1. Conéctese a su perfil y permita que el cliente se sincronice con el servidor.
1. (opcional) Para utilizar el IME, realice los siguientes cambios en el [!DNL Insight.cfg] archivo:

   ```
   Localized IME = bool: true
   ```

   El Editor de métodos de entrada (IME) permite introducir caracteres internacionales.

1. (opcional) Edite el [!DNL Insight.cfg] archivo para actualizar automáticamente el software:

   ```
   Update Software = bool: true
   ```

   Consulte las instrucciones para implementar el IME.
1. Reinicie de nuevo después de la sincronización de perfiles para utilizar el [!DNL .zbin] archivo más reciente.

La instalación del cliente se ha completado.
