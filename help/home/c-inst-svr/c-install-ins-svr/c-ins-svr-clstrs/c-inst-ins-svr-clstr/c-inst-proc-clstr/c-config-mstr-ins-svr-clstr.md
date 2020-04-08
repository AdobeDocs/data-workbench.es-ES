---
description: Información sobre la configuración del clúster en el servidor de Master Insight Server, la actualización del archivo control de acceso para un clúster y mucho más.
solution: Insight
title: Configuración del servidor maestro de perspectiva para la agrupación en clúster
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# Configuración del servidor maestro de perspectiva para la agrupación en clúster{#configuring-the-master-insight-server-for-clustering}

Información sobre la configuración del clúster en el servidor de Master Insight Server, la actualización del archivo control de acceso para un clúster y mucho más.

Para configurar el clúster, realice los siguientes pasos en el maestro [!DNL Insight Server]:

* Añada los nombres y direcciones [!DNL Insight Servers’] comunes de procesamiento en el archivo de direcciones.
* Añada todo el [!DNL Insight Servers] en el grupo Servidores de clúster del [!DNL Access Control.cfg] archivo.

* Actualice el [!DNL Synchronize.cfg] archivo en el directorio Componentes para servidores de procesamiento para que señale al maestro [!DNL Insight Server].

* Si es necesario, modifique el [!DNL Disk Files.cfg] archivo en el directorio Componentes para servidores de procesamiento para especificar la ubicación del [!DNL temp.db] archivo en el proceso [!DNL Insight Servers].

Para completar estos pasos, debe conocer los nombres comunes (según se especifica en los certificados digitales del individuo [!DNL Insight Server]) y las direcciones IP de cada uno [!DNL Insight Server] del clúster. Si todavía no dispone de esta información, obténgala antes de continuar.

>[!NOTE]
>
>Los procedimientos descritos en esta sección requieren [!DNL Insight]. Si no ha instalado [!DNL Insight], siga las instrucciones de la **[!DNL Insight]Guía **del usuario antes de continuar.

## Añadir los servidores de perspectiva de procesamiento en el archivo de direcciones {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Utilice el procedimiento siguiente para agregar los nombres [!DNL Insight Servers’] comunes de procesamiento y las direcciones IP al archivo de direcciones del maestro [!DNL Insight Server]. (Aunque el archivo de dirección se mantiene y administra en el maestro [!DNL Insight Server], lo utilizan todos los [!DNL Insight Servers] del clúster).

>[!NOTE]
>
>Lo siguiente supone que el archivo de dirección ya se ha configurado para el maestro [!DNL Insight Server]. Si aún no ha agregado las direcciones [!DNL Insight Server’s] IP maestras al archivo de direcciones, complete el procedimiento descrito en [Definición de la ubicación](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) de red del servidor antes de comenzar.

**Para agregar el procesamiento[!DNL Insight Servers]al archivo de dirección**

1. Inicio [!DNL Insight] y cargue el perfil de configuración (si aún no está abierto) haciendo clic con el botón secundario en la barra de título y haciendo clic en **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón **[!UICONTROL Insight Server]** y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], abra el directorio Direcciones y haga lo siguiente para abrir el archivo de [!DNL Insight Server’s] direcciones:

   1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón secundario en la marca de verificación de la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda el contenido de la [!DNL Locations] estructura y luego NetworkLocation 0, Address y AddressDefinition.
1. Para agregar una AddressDefinition a NetworkLocation 0 para cada procesamiento [!DNL Insight Server] del clúster, haga lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL AddressDefinition]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. En el parámetro Name, especifique el nombre [!DNL Insight Server’s] común de procesamiento.
   1. En el parámetro Address, especifique la dirección [!DNL Insight Server’s] IP de procesamiento.

      Puede utilizar un asterisco como comodín en el campo Dirección, como 10.10.116.*, para simplificar la agrupación en clúster. Consulte [Explicación de los niveles](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)de acceso.

      El ejemplo siguiente define un clúster que contiene dos [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Si los servidores están conectados a varias redes, repita el paso 6 para agregar el procesamiento [!DNL Insight Servers] a NetworkLocations para esas redes.

   El siguiente ejemplo muestra un grupo de cuatro [!DNL Insight Servers] anexados a dos redes (&quot;Intranet corporativa&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Actualización del archivo Control de acceso de un clúster {#section-fce1367d92a445168c35e9ca506e7d6b}

Para usar [!DNL Insight Servers] en un clúster, cada uno [!DNL Insight Server] del clúster (incluido el maestro [!DNL Insight Server]) debe pertenecer al grupo de controles de acceso Servidores de clúster. El grupo Servidores de clúster identifica los servidores (por dirección IP) a los que se permite participar en el clúster. Aunque este archivo se mantiene y administra en el maestro [!DNL Insight Server], lo utilizan todos los [!DNL Insight Servers] del clúster.

**Para editar el archivo control de acceso**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], abra el directorio de Control de acceso.
1. Para abrir el [!DNL Access Control.cfg] archivo, haga lo siguiente:

   1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón secundario en la marca de verificación de la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura Grupos de Control de acceso y luego expanda AccessGroup (Servidores de clúster).
1. Para cada [!DNL Insight Server] componente del clúster (incluido el maestro [!DNL Insight Server]), haga lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL Members]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Especifique la dirección [!DNL Insight Server’s] IP (su dirección IP numérica, no su nombre). Si los [!DNL Insight Servers] están conectados a varias redes, este AccessGroup debe contener solamente las direcciones internas que [!DNL Insight Servers] utiliza para la comunicación entre servidores dentro del clúster.

      A continuación se muestra AccessGroup (Servidores de clúster) para un clúster de cuatro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL Temp] columna y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuración del archivo de sincronización {#section-d23e751771c84da6bab6a34a8db867bc}

Puede utilizar el procedimiento siguiente para configurar la copia central del [!DNL Synchronize.cfg] archivo. La copia central de este archivo se mantiene en el maestro [!DNL Insight Server]. El procesamiento [!DNL Insight Servers] del clúster inicia la comunicación con el maestro [!DNL Insight Server] para recuperar una copia actualizada de este archivo.

El [!DNL Synchronize.cfg] archivo especifica la ubicación del maestro [!DNL Insight Server]. También identifica el conjunto de archivos administrativos que cada uno de los procesos [!DNL Insight Servers] del clúster recupera del maestro [!DNL Insight Server]. El procesamiento [!DNL Insight Servers] descarga automáticamente estos archivos del maestro [!DNL Insight Server] cuando se inicio. También recuperan de forma dinámica copias actualizadas de estos archivos desde el maestro [!DNL Insight Server] cuando cambian los archivos.

>[!NOTE]
>
>Aunque se configura el [!DNL Synchronize.cfg] archivo en el archivo principal [!DNL Insight Server], el [!DNL Insight Server] propio maestro no utiliza este archivo. Este archivo se actualiza en el archivo principal [!DNL Insight Server] para que se configure correctamente cuando el procesamiento [!DNL Insight Servers] recupere el archivo.

**Para actualizar el archivo Synchronize.cfg en el maestro[!DNL Insight Server]**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], abra el directorio **[!UICONTROL Components]** para servidores de procesamiento.

1. Para abrir [!DNL Synchronize.cfg]:

   1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón secundario en la [!DNL Temp] marca de verificación y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura del componente.
1. En el parámetro de dirección del servidor primario del clúster, especifique la dirección IP del maestro (principal) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Para crear un registro que registre cada vez que se produce la sincronización entre el maestro [!DNL Insight Server] y el procesamiento [!DNL Insight Servers], asegúrese de que el parámetro Habilitar registro de sincronización está establecido en &quot;true&quot;.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL Temp] columna y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuración de la ubicación del conjunto de datos (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Realice el siguiente procedimiento si desea que el procesamiento [!DNL Insight Servers] se mantenga [!DNL temp.db] (el conjunto de datos) en un directorio o unidad diferente de la ubicación predeterminada o si desea distribuir [!DNL temp.db] en varias unidades.

>[!NOTE]
>
>Dado que el procesamiento [!DNL Insight Servers] todos comparten el mismo [!DNL Disk Files.cfg], todos deben admitir las ubicaciones de archivo que especifique en este archivo. Por ejemplo, si asigna [!DNL temp.db] a la E: , cada procesamiento [!DNL Insight Server] del clúster debe tener una E: unidad.

**Para configurar la ubicación de temp.db**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del patrón [!DNL Insight Server] y haga clic en **[!UICONTROL Server Files]**.

1. En el [!DNL Server Files Manager], abra el **[!UICONTROL Components for Processing Servers]** directorio.

1. Para abrir [!DNL Disk Files.cfg]:

   1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor y haga clic en **[!UICONTROL Make Local]**.

   1. Haga clic con el botón secundario en la marca de verificación de la [!DNL Temp]columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda la estructura DiskSpaceManagerComponent y, a continuación, expanda la lista Disk Files.
1. Edite la entrada 0 para cambiar la ubicación del [!DNL temp.db] archivo.
1. Si desea distribuir [!DNL temp.db] entre varias unidades, utilice los pasos siguientes para crear una entrada adicional para cada unidad adicional.

   1. Haga clic con el botón derecho **[!UICONTROL Disk Files]** y haga clic en **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. En la nueva entrada, especifique la ubicación en la que desea [!DNL temp.db] escribir.
   A continuación se muestra [!DNL temp.db] escrito en cuatro unidades.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL Temp] columna y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

