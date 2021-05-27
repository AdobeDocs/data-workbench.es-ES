---
description: Información sobre la configuración del clúster en Master Insight Server, la actualización del archivo de control de acceso para un clúster y más.
title: Configuración de Master Insight Server para la agrupación en clúster
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configuración de Master Insight Server para la agrupación en clúster{#configuring-the-master-insight-server-for-clustering}

Información sobre la configuración del clúster en Master Insight Server, la actualización del archivo de control de acceso para un clúster y más.

Para configurar el clúster, realice los siguientes pasos en el [!DNL Insight Server] maestro:

* Agregue los nombres y direcciones comunes de procesamiento [!DNL Insight Servers’] al archivo de direcciones.
* Agregue todo el [!DNL Insight Servers] al grupo Servidores de clúster en el archivo [!DNL Access Control.cfg].

* Actualice el archivo [!DNL Synchronize.cfg] en el directorio Componentes para servidores de procesamiento para que apunte al [!DNL Insight Server] maestro.

* Si es necesario, modifique el archivo [!DNL Disk Files.cfg] en el directorio Componentes para servidores de procesamiento para especificar la ubicación del archivo [!DNL temp.db] en el [!DNL Insight Servers] de procesamiento.

Para completar estos pasos, debe conocer los nombres comunes (como se especifica en los certificados digitales para el [!DNL Insight Server] individual) y las direcciones IP de cada [!DNL Insight Server] en el clúster. Si todavía no dispone de esta información, consígala antes de continuar.

>[!NOTE]
>
>Los procedimientos descritos en esta sección requieren [!DNL Insight]. Si no ha instalado [!DNL Insight], siga las instrucciones de la **[!DNL Insight]Guía del usuario** antes de continuar.

## Añadir los servidores de perspectiva de procesamiento al archivo de direcciones {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Utilice el siguiente procedimiento para añadir los nombres comunes y las direcciones IP de procesamiento [!DNL Insight Servers’] al archivo de dirección del [!DNL Insight Server] maestro. (Aunque el archivo de dirección se mantiene y se administra en el [!DNL Insight Server] maestro, lo utilizan todos los [!DNL Insight Servers] del clúster).

>[!NOTE]
>
>A continuación se supone que el archivo de dirección ya se ha configurado para el archivo maestro [!DNL Insight Server]. Si todavía no ha agregado las [!DNL Insight Server’s] direcciones IP principales al archivo de direcciones, complete el procedimiento descrito en [Definición de la ubicación de red del servidor](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) antes de comenzar.

**Para añadir el procesamiento  [!DNL Insight Servers] al archivo de dirección**

1. Inicie [!DNL Insight] y cargue el perfil de configuración (si aún no está abierto) haciendo clic con el botón derecho en la barra de título y haciendo clic en **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del maestro **[!UICONTROL Insight Server]** y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], abra el directorio Direcciones y haga lo siguiente para abrir el archivo de dirección [!DNL Insight Server’s]:

   1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación de la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda el contenido de la estructura [!DNL Locations] y, a continuación, expanda NetworkLocation 0, Addresses y AddressDefinition.
1. Haga lo siguiente para agregar AddressDefinition a NetworkLocation 0 para cada [!DNL Insight Server] procesamiento en el clúster:

   1. Haga clic con el botón derecho en **[!UICONTROL AddressDefinition]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. En el parámetro Name , especifique el nombre común de procesamiento [!DNL Insight Server’s].
   1. En el parámetro Address , especifique la dirección IP de procesamiento [!DNL Insight Server’s].

      Puede utilizar un asterisco como comodín en el campo Dirección, por ejemplo, 10.10.116.*, para simplificar la agrupación en clústeres. Consulte [Explicación de los niveles de acceso](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      El siguiente ejemplo define un clúster que contiene dos [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si los servidores están conectados a varias redes, repita el paso 6 para agregar el procesamiento [!DNL Insight Servers] a NetworkLocations para esas redes.

   El siguiente ejemplo muestra un clúster de cuatro [!DNL Insight Servers] conectados a dos redes (&quot;Intranet corporativa&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Actualización del archivo de control de acceso para un clúster {#section-fce1367d92a445168c35e9ca506e7d6b}

Para utilizar [!DNL Insight Servers] en un clúster, cada [!DNL Insight Server] del clúster (incluido el [!DNL Insight Server] maestro) debe pertenecer al grupo de control de acceso de los Servidores de clúster . El grupo Servidores de clúster identifica los servidores (por dirección IP) a los que se permite participar en el clúster. Aunque este archivo se mantiene y se administra en el [!DNL Insight Server] maestro, lo utilizan todos los [!DNL Insight Servers] del clúster.

**Para editar el archivo de control de acceso**

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del maestro [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], abra el directorio Control de acceso.
1. Haga lo siguiente para abrir el archivo [!DNL Access Control.cfg]:

   1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación de la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura Grupos de control de acceso y, a continuación, expanda Grupo de acceso (Servidores de clúster).
1. Para cada [!DNL Insight Server] en el clúster (incluido el [!DNL Insight Server] maestro), haga lo siguiente:

   1. Haga clic con el botón derecho en **[!UICONTROL Members]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Especifique la dirección IP [!DNL Insight Server’s] (su dirección IP numérica, no su nombre). Si los [!DNL Insight Servers] están conectados a varias redes, este AccessGroup debe contener únicamente las direcciones internas que [!DNL Insight Servers] utiliza para la comunicación entre servidores dentro del clúster.

      A continuación se muestra AccessGroup (Cluster Servers) para un clúster de cuatro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL Temp] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuración del archivo de sincronización {#section-d23e751771c84da6bab6a34a8db867bc}

Puede utilizar el siguiente procedimiento para configurar la copia central del archivo [!DNL Synchronize.cfg]. La copia central de este archivo se mantiene en el [!DNL Insight Server] maestro. El [!DNL Insight Servers] de procesamiento del clúster inicia la comunicación con el [!DNL Insight Server] maestro para recuperar una copia actualizada de este archivo.

El archivo [!DNL Synchronize.cfg] especifica la ubicación del archivo maestro [!DNL Insight Server]. También identifica el conjunto de archivos administrativos que cada uno de los [!DNL Insight Servers] de procesamiento del clúster recupera del [!DNL Insight Server] maestro. El [!DNL Insight Servers] de procesamiento descarga automáticamente estos archivos desde el [!DNL Insight Server] maestro cuando se inician. También recuperan dinámicamente copias actualizadas de estos archivos desde el [!DNL Insight Server] maestro cuando cambian los archivos.

>[!NOTE]
>
>Aunque configure el archivo [!DNL Synchronize.cfg] en el archivo maestro [!DNL Insight Server], el [!DNL Insight Server] maestro en sí no utiliza este archivo. Actualice este archivo en el [!DNL Insight Server] maestro para que se configure correctamente cuando el [!DNL Insight Servers] de procesamiento recupere el archivo.

**Para actualizar el archivo Synchronize.cfg en el maestro[!DNL Insight Server]**

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del maestro [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], abra el directorio **[!UICONTROL Components]** para servidores de procesamiento.

1. Haga lo siguiente para abrir [!DNL Synchronize.cfg]:

   1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura del componente.
1. En el parámetro Dirección del servidor primario del clúster, especifique la dirección IP del maestro (principal) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Para crear un registro que registre cada vez que se produce la sincronización entre el maestro [!DNL Insight Server] y el procesamiento [!DNL Insight Servers], asegúrese de que el parámetro Enable Synchronization Log esté configurado como &quot;true&quot;.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL Temp] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuración de la ubicación del conjunto de datos (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Realice el siguiente procedimiento si desea que el [!DNL Insight Servers] de procesamiento mantenga [!DNL temp.db] (el conjunto de datos) en un directorio o unidad diferente de la ubicación predeterminada o si desea distribuir [!DNL temp.db] en varias unidades.

>[!NOTE]
>
>Dado que el [!DNL Insight Servers] procesamiento comparte los mismos [!DNL Disk Files.cfg], todos deben admitir las ubicaciones de archivo que especifique en este archivo. Por ejemplo, si asigna [!DNL temp.db] a la E: unidad, cada [!DNL Insight Server] de procesamiento del clúster debe tener una E: unidad.

**Para configurar la ubicación de temp.db**

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del maestro [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], abra el directorio **[!UICONTROL Components for Processing Servers]**.

1. Haga lo siguiente para abrir [!DNL Disk Files.cfg]:

   1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación de la columna [!DNL Temp]y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura DiskSpaceManagerComponent y, a continuación, expanda la lista Archivos de disco.
1. Edite la entrada 0 para cambiar la ubicación del archivo [!DNL temp.db].
1. Si desea distribuir [!DNL temp.db] entre varias unidades, siga los pasos a continuación para crear una entrada adicional para cada unidad adicional.

   1. Haga clic con el botón derecho en **[!UICONTROL Disk Files]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. En la nueva entrada, especifique la ubicación donde desea que se escriba [!DNL temp.db].
   A continuación se muestra [!DNL temp.db] escrito en cuatro unidades.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL Temp] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
