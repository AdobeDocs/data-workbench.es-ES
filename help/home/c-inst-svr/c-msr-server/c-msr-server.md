---
description: Identifique los requisitos mínimos y las recomendaciones para los componentes del servidor de Área de trabajo de datos (anteriormente [!DNL Insight]) antes de planificar e implementar su sistema.
title: Requisitos del sistema del servidor
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Requisitos del sistema del servidor{#server-system-requirements}

Identifique los requisitos mínimos y las recomendaciones para los componentes del servidor de Área de trabajo de datos antes de planificar e implementar el sistema.

## Requisitos de DPU{#dpu-requirements}

La unidad de procesamiento de datos del servidor (DPU) es el componente principal de procesamiento de datos del área de trabajo de datos. Escucha conexiones de red desde el Área de trabajo de datos, lee datos de origen sin procesar de la Unidad de servidor de archivos (FSU) y utiliza importantes recursos computacionales y de almacenamiento.

### Capacidad con licencia {#section-71850e13783443798b3df9eb22cc63dc}

Consulte la Descripción de los servicios en el Acuerdo *de servicio de[!DNL Data Workbench (Insight)]Adobe* para obtener información sobre la capacidad de licencia.

>[!NOTE]
>
>Para *MS System Center Endpoint Protection* en servidores Windows 2012, estos ejecutables deben agregarse a los procesos ***excluidos:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### Recomendaciones y requisitos del sistema DPU {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe proporciona recomendaciones sobre un diseño de Área de trabajo de datos que satisface las necesidades comerciales. Sin embargo, las siguientes directrices son útiles a la hora de seleccionar el sistema operativo (SO) y el hardware, ya que la naturaleza optimizada del software DPU coloca requisitos específicos en la plataforma de SO/hardware.

Si un solo conjunto de datos está limitado por la capacidad o velocidad de un solo DPU, puede agruparlos. Por ejemplo, supongamos que tiene tres copias con licencia del software DPU que se utilizan en conjunto para ejecutar más rápidamente un conjunto de datos más grande. Dado que los datos se dividen uniformemente entre las máquinas, la capacidad con licencia del conjunto de datos se multiplica por tres. Además, la velocidad de procesamiento por fila es tres veces más rápida que una sola DPU.

Para obtener el mejor rendimiento de su inversión en DPU, Adobe recomienda los siguientes componentes de alto rendimiento descritos en la tabla siguiente:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Requerido </th> 
   <th colname="col3" class="entry"> Recomendado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sistema operativo  </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>Consulte Recomendaciones. </p> </td> 
   <td colname="col3"> Se recomiendan los procesadores de 4 núcleos de última generación de Intel o AMD. Para un rendimiento óptimo, 8 núcleos; para una compensación entre velocidad y coste, se recomiendan 4 núcleos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Almacenamiento de datos de trabajo </p> </td> 
   <td colname="col2"> <p>1 TB+ del almacenamiento temporal lógico total. </p> <p>Acceso de baja latencia al subsistema de disco </p> </td> 
   <td colname="col3"> <p>Para almacenamiento temporal, Adobe recomienda: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 a 8) * (750 GB o más) discos duros SATA (ejes de 3,5") </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 a 10) * (300 GB o más) discos duros SATA (ejes de 2,5") </li> 
    </ul> <p>Estos deben configurarse en una matriz JBOD. Alternativamente, cuando la capacidad de disco bruta supera los 2 TB, se puede utilizar una matriz de volúmenes RAID1 de 2 discos. Por ejemplo, configure seis discos como un par RAID 1 de 3*(2*750 GB). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Almacenamiento de datos del sistema </p> </td> 
   <td colname="col2"> <p>Además, Adobe requiere un almacenamiento de alta disponibilidad de un tamaño modesto (20 GB) para el sistema operativo, el software DPU y otro software del sistema. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hardware de clústeres </p> </td> 
   <td colname="col2"> <p>Consulte Recomendaciones. </p> </td> 
   <td colname="col3"> <p>Utilice un conjunto homogéneo de servidores. En un clúster de DPU, el servidor más lento reduce el rendimiento de todo el conjunto de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendimiento de red en clúster </td> 
   <td colname="col2"> Conexión Ethernet Gigabit conmutada o buena. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Subsistemas de discos alternativos {#section-6f984eabe8074759aa9deaf17e3a68b7}

Al considerar subsistemas de disco alternativos para almacenamiento temporal, tenga en cuenta los siguientes factores y pautas:

* El DPU exige excepcionalmente un sistema de disco de alto rendimiento, por lo que la configuración de un subsistema de disco inadecuado puede causar cuellos de botella en el rendimiento.
* El software de DPU realiza su propio striping de datos orientado al rendimiento en un conjunto de discos JBOD. No utilice RAID para aumentar la velocidad.
* Adobe recomienda que el DPU tenga un ancho de banda sostenido agregado de 400 MB/s a los discos.
* Los tamaños de lectura promedio son muy altos (más de 2 MB). Por este motivo, los discos SAS de 15.000 o 10.000 veces funcionan un poco mejor (o peor) que los discos SATA con un costo y una reducción de la capacidad significativos.
* Evite utilizar una arquitectura SAN. La experiencia demuestra que el costo de lograr que un SAN funcione en los niveles requeridos es generalmente extremo.
* El subsistema de disco local se utiliza como espacio de memoria virtual; no se pierden datos de forma permanente debido a una falla del disco duro, por lo que hay que evitar sistemas costosos, más lentos y de alta disponibilidad.

### Consideraciones sobre la velocidad {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe no puede proporcionar una garantía ni una representación respecto a la velocidad a la que un área de trabajo de datos configurada procesa los datos, ya que una serie de factores afectan la velocidad de procesamiento de datos, entre los que se incluyen los siguientes:

* Número de filas de datos
* Número de dimensiones (columnas) de datos
* Número y complejidad de los pasos de procesamiento personalizados
* Uso de clústeres
* Velocidad del hardware

## Requisitos de unidad del servidor de archivos{#file-server-unit-requirements}

La unidad de servicio de archivos (FSU) del servidor es el principal componente de administración y almacenamiento de datos del área de trabajo de datos. La FSU actúa como servidor de archivos para los datos de origen sin procesar en la DPU y, cuando procede, coordina la agrupación de DPU. Cada FSU tiene licencia para suministrar datos de origen de hasta cinco (5) DPUs.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componentes de FSU </th> 
   <th colname="col2" class="entry"> Las actividades de </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sistema operativo, CPU, RAM </p> </td> 
   <td colname="col2"> <p>Estos requisitos son los mismos que los del DPU. Sin embargo, para la FSU, Adobe recomienda utilizar los requisitos mínimos en lugar de seguir las recomendaciones. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistema de discos </p> <p>La FSU requiere almacenamiento redundante y de alta disponibilidad para grandes volúmenes de datos. Adobe trabajará con usted para determinar sus requisitos exactos. </p> </td> 
   <td colname="col1"> <p>Adobe recomienda: </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 o más) * (750 GB o buenos) discos duros SATA en una configuración RAID 5/6. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Conexión SAN de alto rendimiento compatible con ancho de banda sostenido de más de 100 MB/s. </li> 
    </ul> <p>Dado que la FSU mantiene los datos de la fuente sin procesar, cualquier pérdida sería irrecuperable y Adobe sugiere realizar copias de seguridad de estos datos de forma regular. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rendimiento de red </p> </td> 
   <td colname="col2"> <p>Adobe requiere conexiones Ethernet gigabit conmutadas entre FSU y DPU que funcionen juntas. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Requisitos del sensor{#sensor-requirements}

Data Workbench recopila datos de eventos de servidores Web, de aplicaciones y de recopilación de datos para que se transmitan a cualquier servidor. [!DNL Sensor’s] la instrumentación garantiza una medición coherente y precisa de los eventos que se producen en el canal de Internet. [!DNL Sensor] admite muchas combinaciones de software de servidor web y sistema operativo.

### Recomendaciones del sistema de sensores {#section-0a981c3a47b644c1a1a56974ba033b9c}

La siguiente tabla describe las recomendaciones del sistema para [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funciones  </th> 
   <th colname="col2" class="entry"> Recomendado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Almacenamiento en disco </p> </td> 
   <td colname="col2"> <p>512 MB como mínimo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MB de RAM deben estar disponibles para <span class="wintitle"> Sensor </span> en el HTTP u otro equipo servidor que sea su host. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rendimiento de red </p> </td> 
   <td colname="col2"> <p>1 Mbps o buena conexión de red a un servidor repetidor o a un servidor <span class="keyword"> de área de trabajo de datos </span>. <span class="wintitle"> El sensor </span> suele consumir mucho menos ancho de banda que uno (1) Mbps. Sus asesores de Adobe le ayudarán a estimar la cantidad real de ancho de banda que se necesitaría de forma rutinaria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puertos de red y servidores de seguridad </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> El sensor </span> se conecta al servidor del área de trabajo de <span class="keyword"> datos </span> utilizando HTTPS (normalmente, el puerto 443, aunque es configurable) o HTTP (normalmente el puerto 80, aunque es configurable). </p> <p>El puerto apropiado en cualquier servidor de seguridad que resida entre un <span class="wintitle"> sensor </span> y el servidor del área de trabajo de datos de destino <span class="keyword"> o el servidor repetidor sólo debe abrirse entre el equipo de alojamiento </span> Sensor <span class="wintitle"> respectivo y el servidor del área de trabajo de datos </span> o el servidor repetidor antes de iniciar el proceso de instalación del <span class="keyword"> sensor </span> <span class="wintitle"> </span> . <span class="wintitle"> Sensor </span> realiza una conexión HTTP o HTTPS unidireccional a un servidor de área de trabajo de datos <span class="keyword"> </span> o un servidor repetidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistemas de administración de redes </p> </td> 
   <td colname="col2"> <p>Los sistemas de administración de redes existentes deben supervisar el estado del hardware informático subyacente (por ejemplo, espacio en disco, servicio de red) y la conectividad de red, así como el registro de eventos de Windows o el syslog UNIX. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronización del tiempo del servidor </p> </td> 
   <td colname="col2"> <p>Asegúrese de que el tiempo del sistema del equipo se sincroniza continuamente en todos los equipos que hospedan un <span class="wintitle"> sensor </span>. Las aplicaciones de servidor Web y los equipos que son supervisados por <span class="wintitle"> Sensor </span> deben tener tiempos de sistema sincronizados para que los datos de eventos recopilados de ellos sean precisos. Consulte la documentación del sistema operativo para ver los pasos para sincronizar las horas del sistema de forma continua con NTP u otra instalación de sincronización de tiempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso del nombre DNS </p> </td> 
   <td colname="col2"> <p>Adobe recomienda que <span class="wintitle"> los sensores </span> utilicen un nombre DNS (en lugar de una dirección IP) para resolver la dirección de red de un servidor de área de trabajo de datos <span class="keyword"> </span> o un servidor repetidor. Cuando un <span class="wintitle"> sensor </span> utiliza un nombre DNS, es necesario configurar el archivo DNS o los hosts locales del servidor web host para resolver el nombre del servidor del área de trabajo de datos <span class="keyword"> o del servidor repetidor </span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

### Software de servidor de soporte {#section-d6071706539f49d9a861d87b98e6f382}

En la tabla siguiente se enumeran las combinaciones más comunes que [!DNL Sensor] admite:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Software de servidor Web </th> 
   <th colname="col2" class="entry"> Sistema operativo  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidor Apache / Servidor HTTP IBM 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o posterior; RedHat Enterprise Linux 6.x o posterior; Sun Solaris 8.x o posterior; IBM AIX 5.1x o posterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x o posterior </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o posterior </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de aplicaciones Java (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 o posterior; RedHat Enterprise Linux 6.x o posterior; Sun Solaris 8.x o posterior; IBM AIX 5.1x o posterior. </p> </td> 
  </tr> 
 </tbody> 
</table>

Para otras combinaciones de servidores y sistemas operativos, consulte a Adobe acerca de la disponibilidad. No todas las características de [!DNL Sensor] están disponibles con todas las combinaciones de servidor web/de aplicaciones y sistema operativo. Para obtener más información sobre [!DNL Sensor] versiones concretas, póngase en contacto con el servicio de asistencia técnica de Adobe.

## Requisitos del servidor de informes{#report-server-requirements}

El servidor de informes del área de trabajo de datos es el componente que permite generar informes programados. Los informes que se generan pueden tener la forma de imágenes .PNG o hojas de cálculo .XLS ubicadas en un sistema de archivos o como correos electrónicos. Sus requisitos de hardware son idénticos a los del cliente [de Área de trabajo de datos](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html).

Existen los siguientes requisitos para [!DNL report server]:

* Acceso al sistema de archivos para la salida de datos (recurso compartido de red o unidad local).
* Acceso al servidor SMTP configurado.
* Microsoft Excel 2003 o superior instalado en el [!DNL report] servidor. Consulte [Consideraciones para la automatización de Office](http://support.microsoft.com/kb/257757) en el servidor para obtener información adicional.

## Administración de redes{#network-management}

Adobe recomienda que los sistemas de administración de redes existentes supervisen el hardware y la red de los que depende la plataforma Área de trabajo de datos.

Además, Adobe recomienda supervisar los registros de eventos de Windows de los FSU y DPU, en los que se escriben cuando se produce un error.

>[!NOTE]
>
>Cualquier sistema de networked storage que aloja archivos de registro debe proporcionar al menos 10 MB por DPU de ancho de banda sostenido.

## Disponibilidad de datos{#data-availability}

Es una práctica normal y necesaria para que un DPU de servidor procese y vuelva a procesar los datos en un conjunto de datos nuevo o actualizado.

Esto puede deberse a cambios en la configuración, cambios en la fuente de datos, cambios en el hardware, configuración inadecuada, fallas en el hardware, fallas en el software, fallas en la alimentación, etc. Cuando se produce dicho procesamiento o reprocesamiento, todos los datos del conjunto de datos y del sistema deben estar inmediatamente disponibles para los componentes de DPU y FSU. El incumplimiento de este requisito puede llevar a un tiempo de inactividad significativo e innecesario.

## Problemas de red de DPU y FSU{#dpu-and-fsu-network-issues}

Consideraciones a tener en cuenta al trabajar con redes DPU y FSU.

* Para la distribución de archivos de registro en red, cualquier sistema de almacenamiento en red que aloja archivos de registro debe proporcionar al menos 10 MB por DPU de ancho de banda sostenido.
* DPU, FSU y Área de trabajo de datos se comunican de forma interdireccional mediante HTTP o HTTPS en el puerto 80 o 443 (de forma predeterminada; los puertos se pueden configurar de forma alternativa).
* El área de trabajo de datos [!DNL Sensor(s)] debe poder conectarse (unidireccional) a los servidores.
* Para permitir que el DPU envíe mensajes de alerta mediante SMTP, debe poder ponerse en contacto con el servidor SMTP configurado.
* Adobe recomienda que los FSU y los DPU tengan nombres de red como FSU01.CLIENT.COM para evitar la reconfiguración si cambia el caso de una dirección IP.