---
description: Información sobre las unidades del servidor de archivos de Insight Server y el proceso de configuración del servidor de archivos.
solution: Analytics
title: Configuración de una unidad de servidor de archivos del servidor de área de trabajo de datos
topic: Data workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Configuración de una unidad de servidor de archivos del servidor de área de trabajo de datos{#configuring-a-data-workbench-server-file-server-unit}

Información sobre las unidades del servidor de archivos de Insight Server y el proceso de configuración del servidor de archivos.

<!--
c_abt_file_svr_units.xml
-->

Puede configurar el servidor del área de trabajo de datos (InsightServer64.exe) para que se ejecute como una unidad de servidor de archivos (FSU) completando los parámetros en el nodo **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** del [!DNL Log Processing.cfg] archivo. Cuando el servidor del área de trabajo de datos está configurado para ejecutarse como FSU, almacena archivos de origen ( [!DNL .vsl] archivos, archivos de texto o archivos XML) a los que pueden acceder rápidamente varios servidores de procesamiento (DPU). Cuando las DPU de un clúster de servidores del área de trabajo de datos acceden a la FSU para leer los archivos de registro, dividen los archivos de registro entre ellos y garantizan que el mismo archivo no se procesa más de una vez.

>[!NOTE]
>
>Al configurar una FSU que sirve un clúster de servidores del área de trabajo de datos que consta de cinco a diez unidades de disco, debe convertir el servidor maestro del clúster en la FSU.

Para obtener información sobre la instalación de un clúster de servidores del área de trabajo de datos, consulte la Guía *de instalación y administración de productos del* servidor.

<!--
c_file_svr_config_proc.xml
-->

Si la ubicación es una ubicación remota, el equipo del servidor del área de trabajo de datos que procesa los datos se conecta al equipo remoto designado para leer los registros.

En el equipo del servidor del área de trabajo de datos designado para ejecutarse como una FSU, el [!DNL Access Control.cfg] archivo permite que las DPU se conecten a la FSU y el [!DNL Communications.cfg] archivo asigna la ubicación de los archivos de datos remotos. Los pasos del proceso para configurar una FSU son los siguientes:

1. En el [!DNL Log Processing.cfg] archivo del servidor maestro del área de trabajo de datos, especifique el tipo de fuente de datos y la ubicación del origen. Consulte [Especificación de la fuente](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383)de datos.

1. En el [!DNL Access Control.cfg] archivo de la FSU, edite los permisos para permitir que las DPU se conecten a la FSU para leer los datos del registro. Consulte [Edición de permisos en la unidad](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef)del servidor de archivos.

1. En el [!DNL Communications.cfg] archivo de la FSU, edite la configuración de las entradas [!DNL LoggingServer] y [!DNL FileServer] para especificar la ubicación de los archivos de registro. Consulte [Especificación de la ubicación de los archivos](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0)de registro.

1. Si está configurando el perfil de conjunto de datos para que se ejecute en un clúster de servidores del área de trabajo de datos, también debe convertir la FSU del clúster en el servidor donde se construyen todas las dimensiones del perfil:
(Solo para clústeres de servidores del área de trabajo de datos) En los archivos [!DNL Communications.cfg] y [!DNL cluster.cfg] del FSU, agregue entradas para un &quot;servidor normalizado&quot; para que el FSU sea el servidor dentro del clúster donde se construyen todas las dimensiones. Consulte [Creación de un servidor de normalización centralizado para un clúster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Para obtener instrucciones sobre cómo configurar un perfil de conjunto de datos para que lo procese un clúster de servidores del área de trabajo de datos, consulte la Guía *de instalación y administración de productos del* servidor.

>[!NOTE]
>
>Las siguientes instrucciones suponen que todos los archivos de registro residen en el directorio predeterminado. Si desea almacenar los registros en otro directorio o crear varias rutas de registro, póngase en contacto con los servicios de consultoría de Adobe para analizar su configuración específica.

## Especificación de la fuente de datos {#section-d2b545db7ab142ffb4be32e040395383}

Al especificar orígenes de datos remotos para un conjunto de datos, debe especificar el tipo de origen de datos y la ubicación de los archivos de registro en el servidor maestro del área de trabajo de datos.

**Especificación del origen de datos y su ubicación**

1. Open the [!DNL Log Processing.cfg] file. Consulte [Edición del archivo](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuración de procesamiento de registros.

1. Agregue un [!DNL Sensor], archivo de registro o origen de datos XML. See [Log Files](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Complete el parámetro Rutas de registro. Consulte Archivos [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)de sensor, Archivos [de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)o Fuentes [de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)XML. Asegúrese de especificar un URI válido.

1. Complete los parámetros del servidor de registro definidos en la tabla siguiente:

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre que identifica el servidor de archivos remoto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre común del servidor SSL </td> 
   <td colname="col2"> <p> <span class="wintitle"> Nombre</span> común del servidor que aparece en el certificado SSL del servidor de archivos. </p> <p> Este parámetro es opcional si <span class="wintitle"> Use SSL</span> está establecido en false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> <p>Dirección del equipo del servidor de archivos. Se puede dejar en blanco si <span class="wintitle"> Name</span> coincide con <span class="wintitle"> SSL Server Common Name</span>. </p> <p> Por ejemplo: <span class="filepath"> visual.mycompany.com</span> o 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto </td> 
   <td colname="col2"> Puerto a través del cual el equipo del servidor del área de trabajo de datos se comunica con el servidor de archivos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> Nombre del <span class="wintitle"> archivo de certificado</span> SSL para el servidor del área de trabajo de datos (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar SSL </td> 
   <td colname="col2"> True o false. True indica que el servidor de archivos utiliza <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Si se requiere un servidor proxy para que las DPU se conecten a la FSU, deberá completar los siguientes parámetros:

| Parámetro | Descripción |
|---|---|
| Dirección proxy | La dirección de un servidor proxy que debe utilizar el servidor del área de trabajo de datos para acceder al servidor de archivos. |
| Contraseña de proxy | Opcional. La contraseña del servidor proxy. |
| Puerto proxy | El puerto del servidor proxy. El valor predeterminado es 8080. |
| Nombre de usuario proxy | Opcional. El nombre de usuario del servidor proxy. |

A continuación se muestra un ejemplo de un elemento definido [!DNL Log Server] en el [!DNL Log Processing.cfg] archivo. El origen de registro #1 es un origen LogFile que apunta a un directorio llamado Logs (observe el URI especificado en el parámetro Log Paths) en el equipo llamado FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Edición de los permisos en la unidad del servidor de archivos {#section-b4a54b591b4e4435a728a67f194057ef}

En el proceso anterior, configuró un perfil para un conjunto de datos determinado para leer archivos de registro de una FSU. Ahora debe editar los permisos en la FSU para permitir conexiones desde las DPU que ejecutan el perfil. Los siguientes pasos le guían a través de la edición del archivo de permisos [!DNL Access Control.cfg].

**Para editar permisos en la FSU**

1. Abra el [!DNL Server Files Manager] para el equipo del servidor del área de trabajo de datos que está configurando como FSU y haga clic en **[!UICONTROL Access Control]** para mostrar su contenido.

   Para obtener información sobre cómo abrir y trabajar con el [!DNL Server Files Manager], consulte la Guía del usuario *del área de trabajo de datos*.

1. En la [!DNL Server Files Manager] ventana, haga clic en **[!UICONTROL Access Control]** para mostrar su contenido. El [!DNL Access Control.cfg] archivo se encuentra dentro de este directorio.

1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre del servidor para [!DNL Access Control.cfg]y, a continuación, haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Access Control.cfg].

1. Haga clic con el botón secundario en la marca de verificación recién creada debajo de la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. En la [!DNL Access Control] ventana, haga clic en **[!UICONTROL Access Control Groups]** para mostrar su contenido.

1. Haga clic con el botón secundario en la etiqueta numérica del final [!DNL AccessGroup] de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Introduzca un [!DNL Name] para el nuevo [!DNL AccessGroup]. Ejemplo: Conexión de servidores.

1. Haga clic con el botón secundario **[!UICONTROL Member]** debajo del nuevo [!DNL AccessGroup], luego haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Introduzca la dirección IP del DPU del servidor del área de trabajo de datos que se conecta a este servidor de archivos.
1. Repita los pasos 4 y 5 para cualquier otra DPU del servidor del área de trabajo de datos que se conecte a esta FSU, incluidas las DPU del servidor del área de trabajo de datos de un clúster que deba acceder a los archivos de registro.
1. Haga clic con el botón secundario **[!UICONTROL Read-Only Access]** debajo del nuevo [!DNL AccessGroup], luego haga clic en **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Introduzca la ubicación de los archivos de registro almacenados en el equipo del servidor de archivos. Utilice barras diagonales (/) en la especificación de ruta. La ubicación predeterminada es /Logs/.
1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.

1. En la [!DNL Server Files Manager] ventana, haga clic con el botón secundario en la marca de verificación de [!DNL Access Control.cfg] la [!DNL Temp] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL server name]** para guardar los cambios realizados localmente en la FSU del servidor del área de trabajo de datos.

## Especificación de la ubicación de los archivos de registro {#section-f9a649bf1b2544feb10ad8820384edb0}

Debe editar el [!DNL Communications.cfg] archivo en la FSU para especificar la ubicación de los archivos de registro.

**Especificación de la ubicación de los archivos de registro**

1. En la [!DNL Server Files Manager] ventana, haga clic en **[!UICONTROL Components]** para mostrar su contenido. El [!DNL Communications.cfg] archivo se encuentra dentro de este directorio.

1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre del servidor para [!DNL Communications.cfg]y, a continuación, haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Communications.cfg].

1. Haga clic con el botón secundario en la marca de verificación recién creada debajo de la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. En la [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL component]** para mostrar su contenido.

1. En la [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL Servers]** para mostrar su contenido. Pueden aparecer varios servidores: Servidores de archivos, Servidores de registro, Servidores de entrada, Servidores de estado, Servidores de envío o Servidores de replicación.

1. (Solo para orígenes [!DNL Sensor] de registro) Busque el [!DNL LoggingServer], que es donde [!DNL Sensor] escribe los archivos de registro que va a procesar el servidor del área de trabajo de datos, y luego haga clic en su número para ver el menú. Edite el parámetro Directorio de registros para reflejar la ubicación deseada de los archivos de registro. El directorio de registro predeterminado es la carpeta Registros dentro del directorio de instalación del servidor del área de trabajo de datos.

   No modifique ningún otro parámetro para el [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Busque el FileServer que especifica la ubicación de los archivos de registro. Puede haber varios servidores de archivos en Servidores, por lo que es posible que tenga que ver el contenido de muchos de ellos (haciendo clic en el número de servidor) para encontrar el servidor deseado.
1. Edite los parámetros [!DNL Local Path] y URI para que FileServer refleje la ubicación de los archivos de registro. El siguiente ejemplo muestra que los archivos de registro residen en la carpeta Registros dentro del directorio de instalación del servidor del área de trabajo de datos:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Si los parámetros [!DNL Local Path] y URI se rellenan como se muestra, puede acceder a los archivos de registro de la FSU desde cualquier servidor del área de trabajo de datos haciendo clic [!DNL Logs] en la [!DNL Server Files Manager].

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana de configuración y, a continuación, haga clic en **[!UICONTROL Save]**.

1. En la [!DNL Server Files Manager] ventana, haga clic con el botón secundario en la marca de verificación de [!DNL Communications.cfg] la [!DNL Temp] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* para guardar los cambios realizados localmente en la FSU del servidor del área de trabajo de datos.

## Creación de un servidor de normalización centralizado para un clúster {#section-2c1f57b683f94cc193bc069e886bba28}

Si está configurando el perfil de conjunto de datos para que se ejecute en un clúster de servidores del área de trabajo de datos, debe convertir la FSU del clúster en el servidor donde se construyen todas las dimensiones del perfil.

Adobe recomienda encarecidamente que la FSU del clúster actúe como servidor maestro del clúster y como servidor de normalización centralizado.

Para que la FSU sea el servidor de normalización centralizado, debe abrir y editar los archivos [!DNL Communications.cfg] y [!DNL Cluster.cfg] archivos en la FSU.

**Convertir la FSU en el servidor de normalización centralizado**

1. Agregue una [!DNL NormalizeServer] entrada al [!DNL Communications.cfg] archivo en la FSU.

   >[!NOTE]
   >
   >Si ha instalado el paquete de versión completo para el servidor del área de trabajo de datos v5.0 o posterior, el [!DNL Communications.cfg] archivo de la FSU ya debería tener una [!DNL NormalizeServer] entrada. Puede seguir los pasos a continuación para confirmar que la entrada existe.

   1. Abra el [!DNL Communications.cfg] archivo en el área de trabajo de datos como se describe en [Especificación de la ubicación de los archivos](#section-f9a649bf1b2544feb10ad8820384edb0)de registro.

   1. Haga clic en **[!UICONTROL component]** para mostrar su contenido.
   1. Haga clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. En el parámetro URI del [!DNL NormalizeServer], escriba [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager] ventana, haga clic con el botón secundario en la marca de verificación de [!DNL Communications.cfg] la [!DNL Temp] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* name para guardar los cambios realizados localmente en el servidor FSU del área de trabajo de datos.

1. Defina el servidor de normalización centralizado en el [!DNL Cluster.cfg] archivo del servidor maestro del clúster de servidores del área de trabajo de datos.

   >[!NOTE]
   >
   >Si la FSU en la que está configurando el servidor de normalización centralizada no es el servidor maestro del área de trabajo de datos del clúster, debe agregar las direcciones IP de las DPU del clúster al grupo de [!DNL Cluster Servers] acceso del [!DNL Access Control.cfg] archivo de FSU. Para obtener instrucciones sobre cómo agregar servidores al [!DNL Cluster Servers] grupo, consulte la sección Actualización del archivo de control de acceso para un clúster en la Guía de instalación y administración de productos de *servidor.*

   1. Abra el [!DNL Profile Manager] perfil del conjunto de datos y, a continuación, haga clic en **[!UICONTROL Dataset]** para mostrar su contenido. El [!DNL Cluster.cfg] archivo se encuentra dentro de este directorio.

   1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Cluster.cfg]y, a continuación, haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

   1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. Agregue el texto resaltado en el siguiente fragmento de archivo:

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >Al introducir el nombre común de FSU para el parámetro Nombre común del servidor SSL, la FSU utiliza su [!DNL .address] archivo para resolver el nombre común. Para obtener más información sobre el [!DNL .address] archivo, consulte la Guía *de instalación y administración de productos* de servidor.

   1. Guarde el archivo.
   1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL Cluster.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** para guardar los cambios realizados localmente en el perfil del conjunto de datos.
