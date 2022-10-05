---
description: Si los servidores de seguridad de red no impiden el acceso al servidor repetidor desde equipos de Insight, puede crear una conexión entre el servidor repetidor y Insight para poder administrar el servidor repetidor mediante Insight.
title: Creación de una conexión entre Insight y el repetidor
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---

# Creación de una conexión entre Insight y el repetidor{#creating-a-connection-between-insight-and-repeater}

{{eol}}

Si los servidores de seguridad de red no impiden el acceso al servidor repetidor desde equipos de Insight, puede crear una conexión entre el servidor repetidor y Insight para poder administrar el servidor repetidor mediante Insight.

**Para crear una conexión entre [!DNL Insight] y el servidor repetidor**

1. En [!DNL Insight], en el [!DNL Admin] , haga clic en la pestaña **[!UICONTROL Configure Connections to Servers]** miniatura para abrir el espacio de trabajo Configurar conexiones a servidores .
1. En el [!DNL Insight.cfg] ventana, clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
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
   <td colname="col2">(Opcional) El nombre que desea que aparezca <span class="keyword"> Insight</span> para representar el servidor repetidor en su interfaz de usuario. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> <p>El nombre de host o la dirección IP numérica del servidor repetidor. </p> <p>Ejemplo: <span class="filepath"> Repeater.mycompany.com</span> o 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> <p>Opcional a menos que tenga más de un certificado. El nombre del archivo que contiene el certificado digital para esta copia de <span class="keyword"> Insight</span>. (Este es el archivo que descargó al instalar <span class="keyword"> Insight</span>.) </p> <p>Ejemplo: <span class="filepath"> Samantha Smith.pem</span></p> <p>Si deja este parámetro en blanco, <span class="keyword"> Insight</span> utiliza el certificado que esté presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor SSL </p> <p>Nombre común </p> </td> 
   <td colname="col2">El nombre común asignado al servidor repetidor. Este nombre debe coincidir con el nombre común asignado al servidor repetidor dentro de su certificado de licencia. Si tiene acceso al archivo de certificado del repetidor (<span class="filepath"> Certificados\server_cert.pem</span>), puede encontrar el nombre común abriendo el archivo con un editor de texto como el Bloc de notas. El nombre común se identifica en el campo CN del certificado. </td> 
  </tr> 
 </tbody> 
</table>

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**. [!DNL Insight] intentará conectarse al servidor repetidor utilizando la configuración especificada. Si se establece una conexión, aparece un icono verde del servidor en la variable [!DNL Servers Manager] interfaz. Si no se puede establecer una conexión, aparece un icono rojo.

   Para obtener más información sobre la variable [!DNL Servers Manager] , consulte el [!DNL Insight] Guía del usuario*.
