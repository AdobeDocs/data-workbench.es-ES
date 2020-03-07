---
description: Si los servidores de seguridad de red no impiden el acceso al servidor repetidor desde los equipos de Insight, puede crear una conexión entre el servidor repetidor y Insight para poder administrar el servidor repetidor mediante Insight.
solution: Insight
title: Creación de una conexión entre Insight y Repeater
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación de una conexión entre Insight y Repeater{#creating-a-connection-between-insight-and-repeater}

Si los servidores de seguridad de red no impiden el acceso al servidor repetidor desde los equipos de Insight, puede crear una conexión entre el servidor repetidor y Insight para poder administrar el servidor repetidor mediante Insight.

**Para crear una conexión entre[!DNL Insight]y el servidor repetidor**

1. En [!DNL Insight], en la ficha [!DNL Admin] , haga clic en la **[!UICONTROL Configure Connections to Servers]** miniatura para abrir el espacio de trabajo Configurar conexiones a servidores.
1. En la [!DNL Insight.cfg] ventana, haga clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Para el nuevo servidor, complete los siguientes parámetros:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parámetro... </th> 
   <th colname="col2" class="entry"> Especifique... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2">(Opcional) El nombre que desea que utilice Insight <span class="keyword"></span> para representar el servidor repetidor en su interfaz de usuario. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> <p>El nombre de host o la dirección IP numérica del servidor repetidor. </p> <p>Ejemplo: <span class="filepath"> Repeater.mycompany.com</span> o 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> <p>Opcional a menos que tenga más de un certificado. Nombre del archivo que contiene el certificado digital para esta copia de <span class="keyword"> Insight</span>. (Este es el archivo que descargó durante la instalación de <span class="keyword"> Insight</span>). </p> <p>Ejemplo: <span class="filepath"> Samantha Smith.pem</span></p> <p>Si deja este parámetro en blanco, <span class="keyword"> Insight</span> utiliza el certificado que esté presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor SSL </p> <p>Nombre común </p> </td> 
   <td colname="col2">Nombre común asignado al servidor repetidor. Este nombre debe coincidir con el nombre común asignado al servidor repetidor dentro de su certificado de licencia. Si tiene acceso al archivo de certificado del repetidor (<span class="filepath"> Certificates\server_cert.pem</span>), puede encontrar el nombre común abriendo el archivo con un editor de texto como Bloc de notas. El nombre común se identifica en el campo CN del certificado. </td> 
  </tr> 
 </tbody> 
</table>

1. Para guardar el archivo, haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**. [!DNL Insight] intentará conectarse al servidor repetidor utilizando la configuración especificada. Si se establece una conexión, aparece un icono de servidor verde en la [!DNL Servers Manager] interfaz. Si no se puede establecer una conexión, aparece un icono rojo.

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.

