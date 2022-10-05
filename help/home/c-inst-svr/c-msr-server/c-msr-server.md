---
description: Identificar los requisitos mínimos y las recomendaciones para la Data Workbench (anteriormente [!DNL Insight]) componentes del servidor antes de planificar e implementar el sistema.
title: Requisitos del sistema del servidor
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Requisitos del sistema del servidor{#server-system-requirements}

{{eol}}

Identifique los requisitos mínimos y las recomendaciones para los componentes del servidor de Data Workbench antes de planificar e implementar su sistema.

## Requisitos de DPU{#dpu-requirements}

La unidad de procesamiento de datos (DPU) del servidor es el componente principal de procesamiento de datos de la Data Workbench. Escucha las conexiones de red desde la Data Workbench, lee los datos de origen sin procesar de la Unidad de Servidor de Archivos (FSU) y utiliza importantes recursos de computación y almacenamiento.

### Capacidad con licencia {#section-71850e13783443798b3df9eb22cc63dc}

Consulte la Descripción de los servicios en la sección *Adobe [!DNL Data Workbench (Insight)] Acuerdo de servicio* para información de capacidad de licencia.

>[!NOTE]
>
>Para *Protección de extremo de MS System Center* en los servidores de Windows 2012, estos ejecutables deben agregarse al ***Procesos excluidos:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>


### Requisitos y Recommendations del sistema DPU {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe proporciona recomendaciones con respecto a un diseño de Data Workbench que satisfaga sus necesidades comerciales. Sin embargo, las siguientes directrices son útiles al seleccionar el sistema operativo (OS) y el hardware, ya que la naturaleza optimizada del software DPU coloca requisitos específicos en la plataforma SO/hardware.

Si un único conjunto de datos está limitado por la capacidad o velocidad de una sola DPU, puede agruparlos. Por ejemplo, supongamos que tiene tres copias con licencia del software DPU que se utilizan juntas para ejecutar más rápidamente un conjunto de datos más grande. Como los datos se dividen de manera uniforme entre las máquinas, la capacidad de licencia del conjunto de datos se multiplica por tres. Además, la velocidad de procesamiento por fila es tres veces más rápida que una sola DPU.

Para obtener el mejor rendimiento de su inversión en DPU, Adobe recomienda los siguientes componentes de alto rendimiento descritos en la siguiente tabla:

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
   <td colname="col1"> <p>Sistema operativo </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td>
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>CPU </p> </td>
   <td colname="col2"> <p>Consulte Recomendaciones. </p> </td>
   <td colname="col3"> Se recomiendan los procesadores de más de 4 núcleos de última generación de Intel o AMD. Para un rendimiento óptimo, 8 núcleos; para una compensación entre velocidad y coste, se recomiendan 4 núcleos. </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Almacenamiento de datos en funcionamiento </p> </td>
   <td colname="col2"> <p>1 TB+ de almacenamiento temporal lógico total. </p> <p>Acceso de baja latencia al subsistema de disco </p> </td>
   <td colname="col3"> <p>Para el Adobe de almacenamiento temporal, se recomienda: </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 a 8) * (750 GB o más) discos duros SATA (eje de 3,5") </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 a 10) * (300 GB o más) discos duros SATA (eje de 2,5") </li>
    </ul> <p>Estos deben configurarse en una matriz JBOD. Alternativamente, cuando la capacidad bruta de disco supera los 2 TB, se puede utilizar una matriz de volúmenes RAID1 de 2 discos. Por ejemplo, configure seis discos como un par RAID 1 de 3*(2*750 GB). </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Almacenamiento de datos del sistema </p> </td>
   <td colname="col2"> <p>Además, el Adobe requiere almacenamiento de información de alta disponibilidad de un tamaño modesto (20 GB) para el sistema operativo, el software DPU y otro software del sistema. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Hardware de agrupación en clúster </p> </td>
   <td colname="col2"> <p>Consulte Recomendaciones. </p> </td>
   <td colname="col3"> <p>Utilice un conjunto de servidores homogéneo. En un clúster de DPU, el servidor más lento reduce el rendimiento de todo el conjunto de datos. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Rendimiento de la red en clúster </td>
   <td colname="col2"> Una conexión Ethernet Gigabit conmutada o buena. </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

### Subsistemas de disco alternativos {#section-6f984eabe8074759aa9deaf17e3a68b7}

Cuando considere subsistemas de disco alternativos para almacenamiento temporal, tenga en cuenta los siguientes factores y pautas:

* La DPU exige un sistema de disco de alto rendimiento, por lo que la configuración de un subsistema de disco inadecuado puede provocar cuellos de botella en el rendimiento.
* El software de DPU realiza su propia depuración de datos orientada al rendimiento en un conjunto de discos JBOD. No utilice RAID para aumentar la velocidad.
* Adobe recomienda que el DPU tenga un ancho de banda sostenido agregado de más de 400 MB/s a los discos.
* Los tamaños de lectura promedio son muy altos (2 MB+). Por este motivo, los discos SAS de 15.000 o 10.000 suelen funcionar un poco mejor (o peor) que los discos SATA con un costo y una capacidad considerables.
* Evite utilizar una arquitectura SAN. La experiencia muestra que el costo de obtener un SAN para realizar los niveles requeridos es generalmente extremo.
* El subsistema de disco local se utiliza como espacio de memoria virtual; no se pierden datos de forma permanente debido a una falla en el disco duro, por lo que se debe evitar sistemas costosos, lentos y de alta disponibilidad.

### Consideraciones sobre la velocidad {#section-01330be232894e08a526d8d82b7c4eb2}

El Adobe no puede proporcionar una garantía o representación sobre la velocidad a la que una Data Workbench configurada procesa los datos, ya que una variedad de factores afectan a la velocidad de procesamiento de los datos, incluidos, entre otros, los siguientes:

* Número de filas de datos
* Número de dimensiones (columnas) de datos
* Número y complejidad de los pasos de procesamiento personalizados
* Uso de clústeres
* Velocidad del hardware

## Requisitos de la unidad del servidor de archivos{#file-server-unit-requirements}

La Unidad de Servicio de Archivos (FSU) del servidor es el principal componente de almacenamiento y administración de datos de la Data Workbench. La FSU actúa como servidor de archivos para los datos de origen sin procesar de la DPU y, cuando corresponde, coordina la agrupación de DPU. Cada FSU tiene licencia para suministrar datos de origen de hasta cinco (5) DPUs.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Componentes de FSU </th>
   <th colname="col2" class="entry"> Recomendaciones </th>
   <th colname="col3" class="entry"> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Sistema operativo, CPU, RAM </p> </td>
   <td colname="col2"> <p>Estos requisitos son los mismos que los de la DPU. Sin embargo, para la FSU, el Adobe recomienda utilizar los requisitos mínimos en lugar de seguir las recomendaciones. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sistema de discos </p> <p>La FSU requiere almacenamiento redundante y altamente disponible para grandes volúmenes de datos. Adobe trabajará con usted para determinar sus necesidades exactas. </p> </td>
   <td colname="col1"> <p>Adobe recomienda: </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 o más) * (750 GB o buenos) discos duros SATA en una configuración RAID 5/6. </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">Conexión SAN de alto performance que soporta ancho de banda sostenido de 100 MB/s+. </li>
    </ul> <p>Como la FSU posee los datos de la fuente sin procesar, cualquier pérdida sería irrecuperable, y el Adobe sugiere realizar copias de seguridad de estos datos de forma regular. </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Rendimiento de red </p> </td>
   <td colname="col2"> <p>El Adobe requiere conexiones Ethernet Gigabit conmutadas entre FSU y DPU que trabajan juntas. </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## Requisitos del sensor{#sensor-requirements}

El sensor de Data Workbench recopila datos de eventos de servidores web, de aplicaciones y de recopilación de datos para transmitirlos a cualquier servidor. [!DNL Sensor’s] la instrumentación garantiza una medición precisa y coherente de los eventos que se producen en su canal de Internet. [!DNL Sensor] admite muchas combinaciones de software de servidor web y sistema operativo.

### Sistema de sensores Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

En la tabla siguiente se describen las recomendaciones del sistema para [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Funciones </th>
   <th colname="col2" class="entry"> Recomendado </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Almacenamiento en disco </p> </td>
   <td colname="col2"> <p>512 MB mínimo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>32 MB de RAM deben estar disponibles para <span class="wintitle"> Sensor </span> en el equipo HTTP u otro equipo servidor que sea su host. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Rendimiento de red </p> </td>
   <td colname="col2"> <p>1 Mbps o buena conexión de red a un servidor repetidor o <span class="keyword"> servidor de data workbench </span>. <span class="wintitle"> Sensor </span> normalmente consume mucho menos ancho de banda que uno (1) Mbps. Los consultores de Adobe le ayudarán a estimar la cantidad real de ancho de banda que se necesitaría de forma rutinaria. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Puertos de red y cortafuegos </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> se conecta a la función <span class="keyword"> servidor de data workbench </span> uso de HTTPS (normalmente puerto 443, aunque esto es configurable) o HTTP (normalmente puerto 80, aunque esto es configurable). </p> <p>El puerto apropiado en cualquier cortafuegos que resida entre un <span class="wintitle"> Sensor </span> y el objetivo <span class="keyword"> servidor de data workbench </span> o el servidor repetidor solo debe abrirse entre los <span class="wintitle"> Sensor </span> equipo de alojamiento y <span class="keyword"> servidor de data workbench </span> o el servidor repetidor antes de comenzar el <span class="wintitle"> Sensor </span> proceso de instalación. <span class="wintitle"> Sensor </span> realiza una conexión unidireccional HTTPS o HTTP a un <span class="keyword"> servidor de data workbench </span> o servidor repetidor. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sistemas de administración de redes </p> </td>
   <td colname="col2"> <p>Los sistemas de administración de redes existentes deben supervisar el estado del hardware informático subyacente (por ejemplo, el espacio en disco, el servicio de red) y la conectividad de red, así como el registro de eventos de Windows o el syslog UNIX. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sincronización de tiempo del servidor </p> </td>
   <td colname="col2"> <p>Asegúrese de que el tiempo del sistema del equipo se sincroniza continuamente en todos los equipos que hospedan un <span class="wintitle"> Sensor </span>. Las aplicaciones y los equipos del servidor web supervisados por <span class="wintitle"> Sensor </span> debe tener tiempos de sistema sincronizados para que los datos de evento recopilados de ellos sean precisos. Consulte la documentación de su sistema operativo para ver los pasos necesarios para sincronizar los tiempos del sistema de forma continua con NTP u otra instalación de sincronización de tiempo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Uso del nombre DNS </p> </td>
   <td colname="col2"> <p>Adobe recomienda que <span class="wintitle"> Sensores </span> usar un nombre DNS (en lugar de una dirección IP) para resolver la dirección de red de una <span class="keyword"> servidor de data workbench </span> o servidor repetidor. Cuando <span class="wintitle"> Sensor </span> utiliza un nombre DNS, el archivo DNS o los hosts locales del servidor web host deben configurarse para resolver el nombre del <span class="keyword"> servidor de data workbench </span> o servidor repetidor. </p> </td>
  </tr>
 </tbody>
</table>

### Software de servidor de soporte {#section-d6071706539f49d9a861d87b98e6f382}

En la tabla siguiente se enumeran las combinaciones más comunes que [!DNL Sensor] admite:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Software de servidor web </th>
   <th colname="col2" class="entry"> Sistema operativo </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Servidor Apache/Servidor HTTP IBM 2.2 </p> </td>
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

Para otras combinaciones de servidor y sistema operativo, consulte el Adobe sobre disponibilidad. No todas las características de [!DNL Sensor] están disponibles con todas las combinaciones de servidor web/aplicación y sistema operativo. Para obtener más información sobre [!DNL Sensor] versiones, póngase en contacto con el servicio de asistencia de Adobe.

## Requisitos del servidor de informes{#report-server-requirements}

El servidor de informes de Data Workbench es el componente que permite generar informes programados. Los informes que se muestran pueden presentar en forma de imágenes .PNG o hojas de cálculo .XLS colocadas en un sistema de archivos o como correos electrónicos. Sus requisitos de hardware son idénticos a los de [Cliente de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=es).

Los siguientes requisitos existen para [!DNL report server]:

* Acceso al sistema de archivos para la salida de datos (recurso compartido de red o unidad local).
* Acceso al servidor SMTP configurado.
* Microsoft Excel 2003 o superior instalado en [!DNL report] servidor. Consulte [Consideraciones para la automatización de Office en el lado del servidor](https://support.microsoft.com/kb/257757) para obtener más información.

## Administración de redes{#network-management}

Adobe recomienda que los sistemas de administración de redes existentes controlen el hardware y la red en los que se basa la plataforma de Data Workbench.

Además, Adobe recomienda monitorizar los registros de eventos de Windows de las FSU y DPU, que se escriben en cuando se produce un error.

>[!NOTE]
>
>Cualquier sistema de almacenamiento en red que hospede archivos de registro debe proporcionar al menos 10 MB por DPU de ancho de banda sostenido.

## Disponibilidad de datos{#data-availability}

Es una práctica normal y necesaria para que una DPU de servidor procese y vuelva a procesar los datos en conjuntos de datos nuevos o actualizados.

Esto puede deberse a cambios de configuración, cambios en la fuente de datos, cambios en el hardware, configuración inadecuada, fallo de hardware, fallo de software, fallo de alimentación, etc. Cuando se produce tal procesamiento o reprocesamiento, todos los datos del conjunto de datos y del sistema deben estar disponibles inmediatamente para los componentes de DPU y FSU. El incumplimiento de este requisito puede llevar a un tiempo de inactividad significativo e innecesario del sistema.

## Problemas de red de DPU y FSU{#dpu-and-fsu-network-issues}

Consideraciones a tener en cuenta cuando se trabaja con redes DPU y FSU.

* Para la distribución de archivos de registro en red, cualquier sistema de almacenamiento en red que hospede archivos de registro debe proporcionar al menos 10 MB por DPU de ancho de banda sostenido.
* La DPU, la FSU y la Data Workbench se comunican de forma interdireccional mediante HTTP o HTTPS en el puerto 80 o 443 (de forma predeterminada; los puertos se pueden configurar alternativamente).
* Data Workbench [!DNL Sensor(s)] debe poder conectarse (unidireccional) a los servidores.
* Para permitir que la DPU envíe mensajes de alerta a través de SMTP, debe poder comunicarse con el servidor SMTP configurado.
* Adobe recomienda que las FSU y las DPU reciban nombres de red como FSU01.CLIENT.COM para evitar la reconfiguración si cambia el caso de una dirección IP.
