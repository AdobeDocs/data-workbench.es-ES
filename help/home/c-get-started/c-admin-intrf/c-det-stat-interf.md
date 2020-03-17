---
description: La interfaz de estado detallado resulta útil para solucionar errores u otros problemas con los equipos del servidor de Área de trabajo de datos.
solution: Analytics
title: Interfaz de estado detallada
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: fd3afa80250d5ae20b7758ba840fd4d436545cf2

---


# Interfaz de estado detallada{#detailed-status-interface}

La interfaz de estado detallado resulta útil para solucionar errores u otros problemas con los equipos del servidor de Área de trabajo de datos.

Esto incluye cualquier [!DNL Transform] perfil que se ejecute en esos equipos o en [!DNL Report] equipos que sean clientes del servidor de Área de trabajo de datos. Puede acceder a [!DNL Master Server] las interfaces y [!DNL Query Server Detailed Status] a ellas a través del [!DNL Admin] menú. Para acceder a la [!DNL Detailed Status] interfaz de otros equipos, en la [!DNL Servers Manager], haga clic con el botón secundario en el nodo del servidor para el que desea ver el estado y haga clic en **[!UICONTROL Detailed Status]**. Consulte [El Administrador](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba)De Servidores.

Para obtener más información sobre el servidor de Área de trabajo de datos, consulte la Guía *de instalación y administración de productos de* servidor.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Para actualizar la información en una [!DNL Detailed Status] interfaz, haga clic con el botón derecho en el **[!UICONTROL Detailed Status]** encabezado y haga clic en **[!UICONTROL Refresh]**.

En la tabla siguiente se enumeran las tareas que se pueden completar mediante la [!DNL Detailed Status] interfaz.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para realizar esta tarea... </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para mostrar cada componente de equipo y su estado actual </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span>del componente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para mostrar la cantidad de memoria que se utiliza en el equipo </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span> de memoria &gt; <span class="uicontrol"> Carga</span>de espacio de direcciones. </p> <p>Para obtener más información sobre la supervisión de la carga de espacio de direcciones, consulte la Guía <i>de instalación y administración de productos</i>de servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar si el equipo está configurado para utilizar el conmutador /3GB </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span> de memoria &gt; <span class="uicontrol"> Espacio</span>de direcciones de proceso. </p> <p>Si el campo <span class="wintitle"> Total</span> muestra más de 300000 KB, el equipo está configurado para utilizar el modificador /3GB. </p> <p>Para obtener más información sobre el conmutador /3GB, consulte la Guía <i>de instalación y administración de productos de</i>servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitorear la cantidad de espacio en disco y memoria utilizada para almacenar cada dimensión, así como la utilizada para almacenar los nombres de sus elementos </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Dimensiones</span> &gt; Uso <span class="uicontrol"> de disco &gt;</span> &lt; <i>nombre<span class="uicontrol"> de perfil&gt;o Rendimiento &gt;</span></i><span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>Dimensiones&gt; Uso de memoria&gt;&lt;nombreDe perfil&gt;. </p> <p>Los campos Uso <span class="wintitle"> del disco</span> proporcionan el nombre y la cantidad de espacio en disco (en MB) necesarios para almacenar cada dimensión. Los números de uso de discos grandes pueden afectar negativamente a los tiempos de consulta porque el servidor de Área de trabajo de datos tiene que leer todos los datos para completar las consultas relacionadas. La disminución del uso del disco para una dimensión puede reducir el tiempo que se tarda en completar las consultas relacionadas. </p> <p>Los campos Uso <span class="wintitle"> de</span> memoria proporcionan el número de elementos en cada dimensión y la cantidad de memoria necesaria para almacenar la lista de nombres de elementos. Un gran número de elementos puede afectar negativamente a la cantidad de memoria que se utiliza durante una consulta, ya que el servidor de Área de trabajo de datos tiene que leer a través de cada elemento. La reducción del número de elementos en una dimensión puede reducir el tiempo que se tarda en completar las consultas relacionadas. </p> <p>Ejemplo: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorear el uso de CPU en las etapas de Procesamiento de registro y Transformación </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Uso</span> de CPU &gt; <span class="uicontrol"> Procesamiento</span> de registro &gt; <i>&lt;<span class="uicontrol"> nombre</span></i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span><span class="uicontrol"></span>de perfil o Rendimiento&gt; Uso de CPU&gt; Transformación &gt; &lt;nombre de perfil&gt;. </p> <p>Cada uno de estos conjuntos de campos le proporciona el Uso de CPU (en segundos) para cada una de las etapas de Procesamiento de registro y Transformación. </p> <p>Ejemplo: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>El tiempo que se tarda en completar una consulta generalmente es proporcional al tamaño total de todas las dimensiones. Después de revisar el tamaño de cada dimensión, puede evaluar si una dimensión en particular es lo suficientemente útil y se utiliza con suficiente frecuencia para justificar el coste de rendimiento de la dimensión. Si no es así, puede eliminar la dimensión en el Administrador <span class="wintitle"> de perfiles</span>.<p>Una dimensión cuya lista de nombres de elementos es excesivamente grande (es decir, más de 128 MB) puede provocar errores de "Memoria insuficiente" aunque el uso total del espacio de direcciones no esté cerca del límite. </p> <p>Además, si utiliza un clúster de servidores de Área de trabajo de datos pero no la normalización centralizada, una dimensión cuya lista de nombres de elementos sea grande tendrá un impacto significativo en los presupuestos de memoria de envío. Para obtener más información sobre la normalización centralizada, consulte la Guía <i>de configuración de</i>Dataset. Si la cantidad de memoria necesaria para almacenar todas las listas de nombres de elementos combinadas es superior a 100 MB en todos los servidores del clúster, puede recibir errores de "Enviar presupuesto de memoria excedido" aunque la actividad de consulta sea ligera. Por ejemplo, si tiene un clúster de cuatro servidores con más de 25 MB en cada servidor que se utiliza para almacenar las listas de nombres de elementos, puede que reciba errores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorear el tiempo empleado en el procesamiento y la transformación de registros </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Uso</span> de CPU &gt; <span class="uicontrol"> Procesamiento</span> de registro &gt; <i>&lt;<span class="uicontrol"> nombre</span></i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>de perfil o Rendimiento&gt; Uso de CPU&gt; Transformación&gt;&lt;nombre de perfil de &gt;. </p> <p>La revisión de los campos de estas secciones le permite identificar filtros y transformaciones que pueden estar afectando negativamente la cantidad de tiempo necesaria para el procesamiento y la transformación de registros. A continuación, puede tomar decisiones de diseño con respecto a filtros y transformaciones individuales con largos tiempos de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorear el uso del espacio en disco y aumentar la velocidad de consulta </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Campos</span> de procesamiento de registros &gt; <i>&lt;<span class="uicontrol"> nombre</span>de perfil&gt;</i>. </p> <p>Cada elemento de línea de esta sección corresponde a un parámetro en el <span class="filepath"> archivo Log Processing.cfg</span> . La revisión de estos campos le permite ver cuánta memoria utiliza cada parámetro. Luego puede tomar decisiones de diseño con respecto a elementos individuales que son bastante grandes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinar el tiempo transcurrido desde el reprocesamiento o transformación anterior </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span> de procesamiento &gt; <i>&lt;<span class="uicontrol"> nombre</span>de perfil&gt;</i> &gt; <span class="uicontrol"> Historial</span>del modo de procesamiento. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Tiempo real: tiempo en el que el servidor de Área de trabajo de datos estaba disponible para realizar consultas. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrada rápida: esta vez más el tiempo de combinación rápida es el tiempo total necesario para procesar el conjunto de datos. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Combinación rápida: tiempo total necesario para transformar el conjunto de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para diagnosticar problemas de "A medida" </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span> de procesamiento &gt; <i>&lt;<span class="uicontrol"> nombre</span>de perfil&gt;</i> &gt; <span class="uicontrol"> Con fecha de hora</span> &gt; <span class="uicontrol"> Fuentes tal cual</span>. </p> <p>La revisión de los tiempos de cada fuente puede ayudarle a determinar qué fuentes pueden estar afectando negativamente al valor global de A-of. Luego puede abordar los problemas con esas fuentes en particular. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para estimar cuánto tarda en completarse una consulta en ejecución </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Motor</span>de ejecución. </p> <p>La revisión del campo Tiempo <span class="wintitle"></span> de barrido de datos le proporciona una estimación del tiempo que tarda una consulta en completarse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para enumerar todos los perfiles disponibles en este equipo y obtener detalles sobre su estado </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Perfiles</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver el estado de la replicación </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span>del componente. </p> <p>Compruebe el estado del componente Replicate. Si la replicación se está ejecutando, se muestra Aceptar. Si el componente Replicar ha fallado, se muestra un mensaje de error. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver <span class="wintitle"> el estado del servidor</span> de informes de un equipo de <span class="keyword"> informes</span> que se conecta al servidor de Área de trabajo de datos </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span>del servidor de informes. </p> <p>Esta sección de la interfaz Estado <span class="wintitle"> detallado incluye una copia del archivo</span> Report Server.cfg <span class="filepath"></span> , información sobre el número de informes que se están ejecutando (fracción actual) e información sobre el error más reciente (último error). </p> <p>Para ver los pasos para editar el archivo <span class="filepath"> Report Server.cfg</span> , consulte la Guía <i>de informes</i>de Área de trabajo de datos. </p> <p> <p>Nota: Si la sección Estado <span class="wintitle"> del servidor de informes no aparece en la interfaz Estado</span> detallado, es posible que tenga que configurar el servidor de Área de trabajo de datos para que muestre el estado <span class="wintitle"> del</span> <span class="wintitle"></span>servidor de informes. Para obtener más información, consulte la Guía <i>del informe Área de trabajo de datos</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver la información de uso de memoria para Transform </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado</span> de procesamiento &gt; <span class="uicontrol"> Transformar</span>. </p> <p>Para obtener más información sobre Transformar, consulte la Guía <i>de instalación y administración de productos de</i> servidor y la Guía <i>de configuración de</i>Dataset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para guardar la interfaz de estado <span class="wintitle"> detallado como un archivo</span> *.cfg <span class="filepath"></span> que se puede abrir en un editor de texto como Bloc de notas o distribuirlo a otros usuarios </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón secundario en el encabezado Estado <span class="uicontrol"> detallado y, a continuación, haga clic en</span> Guardar copia como <span class="uicontrol"></span>. </p> <p>Nota:  <p>Hacer clic con el botón derecho en el encabezado Estado <span class="uicontrol"> detallado y hacer clic en</span> Guardar <span class="uicontrol"> en el nombre</span> /estado del <i>servidor/ no funciona en la interfaz Estado</i><span class="wintitle"></span> detallado. Aparece el siguiente mensaje de error: </p> <p>No se puede guardar /Status/. 403 Prohibido </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver <span class="uicontrol"> filas por métrica Origen</span> de registro </p> </td> 
   <td colname="col2"> <p>Si la métrica Filas por origen de registro debe informarse en Estado detallado, el administrador del área de trabajo de datos debe definir el "ID de origen de registro" y proporcionar un nombre único en Procesamiento de registro del perfil personalizado.cfg. </p> </td> 
  </tr> 
 </tbody> 
</table>

