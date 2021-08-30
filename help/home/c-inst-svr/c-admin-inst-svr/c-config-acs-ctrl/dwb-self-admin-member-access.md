---
description: Los administradores pueden dar a los usuarios de la estación de trabajo la capacidad parcial de administrar el control de acceso para los grupos personalizados.
title: Administración de usuario del acceso de los miembros del grupo
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Administración de usuario del acceso de los miembros del grupo{#user-administration-of-group-member-access}

Los administradores pueden dar a los usuarios de la estación de trabajo la capacidad parcial de administrar el control de acceso para los grupos personalizados.

**La autoadministración de** acceso de miembros del grupo otorga derechos a los no administradores para agregar y eliminar miembros en un grupo personalizado. El administrador crea un archivo **User List** y configura el acceso de grupo en el archivo [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) para los nuevos miembros del grupo.

**Acceso al Administrador de servidores**

La configuración del archivo **[!DNL User List]** y la sincronización con el archivo **[!DNL Communications.cfg]** se realiza en el espacio de trabajo **Servers Manager**.

1. En la superficie de trabajo, haga clic en la pestaña **Admin** > **Dataset and Profile**.

1. Abra el espacio de trabajo **Servers Manager**.
1. Haga clic con el botón derecho >*su nombre de servidor* en el diagrama y seleccione **Files**.

   Los archivos del servidor se abrirán en una tabla con las columnas *File*, *`<server name>`* y *Temp*.

1. **Haga** clic con el botón derecho en la columna de servidor de un archivo de servidor (para esta función  **[!DNL Access Control]** y  **[!DNL Components/Communications.cfg)]**).

   Aparecerá una marca de verificación blanca en la columna **Temp**. Puede editar en la carpeta temporal. A continuación, haga clic con el botón derecho en la marca de verificación y **Save To** en el servidor. (Se vuelve rojo cuando se sincroniza con el servidor).

## Crear un archivo User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

El administrador debe crear un archivo **[!DNL User List.cfg]** en la carpeta **[!DNL Access Control]**.

1. Haga clic con el botón derecho del ratón** en la fila **Temp** y seleccione **Abrir** > **Carpeta**. ![](assets/6_4_workstation_groups_3.png)

   La carpeta Control de acceso de la carpeta **Temp** se abrirá y mostrará un solo archivo **[!DNL Access Control.cfg]**.

1. Agregue otro archivo de texto a esta carpeta y asígnele el nombre **[!DNL User List.cfg]** (junto a **[!DNL Access Control.cfg]**).

1. Agregue los siguientes parámetros al archivo **[!DNL User List.cfg]**.

El archivo Lista de usuarios debe contener un vector de objetos **AccessGroup** y cada objeto **AccessGroup** debe tener un nombre y un vector de cadenas denominado **Members**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

A continuación, puede editar y agregar esto a los usuarios en la vista Estación de trabajo del archivo **[!DNL User List.cfg]**.

![](assets/6_4_workstation_groups_4.png)

Estos son los parámetros más básicos que se deben agregar al archivo **[!DNL User List.cfg]**. Los Miembros se pueden agregar luego en la vista Estación de trabajo.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Al igual que con cualquier archivo **[!DNL .cfg]** que edite manualmente, asegúrese de utilizar espacios en lugar de pestañas y de prestar especial atención a los espacios en blanco y la sintaxis. Un error en este archivo hará que *Adobe Insight Server* ignore el archivo de lista de usuarios.

Se hará referencia al campo **Name** de cada **Grupo de acceso** dentro del archivo [!DNL Access Control.cfg].

>[!NOTE]
>
>Solo se aceptan miembros válidos con prefijos de servicio de directorio, como **CN:** o **OU:**, que no pueden contener caracteres comodín (*).

## Configuración del archivo Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Un administrador habilita primero esta función abriendo el archivo **[!DNL Components]>[!DNL Communications.cfg]** y agregando una clave nueva con el nombre **[!DNL Access Control User List File]**. El valor de cadena de esta clave es la ruta donde se ubicará este nuevo archivo.

1. En los archivos del servidor, haga clic en **Componentes** y haga clic con el botón derecho en la marca de verificación de la columna del servidor. Haga clic en **Convertir en local**.

   Aparecerá una marca de verificación blanca en la columna **Temp**.

1. Haga clic con el botón derecho en la marca de verificación de la columna **Temp** y seleccione **Abrir** > **en Workstation**.

1. En el archivo **Communication.cfg**, haga clic con el botón derecho en **component** y seleccione **Agregar clave personalizada.** ![](assets/6_4_workstation_groups.png)

1. Escriba **Nombre** como *Archivo de lista de usuarios de control de acceso* y establezca **De tipo** como *Cadena*.

   >[!NOTE]
   No puede crear el nuevo archivo de lista como una ruta. Para remediar esto, debe guardar el archivo, abrirlo en un editor (Bloc de notas) y cambiar &quot;String&quot; a &quot;Path&quot;:

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

1. Guarde el archivo **[!DNL Communications.cfg]** y (si es necesario) guárdelo en el servidor. Esto reiniciará los componentes del servidor para asegurarse de que no se ha cometido ningún error que pudiera impedir que se analice el archivo **[!DNL Communications.cfg]**.
1. Si el sistema incluye servidores de procesamiento, modifique el archivo de configuración en el archivo **[!DNL Components for Processing Servers.cfg]**.
1. Haga clic con el botón derecho en **[!DNL Communications.cfg]** y guarde en el servidor.

El administrador de Datas Workbench ahora puede confirmar que los usuarios a los que va dirigido tengan acceso al archivo de lista de usuarios y permitir que los usuarios administren el grupo. Los usuarios podrán abrir el archivo Lista de usuarios, editarlo y agregar y quitar miembros CN u OU según sea necesario.

## Sincronizar el archivo Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

A continuación, el administrador puede editar el **[!DNL Access Control.cfg]** e insertar referencias a los grupos definidos por el archivo *Lista de usuarios*.

Las referencias a los grupos deben insertarse como cualquier otro miembro, pero con la siguiente sintaxis:

```
$(Group Name)
```

Donde &quot;Nombre de grupo&quot; coincide con lo definido en el archivo de lista de usuarios, incluidos los espacios en blanco. ![](assets/6_4_workstation_groups_2.png)

En este punto, el administrador de Datas Workbench puede confirmar que los usuarios del grupo seleccionado tienen acceso al archivo de lista de usuarios. A continuación, los usuarios seleccionados pueden abrir el archivo **[!DNL User List.cfg]**, editarlo y añadir y eliminar miembros CN u OU según sea necesario.
