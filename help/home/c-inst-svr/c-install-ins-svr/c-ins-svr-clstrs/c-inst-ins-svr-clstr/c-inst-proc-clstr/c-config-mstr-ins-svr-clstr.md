---
description: Información sobre la configuración del clúster en Master Insight Server, la actualización del archivo de control de acceso para un clúster y más.
title: Configuración de Master Insight Server para la agrupación en clúster
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configuración de Master Insight Server para la agrupación en clúster{#configuring-the-master-insight-server-for-clustering}

{{eol}}

Información sobre la configuración del clúster en Master Insight Server, la actualización del archivo de control de acceso para un clúster y más.

Para configurar el clúster, realice los siguientes pasos en el maestro [!DNL Insight Server]:

* Añadir el procesamiento [!DNL Insight Servers’] nombres y direcciones comunes del archivo de direcciones.
* Agregue todo el [!DNL Insight Servers] al grupo Servidores de clúster en la [!DNL Access Control.cfg] archivo.

* Actualice el [!DNL Synchronize.cfg] en el directorio Componentes para servidores de procesamiento para que apunten al archivo maestro [!DNL Insight Server].

* Si es necesario, modifique la [!DNL Disk Files.cfg] en el directorio Componentes para servidores de procesamiento para especificar la ubicación del [!DNL temp.db] en el procesamiento [!DNL Insight Servers].

Para completar estos pasos, debe conocer los nombres comunes (tal y como se especifica en los certificados digitales para la [!DNL Insight Server]) y las direcciones IP de cada [!DNL Insight Server] en el clúster. Si todavía no dispone de esta información, consígala antes de continuar.

>[!NOTE]
>
>Los procedimientos descritos en esta sección requieren [!DNL Insight]. Si no está instalado [!DNL Insight], siga las instrucciones de la sección **[!DNL Insight]Guía del usuario** antes de continuar.

## Adición de los servidores de perspectiva de procesamiento al archivo de direcciones {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Utilice el siguiente procedimiento para añadir el procesamiento [!DNL Insight Servers’] nombres comunes y direcciones IP del archivo de dirección del maestro [!DNL Insight Server]. (Aunque el archivo de dirección se mantiene y se administra en el maestro [!DNL Insight Server], lo utilizan todos los [!DNL Insight Servers] en el clúster).

>[!NOTE]
>
>A continuación se supone que el archivo de dirección ya se ha configurado para el archivo maestro [!DNL Insight Server]. Si aún no ha añadido el patrón [!DNL Insight Server’s] Direcciones IP al archivo de direcciones, complete el procedimiento descrito en [Definición de la ubicación de red del servidor](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) antes de empezar.

**Para añadir el procesamiento [!DNL Insight Servers] al archivo de dirección**

1. Inicio [!DNL Insight] y cargar el perfil de configuración (si aún no está abierto) haciendo clic con el botón derecho en la barra de título y haciendo clic en **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón **[!UICONTROL Insight Server]** y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], abra el directorio Direcciones y haga lo siguiente para abrir el [!DNL Insight Server’s] archivo de dirección:

   1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación de la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda el contenido del [!DNL Locations] estructura, luego expanda NetworkLocation 0, Addresses y AddressDefinition.
1. Haga lo siguiente para agregar AddressDefinition a NetworkLocation 0 para cada procesamiento [!DNL Insight Server] en el clúster:

   1. Clic con el botón derecho **[!UICONTROL AddressDefinition]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. En el parámetro Name , especifique el procesamiento [!DNL Insight Server’s] nombre común.
   1. En el parámetro Address , especifique el [!DNL Insight Server’s] Dirección IP.

      Puede utilizar un asterisco como comodín en el campo Dirección, por ejemplo, 10.10.116.&#42;, para simplificar la agrupación en clústeres. Consulte [Explicación de los niveles de acceso](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      El ejemplo siguiente define un clúster que contiene dos [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si los servidores están conectados a varias redes, repita el paso 6 para agregar el procesamiento [!DNL Insight Servers] a NetworkLocations para esas redes.

   El siguiente ejemplo muestra un clúster de cuatro [!DNL Insight Servers] se adjuntan a dos redes (&quot;Intranet corporativa&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Actualización del archivo de control de acceso para un clúster {#section-fce1367d92a445168c35e9ca506e7d6b}

Para usar [!DNL Insight Servers] en un clúster, cada [!DNL Insight Server] en el clúster (incluido el maestro [!DNL Insight Server]) debe pertenecer al grupo de control de acceso Servidores de clúster . El grupo Servidores de clúster identifica los servidores (por dirección IP) a los que se permite participar en el clúster. Aunque este archivo se mantiene y se administra en el maestro [!DNL Insight Server], lo utilizan todos los [!DNL Insight Servers] en el clúster.

**Para editar el archivo de control de acceso**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], abra el directorio Control de acceso .
1. Haga lo siguiente para abrir el [!DNL Access Control.cfg] archivo:

   1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación de la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura Grupos de control de acceso y, a continuación, expanda Grupo de acceso (Servidores de clúster).
1. Para cada [!DNL Insight Server] en el clúster (incluido el maestro [!DNL Insight Server]), haga lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL Members]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Especifique la variable [!DNL Insight Server’s] Dirección IP (su dirección IP numérica, no su nombre). Si la variable [!DNL Insight Servers] están conectadas a varias redes, este AccessGroup debe contener solo las direcciones internas que la variable [!DNL Insight Servers] utilice para la comunicación entre servidores dentro del clúster.

      A continuación se muestra AccessGroup (Cluster Servers) para un clúster de cuatro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuración del archivo de sincronización {#section-d23e751771c84da6bab6a34a8db867bc}

Puede utilizar el siguiente procedimiento para configurar la copia central de la variable [!DNL Synchronize.cfg] archivo. La copia central de este archivo se mantiene en el maestro [!DNL Insight Server]. El procesamiento [!DNL Insight Servers] en el clúster inicie la comunicación con el maestro [!DNL Insight Server] para recuperar una copia actualizada de este archivo.

La variable [!DNL Synchronize.cfg] especifica la ubicación del maestro [!DNL Insight Server]. También identifica el conjunto de archivos administrativos que cada uno de los procesos [!DNL Insight Servers] en el clúster recupera del maestro [!DNL Insight Server]. El procesamiento [!DNL Insight Servers] descargar automáticamente estos archivos del maestro [!DNL Insight Server] cuando empiecen. También recuperan dinámicamente copias actualizadas de estos archivos del maestro [!DNL Insight Server] cuando cambien los archivos.

>[!NOTE]
>
>Aunque configure la variable [!DNL Synchronize.cfg] en el archivo maestro [!DNL Insight Server], el patrón [!DNL Insight Server] no utiliza este archivo. Actualiza este archivo en el maestro [!DNL Insight Server] para que esté correctamente configurado al procesar [!DNL Insight Servers] recupere el archivo .

**Para actualizar el archivo Synchronize.cfg en el maestro[!DNL Insight Server]**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], abra el **[!UICONTROL Components]** para el directorio Servidores de procesamiento.

1. Haga lo siguiente para abrir [!DNL Synchronize.cfg]:

   1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en el [!DNL Temp] marca de verificación y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura del componente.
1. En el parámetro Dirección del servidor primario del clúster, especifique la dirección IP del maestro (principal) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Para crear un registro que registre cada vez que se produzca una sincronización entre el maestro [!DNL Insight Server] y el procesamiento [!DNL Insight Servers], asegúrese de que el parámetro Enable Synchronization Log está establecido en &quot;true&quot;.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuración de la ubicación del conjunto de datos (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Realice el siguiente procedimiento si desea realizar el procesamiento [!DNL Insight Servers] para mantener [!DNL temp.db] (el conjunto de datos) en un directorio o unidad diferente de la ubicación predeterminada o si desea distribuir [!DNL temp.db] en varias unidades.

>[!NOTE]
>
>Porque el procesamiento [!DNL Insight Servers] todos comparten lo mismo [!DNL Disk Files.cfg], todas deben admitir las ubicaciones de archivos que especifique en este archivo. Por ejemplo, si asigna [!DNL temp.db] a la E: unidad, cada procesamiento [!DNL Insight Server] en el clúster debe tener una E: unidad.

**Para configurar la ubicación de temp.db**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], abra el **[!UICONTROL Components for Processing Servers]** directorio.

1. Haga lo siguiente para abrir [!DNL Disk Files.cfg]:

   1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón derecho en la marca de verificación de la [!DNL Temp]y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura DiskSpaceManagerComponent y, a continuación, expanda la lista Archivos de disco.
1. Editar entrada 0 para cambiar la ubicación de la variable [!DNL temp.db] archivo.
1. Si desea distribuir [!DNL temp.db] en varias unidades, siga los pasos a continuación para crear una entrada adicional para cada unidad adicional.

   1. Clic con el botón derecho **[!UICONTROL Disk Files]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. En la nueva entrada, especifique la ubicación donde desee [!DNL temp.db] escrito.
   A continuación se muestran los [!DNL temp.db] escrito en cuatro unidades.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
