---
description: La interfaz Estado detallado es útil para solucionar errores u otros problemas con los equipos del servidor de Data Workbench.
title: Interfaz de estado detallada
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Interfaz de estado detallada{#detailed-status-interface}

La interfaz Estado detallado es útil para solucionar errores u otros problemas con los equipos del servidor de Data Workbench.

Esto incluye cualquier perfil [!DNL Transform] que se ejecute en esos equipos o equipos [!DNL Report] que sean clientes del servidor de Data Workbench. Puede acceder a las interfaces [!DNL Master Server] y [!DNL Query Server Detailed Status] a través del menú [!DNL Admin]. Para acceder a la interfaz [!DNL Detailed Status] de otros equipos, en [!DNL Servers Manager], haga clic con el botón derecho en el nodo del servidor para el que desea ver el estado y haga clic en **[!UICONTROL Detailed Status]**. Consulte [Administrador de servidores](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Para obtener más información acerca del servidor de Data Workbench, consulte la *Guía de instalación y administración de productos de servidor*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Para actualizar la información en una interfaz [!DNL Detailed Status], haga clic con el botón derecho en el encabezado **[!UICONTROL Detailed Status]** y haga clic en **[!UICONTROL Refresh]**.

En la tabla siguiente se enumeran las tareas que se pueden completar mediante la interfaz [!DNL Detailed Status] .

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
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado del componente</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para mostrar cuánta memoria se está utilizando en el equipo </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado de memoria</span> &gt; <span class="uicontrol"> Carga del espacio de direcciones</span>. </p> <p>Para obtener más información sobre la supervisión de la carga de espacio de direcciones, consulte la <i>Guía de instalación y administración de productos de servidor</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar si el equipo está configurado para utilizar el conmutador /3GB </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado de memoria</span> &gt; <span class="uicontrol"> Espacio de dirección de proceso</span>. </p> <p>Si el campo <span class="wintitle"> Total</span> muestra más de 300000 KB, su equipo está configurado para utilizar el conmutador /3GB. </p> <p>Para obtener más información acerca del conmutador /3GB, consulte la <i>Guía de instalación y administración de productos de servidor</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorizar la cantidad de espacio en disco y memoria utilizada para almacenar cada dimensión, así como la utilizada para almacenar los nombres de sus elementos </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> Uso del disco</span> &gt; <i>&lt;<span class="uicontrol"> nombre del perfil</span> </i>o <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> Uso de memoria</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span>&gt;</i>. </p> <p>Los campos <span class="wintitle"> Uso del disco</span> proporcionan el nombre y la cantidad de espacio en disco (en MB) necesarios para almacenar cada dimensión. Los números de uso de disco grandes pueden afectar negativamente a los tiempos de consulta, ya que el servidor de Data Workbench tiene que leer todos los datos para completar las consultas relacionadas. Reducir el uso del disco para una dimensión puede reducir el tiempo que se tarda en completar las consultas relacionadas. </p> <p>Los campos <span class="wintitle"> Uso de memoria</span> proporcionan el número de elementos en cada dimensión y la cantidad de memoria necesaria para almacenar la lista de nombres de elementos. Un gran número de elementos puede afectar negativamente a la cantidad de memoria que se utiliza durante una consulta, ya que el servidor de Data Workbench debe leer a través de cada elemento. La reducción del número de elementos en una dimensión puede reducir el tiempo que se tarda en completar las consultas relacionadas. </p> <p>Ejemplo: <code>+&nbsp;Performance
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
   <td colname="col1"> <p>Para monitorizar el uso de la CPU en las etapas dentro de Procesamiento de registros y Transformación </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Uso de CPU</span> &gt; <span class="uicontrol"> Procesamiento de registros</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span></i> o <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Uso de CPU</span> &gt; <span class="uicontrol"> Transformación</span> &gt; &lt;<span class="uicontrol"> nombre del perfil</span>&gt;. </p> <p>Cada uno de estos conjuntos de campos le proporciona el Uso de CPU (en segundos) para cada una de las etapas dentro de Procesamiento de registros y Transformación. </p> <p>Ejemplo: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>El tiempo que tarda en completar una consulta suele ser proporcional al tamaño total de todas las dimensiones. Después de revisar el tamaño de cada dimensión, puede evaluar si una dimensión en particular es lo suficientemente útil y se utiliza con la frecuencia suficiente para justificar el coste de rendimiento de la dimensión. Si no es así, puede eliminar la dimensión en el <span class="wintitle"> Administrador de perfiles</span>.<p>Una dimensión cuya lista de nombres de elementos sea excesivamente grande (es decir, más de 128 MB) puede causar errores de "Memoria insuficiente" incluso si el uso total del espacio de direcciones no está cerca del límite. </p> <p>Además, si utiliza un clúster de servidores de Data Workbench pero no utiliza la normalización centralizada, una dimensión cuya lista de nombres de elementos sea grande tendrá un impacto significativo en los presupuestos de memoria de envío. Para obtener más información sobre la normalización centralizada, consulte la <i>Guía de configuración de conjuntos de datos</i>. Si la cantidad de memoria necesaria para almacenar todas las listas de nombres de elementos combinadas es superior a 100 MB en todos los servidores del clúster, puede recibir errores de "Enviar presupuesto de memoria excedido" incluso cuando la actividad de consulta sea ligera. Por ejemplo, si tiene un clúster de cuatro servidores con más de 25 MB en cada servidor que se utiliza para almacenar las listas de nombres de elementos, puede que reciba errores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorizar el tiempo empleado en el procesamiento y la transformación de registros </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Uso de CPU</span> &gt; <span class="uicontrol"> Procesamiento de registros</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span></i> o <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Uso de CPU</span> &gt; <span class="uicontrol"> Transformación</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span></i>. </p> <p>Al revisar los campos de estas secciones, puede identificar filtros y transformaciones que puedan estar afectando negativamente a la cantidad de tiempo necesaria para el procesamiento y la transformación de registros. A continuación, puede tomar decisiones de diseño con respecto a filtros individuales y transformaciones con largos tiempos de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorizar el uso del espacio en disco y aumentar la velocidad de las consultas </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Rendimiento</span> &gt; <span class="uicontrol"> Campos de procesamiento de registros</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span></i>. </p> <p>Cada elemento de línea de esta sección corresponde a un parámetro del archivo <span class="filepath"> Log Processing.cfg</span>. La revisión de estos campos le permite ver cuánta memoria utiliza cada parámetro. A continuación, puede tomar decisiones de diseño con respecto a elementos individuales que son bastante grandes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar el tiempo transcurrido de reprocesamiento o transformación anterior </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado de procesamiento</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span>&gt;</i> &gt; <span class="uicontrol"> Historial del modo de procesamiento</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Tiempo real: tiempo en el que el servidor de Data Workbench estaba disponible para realizar consultas. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrada rápida: esta vez, además del tiempo de fusión rápida, es el tiempo total necesario para procesar el conjunto de datos. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fusión rápida: tiempo total necesario para transformar el conjunto de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para diagnosticar problemas de "A la hora" </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado de procesamiento</span> &gt; <i>&lt;<span class="uicontrol"> nombre de perfil</span>&gt;</i> &gt; <span class="uicontrol"> Con fecha</span> &gt; <span class="uicontrol"> Fuentes con fecha</span>. </p> <p>La revisión del tiempo de cada fuente puede ayudarle a determinar qué fuentes pueden estar afectando negativamente al valor global de A-v. Luego puede abordar los problemas con esas fuentes en particular. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para estimar el tiempo que tarda una consulta en completarse </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Motor de ejecución</span>. </p> <p>Al revisar el campo <span class="wintitle"> Tiempo de barrido de datos</span> se obtiene una estimación del tiempo que tarda una consulta en completarse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para enumerar todos los perfiles disponibles en este equipo y detalles sobre su estado </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Perfiles</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver el estado de replicación </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado del componente</span>. </p> <p>Compruebe el estado del componente Replicar. Si la replicación se está ejecutando, se muestra Aceptar. Si el componente Replicar ha fallado, se muestra un mensaje de error. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver el estado de <span class="wintitle"> Report Server</span> para un equipo <span class="keyword"> Report</span> que se conecta al servidor de Data Workbench </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado del servidor de informes</span>. </p> <p>Esta sección de la interfaz <span class="wintitle"> Estado detallado</span> incluye una copia del archivo <span class="filepath"> Report Server.cfg</span>, información sobre el número de informes que se están ejecutando (fracción actual) e información sobre el error más reciente (último error). </p> <p>Para ver los pasos para editar el archivo <span class="filepath"> Report Server.cfg</span>, consulte la <i>Guía del informe de Data Workbench</i>. </p> <p> <p>Nota: Si la sección <span class="wintitle"> Estado del servidor de informes</span> no aparece en la interfaz <span class="wintitle"> Estado detallado</span>, es posible que tenga que configurar el servidor de Data Workbench para que muestre <span class="wintitle"> Estado del servidor de informes</span>. Para ver los pasos, consulte la <i>Guía del informe de Data Workbench</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver la información de uso de memoria de Transform </p> </td> 
   <td colname="col2"> <p>Haga clic en <span class="uicontrol"> Estado de procesamiento</span> &gt; <span class="uicontrol"> Transformar</span>. </p> <p>Para obtener más información sobre la Transformación, consulte la <i>Server Products Installation and Administration Guide</i> y la <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para guardar la interfaz <span class="wintitle"> Estado detallado</span> como archivo <span class="filepath"> *.cfg</span> que se puede abrir en un editor de texto como el Bloc de notas o distribuirlo a otros </p> </td> 
   <td colname="col2"> <p>Haga clic con el botón derecho en el encabezado <span class="uicontrol"> Estado detallado</span> y haga clic en <span class="uicontrol"> Guardar copia como</span>. </p> <p>Nota:  <p>Hacer clic con el botón derecho en el encabezado <span class="uicontrol"> Estado detallado</span> y hacer clic en <span class="uicontrol"> Guardar</span> en <i>nombre del servidor</i>/Estado/ no funciona en la interfaz <span class="wintitle"> Estado detallado</span> . Aparece el siguiente mensaje de error: </p> <p>No se puede guardar /Status/. 403 Prohibido </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver la métrica <span class="uicontrol"> Filas por origen de registro</span> </p> </td> 
   <td colname="col2"> <p>Si es necesario registrar las filas por métrica de origen de registro en Estado detallado, el administrador de Datas Workbench debe definir el "ID de origen de registro" y proporcionar un nombre único en Procesamiento de registros del perfil personalizado. </p> </td> 
  </tr> 
 </tbody> 
</table>
