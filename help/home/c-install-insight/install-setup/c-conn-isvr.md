---
description: Después de instalar el software y el certificado digital de Insight, debe iniciar Insight y configurar su conexión con Insight Server.
title: Configuración de la conexión con el servidor de Insight
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Configuración de la conexión con el servidor de Insight{#configuring-the-connection-to-insight-server}

Después de instalar el software y el certificado digital de Insight, debe iniciar Insight y configurar su conexión con Insight Server.

>[!NOTE]
>
>En algunos casos, es posible que los servicios de consultoría de Adobe o el administrador del sistema hayan preconfigurado la conexión a Insight Server. Si es así, no es necesario que complete esta tarea.

Al iniciar Insight por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar el certificado digital. Para completar el proceso de registro correctamente, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

>[!NOTE]
>
>Si ya ha solicitado, descargado e instalado un certificado prebloqueado como se describe en [Descarga e instalación del certificado](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)digital, Insight no intentará conectarse al servidor de licencias y no recibirá un error.

**Para configurar la conexión a Insight Server**

Al trabajar en un entorno agrupado, Insight debe configurarse para acceder al servidor maestro de Insight para evitar problemas de sincronización. En Insight puede ver información sobre el procesamiento [!DNL Insight Servers] en el clúster mediante el [!DNL Related Servers] elemento de menú del Administrador de [servidores](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Inicie Insight.
1. En el [!DNL Worktop], haga clic en **[!UICONTROL Admin]**, luego **[!UICONTROL First Steps]**.

1. Haga clic en la **[!UICONTROL Configure Connection to Servers]** miniatura.

   Se muestran [!DNL Servers Manager], el [!DNL Insight.cfg] archivo y las instrucciones para configurar el [!DNL Insight.cfg]archivo.

1. En la [!DNL Insight.cfg] ventana, haga clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Complete o modifique los parámetros del servidor para proporcionar a Insight acceso al servidor maestro de Insight Server. Para obtener descripciones detalladas de los parámetros en el archivo Insight.cfg, consulte Parámetros [de configuración](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. Repita los pasos 4 y 5 para cada servidor de Insight en el que desee configurar una conexión.
1. Para guardar los cambios de configuración, haga clic con el botón derecho **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

   Insight intenta conectarse al [!DNL Insight Server(s)] con la configuración especificada. Si se establece una conexión, aparece un nodo verde en la página [!DNL Servers Manager] , como se muestra en la página siguiente.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Verde:** Indica que la conexión con el servidor de Insight está activa.
   * **Rojo claro:** Indica un posible problema con el servidor, como un drenaje del procesamiento del servidor, un uso elevado de memoria o un espacio reducido en el disco.
   * **Rojo:** Indica que la conexión con el servidor de Insight no está activa.
   Si Insight no se puede conectar con la configuración especificada, aparecerá un nodo rojo en el [!DNL Servers Manager]. Si esto sucede, consulte Solución de problemas [de la conexión](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Al seleccionar un perfil para utilizarlo, la información del perfil (incluidos los datos relacionados y los espacios de trabajo o visualizaciones específicos definidos para el perfil) se descarga en el equipo. A medida que descarga cada perfil, Insight crea una carpeta dentro del directorio de instalación utilizando el nombre del perfil.

Por ejemplo, si selecciona un perfil llamado Ventas, aparecerá una carpeta denominada Ventas en el directorio de Insight. Esta carpeta contiene las métricas, dimensiones, espacios de trabajo y visualizaciones definidas en el perfil de ventas. Después de la carga inicial del perfil, este se puede utilizar al trabajar sin conexión. Consulte [Trabajo sin conexión y en línea](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-off-on.html).

Además, cuando se conecta a Insight Server por primera vez desde Insight, Insight Server crea los siguientes directorios en el directorio de instalación de Insight.

* **[!DNL Trace]directorio:**Dentro del[!DNL Trace]directorio se encuentra el archivo de registro de Insight ([!DNL insight.log]). Cuando el tamaño del[!DNL Insight.log]archivo alcanza los 100 MB, se cambia el nombre del archivo a[!DNL insight-1.log]. Si[!DNL insight-1.log]ya existe un archivo con el nombre,[!DNL insight-1.log]se cambia el nombre a[!DNL insight-2.log], y así sucesivamente, con un máximo de[!DNL insight-9.log]. El archivo[!DNL insight.log]siempre contiene la información de registro más reciente y[!DNL insight-max.log]contiene la más antigua.

* **[!DNL User]directorio:**Dentro del[!DNL User]directorio hay carpetas que corresponden a cada perfil utilizado hasta la fecha, y dentro de cada carpeta de perfil hay carpetas denominadas[!DNL Work]y[!DNL Workspaces]. El directorio`User\*profile name*\Workspaces`es la ubicación predeterminada en la que se guardan los archivos del espacio de trabajo de Insight.`User\*profile name*\Work`es la ubicación predeterminada en la que se guardan las visualizaciones de Insight y otro trabajo personalizado realizado por el usuario de Insight.

La siguiente tabla enumera las ubicaciones predeterminadas de los componentes a los que se accede con frecuencia.

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
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Áreas de trabajo guardadas <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Workspaces\<i>tab name</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archivos .png<span class="filepath"> guardados</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caché de datos </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Archivo Insight.log</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

Puede buscar por nombre de clave, tipo de clave o valor para localizar rápidamente una entrada, con el fin de eliminar la necesidad de desplazarse por archivos extendidos y grandes para obtener información anidada. Puede localizar nombres de dimensión, nombres de servidor, etc. El siguiente ejemplo muestra las coincidencias de una búsqueda en el mapa de frases.

![](assets/cfg_search.PNG)

Escriba una frase de búsqueda en este campo para localizar los datos. Según el éxito de una coincidencia, el color del campo cambia. Las coincidencias se muestran resaltadas y las no coincidencias aparecen atenuadas. Si no hay coincidencias, el fondo del campo de búsqueda se vuelve rojo. Al pulsar Intro, el árbol de configuración expande todos los lugares donde hay una coincidencia y se contrae cuando no hay una coincidencia.

También puede utilizar expresiones regulares en el [!DNL Search] campo. Por ejemplo, puede utilizar re: [!DNL *zip.*]para cualquier entrada que contenga la palabra &quot;zip&quot;.

Para borrar una búsqueda, presione **[!UICONTROL Escape]**.
