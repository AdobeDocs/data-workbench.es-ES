---
description: El archivo Control de acceso.cfg administra el acceso a determinadas funciones de Insight Server.
solution: Analytics
title: Actualización del archivo de control de acceso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---


# Actualización del archivo de control de acceso{#updating-the-access-control-file}

El archivo Control de acceso.cfg administra el acceso a determinadas funciones de Insight Server.

Define entidades denominadas AccessGroups. AccessGroup identifica un grupo de usuarios que tienen permiso para utilizar determinadas funciones del servidor.

Para poder conectarse a [!DNL Insight Server] con [!DNL Insight], debe actualizar el grupo de acceso de administradores para incluir una de las [!DNL Insight] licencias que Adobe ha emitido a su organización. AccessGroup identifica a los usuarios a los que se permite realizar funciones administrativas mediante [!DNL Insight].

El siguiente procedimiento describe cómo agregar una licencia al grupo de acceso de administradores. Para completar esta tarea, debe determinar qué [!DNL Insight] licencia tiene privilegios administrativos para su organización. (Para la configuración y configuración iniciales, la concesión de privilegios administrativos a una única licencia es suficiente. Puede otorgar privilegios administrativos a licencias adicionales más adelante). También necesita conocer el &quot;nombre común&quot; asignado a esta licencia. Para obtener este valor, puede examinar los certificados de licencia de su cuenta en [https://aap.adobe.com](https://aap.adobe.com).

El propósito de este procedimiento es simplemente identificar una copia con licencia de la [!DNL Insight] que puede utilizar para configurar y configurar inicialmente [!DNL Insight Server]. Una vez que identifique esta licencia, puede realizar todas las configuraciones de servidor subsiguientes (incluida la configuración de AccessGroup adicional) mediante la copia con licencia de [!DNL Insight]. Para obtener información adicional sobre el control del acceso al servidor mediante AccessGroups, consulte [Configuración de Control de acceso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Para actualizar el archivo control de acceso**

1. Vaya a la [!DNL Access Control] carpeta del directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra el [!DNL Access Control.cfg] archivo en un editor de texto como Bloc de notas.
1. Busque la entrada CN en el grupo de acceso de administradores y reemplace el valor existente de esta entrada por el nombre común que identifica el [!DNL Insight] que utilizará para configurar y administrar inicialmente [!DNL Insight Server]. El siguiente fragmento de archivo ilustra dónde se inserta el nombre común en el [!DNL Access Control.cfg] archivo.

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   Si utiliza la autenticación basada en credenciales, habrá algunas entradas adicionales disponibles para la configuración. Estas entradas son:

   * O (identificador de organización): Esta entrada representa el ID de la organización. Por ejemplo: `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Este ID se encuentra en el Admin Console.
   * PLC: Esta entrada permite acceder a los usuarios aprovisionados para una configuración de producto concreta. Se puede utilizar en formato `Organization_Id-PLC`. Por ejemplo: `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Los usuarios aprovisionados para la Data Workbench mediante PLC `DataworkbenchAdminUsers` obtendrán acceso a sus servidores.
   * Correo electrónico: Esta entrada permite el acceso a cualquier usuario individual. Su valor debe ser la dirección de correo electrónico del usuario aprovisionado. Por ejemplo: `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Las entradas distinguen entre mayúsculas y minúsculas. Debe asegurarse de que los valores especificados para O, PLC y Correo electrónico son exactamente los mismos que los que se muestran en el Admin Console.
   >    * Escriba el nombre común exactamente como aparece en el certificado.
   >    * No utilice la tecla Tab para generar espacios en blanco en el [!DNL Access Control.cfg] archivo (o en cualquier otro archivo de configuración de un componente Adobe). Utilice solo espacios para crear espacios en blanco. Un carácter de tabulación impide que el sistema lea el archivo correctamente.


1. Guarde y cierre el archivo.

