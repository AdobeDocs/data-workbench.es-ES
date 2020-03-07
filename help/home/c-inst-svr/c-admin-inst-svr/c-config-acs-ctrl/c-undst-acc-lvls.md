---
description: Los niveles de acceso describen los URI del equipo en los que se permite leer o modificar a un grupo de usuarios.
solution: Insight
title: Explicación de los niveles de acceso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de los niveles de acceso{#understanding-access-levels}

Los niveles de acceso describen los URI del equipo en los que se permite leer o modificar a un grupo de usuarios.

Siga estas directrices para definir los niveles de acceso deseados para los usuarios de la organización:

* Los URI específicos sin carácter de barra diagonal final solo restringen el acceso a ese URI. Por ejemplo, [!DNL /Components/Communications.cfg] proporciona acceso sólo al [!DNL Communications.cfg]archivo.

* Una barra diagonal final (/), que especifica un directorio, proporciona a los miembros del grupo acceso a cualquier URI que comience con esa cadena. Por ejemplo, /Profiles/ proporciona acceso a todo el directorio Profiles.
* Un símbolo de signo de dólar final ($) restringe el acceso al URI exacto solo, aunque sea un directorio. Por ejemplo, /Profiles/$ proporciona acceso para leer el directorio principal Profiles, pero no para leer ningún archivo dentro de ese directorio.

   Para acceder a archivos específicos, no necesita utilizar un $ final.

   Por ejemplo, [!DNL /Components/Communications.cfg] y [!DNL /Components/Communications.cfg$] proporcione el mismo acceso.

* Se puede utilizar un símbolo de porcentaje (%) con CN (Nombre común) para permitir el acceso. Por ejemplo, /Users/%CN%/ permite el acceso al directorio Usuario que coincide con el nombre común del certificado SSL del [!DNL Insight] usuario. Tenga en cuenta que esta sintaxis solo se puede usar una vez en un URI.

Los URI de los grupos de control de acceso predefinidos se han configurado de la siguiente manera:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre del grupo </th> 
   <th colname="col2" class="entry"> Acceso de sólo lectura </th> 
   <th colname="col3" class="entry"> Acceso de lectura y escritura </th> 
   <th colname="col4" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administradores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura a todos los directorios de <span class="keyword"> Insight Server</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura a los dos archivos que los <span class="wintitle"> sensores</span> utilizan para comunicarse con el <span class="keyword"> servidor</span>de Insight. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios </p> </td> 
   <td colname="col2"> <p>/Profiles/ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> /Usuarios/%CN%/ </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura al directorio Usuario que coincide con el nombre común del certificado SSL del usuario de <span class="keyword"> Insight</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios avanzados </p> </td> 
   <td colname="col2"> <p>/Profiles/$ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> <p>/Profiles/ </p> <p>/Usuarios/%CN%/ </p> </td> 
   <td colname="col4"> <p>Los usuarios avanzados tienen el mismo acceso que los usuarios, con la capacidad añadida de escribir en el directorio Perfiles. Estos usuarios pueden editar perfiles y permitir que los cambios se actualicen automáticamente para otros usuarios de <span class="keyword"> Insight</span> , como al distribuir espacios de trabajo recién definidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de clúster </p> </td> 
   <td colname="col2"> <p>/Componentes para servidores de procesamiento/ </p> <p>/Direcciones/ </p> <p>/Profiles/ </p> <p>/Lookups/ </p> <p>/Access Control/ </p> <p>/Bin/ </p> <p>/Registros/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura al directorio Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de informes </p> </td> 
   <td colname="col2"> <p>/Profiles/$ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> <p>/Profiles/ </p> <p>/Usuarios/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Los equipos de informes tienen el mismo acceso que los usuarios avanzados, con la capacidad adicional de escribir en el archivo <span class="filepath"> ReportStatus.vsp</span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Para configurar el control de acceso**

Al definir los grupos de control de acceso, debe incluir a todos los administradores de sistema, usuarios, servidores de clúster y usuarios del servidor de informes que requieran acceso a este [!DNL Insight Server] equipo. Puede otorgar acceso mediante la dirección IP o la información del certificado SSL, como el nombre común o la organización.

>[!NOTE]
>
>Cuando se cambia el [!DNL Access Control.cfg] archivo [!DNL Insight Server], todas las conexiones existentes finalizan y se ven obligadas a volver a conectarse. Las conexiones se comprueban con los permisos del [!DNL Access Control.cfg] archivo actualizado. En la interfaz del Administrador de servidores, el [!DNL Insight Server] icono se vuelve a poner rojo temporalmente y, a continuación, verde porque la conexión se termina y se fuerza a volver a conectar con todos los demás.

1. En la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Files]**.

1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Access Control]** para ver su contenido. El [!DNL Access Control.cfg] archivo se encuentra dentro de este directorio.

1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL Access Control.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Access Control.cfg].

1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. En la [!DNL Access Control.cfg] ventana, haga clic en **[!UICONTROL Access Control Groups]** para ver su contenido.

   ![](assets/access_ctrl_cfg.png)

1. Para agregar un nuevo grupo de control de acceso:

   1. Haga clic con el botón derecho **[!UICONTROL Access Control Groups]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Haga clic con el botón derecho **[!UICONTROL Members]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Los miembros de los grupos predeterminados no están predefinidos. De forma predeterminada, el acceso de administrador se concede a 127.0.0.1 (host local) y [!DNL Sensor] el acceso se concede a IP:*. Se deben definir todos los demás miembros del grupo de control de acceso.

   1. Complete los parámetros.

1. Para agregar nuevos miembros a un grupo de control de acceso existente:

   1. Haga clic con el botón secundario **[!UICONTROL Members]** en el grupo de control de acceso correspondiente y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Guarde el archivo haciendo clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y luego haciendo clic en **[!UICONTROL Save]**.

1. Para guardar los cambios realizados localmente en el [!DNL Insight Server] equipo, en la [!DNL Server Files Manager], haga clic con el botón secundario en la marca de verificación de [!DNL Access Control.cfg] la [!DNL Temp] columna y, a continuación, haga clic en **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

