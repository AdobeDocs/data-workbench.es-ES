---
description: Actualización de componentes de servidor para Área de trabajo de datos 6.3.
title: Actualización del servidor DWB 6.2 a 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Actualización del servidor DWB: 6.2 a 6.3{#dwb-server-upgrade-to}

Actualización de componentes de servidor para Área de trabajo de datos 6.3.

**Actualizar servidor**

Si tiene perfiles personalizados que tienen prioridad sobre los archivos predeterminados que se proporcionan en el [!DNL Base] paquete, deberá actualizar estos archivos personalizados:

* **Actualice el archivo** Meta.cfg ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]para establecer el cifrado de contraseña actualizado para la unidad del sistema de archivos (servidor FSU) y para agregar entradas para las transformaciones del par de valores de nombre para aprovechar las agrupaciones [de cadenas de](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0)consulta.

   1. Abra el [!DNL meta.cfg] archivo en la FSU.
   1. Cambie el tipo de datos para **[!UICONTROL Proxy Password]** de &quot; [!DNL string"] a &quot; [!DNL EncryptedString]&quot; en la sección Configuración *de* estación de trabajo.

      ```
      Proxy User Name = string: 
      Proxy Password = EncryptedString:   ( 
      
<i>from Proxy Password = String</i>)Usar archivo de dirección = bool: true&quot;

    1. Agregue nuevas entradas para habilitar las nuevas transformaciones del par de valores de nombre: *BuildNameValuePair* y *ExtractNameValuePairs*.
    
    Abra un espacio de trabajo y haga clic con el botón secundario en **Administración** > **Administrador de perfiles**.
    
    En **Contexto**, haga clic en el archivo **meta.cfg*** de la columna **Base** y, a continuación, haga clic en **Convertir en local**. En la columna de la tabla Usuario, haga clic con el botón derecho y seleccione **Abrir** > **En estación de trabajo**.
    
    ![](assets/meta_cfg.png)
    
    * En la nueva ventana, haga clic en **metadata** y agregue plantillas secundarias aceptables.
    
    ![](assets/meta_cfg_child.png)
    
    * Abra **transformación** y agregue nuevas plantillas.
    
    ![](assets/meta_cfg_template.png)

* **Actualización para mejoras** de combinación rápida. Agregue parámetros o cambie valores a los siguientes archivos de configuración para aprovechar las mejoras de velocidad en el área de trabajo de datos durante una transformación.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:  
          URI = string: /SourceListServer/ 
          Listing Interval = int: 10 ( 
      <new>)
      ```

   * **Disk Files.cfg** (at [!DNL E:\Server\Components] y [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024  
      <(from double: 256)> 
      Disk Cache Read Limit (MB) = double: 768  
      <(new)>
      ```

   * **Modo de procesamiento de registros.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed) 
      Batch Bytes = int: 268435456 
      Cloud Bytes = int: 268435456 
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      ( 
      <new>) 
      Cache Bytes = int: 32000000 
      Fast Input Decision Ratio = double: 200 
      Fast Input FIFO Bytes = int: 268435456 
      FIFO Hash Mask = int: 16383 
      Fast Merge Buffer Bytes = int: 536870912 
      Slow Merge Buffer Bytes = int: 268435456 
      Fast Merge Fan In = int: 64 
      Key Cache Size Logarithm = int: 21 
      Max Seeks = int: 512 
      Output Old Buffer Bytes = int: 536870912 
      Overflow FIFO Bytes = int: 67108864 
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >Para aprovechar las mejoras de Combinación rápida, asegúrese de que dispone de al menos 8 GB de RAM por DPU.

* **Actualización** de integración de Adobe Target con DWB. Un nuevo archivo de exportación [!DNL ExportIntegration.exe], reemplaza el [!DNL TnTSend.exe] archivo existente en el servidor de Insight (`E:\Server\Scripts\TnTSend.exe`). Este nuevo archivo de exportación admite la integración y coordinación de [Adobe Target](https://www.adobe.com/marketing/target.html) con el nuevo perfil de marketing maestro (MMP) y [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Deberá actualizar los siguientes comandos para las exportaciones de Adobe Target.

   `Command = string: TnTSend.exe`

   a

   ```
   <filepath>
   Command = string: ExportIntegration.exe 
   </filepath>
   ```

   >[!NOTE]
   >
   >Esto solo afectará a las exportaciones creadas antes de la versión 6.3.

   También puede probar lo siguiente para utilizar el antiguo proceso de exportación:

   * Cree una nueva exportación de Test And Target en la estación de trabajo.
   * Modifique la antigua exportación de Test y Target que se encuentra en [!DNL Server/Profiles/`<your profile>`/Export.]

* **Actualice el perfil de Adobe SC.** Los cambios en el [!DNL Exclude Hit.cfg] archivo requieren que se declare un campo en el [!DNL Decoding Instructions.cfg] archivo asociado.

   >[!NOTE]
   >
   >Si su perfil de Adobe SC incluye un [!DNL Decoding Instructions.cfg] archivo personalizado, deberá incluir un [!DNL DelimitedDecoder] parámetro en el archivo personalizado.

   ```
   0 = DelimitedDecoder: 
      Delimiter = string: \t 
      Fields = vector: x items 
      …  
         5 = string: 
   Changed to: 
   
   5 = string: x-hit_source
   ```

   La adición del [!DNL DelimitedDecoder] campo permite aprovechar las actualizaciones de funciones y evitar posibles problemas de procesamiento de registros que resulten de estas actualizaciones.
