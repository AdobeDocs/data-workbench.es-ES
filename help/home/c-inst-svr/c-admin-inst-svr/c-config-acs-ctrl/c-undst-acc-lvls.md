---
description: Los niveles de acceso describen qué URI del equipo puede leer o modificar un grupo de usuarios.
title: Explicación de los niveles de acceso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Explicación de los niveles de acceso{#understanding-access-levels}

{{eol}}

Los niveles de acceso describen qué URI del equipo puede leer o modificar un grupo de usuarios.

Siga estas directrices para definir los niveles de acceso que desee para los usuarios de su organización:

* Los URI específicos sin carácter de barra diagonal limitan el acceso a ese URI únicamente. Por ejemplo, [!DNL /Components/Communications.cfg] proporciona acceso al [!DNL Communications.cfg]solo archivo.

* Una barra diagonal (/), que especifica un directorio, proporciona a los miembros del grupo acceso a cualquier URI que comience con esa cadena. Por ejemplo, /Profiles/ proporciona acceso a todo el directorio Profiles .
* El símbolo de signo de dólar al final ($) restringe el acceso solo al URI exacto, aunque sea un directorio. Por ejemplo, /Profiles/$ proporciona acceso para leer el directorio principal de Perfiles, pero no para leer ningún archivo dentro de ese directorio.

   Para acceder a archivos específicos, no necesita utilizar un $ final.

   Por ejemplo, [!DNL /Components/Communications.cfg] y [!DNL /Components/Communications.cfg$] proporciona el mismo acceso.

* Se puede utilizar un símbolo de porcentaje (%) con CN (Nombre común) para permitir el acceso. Por ejemplo, /Users/%CN%/ permite el acceso al directorio de usuario que coincide con el nombre común del certificado SSL del [!DNL Insight] usuario. Tenga en cuenta que esta sintaxis solo se puede utilizar una vez en un URI.

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
   <td colname="col4"> <p>Acceso de lectura y escritura para todo <span class="keyword"> Insight Server</span> directorios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura a los dos archivos que la variable <span class="wintitle"> Sensores</span> utilice para comunicarse con el <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios </p> </td> 
   <td colname="col2"> <p>/Perfiles/ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Acceso de lectura y escritura al directorio de usuario que coincide con el nombre común del certificado SSL de la variable <span class="keyword"> Insight</span> usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios avanzados </p> </td> 
   <td colname="col2"> <p>/Perfiles/$ </p> <p>/Estado/ </p> <p>/Software/ </p> <p>/Direcciones/ </p> <p>/Usuarios/$ </p> </td> 
   <td colname="col3"> <p>/Perfiles/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Los usuarios avanzados tienen el mismo acceso que los usuarios, con la capacidad añadida de escribir en el directorio Perfiles . Estos usuarios pueden editar perfiles y permitir que los cambios se actualicen automáticamente para otros <span class="keyword"> Insight</span> usuarios, como cuando se distribuyen espacios de trabajo recién definidos. </p> </td> 
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
   <td colname="col4"> <p>Los equipos de informes tienen el mismo acceso que los usuarios avanzados, con la capacidad añadida de escribir en el <span class="filepath"> ReportStatus.vsp</span> archivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Para configurar el control de acceso**

Al definir grupos de control de acceso, debe incluir todos los administradores del sistema, usuarios, servidores de clúster y usuarios del servidor de informes que requieran acceso a este [!DNL Insight Server] equipo. Puede conceder acceso mediante la dirección IP o la información del certificado SSL, como el nombre común o la organización.

>[!NOTE]
>
>Cuando la variable [!DNL Access Control.cfg] el archivo cambia en [!DNL Insight Server], todas las conexiones existentes se terminan y se obligan a volver a conectar. Las conexiones se comprueban con los permisos en la [!DNL Access Control.cfg] archivo. En la interfaz del Administrador de servidores, la variable [!DNL Insight Server] se vuelve rojo temporalmente y luego verde de nuevo porque la conexión termina y se fuerza a volver a conectar con todos los demás.

1. En el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.

1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Files]**.

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Access Control]** para ver su contenido. La variable [!DNL Access Control.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL Access Control.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Access Control.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. En el [!DNL Access Control.cfg] ventana, haga clic en **[!UICONTROL Access Control Groups]** para ver su contenido.

   ![](assets/access_ctrl_cfg.png)

1. Para agregar un nuevo grupo de control de acceso:

   1. Clic con el botón derecho **[!UICONTROL Access Control Groups]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Clic con el botón derecho **[!UICONTROL Members]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Los miembros de los grupos predeterminados no están predefinidos. De forma predeterminada, el acceso de administrador se concede a 127.0.0.1 (host local) y [!DNL Sensor] el acceso se concede a la IP:&#42;. Se deben definir todos los demás miembros del grupo de control de acceso.

   1. Complete los parámetros.

1. Para agregar nuevos miembros a un grupo de control de acceso existente:

   1. Clic con el botón derecho **[!UICONTROL Members]** en el grupo de control de acceso correspondiente y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.

1. Para guardar los cambios realizados localmente en la variable [!DNL Insight Server] máquina, en el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Access Control.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
