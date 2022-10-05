---
description: El acceso a y los permisos dentro del portal de informes se controlan mediante cuentas de usuario y grupo individuales.
title: Edición del archivo Email.asp
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 2%

---

# Edición del archivo Email.asp{#edit-the-email-asp-file}

{{eol}}

El acceso a y los permisos dentro del portal de informes se controlan mediante cuentas de usuario y grupo individuales.

Cada vez que agregue una cuenta nueva o edite una existente, se puede enviar un correo electrónico de confirmación a la dirección de correo electrónico que especifique para esa cuenta (consulte [Uso de cuentas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) y se copian en las direcciones de correo electrónico que especifique en la variable [!DNL email.asp] archivo.

>[!NOTE]
>
>Los correos electrónicos de notificación se envían a los usuarios de la cuenta solo cuando ha especificado una dirección de correo electrónico para la cuenta y ha configurado correctamente el [!DNL email.asp] archivo. Si no desea que se envíen correos electrónicos de notificación para una cuenta, deje el campo de correo electrónico de la cuenta en blanco.

Este archivo reside en la variable `\*PortalName*\PortalASP` carpeta.

1. En el equipo en el que se está ejecutando IIS, abra el [!DNL email.asp] en un editor de texto como Bloc de notas.
1. Establezca las siguientes variables:

<table id="table_44F52DA266364DF993C40678A28E0F0D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Para esta variable . . . </th>
   <th colname="col2" class="entry"> Proporcione esta información . . . </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> smtpserver </td>
   <td colname="col2"> <p>Nombre DNS o dirección IP del servidor SMTP a través del cual se envían los mensajes. </p> <p>Por ejemplo: <span class="filepath"> mail.hq.omniture.com</span></p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpserverport </td>
   <td colname="col2"> Puerto en el que el servidor SMTP escucha las conexiones. Normalmente es el puerto 25. </td>
  </tr>
  <tr>
   <td colname="col1"> envío </td>
   <td colname="col2"> <p>Indica cómo se enviará el mensaje. Los valores son los siguientes: </p> <p>1 - Enviar mensajes utilizando el servicio SMTP instalado localmente. Utilice este valor si el servicio SMTP está instalado en el equipo en el que se está ejecutando la secuencia de comandos. </p> <p>2 - Enviar mensajes utilizando el servicio SMTP en la red. Utilice este valor si el servicio SMTP no está instalado en el equipo en el que se está ejecutando la secuencia de comandos. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpconnection timeout </td>
   <td colname="col2">La cantidad de tiempo que <span class="wintitle"> Informe</span> debe esperar una respuesta del servidor SMTP antes de agotar el tiempo de espera de la conexión. </td>
  </tr>
 </tbody>
</table>

1. Para la variable [!DNL NewUserEmail()] y [!DNL UpdateUserEmail()] , configure las siguientes variables:

   <table id="table_91C5E36B84A94C4097EE5993592BE587">
   <thead>
   <tr>
      <th colname="col1" class="entry"> Para esta variable . . . </th>
      <th colname="col2" class="entry"> Proporcione esta información . . . </th>
   </tr>
   </thead>
   <tbody>
   <tr>
      <td colname="col1"> De </td>
      <td colname="col2">Texto que desea que aparezca en la línea del encabezado Desde de los correos electrónicos de confirmación. Este valor puede ser el mismo que la variable <span class="wintitle"> CC</span> valor. </td>
   </tr>
   <tr>
      <td colname="col1"> CC </td>
      <td colname="col2"> <p>Opcional. La dirección de correo electrónico válida de la persona o alias que debe recibir una copia de todos los mensajes relacionados con las cuentas de usuario nuevas y modificadas. Puede especificar varias direcciones de correo electrónico separándolas con comas (sin espacios). </p> <p>Por ejemplo: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Nota: Los destinatarios reciben copias de correos electrónicos que contienen contraseñas de usuario. </p> </p> </td>
   </tr>
   <tr>
      <td colname="col1"> Asunto </td>
      <td colname="col2"> Texto que desea que aparezca en la línea del encabezado Asunto de los correos electrónicos de confirmación. </td>
   </tr>
   <tr>
      <td colname="col1"> WebPath </td>
      <td colname="col2"> <p>La ruta real a su portal. </p> <p>Por ejemplo: <span class="filepath"> https://portal.omniture.com/Example</span></p> </td>
   </tr>
   <tr>
      <td colname="col1"> Cuerpo </td>
      <td colname="col2"> <p>Texto incluido en los correos electrónicos generados automáticamente. </p> <p>Por ejemplo, el siguiente es el texto predeterminado incluido en los correos electrónicos enviados para proporcionar información de inicio de sesión:
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">La información de inicio de sesión del portal web se proporciona a continuación: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName: username </p><p>Nueva contraseña: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Puede acceder al portal utilizando la siguiente URL: </p><p><span class="filepath"> https://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Después de iniciar sesión en el portal, puede cambiar la contraseña en la <span class="wintitle"> Administrador</span> pestaña . </li>
      </ul></p> </td>
   </tr>
   </tbody>
   </table>

1. Guarde y cierre el archivo.
