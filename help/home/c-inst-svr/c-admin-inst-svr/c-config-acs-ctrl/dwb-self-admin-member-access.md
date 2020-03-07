---
description: Los administradores pueden dar a los usuarios de la estación de trabajo la capacidad parcial de administrar el control de acceso para los grupos personalizados.
title: Administración de usuarios de acceso de miembros del grupo
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# User Administration of Group Member Access{#user-administration-of-group-member-access}

Los administradores pueden dar a los usuarios de la estación de trabajo la capacidad parcial de administrar el control de acceso para los grupos personalizados.

**La autoadministración del acceso** de miembros del grupo otorga derechos a los no administradores para agregar y eliminar miembros en un grupo personalizado. El administrador crea un archivo de lista **de** usuarios y configura el acceso de grupo en el archivo [Access Control.cfg](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) para los nuevos miembros del grupo.

**Acceso al Administrador de servidores**

La configuración del **[!DNL User List]** archivo y su sincronización con el **[!DNL Communications.cfg]** archivo se realiza en el espacio de trabajo del Administrador **de** servidores.

1. En la superficie de trabajo, haga clic en la ficha **Administración** > **Conjunto de datos y perfil** .

1. Abra el espacio de trabajo **Administrador** de servidores.
1. Haga clic con el botón derecho >*su nombre* de servidor> en el diagrama y seleccione **Archivos**.

   Los archivos del servidor se abrirán en una tabla con las columnas *Archivo*, *`<server name>`* y *Temperatura*.

1. **Convertir en local** haciendo clic con el botón derecho en la columna de servidor de un archivo de servidor (para esta función **[!DNL Access Control]** y **[!DNL Components/Communications.cfg)]**.

   Aparecerá una marca de verificación blanca en la columna **temporal** . Puede editar en la carpeta temporal. A continuación, haga clic con el botón secundario en la marca de verificación y **Guardar en** el servidor. (Se vuelve rojo cuando se sincroniza con el servidor).

## Crear un archivo User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

El administrador debe crear un **[!DNL User List.cfg]** archivo en la **[!DNL Access Control]** carpeta.

1. Haga clic con el botón derecho en la fila*** Control de acceso** de la columna **Temp** y seleccione **Abrir** > **Carpeta**. ![](assets/6_4_workstation_groups_3.png)

   La carpeta Control de acceso de la carpeta **Temp** se abrirá enumerando un solo **[!DNL Access Control.cfg]** archivo.

1. Agregue otro archivo de texto a esta carpeta y asígnele un nombre **[!DNL User List.cfg]** (junto al **[!DNL Access Control.cfg]**).

1. Add the following parameters to the **[!DNL User List.cfg]** file.

El archivo de lista de usuarios debe contener un vector de objetos **AccessGroup** y cada objeto **AccessGroup** debe tener un nombre y un vector de cadenas denominado **Miembros**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

A continuación, puede editar y agregar usuarios en la vista de estación de trabajo del archivo **[!DNL User List.cfg]***.

![](assets/6_4_workstation_groups_4.png)

Estos son los parámetros más básicos que se deben agregar al **[!DNL User List.cfg]** archivo. Los Miembros se pueden agregar en la vista Estación de trabajo.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Al igual que con cualquier **[!DNL .cfg]** archivo que edite manualmente, asegúrese de utilizar espacios en lugar de fichas y de prestar especial atención al espacio en blanco y a la sintaxis. Un error en este archivo hará que *Adobe Insight Server* ignore el archivo de lista de usuarios.

Se hará referencia al campo **Nombre** de cada grupo **de** acceso dentro del [!DNL Access Control.cfg] archivo.

>[!NOTE]
>
>Sólo miembros válidos con prefijos de servicio de directorio, como **CN:** o **OU:** y no pueden contener caracteres comodín (*).

## Configuración del archivo Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

En primer lugar, un administrador activa esta función abriendo el archivo **[!DNL Components]>[!DNL Communications.cfg]**y agregando una nueva clave con el nombre **[!DNL Access Control User List File]**. El valor de cadena de esta clave es la ruta donde se ubicará este nuevo archivo.

1. En los archivos del servidor, haga clic en **Componentes** y, a continuación, haga clic con el botón secundario en la marca de verificación de la columna del servidor. Haga clic en **Convertir en local**.

   Aparecerá una marca de verificación blanca en la columna **temporal** .

1. Haga clic con el botón derecho en la marca de verificación de la columna **Temperatura** y seleccione **Abrir** > **en Estación de trabajo**.

1. En el archivo **Communication.cfg** , haga clic con el botón derecho en el **componente** y seleccione **Agregar clave personalizada.** ![](assets/6_4_workstation_groups.png)

1. Escriba el **Nombre** como Archivo *de lista de usuarios de control de* acceso y establezca **El tipo** como *Cadena*.

   >[!NOTE]
   No puede crear el nuevo archivo de lista como una ruta. Para solucionar esto, debe guardar el archivo, abrirlo en un editor (Bloc de notas) y cambiar &quot;String&quot; por &quot;Path&quot;:

   Antes de registrar los valores de:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   Después:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. Guarde el **[!DNL Communications.cfg]** archivo y, si es necesario, guárdelo en el servidor. Esto reiniciará los componentes del servidor para asegurarse de que no ha cometido ningún error que pudiera impedir que se analizara el **[!DNL Communications.cfg]** archivo.
1. Si el sistema incluye servidores de procesamiento, modifique el archivo de configuración en el **[!DNL Components for Processing Servers.cfg]** archivo.
1. Haga clic con el botón secundario **[!DNL Communications.cfg]** y guarde en el servidor.

El administrador del área de trabajo de datos ahora puede confirmar que los usuarios a los que va destinado tienen acceso al archivo de lista de usuarios y permiten a los usuarios administrar el grupo. Los usuarios podrán abrir el archivo de lista de usuarios, editarlo y agregar y eliminar miembros de CN u OU según sea necesario.

## Sincronizar el archivo Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

A continuación, el administrador puede editar **[!DNL Access Control.cfg]** e insertar referencias a los grupos definidos por el archivo de lista *de* usuarios.

Las referencias a los grupos deben insertarse como cualquier otro miembro, pero con la siguiente sintaxis:

```
$(Group Name)
```

Donde &quot;Nombre del grupo&quot; coincide con lo que se define en el archivo de lista de usuarios, incluidos los espacios en blanco. ![](assets/6_4_workstation_groups_2.png)

En este punto, el administrador del área de trabajo de datos puede confirmar que los usuarios del grupo seleccionado tienen acceso al archivo de lista de usuarios. A continuación, los usuarios seleccionados pueden abrir el **[!DNL User List.cfg]** archivo, editarlo y agregar y quitar miembros CN u OU según sea necesario.
