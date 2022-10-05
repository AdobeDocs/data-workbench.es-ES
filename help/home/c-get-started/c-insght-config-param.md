---
description: Establezca los parámetros del archivo Insight.cfg para especificar la conexión de red y los ajustes de configuración de Data Workbench.
title: Parámetros de configuración
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Parámetros de configuración{#configuration-parameters}

{{eol}}

Establezca los parámetros del archivo Insight.cfg para especificar la conexión de red y los ajustes de configuración de Data Workbench.

El ejemplo siguiente contiene solo los parámetros incluidos en la variable [!DNL Insight.cfg] de forma predeterminada.

**Nueva vista Diseño**

![](assets/config_tree_new_layout.png)

**Vista Diseño original**

![](assets/cfg_Workstation_AddServer.png)

Algunos de los parámetros disponibles en la nueva [!DNL Insight.cfg] puede que no esté disponible en su versión de [!DNL Insight.cfg] archivo. Si se necesita uno de estos parámetros, debe agregarlo al [!DNL Insight.cfg] archivo que utiliza [!DNL Add Custom Key], haciendo clic con el botón derecho en un parámetro y, a continuación, especificando el nombre y el tipo. También puede agregar parámetros abriendo la variable [!DNL .cfg] (ubicado en el directorio de instalación de la Data Workbench) utilizando un editor de texto.

A continuación se muestra un ejemplo de todos los parámetros disponibles para la variable [!DNL Insight.cfg] archivo que puede usar como modelo para agregar entradas de parámetros:

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

En la tabla siguiente se describen los [!DNL Insight.cfg] parámetros de archivo en orden alfabético.

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dirección </p> </td> 
   <td colname="col2"> <p>El nombre de host o la dirección IP numérica del equipo servidor de Data Workbench. </p> <p>Ejemplo: <span class="filepath"> vsServer.mycompany.com o 192.168.1.90</span> </p> <p>If <span class="wintitle"> Dirección</span> no se ha especificado, <span class="keyword"> el cliente</span> utiliza el nombre común especificado en el parámetro SSL Server Common Name cuando Usar archivo de direcciones está establecido en false. </p> <p> <p>Nota: Si el parámetro Usar archivo de dirección se establece en true, el texto introducido en el parámetro Address se puede eliminar una vez abierto el primer perfil en <span class="keyword"> el cliente</span>. A continuación, la configuración del parámetro de ubicación de red determina las direcciones del archivo de dirección del clúster que se utilizan para conectarse al servidor maestro. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de colores </p> </td> 
   <td colname="col2"> <p>Especifica el color de fondo del <span class="keyword"> aplicación cliente</span>. Las opciones son las siguientes: </p> <p>0 = negro </p> <p>1 = blanco </p> <p>2 = monocromo </p> <p>El valor predeterminado es 0, negro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nivel predeterminado en línea </p> </td> 
   <td colname="col2"> <p>Opcional. Permite hacer que la instancia de Data Workbench funcione de forma predeterminada como flujo continuo, sin conexión o en línea cada vez que se abre. Las opciones son Streaming, Online o Offline. La configuración predeterminada para la Data Workbench es funcionar sin conexión. </p> <p> <p>Nota: Antes de decidir trabajar en línea de forma predeterminada, asegúrese de sopesar los beneficios y consecuencias descritos en <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Trabajar sin conexión y en línea</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuentes </p> </td> 
   <td colname="col2"> <p>Opcional. Vector que enumera las fuentes que <span class="keyword"> el cliente</span> debe utilizarse para procesar caracteres especiales unicode basados en UTF8. El número de fuentes de la lista es ilimitado. </p> <p>La primera fuente siempre debe ser la consola Lucida Sans. Si este parámetro no está incluido en la variable <span class="filepath"> Insight.cfg</span> , la Data Workbench solo utiliza la consola Lucida Sans para mostrar el texto. </p> <p> La Data Workbench utiliza la primera fuente de la lista para representar todos los caracteres hasta que encuentra un carácter que no puede procesar. Utiliza la segunda fuente de la lista para representar ese carácter. Si esa fuente no representa el carácter, la Data Workbench utiliza la tercera fuente de la lista para representar ese carácter, etc., hasta que llega al final de la lista de fuentes. Si la fuente correcta no aparece enumerada en el vector, la Data Workbench muestra el valor hexadecimal del carácter. </p> <p> <p>Nota: No cambie este parámetro mientras se esté ejecutando la Data Workbench. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Configuración de gamma para la visualización de la Data Workbench. El valor predeterminado es 1.6. Adobe no recomienda cambiar este valor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licencias </p> </td> 
   <td colname="col2"> <p>Opcional. Solo es necesario modificar los parámetros del vector de licencias si se pone en contacto con el servidor de licencias de Adobe a través de un servidor proxy. </p> <p>Identificador de sección para parámetros que habilitan el <span class="keyword"> cliente</span> para ponerse en contacto con el servidor de licencias de Adobe a través de un servidor proxy. Expanda el nodo Licencias y complete los siguientes parámetros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección proxy </p> </td> 
   <td colname="col2"> <p>Opcional. La dirección del servidor proxy que <span class="keyword"> cliente</span> debe utilizar para acceder al servidor de licencias de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puerto proxy </p> </td> 
   <td colname="col2"> <p>Opcional. Puerto del servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre de usuario proxy </p> </td> 
   <td colname="col2"> <p>Opcional. El nombre de usuario del servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contraseña de proxy </p> </td> 
   <td colname="col2"> <p>Opcional. La contraseña asociada al nombre de usuario proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tamaño máximo de la muestra (MB) </p> </td> 
   <td colname="col2"> <p>Especifica el tamaño máximo permitido en la caché de datos utilizada por <span class="keyword"> el cliente</span> en un solo equipo. </p> <p>Mientras que el parámetro Bytes de ejemplo en la variable <span class="filepath"> Server.cfg</span> especifica el tamaño de la caché de datos para todos <span class="keyword"> clientes</span> al conectarse a un servidor de Data Workbench (250e6 bytes de forma predeterminada), el parámetro Maximum Sample Size permite limitar aún más el tamaño de la caché de datos de un equipo en particular. Esto resulta útil cuando el cliente está instalado en un equipo con capacidad de almacenamiento o computación limitada. </p> <p> <p>Nota: Este parámetro limita el tamaño de una muestra de datos local consultada localmente por el programa cliente. Por el contrario, la variable <span class="filepath"> cache.db</span> contiene datos para cada perfil al que se conecta el cliente, además de los nombres de los elementos y sus dimensiones. Estos nombres y dimensiones de elementos en la <span class="filepath"> cache.db</span> se necesitan archivos para ejecutar consultas locales. Por lo tanto, no hay otra forma de limitar su tamaño que la de reducir el número de elementos en el conjunto de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre </p> </td> 
   <td colname="col2">Opcional. El nombre que <span class="keyword"> el cliente</span> para identificar los <span class="keyword"> server</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ubicación de red </p> </td> 
   <td colname="col2"> <p>Opcional. La ubicación de red que <span class="keyword"> cliente</span> utiliza para resolver el nombre común del servidor de Data Workbench en una dirección IP. Las ubicaciones de red disponibles se definen en el archivo de dirección del servidor. Para obtener más información, consulte la <i>Guía de instalación y administración de productos para servidor</i>. </p> <p>Si no especifica una ubicación de red, <span class="keyword"> cliente</span> resuelve los nombres comunes usando la ubicación de red predeterminada, "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puerto </p> </td> 
   <td colname="col2"> <p>Puerto al que <span class="keyword"> el cliente</span> envía solicitudes. Este número de puerto debe coincidir con el puerto en el que el servidor de Data Workbench está escuchando solicitudes. Esto suele ser 443 para conexiones seguras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección proxy </p> </td> 
   <td colname="col2"> <p>Si se necesita un servidor proxy para conectarse a los equipos servidor de Data Workbench, debe completar al menos este parámetro y el parámetro de puerto proxy. Si lo desea, puede completar los parámetros Nombre de usuario proxy y Contraseña de usuario proxy. </p> <p>La dirección del servidor proxy que <span class="keyword"> el cliente</span> debe utilizar para acceder al servidor de Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contraseña de proxy </p> </td> 
   <td colname="col2"> <p>Opcional. La contraseña del servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puerto proxy </p> </td> 
   <td colname="col2"> <p>Puerto del servidor proxy. El valor predeterminado es 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre de usuario proxy </p> </td> 
   <td colname="col2"> <p>Opcional. El nombre de usuario del servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Buscar </p> </td> 
   <td colname="col2"> <p>En el <span class="filepath"> Insight.cfg</span> (o <span class="filepath"> .cfg</span> ), puede buscar por nombre de clave, tipo de clave o valor para localizar rápidamente una entrada, con el fin de eliminar la necesidad de desplazarse por archivos grandes y expandidos para obtener información anidada. Puede localizar nombres de dimensiones, nombres de servidor, etc. </p> <p>Escriba una frase de búsqueda en este campo para localizar los datos. Según el éxito de una coincidencia, el color del campo cambia. Las coincidencias se muestran resaltadas y las no coincidencias aparecen atenuadas. Si no hay coincidencias, el fondo del campo de búsqueda se vuelve rojo. Al pulsar Intro, el árbol de configuración expande cada lugar donde haya una coincidencia y contrae donde no haya una coincidencia. </p> <p>También puede utilizar expresiones regulares en la variable <span class="wintitle"> Buscar</span> campo . Por ejemplo, puede utilizar re: <span class="filepath"> *zip.*</span> para cualquier entrada que contenga la palabra "zip". </p> <p>Para borrar una búsqueda, pulse <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores </p> </td> 
   <td colname="col2"> <p>Encabezado de vectores para <span class="keyword"> cliente</span> a <span class="keyword"> server</span> conexiones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Certificado de cliente SSL </p> </td> 
   <td colname="col2"> <p>Opcional a menos que tenga más de un certificado. Nombre del archivo que contiene el certificado digital para esta copia de Data Workbench. Este es el archivo que descargó en Descargar e instalar el certificado digital. </p> <p>Ejemplo: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Si deja este parámetro en blanco, <span class="keyword"> el cliente</span> utiliza el certificado que esté presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre común del servidor SSL </p> </td> 
   <td colname="col2"> <p>El nombre común del servidor de Data Workbench (tal como se asigna en su certificado digital). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Iconos de la barra de herramientas </p> </td> 
   <td colname="col2"> <p>False desactiva los iconos de la interfaz de usuario de la estación de trabajo y muestra el texto en la barra de herramientas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usar archivo de direcciones </p> </td> 
   <td colname="col2"> <p>Especifica si alguna configuración del archivo de dirección anula la configuración del parámetro Address. Las opciones son true o false. Si se establece en true, la configuración del archivo de direcciones, si está presente, anula la configuración del parámetro Address . El valor predeterminado es true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usar SSL </p> </td> 
   <td colname="col2">Especifica si SSL se utiliza para la comunicación segura entre el servidor de Data Workbench y <span class="keyword"> el cliente</span>. Las opciones son true o false. El valor predeterminado es true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mostrar todo </p> </td> 
   <td colname="col2"> <p>Opcional. Permite mostrar temporalmente todas las métricas, dimensiones y filtros que se han ocultado con cualquiera de las siguientes funciones: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">Configuración [exclusiva] en <span class="filepath"> order.txt</span> files </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Ocultar opción en <span class="filepath"> order.txt</span> files </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Mostrar parámetro en <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>y <span class="filepath"> .filter</span> archivos. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Parámetro oculto en la variable <span class="filepath"> Transformation.cfg</span> archivo. </li> 
     </ul> </p> <p>Para obtener más información sobre estos métodos, consulte <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Ocultar un elemento de menú</a>. </p> <p>Las opciones son true o false. La configuración predeterminada es false. Cambie este parámetro a true para mostrar temporalmente las métricas, dimensiones y filtros ocultos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desbloquear </p> </td> 
   <td colname="col2"> <p>Opcional. Especifica si se le permite desbloquear espacios de trabajo bloqueados. Las opciones son true y false. True permite desbloquear cualquier espacio de trabajo bloqueado, mientras que false no lo hace. El valor predeterminado es false. Para obtener más información sobre los espacios de trabajo bloqueados, consulte <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Desbloquear un espacio de trabajo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar software </p> </td> 
   <td colname="col2"> <p>Opcional. Especifica si se permite <span class="keyword"> el </span>software cliente que actualizará el servidor de Data Workbench. Las opciones son true o false. El valor predeterminado es true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carpeta de usuario </p> </td> 
   <td colname="col2"> <p>Opcional. Especifica el nombre y la ubicación de la carpeta que contiene las copias locales de cualquier espacio de trabajo, métrica, dimensión o archivo de configuración para cada perfil. El valor predeterminado es Usuario\\, que especifica la carpeta Usuario dentro del directorio de instalación de la Data Workbench. </p> <p>Cambiar esta configuración resulta útil cuando dos usuarios comparten el mismo equipo. Para dar cabida a ambos usuarios, puede especificar una carpeta compartida a la que ambos tengan acceso. </p> </td> 
  </tr> 
 </tbody> 
</table>
