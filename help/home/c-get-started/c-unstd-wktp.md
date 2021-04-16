---
description: En la superficie de trabajo es donde se organizan y se accede a todos los espacios de trabajo e informes.
title: Superficies de trabajo
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Superficies de trabajo{#worktops}

En la superficie de trabajo es donde se organizan y se accede a todos los espacios de trabajo e informes.

En la mayoría de los casos, el [!DNL Worktop] se muestra inmediatamente después de abrir la Data Workbench. Las características de [!DNL Worktop] incluyen la barra lateral y la interfaz con pestañas. Además, la barra lateral le permite añadir visualizaciones y acceder a las funciones que usa con regularidad.

**Superficie de trabajo**

![](assets/client-wktp.png)

El [!DNL Worktop] también permite crear y guardar espacios de trabajo e informes nuevos y actualizados, así como publicar espacios de trabajo e informes en el servidor de Data Workbench para que otros usuarios puedan acceder a ellos.

La tabla de elementos [!DNL Worktop] que aparece a continuación describe cada elemento del [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Barra lateral </td> 
   <td colname="col2"> <p>La barra lateral proporciona contexto y control para espacios de trabajo, así como conocimiento del estado actual de un espacio de trabajo y acceso a funciones usadas regularmente. Las siguientes funciones están disponibles en la barra lateral: </p> <p> <b>Conexión: </b> un indicador de estado que muestra el estado en línea. Haga clic en el estado de conexión para habilitar o deshabilitar <span class="wintitle"> Trabajar en línea</span>. Consulte <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Trabajo sin conexión y en línea</a>. </p> <p> <b>Perfil: </b> indicador del perfil actual en uso. </p> <p> <b>Con fecha:  </b>Un indicador de estado que muestra cómo se actualizan los datos en el conjunto de datos del perfil. Estos datos se descargan y procesan desde el servidor DPU, que solo puede producirse cuando está trabajando en línea. </p> <p> <b>Consulta/Ejemplo de confianza:</b> indicador de la finalización de la consulta. Cuando el estado consulta el 100 por ciento, se consultan todos los datos. </p> <p> <b>Agregar: </b> permite agregar visualizaciones como paneles, leyendas y tablas a la barra lateral. Consulte <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Adición de visualizaciones a la barra lateral</a>. </p> <p> <b>Opciones: </b> permite volver a una configuración de barra lateral anterior y ocultar automáticamente la barra lateral. </p> <p>La configuración de la barra lateral se guarda en el archivo <span class="filepath"> sidebar.vw</span> al cerrar la Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Subdirectorios Tab y Subtab o Drop-down (no se muestra) </p> </td> 
   <td colname="col2"> <p>Cada ficha que aparece en la carpeta <span class="wintitle"> Superficie de trabajo</span> corresponde a la carpeta <i>nombre de perfil de trabajo</i>\Workspaces\<i>nombre de ficha</i> del directorio de instalación de la Data Workbench y representa un tipo concreto de información, como Paneles, Actividad, Adquisición, Visitantes, etc. Las subcarpetas de la carpeta de nombre de ficha se muestran como subfichas de forma predeterminada, pero también como subdirectorios. Consulte <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Personalización de fichas de escritorio</a>. </p> <p> <p>Nota:  Cada perfil de Data Workbench se suministra con un conjunto estándar de pestañas. Dado que la implementación se puede personalizar completamente, los espacios de trabajo (y, por lo tanto, las pestañas) que aparecen pueden diferir de lo que se documenta en esta guía. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estado del perfil </td> 
   <td colname="col2"> Proporciona el estado de conexión al servidor de Data Workbench y el nombre del perfil cargado actualmente. El valor Con fecha y hora para los datos en el conjunto de datos del perfil se muestra debajo del indicador en línea. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimizar, Maximizar, Cerrar </td> 
   <td colname="col2"> Funciones estándar de Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniaturas </td> 
   <td colname="col2"> <p>Una miniatura es una instantánea de un espacio de trabajo que aparece en la <span class="wintitle"> superficie de trabajo</span>. Se toma una nueva instantánea cada vez que se guarda el espacio de trabajo. Las miniaturas le permiten identificar rápidamente un espacio de trabajo en particular en la <span class="wintitle"> superficie de trabajo</span>. </p> <p>Para abrir un espacio de trabajo, haga clic en la miniatura. </p> <p> <p>Nota:  Cada perfil de Data Workbench se suministra con un conjunto estándar de espacios de trabajo. Dado que la implementación se puede personalizar completamente, los espacios de trabajo (y, por lo tanto, las miniaturas) que aparecen pueden diferir de lo que se documenta en esta guía. </p> </p> <p>Para obtener más información sobre los espacios de trabajo, consulte <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Configuración de la barra lateral</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mensajes de error </td> 
   <td colname="col2"> <p>Los mensajes de error aparecen en rojo debajo del estado. Para obtener descripciones del código de estado, consulte <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Por ejemplo: 403_Prohibido. </p> </td> 
  </tr> 
 </tbody> 
</table>
