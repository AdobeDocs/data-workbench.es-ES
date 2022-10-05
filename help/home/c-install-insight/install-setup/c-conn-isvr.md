---
description: Después de instalar el software y el certificado digital de Insight, debe iniciar Insight y configurar su conexión con Insight Server.
title: Configuración de la conexión con el servidor de Insight
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
exl-id: 6a87e972-069a-435c-9bac-23b20f165ebb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%

---

# Configuración de la conexión con el servidor de Insight{#configuring-the-connection-to-insight-server}

{{eol}}

Después de instalar el software y el certificado digital de Insight, debe iniciar Insight y configurar su conexión con Insight Server.

>[!NOTE]
>
>En algunos casos, es posible que los servicios de consultoría de Adobe o el administrador del sistema hayan preconfigurado la conexión con Insight Server. Si es así, no es necesario completar esta tarea.

Cuando inicia Insight por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar el certificado digital. Para completar correctamente el proceso de registro, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

>[!NOTE]
>
>Si ya ha solicitado, descargado e instalado un certificado prebloqueado, tal como se describe en [Descarga e instalación del certificado digital](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9), Insight no intentará conectarse al servidor de licencias y no recibirá ningún error.

**Para configurar la conexión con Insight Server**

Cuando se trabaja en un entorno agrupado, Insight debe configurarse para acceder al servidor maestro de Insight para evitar problemas de sincronización. En Insight puede ver información sobre el procesamiento [!DNL Insight Servers] en su clúster utilizando [!DNL Related Servers] del menú [Administrador de servidores](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Iniciar Insight.
1. En el [!DNL Worktop], haga clic en **[!UICONTROL Admin]**, luego **[!UICONTROL First Steps]**.

1. Haga clic en el **[!UICONTROL Configure Connection to Servers]** miniatura.

   La variable [!DNL Servers Manager], el [!DNL Insight.cfg] y las instrucciones para configurar su [!DNL Insight.cfg]se muestran.

1. En el [!DNL Insight.cfg] ventana, clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Complete o modifique los parámetros del servidor para proporcionar a Insight acceso a su servidor maestro de Insight Server. Para obtener descripciones detalladas de los parámetros del archivo Insight.cfg, consulte [Parámetros de configuración](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. Repita los pasos 4 y 5 con cada Insight Server con el que desee configurar una conexión.
1. Para guardar los cambios de configuración, haga clic con el botón derecho del ratón **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

   Insight intenta conectarse al [!DNL Insight Server(s)] usando la configuración especificada. Si se establece una conexión, aparece un nodo verde en la variable [!DNL Servers Manager] como se muestra en la página siguiente.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Verde:** Indica que la conexión con el servidor de Insight está activa.
   * **Rojo claro:** Indica un posible problema con el servidor, como un drenaje del procesamiento del servidor, un alto uso de memoria o un espacio en disco bajo.
   * **Rojo:** Indica que la conexión con el servidor de Insight no está activa.

   Si Insight no se puede conectar con la configuración especificada, aparece un nodo rojo en la variable [!DNL Servers Manager]. Si esto sucede, consulte [Resolución de problemas de conexión](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Al seleccionar un perfil para utilizarlo, la información del perfil (incluidos los datos relacionados y cualquier espacio de trabajo o visualización específicos definidos para el perfil) se descarga en el equipo. A medida que descarga cada perfil, Insight crea una carpeta dentro del directorio de instalación utilizando el nombre del perfil.

Por ejemplo, si selecciona un perfil denominado Ventas, aparecerá una carpeta denominada Ventas en el directorio Perspectiva. Esta carpeta contiene las métricas, dimensiones, espacios de trabajo y visualizaciones definidas en el perfil de ventas. Después de la carga inicial del perfil, este se puede utilizar cuando se trabaja sin conexión. Consulte [Trabajar sin conexión y en línea](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-off-on.html).

Además, cuando se conecta a Insight Server por primera vez desde Insight, Insight Server crea los siguientes directorios en el directorio de instalación de Insight.

* **[!DNL Trace]directorio:** Dentro de [!DNL Trace] es el archivo de registro de Insight ( [!DNL insight.log]). Cuando el tamaño de la variable [!DNL Insight.log] alcanza los 100 MB; se cambia el nombre del archivo a [!DNL insight-1.log]. Si un archivo del nombre [!DNL insight-1.log] ya existe, entonces [!DNL insight-1.log] se cambia el nombre a [!DNL insight-2.log], etc., con un máximo de [!DNL insight-9.log]. El archivo [!DNL insight.log] contiene siempre la información de registro más reciente y [!DNL insight-max.log] contiene el más antiguo.

* **[!DNL User]directorio:** Dentro de [!DNL User] son carpetas que corresponden a cada perfil usado hasta la fecha y dentro de cada carpeta de perfil hay carpetas con nombre [!DNL Work] y [!DNL Workspaces]. El directorio `User\*profile name*\Workspaces` es la ubicación predeterminada en la que se guardan los archivos del espacio de trabajo de Insight . `User\*profile name*\Work` es la ubicación predeterminada en la que se guardan las visualizaciones de Insight y otro trabajo personalizado realizado por el usuario de Insight .

En la tabla siguiente se enumeran las ubicaciones predeterminadas de los componentes a los que se accede con más frecuencia.

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Ubicación del directorio </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizaciones guardadas </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuario\<i>nombre de perfil</i>\Trabajo\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guardado <span class="wintitle"> Espacios de trabajo</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuario\<i>nombre de perfil</i>\Workspaces\<i>nombre de ficha</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guardado<span class="filepath"> .png</span> files </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuario\<i>nombre de perfil</i>\Trabajo\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caché de datos </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuario\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.log</span> file </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

Puede buscar por nombre de clave, tipo de clave o valor para localizar rápidamente una entrada, con el fin de eliminar la necesidad de desplazarse por archivos grandes y expandidos para obtener información anidada. Puede localizar nombres de dimensiones, nombres de servidor, etc. El siguiente ejemplo muestra coincidencias para una búsqueda en el mapa de frases.

![](assets/cfg_search.PNG)

Escriba una frase de búsqueda en este campo para localizar los datos. Según el éxito de una coincidencia, el color del campo cambia. Las coincidencias se muestran resaltadas y las no coincidencias aparecen atenuadas. Si no hay coincidencias, el fondo del campo de búsqueda se vuelve rojo. Al pulsar Intro, el árbol de configuración expande cada lugar donde haya una coincidencia y contrae donde no haya una coincidencia.

También puede utilizar expresiones regulares en la variable [!DNL Search] campo . Por ejemplo, puede utilizar re: [!DNL *zip.*] para cualquier entrada que contenga la palabra &quot;zip&quot;.

Para borrar una búsqueda, pulse **[!UICONTROL Escape]**.
