---
description: Información sobre las unidades del servidor de archivos de Insight Server y el proceso de configuración del servidor de archivos.
title: Configuración de una unidad de servidor de archivos del servidor de Data Workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 1%

---

# Configuración de una unidad de servidor de archivos del servidor de Data Workbench{#configuring-a-data-workbench-server-file-server-unit}

{{eol}}

Información sobre las unidades del servidor de archivos de Insight Server y el proceso de configuración del servidor de archivos.

<!--
c_abt_file_svr_units.xml
-->

Puede configurar el servidor de Data Workbench (InsightServer64.exe) para que se ejecute como una unidad de servidor de archivos (FSU) completando los parámetros en la variable **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** nodo de la variable [!DNL Log Processing.cfg] archivo. Cuando el servidor de Data Workbench está configurado para ejecutarse como una FSU, almacena archivos de origen ( [!DNL .vsl] archivos, archivos de texto o archivos XML) a los que pueden acceder rápidamente varios servidores de procesamiento (DPU). Cuando las DPU de un clúster de servidores de Data Workbench acceden a la FSU para leer los archivos de registro, dividen los archivos de registro entre ellos y garantizan que el mismo archivo no se procese más de una vez.

>[!NOTE]
>
>Al configurar una FSU que sirve a un clúster de servidores de Data Workbench que consta de entre cinco y diez DPU, debe convertir el servidor maestro del clúster en la FSU.

Para obtener información sobre la instalación de un clúster de servidores de Data Workbench, consulte la *Guía de instalación y administración de productos para servidor*.

<!--
c_file_svr_config_proc.xml
-->

Si la ubicación es una ubicación remota, el equipo de servidor de Data Workbench que procesa los datos se conecta al equipo remoto designado para leer los registros.

En el equipo de servidor de Data Workbench designado para ejecutarse como una FSU, la variable [!DNL Access Control.cfg] permite que las DPU se conecten a la FSU, y [!DNL Communications.cfg] asigna la ubicación de los archivos de datos remotos. Los pasos del proceso para configurar una FSU son los siguientes:

1. En el [!DNL Log Processing.cfg] en el servidor maestro de Data Workbench, especifique el tipo de origen de datos y la ubicación del origen. Consulte [Especificación de la fuente de datos](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. En el [!DNL Access Control.cfg] en la FSU, edite los permisos para permitir que las DPU se conecten a la FSU para leer los datos de registro. Consulte [Edición de los permisos en la unidad del servidor de archivos](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. En el [!DNL Communications.cfg] en la FSU, edite la configuración de [!DNL LoggingServer] y [!DNL FileServer] para especificar la ubicación de los archivos de registro. Consulte [Especificación de la ubicación de los archivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Si está configurando su perfil de conjunto de datos para que se ejecute en un clúster de servidores de Data Workbench, también debe hacer de la FSU del clúster el servidor donde se construyen todas las dimensiones del perfil: (Solo para clústeres de servidores de Data Workbench) En la variable [!DNL Communications.cfg] y [!DNL cluster.cfg] archivos en la FSU, añada entradas para un &quot;servidor normalizado&quot; para hacer de la FSU el servidor dentro del clúster donde se construyen todas las dimensiones. Consulte [Creación de un Servidor de Normalización Centralizado para un Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Para obtener instrucciones sobre cómo configurar un perfil de conjunto de datos para que lo procese un clúster de servidores de Data Workbench, consulte *Guía de instalación y administración de productos para servidor*.

>[!NOTE]
>
>Las siguientes instrucciones suponen que todos los archivos de registro residen en el directorio predeterminado. Si desea almacenar registros en otro directorio o crear varias rutas de registro, póngase en contacto con los servicios de consultoría de Adobe para analizar su configuración específica.

## Especificación de la fuente de datos {#section-d2b545db7ab142ffb4be32e040395383}

Al especificar fuentes de datos remotas para un conjunto de datos, debe especificar el tipo de fuente de datos y la ubicación de los archivos de registro en el servidor maestro de Data Workbench.

**Especificación del origen de datos y su ubicación**

1. Abra el [!DNL Log Processing.cfg] archivo. Consulte [Edición del archivo de configuración de procesamiento de registros](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. Agregue un [!DNL Sensor], archivo de registro o fuente de datos XML. Consulte [Archivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Complete el parámetro Log Paths . Consulte [Archivos de sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [Archivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)o [Fuentes de registro XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Asegúrese de especificar un URI válido.

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
   <td colname="col2"> <p> <span class="wintitle"> Nombre común del servidor</span> en el certificado SSL del servidor de archivos. </p> <p> Este parámetro es opcional si <span class="wintitle"> Usar SSL</span> se establece en false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> <p>Dirección del equipo del servidor de archivos. Se puede dejar en blanco si <span class="wintitle"> Nombre</span> matches <span class="wintitle"> Nombre común del servidor SSL</span>. </p> <p> Por ejemplo: <span class="filepath"> visual.mycompany.com</span> o 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto </td> 
   <td colname="col2"> Puerto a través del cual el equipo del servidor de Data Workbench se comunica con el servidor de archivos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> Nombre del <span class="wintitle"> Certificado SSL</span> para el servidor de Data Workbench (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar SSL </td> 
   <td colname="col2"> Verdadero o falso. True indica que el servidor de archivos utiliza <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Si se necesita un servidor proxy para que las DPU se conecten a la FSU, se deben completar los siguientes parámetros:

| Parámetro | Descripción |
|---|---|
| Dirección proxy | La dirección de un servidor proxy que el servidor de Data Workbench debe utilizar para acceder al servidor de archivos. |
| Contraseña de proxy | Opcional. La contraseña del servidor proxy. |
| Puerto proxy | Puerto del servidor proxy. El valor predeterminado es 8080. |
| Nombre de usuario proxy | Opcional. El nombre de usuario del servidor proxy. |

A continuación se muestra un ejemplo de una [!DNL Log Server] en el [!DNL Log Processing.cfg] archivo. El origen de registro 1 es un origen LogFile que apunta a un directorio llamado Logs (observe el URI especificado en el parámetro Log Paths ) en el equipo llamado FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Edición de los permisos en la unidad del servidor de archivos {#section-b4a54b591b4e4435a728a67f194057ef}

En el proceso anterior, configuró un perfil para un conjunto de datos determinado para leer archivos de registro de una FSU. Ahora debe editar los permisos en la FSU para permitir conexiones desde las DPU que ejecutan el perfil. Los siguientes pasos le guían a través de la edición del archivo de permisos [!DNL Access Control.cfg].

**Para editar permisos en la FSU**

1. Abra el [!DNL Server Files Manager] para el equipo de servidor de Data Workbench que está configurando como FSU y haga clic en **[!UICONTROL Access Control]** para mostrar su contenido.

   Para obtener información sobre cómo abrir y trabajar con la variable [!DNL Server Files Manager], consulte la *Guía del usuario de Data Workbench*.

1. En el [!DNL Server Files Manager] ventana, haga clic en **[!UICONTROL Access Control]** para mostrar su contenido. La variable [!DNL Access Control.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la columna de nombre del servidor para [!DNL Access Control.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Access Control.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada debajo de la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. En el [!DNL Access Control] ventana, haga clic en **[!UICONTROL Access Control Groups]** para mostrar su contenido.

1. Haga clic con el botón derecho en la etiqueta numérica de la final [!DNL AccessGroup] en la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Escriba un [!DNL Name] para el nuevo [!DNL AccessGroup]. Ejemplo: Conexión de servidores.

1. Clic con el botón derecho **[!UICONTROL Member]** en el nuevo [!DNL AccessGroup]y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Introduzca la dirección IP del DPU del servidor de Data Workbench que se conecta a este servidor de archivos.
1. Repita los pasos 4 y 5 para cualquier otra DPU del servidor de Data Workbench que se conecte a esta FSU, incluidas las DPU del servidor de Data Workbench en un clúster que debe acceder a los archivos de registro.
1. Clic con el botón derecho **[!UICONTROL Read-Only Access]** en el nuevo [!DNL AccessGroup]y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Introduzca la ubicación de los archivos de registro almacenados en el equipo del servidor de archivos. Utilice barras inclinadas (/) en la especificación de ruta. La ubicación predeterminada es /Logs/.
1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana, haga clic en **[!UICONTROL Save]**.

1. En el [!DNL Server Files Manager] , haga clic con el botón derecho en la marca de verificación de [!DNL Access Control.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL server name]** para guardar los cambios realizados localmente en la FSU del servidor de Data Workbench.

## Especificación de la ubicación de los archivos de registro {#section-f9a649bf1b2544feb10ad8820384edb0}

Debe editar la variable [!DNL Communications.cfg] en la FSU para especificar la ubicación de los archivos de registro.

**Especificación de la ubicación de los archivos de registro**

1. En el [!DNL Server Files Manager] ventana, haga clic en **[!UICONTROL Components]** para mostrar su contenido. La variable [!DNL Communications.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la columna de nombre del servidor para [!DNL Communications.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Communications.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada debajo de la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. En el [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL component]** para mostrar su contenido.

1. En el [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL Servers]** para mostrar su contenido. Es posible que aparezcan varios servidores: Servidores de archivos, Servidores de registro, Servidores de entrada, Servidores de estado, Servidores de envío o Servidores de replicación.

1. (Para [!DNL Sensor] solo las fuentes de registro) Busque la variable [!DNL LoggingServer], donde [!DNL Sensor] escribe sus archivos de registro para que los procese el servidor de Data Workbench y, a continuación, haga clic en su número para ver el menú . Edite el parámetro Directorio de registros para reflejar la ubicación deseada de los archivos de registro. El directorio de registro predeterminado es la carpeta Registros dentro del directorio de instalación del servidor de Data Workbench.

   No modifique ningún otro parámetro para la variable [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Busque el FileServer que especifica la ubicación de los archivos de registro. Puede haber varios servidores de archivos enumerados en Servidores, por lo que puede que necesite ver el contenido de muchos de ellos (haciendo clic en el número de servidor) para encontrar el servidor deseado.
1. Edite el [!DNL Local Path] y parámetros de URI para FileServer para reflejar la ubicación de los archivos de registro. El siguiente ejemplo muestra que los archivos de registro residen en la carpeta Logs del directorio de instalación del servidor de Data Workbench:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Si la variable [!DNL Local Path] y los parámetros de URI se rellenan como se muestra, puede acceder a los archivos de registro en la FSU desde cualquier servidor de Data Workbench haciendo clic en [!DNL Logs] en el [!DNL Server Files Manager].

1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana de configuración, haga clic en **[!UICONTROL Save]**.

1. En el [!DNL Server Files Manager] , haga clic con el botón derecho en la marca de verificación de [!DNL Communications.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* para guardar los cambios realizados localmente en la FSU del servidor de Data Workbench.

## Creación de un Servidor de Normalización Centralizado para un Cluster {#section-2c1f57b683f94cc193bc069e886bba28}

Si está configurando su perfil de conjunto de datos para que se ejecute en un clúster de servidores de Data Workbench, debe hacer de la FSU del clúster el servidor donde se construyen todas las dimensiones del perfil.

Adobe recomienda encarecidamente que la FSU del clúster sirva como servidor maestro del clúster y su servidor de normalización centralizado.

Para que la FSU sea el servidor de normalización centralizado, debe abrir y editar la variable [!DNL Communications.cfg] y [!DNL Cluster.cfg] archivos en la FSU.

**Para hacer de la FSU el servidor de normalización centralizado**

1. Agregue un [!DNL NormalizeServer] entrada al [!DNL Communications.cfg] en la FSU.

   >[!NOTE]
   >
   >Si ha instalado el paquete de versión completo para el servidor de Data Workbench v5.0 o posterior, la variable [!DNL Communications.cfg] en su FSU debe tener un [!DNL NormalizeServer] ya. Puede seguir los pasos a continuación para confirmar que la entrada existe.

   1. Abra el [!DNL Communications.cfg] en data workbench, tal como se describe en [Especificación de la ubicación de los archivos de registro](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. Haga clic en **[!UICONTROL component]** para mostrar su contenido.
   1. Clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. En el parámetro de URI para la variable [!DNL NormalizeServer], tipo [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager] , haga clic con el botón derecho en la marca de verificación de [!DNL Communications.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* nombre para guardar los cambios realizados localmente en la FSU del servidor de Data Workbench.

1. Defina el servidor de normalización centralizada en la variable [!DNL Cluster.cfg] en el servidor maestro del clúster de servidor de Data Workbench.

   >[!NOTE]
   >
   >Si la FSU en la que está configurando su servidor de normalización centralizada no es el servidor maestro de Data Workbench del clúster, debe añadir las direcciones IP de las DPU del clúster a la [!DNL Cluster Servers] grupo de acceso en la FSU [!DNL Access Control.cfg] archivo. Para obtener instrucciones para agregar servidores a la variable [!DNL Cluster Servers] Consulte Actualización del archivo de control de acceso para un clúster en la sección *Guía de instalación y administración de productos para servidor.*

   1. Abra el [!DNL Profile Manager] dentro del perfil del conjunto de datos, haga clic en **[!UICONTROL Dataset]** para mostrar su contenido. La variable [!DNL Cluster.cfg] se encuentra dentro de este directorio.

   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Cluster.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. Añada el texto resaltado en el siguiente fragmento de archivo:

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >Cuando se introduce el nombre común de FSU para el parámetro Nombre común del servidor SSL, la FSU utiliza su [!DNL .address] para resolver el nombre común. Para obtener información sobre la variable [!DNL .address] consulte la *Guía de instalación y administración de productos para servidor*.

   1. Guarde el archivo.
   1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Cluster.cfg] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** para guardar los cambios realizados localmente en el perfil del conjunto de datos.
