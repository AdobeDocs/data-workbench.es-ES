---
description: Los administradores pueden dar a los usuarios de la estación de trabajo la capacidad parcial de administrar el control de acceso para los grupos personalizados.
title: Administración de usuario del acceso de los miembros del grupo
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Administración de usuario del acceso de los miembros del grupo{#user-administration-of-group-member-access}

{{eol}}

Los administradores pueden dar a los usuarios de la estación de trabajo la capacidad parcial de administrar el control de acceso para los grupos personalizados.

**Autoadministración del acceso de los miembros del grupo** otorga derechos a los no administradores para agregar y eliminar miembros en un grupo personalizado. El administrador crea un **Lista de usuarios** y configura el acceso de grupo en la variable [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) para los nuevos miembros del grupo.

**Acceso al Administrador de servidores**

Configuración de la variable **[!DNL User List]** y sincronizarlo con **[!DNL Communications.cfg]** se realiza en la variable **Administrador de servidores** espacio de trabajo.

1. En la superficie de trabajo, haga clic en el botón **Administrador** pestaña > **Conjunto de datos y perfil** pestaña .

1. Abra el **Administrador de servidores** espacio de trabajo.
1. Haga clic con el botón derecho >*su nombre de servidor*> en el diagrama y seleccione **Archivos**.

   Los archivos del servidor se abrirán en una tabla con columnas *Archivo*, *`<server name>`* y *Temp*.

1. **Convertir en local** haciendo clic con el botón derecho en la columna server de un archivo server (para esta función) **[!DNL Access Control]** y **[!DNL Components/Communications.cfg)]**.

   Aparecerá una marca de verificación blanca en la variable **Temp** para abrir el Navegador. Puede editar en la carpeta temporal. A continuación, haga clic con el botón derecho en la marca de verificación y **Guardar en** el servidor. (Se vuelve rojo cuando se sincroniza con el servidor).

## Crear un archivo User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

El administrador debe crear un **[!DNL User List.cfg]** en el **[!DNL Access Control]** carpeta.

1. Haga clic con el botón derecho del ratón en la fila** Control de acceso** de la **Temp** y seleccione **Apertura** > **Carpeta**. ![](assets/6_4_workstation_groups_3.png)

   La carpeta Control de acceso en la **Temp** se abrirá la lista de **[!DNL Access Control.cfg]** archivo.

1. Añada otro archivo de texto a esta carpeta y asígnele un nombre **[!DNL User List.cfg]** (junto al **[!DNL Access Control.cfg]**).

1. Añada los siguientes parámetros al **[!DNL User List.cfg]** archivo.

El archivo Lista de usuarios debe contener un vector de **AccessGroup** objetos y cada **AccessGroup** El objeto debe tener un nombre y un vector de cadenas denominado **Miembros**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

A continuación, puede editar y agregar usuarios en la vista Estación de trabajo del **[!DNL User List.cfg]**archivo.

![](assets/6_4_workstation_groups_4.png)

Estos son los parámetros más básicos que se deben agregar a la variable **[!DNL User List.cfg]** archivo. Los Miembros se pueden agregar luego en la vista Estación de trabajo.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Como con cualquier **[!DNL .cfg]** que edite manualmente, asegúrese de utilizar espacios en lugar de pestañas y de prestar especial atención a los espacios en blanco y a la sintaxis. Un error en este archivo causará *Adobe Insight Server* para ignorar el archivo Lista de usuarios.

La variable **Nombre** en cada **Grupo de acceso** se hace referencia dentro de la variable [!DNL Access Control.cfg] archivo.

>[!NOTE]
>
>Solo miembros válidos con prefijos de servicio de directorio, como **CN:** o **OU:** se aceptan y no pueden contener caracteres comodín (&#42;).

## Configuración del archivo Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Un administrador habilita primero esta función abriendo la variable **[!DNL Components]>[!DNL Communications.cfg]** y agregando una clave nueva con el nombre **[!DNL Access Control User List File]**. El valor de cadena de esta clave es la ruta donde se ubicará este nuevo archivo.

1. En los archivos del servidor, haga clic en **Componentes** y haga clic con el botón derecho en la marca de verificación de la columna servidor. Haga clic en **Convertir en local**.

   Aparecerá una marca de verificación blanca en la variable **Temp** para abrir el Navegador.

1. Haga clic con el botón derecho en la marca de verificación de la **Temp** y seleccione **Apertura** > **en Workstation**.

1. En el **Communication.cfg** archivo, clic con el botón derecho **componente** y seleccione **Agregar clave personalizada.** ![](assets/6_4_workstation_groups.png)

1. Escriba la **Nombre** como *Archivo de lista de usuarios de control de acceso* y establezca **De tipo** como *Cadena*.

   >[!NOTE]
   >
   >No puede crear el nuevo archivo de lista como una ruta. Para remediar esto, debe guardar el archivo, abrirlo en un editor (Bloc de notas) y cambiar &quot;String&quot; a &quot;Path&quot;:

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

1. Guarde el **[!DNL Communications.cfg]** y (si es necesario) guárdelo en el servidor. Esto reiniciará los componentes en el servidor para asegurarse de que no ha cometido ningún error que pudiera impedir la **[!DNL Communications.cfg]** del archivo que se va a analizar.
1. Si el sistema incluye servidores de procesamiento, modifique el archivo de configuración en la **[!DNL Components for Processing Servers.cfg]** archivo.
1. Clic con el botón derecho **[!DNL Communications.cfg]** y guardar en el servidor.

El administrador de Datas Workbench ahora puede confirmar que los usuarios a los que va dirigido tengan acceso al archivo de lista de usuarios y permitir que los usuarios administren el grupo. Los usuarios podrán abrir el archivo Lista de usuarios, editarlo y agregar y quitar miembros CN u OU según sea necesario.

## Sincronizar el archivo Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

El administrador puede editar la variable **[!DNL Access Control.cfg]** e inserte referencias a los grupos definidos por el *Lista de usuarios* archivo.

Las referencias a los grupos deben insertarse como cualquier otro miembro, pero con la siguiente sintaxis:

```
$(Group Name)
```

Donde &quot;Nombre de grupo&quot; coincide con lo definido en el archivo de lista de usuarios, incluidos los espacios en blanco. ![](assets/6_4_workstation_groups_2.png)

En este punto, el administrador de Datas Workbench puede confirmar que los usuarios del grupo seleccionado tienen acceso al archivo de lista de usuarios. A continuación, los usuarios seleccionados pueden abrir el **[!DNL User List.cfg]** , edite y agregue y elimine los miembros CN u OU según sea necesario.
