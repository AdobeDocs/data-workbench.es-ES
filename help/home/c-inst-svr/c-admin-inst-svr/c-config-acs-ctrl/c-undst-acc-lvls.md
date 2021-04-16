---
description: Los niveles de acceso describen qué URI del equipo puede leer o modificar un grupo de usuarios.
title: Explicación de los niveles de acceso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Explicación de los niveles de acceso{#understanding-access-levels}

Los niveles de acceso describen qué URI del equipo puede leer o modificar un grupo de usuarios.

Siga estas directrices para definir los niveles de acceso que desee para los usuarios de su organización:

* Los URI específicos sin carácter de barra diagonal limitan el acceso a ese URI únicamente. Por ejemplo, [!DNL /Components/Communications.cfg] solo proporciona acceso al archivo [!DNL Communications.cfg].

* Una barra diagonal (/), que especifica un directorio, proporciona a los miembros del grupo acceso a cualquier URI que comience con esa cadena. Por ejemplo, /Profiles/ proporciona acceso a todo el directorio Profiles .
* El símbolo de signo de dólar al final ($) restringe el acceso solo al URI exacto, aunque sea un directorio. Por ejemplo, /Profiles/$ proporciona acceso para leer el directorio principal de Perfiles, pero no para leer ningún archivo dentro de ese directorio.

   Para acceder a archivos específicos, no necesita utilizar un $ final.

   Por ejemplo, [!DNL /Components/Communications.cfg] y [!DNL /Components/Communications.cfg$] proporcionan el mismo acceso.

* Se puede utilizar un símbolo de porcentaje (%) con CN (Nombre común) para permitir el acceso. Por ejemplo, /Users/%CN%/ permite el acceso al directorio Usuario que coincide con el nombre común del certificado SSL del usuario [!DNL Insight]. Tenga en cuenta que esta sintaxis solo se puede utilizar una vez en un URI.

Los URI de los grupos de control de acceso predefinidos se han configurado de la siguiente manera:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre del grupo </th> 
   <th colname="col2" class="entry"> Acceso de solo lectura </th> 
   <th colname="col3" class="entry"> Acceso de lectura y escritura </th> 
   <th colname="col4" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administradores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura a todos los directorios <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura a los dos archivos que los <span class="wintitle"> Sensores</span> utilizan para comunicarse con <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios </p> </td> 
   <td colname="col2"> <p>/Perfiles/ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura al directorio de usuario que coincide con el nombre común del certificado SSL del usuario <span class="keyword"> Insight</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios avanzados </p> </td> 
   <td colname="col2"> <p>/Perfiles/$ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> <p>/Perfiles/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Los usuarios avanzados tienen el mismo acceso que los usuarios, con la capacidad añadida de escribir en el directorio Perfiles . Estos usuarios pueden editar perfiles y permitir que los cambios se actualicen automáticamente para otros usuarios de <span class="keyword"> Insight</span>, como al distribuir espacios de trabajo recién definidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de clúster </p> </td> 
   <td colname="col2"> <p>/Componentes para servidores de procesamiento/ </p> <p>/Direcciones/ </p> <p>/Perfiles/ </p> <p>/Lookups/ </p> <p>/Control de acceso/ </p> <p>/Bin/ </p> <p>/Registros/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura al directorio Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de informes </p> </td> 
   <td colname="col2"> <p>/Perfiles/$ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> <p>/Perfiles/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Los equipos de informes tienen el mismo acceso que los usuarios avanzados, con la capacidad añadida de escribir en el archivo <span class="filepath"> ReportStatus.vsp</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Para configurar el control de acceso**

Al definir grupos de control de acceso, debe incluir todos los administradores del sistema, usuarios, servidores de clúster y usuarios del servidor de informes que requieran acceso a este [!DNL Insight Server] equipo. Puede conceder acceso mediante la dirección IP o la información del certificado SSL, como el nombre común o la organización.

>[!NOTE]
>
>Cuando el archivo [!DNL Access Control.cfg] se cambia en [!DNL Insight Server], todas las conexiones existentes se terminan y se fuerza la reconexión. Las conexiones se comprueban con los permisos del archivo [!DNL Access Control.cfg] actualizado. En la interfaz del Administrador de servidores, el icono [!DNL Insight Server] se vuelve a poner rojo temporalmente y, a continuación, verde de nuevo porque la conexión se termina y se fuerza a volver a conectar con todos los demás.

1. En la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Files]**.

1. En [!DNL Server Files Manager], haga clic en **[!UICONTROL Access Control]** para ver su contenido. El archivo [!DNL Access Control.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* para [!DNL Access Control.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la columna [!DNL Temp] de [!DNL Access Control.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada en la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. En la ventana [!DNL Access Control.cfg], haga clic en **[!UICONTROL Access Control Groups]** para ver su contenido.

   ![](assets/access_ctrl_cfg.png)

1. Para agregar un nuevo grupo de control de acceso:

   1. Haga clic con el botón derecho en **[!UICONTROL Access Control Groups]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Haga clic con el botón derecho en **[!UICONTROL Members]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Los miembros de los grupos predeterminados no están predefinidos. De forma predeterminada, el acceso de administrador se concede a 127.0.0.1 (host local) y el acceso [!DNL Sensor] se concede a IP:*. Se deben definir todos los demás miembros del grupo de control de acceso.

   1. Complete los parámetros.

1. Para agregar nuevos miembros a un grupo de control de acceso existente:

   1. Haga clic con el botón derecho **[!UICONTROL Members]** en el grupo de control de acceso correspondiente y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y luego haciendo clic en **[!UICONTROL Save]**.

1. Para guardar los cambios realizados localmente en el equipo [!DNL Insight Server], en [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Access Control.cfg] en la columna [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
