---
description: El archivo Access Control.cfg administra el acceso a determinadas funciones de Insight Server.
title: Actualización del archivo de control de acceso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: 5ce5b8f8b35d2d4f319076f54347e300e5f133df
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 3%

---

# Actualización del archivo de control de acceso{#updating-the-access-control-file}

{{eol}}

El archivo Access Control.cfg administra el acceso a determinadas funciones de Insight Server.

Define entidades denominadas AccessGroups. Un grupo de acceso identifica un grupo de usuarios que tienen permiso para utilizar determinadas características del servidor.

Antes de conectarse a [!DNL Insight Server] con [!DNL Insight], debe actualizar el grupo de acceso de administradores para incluir uno de los [!DNL Insight] licencias que el Adobe ha emitido a su organización. Este grupo de acceso identifica a los usuarios a los que se permite realizar funciones administrativas mediante [!DNL Insight].

En el siguiente procedimiento se describe cómo agregar una licencia al grupo de acceso de administradores. Para completar esta tarea, debe determinar cuál [!DNL Insight] tiene privilegios administrativos para su organización. (Para la configuración inicial, la concesión de privilegios administrativos a una única licencia es suficiente. Puede otorgar privilegios administrativos a licencias adicionales más adelante). También necesita saber el &quot;nombre común&quot; asignado a esta licencia.

El propósito de este procedimiento es simplemente identificar una copia con licencia de [!DNL Insight] que puede utilizar para configurar inicialmente [!DNL Insight Server]. Una vez identificada esta licencia, puede realizar todas las configuraciones de servidor subsiguientes (incluida la configuración de AccessGroup adicional) utilizando la copia con licencia de [!DNL Insight]. Para obtener información adicional sobre cómo controlar el acceso al servidor mediante AccessGroups, consulte [Configuración del control de acceso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Para actualizar el archivo de control de acceso**

1. Vaya a [!DNL Access Control] carpeta en el directorio donde instaló [!DNL Insight Server].

   Ejemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra el [!DNL Access Control.cfg] en un editor de texto como Notepad.
1. Busque la entrada CN en el grupo de acceso de administradores y reemplace el valor existente de esta entrada por el nombre común que identifica la entrada [!DNL Insight] que utilizará para configurar y administrar inicialmente [!DNL Insight Server]. El siguiente fragmento de archivo ilustra dónde se inserta el nombre común en la variable [!DNL Access Control.cfg] archivo.

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

   * O (ID de organización): esta entrada representa el ID de la organización. Por ejemplo, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Esta ID se puede encontrar en el Admin Console.
   * PLC: esta entrada permite acceder a los usuarios aprovisionados para una configuración de producto en particular. Se puede utilizar en formato `Organization_Id-PLC`. Por ejemplo, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Los usuarios aprovisionados para la Data Workbench mediante el PLC `DataworkbenchAdminUsers` tendrán acceso a sus servidores.
   * Correo electrónico: esta entrada permite el acceso a cualquier usuario individual. Su valor debe ser la dirección de correo electrónico del usuario aprovisionado. Por ejemplo, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Las entradas distinguen entre mayúsculas y minúsculas. Debe asegurarse de que los valores especificados para O, PLC y Email sean exactamente iguales a los que se muestran en el Admin Console.
   >    * Escriba el nombre común exactamente como aparece en el certificado.
   >    * No utilice el tabulador para generar espacios en blanco en [!DNL Access Control.cfg] (o en cualquier otro archivo de configuración de un componente de Adobe). Utilice solo espacios para crear espacios en blanco. Un carácter de tabulación impide que el sistema lea el archivo correctamente.


1. Guarde y cierre el archivo.
