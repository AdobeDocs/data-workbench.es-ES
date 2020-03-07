---
description: Establezca los parámetros en el archivo Insight.cfg para especificar la conexión de red y la configuración del Área de trabajo de datos.
solution: Analytics
title: Parámetros de configuración
topic: Data workbench
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Parámetros de configuración{#configuration-parameters}

Establezca los parámetros en el archivo Insight.cfg para especificar la conexión de red y la configuración del Área de trabajo de datos.

El ejemplo siguiente contiene únicamente los parámetros incluidos en el [!DNL Insight.cfg] archivo de forma predeterminada.

**Nueva vista de diseño**

![](assets/config_tree_new_layout.png)

**Vista Diseño original**

![](assets/cfg_Workstation_AddServer.png)

Es posible que algunos de los parámetros disponibles en el nuevo [!DNL Insight.cfg] archivo no estén disponibles en la versión del [!DNL Insight.cfg] archivo. Si se necesita uno de estos parámetros, debe agregarlo al [!DNL Insight.cfg] archivo mediante [!DNL Add Custom Key], haciendo clic con el botón secundario en un parámetro y especificando el nombre y el tipo. También puede agregar parámetros abriendo el [!DNL .cfg] archivo (ubicado en el directorio de instalación de Área de trabajo de datos) mediante un editor de texto.

A continuación se muestra un ejemplo de todos los parámetros disponibles para el [!DNL Insight.cfg] archivo que puede utilizar como modelo para agregar entradas de parámetro:

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

La tabla siguiente proporciona descripciones de los parámetros de [!DNL Insight.cfg] archivo disponibles en orden alfabético.

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
   <td colname="col2"> <p>El nombre de host o la dirección IP numérica del equipo del servidor de Área de trabajo de datos. </p> <p>Ejemplo: <span class="filepath"> vsServer.mycompany.com o 192.168.1.90</span> </p> <p>Si <span class="wintitle"> no se especifica Address</span> , <span class="keyword"> el cliente</span> utiliza el nombre común especificado en el parámetro Nombre común del servidor SSL cuando Usar archivo de dirección se establece en false. </p> <p> <p>Nota: Si el parámetro Usar archivo de dirección se establece en true, el texto introducido en el parámetro Address se puede eliminar una vez abierto el primer perfil en <span class="keyword"> el cliente</span>. A continuación, la configuración del parámetro de ubicación de red determina qué direcciones del archivo de dirección del clúster se utilizan para conectarse al servidor maestro. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de colores </p> </td> 
   <td colname="col2"> <p>Especifica el color de fondo de la aplicación <span class="keyword"> cliente</span>. Las opciones son las siguientes: </p> <p>0 = negro </p> <p>1 = blanco </p> <p>2 = monocromo </p> <p>El valor predeterminado es 0, negro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nivel de conexión predeterminado </p> </td> 
   <td colname="col2"> <p>Opcional. Permite que la instancia de Área de trabajo de datos funcione de forma predeterminada como flujo continuo, sin conexión o en línea cada vez que se abre. Las opciones son Streaming, Online o Offline. La configuración predeterminada de Área de trabajo de datos es trabajar sin conexión. </p> <p> <p>Nota: Antes de decidir trabajar en línea de forma predeterminada, asegúrese de sopesar los beneficios y las consecuencias que se describen en <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Trabajar sin conexión y en línea</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuentes </p> </td> 
   <td colname="col2"> <p>Opcional. Vector que enumera las fuentes que <span class="keyword"> el cliente</span> debe utilizar para representar caracteres especiales unicode basados en UTF8. El número de fuentes de la lista es ilimitado. </p> <p>La primera fuente siempre debe ser la consola Lucida Sans. Si este parámetro no se incluye en el archivo <span class="filepath"> Insight.cfg</span> , Área de trabajo de datos solo utiliza la consola Lucida Sans para mostrar texto. </p> <p> Área de trabajo de datos utiliza la primera fuente de la lista para representar todos los caracteres hasta que encuentre un carácter que no pueda representar. Utiliza la segunda fuente de la lista para representar ese carácter. Si esa fuente no representa el carácter, Área de trabajo de datos utiliza la tercera fuente de la lista para representar ese carácter, etc., hasta que llegue al final de la lista de fuentes. Si la fuente correcta no aparece en el vector, Área de trabajo de datos muestra el valor hexadecimal del carácter. </p> <p> <p>Nota:  No cambie este parámetro mientras se esté ejecutando el Área de trabajo de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Se muestra la configuración de gamma para el Área de trabajo de datos. El valor predeterminado es 1.6. Adobe no recomienda cambiar este valor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licencias </p> </td> 
   <td colname="col2"> <p>Opcional. Solo es necesario modificar los parámetros del vector de licencias si se está poniendo en contacto con el servidor de licencias de Adobe a través de un servidor proxy. </p> <p>Identificador de sección para parámetros que permiten que el <span class="keyword"> cliente</span> se ponga en contacto con el servidor de licencias de Adobe a través de un servidor proxy. Expanda el nodo Licencias y complete los siguientes parámetros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección proxy </p> </td> 
   <td colname="col2"> <p>Opcional. La dirección del servidor proxy que el <span class="keyword"> cliente</span> debe utilizar para acceder al servidor de licencias de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puerto proxy </p> </td> 
   <td colname="col2"> <p>Opcional. El puerto del servidor proxy. </p> </td> 
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
   <td colname="col2"> <p>Especifica el tamaño máximo permitido en la caché de datos utilizada por <span class="keyword"> el cliente</span> que se ejecuta en un único equipo. </p> <p>Mientras que el parámetro Bytes de muestra del archivo <span class="filepath"> Server.cfg</span> especifica el tamaño de caché de datos para todos <span class="keyword"> los clientes</span> que se conectan a un servidor de Área de trabajo de datos (250e6 bytes de forma predeterminada), el parámetro Tamaño máximo de muestra permite limitar aún más el tamaño de caché de datos de un equipo en particular. Esto resulta útil cuando el cliente se instala en un equipo con almacenamiento limitado o capacidad de cómputo. </p> <p> <p>Nota: Este parámetro limita el tamaño de una muestra de datos local consultada localmente por el programa cliente. Por el contrario, el archivo <span class="filepath"> cache.db</span> contiene datos para cada perfil al que se conecta el cliente, además de los nombres de los elementos y sus dimensiones. Estos nombres y dimensiones de elementos en los archivos <span class="filepath"> cache.db</span> son necesarios para ejecutar consultas locales. Por lo tanto, no hay otra forma de limitar su tamaño que reducir el número de elementos en el conjunto de datos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre </p> </td> 
   <td colname="col2">Opcional. Nombre que <span class="keyword"> el cliente</span> utiliza para identificar el <span class="keyword"> servidor</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ubicación de red </p> </td> 
   <td colname="col2"> <p>Opcional. Ubicación de red que <span class="keyword"> el cliente</span> utiliza para resolver el nombre común del servidor de Área de trabajo de datos en una dirección IP. Las ubicaciones de red disponibles se definen en el archivo de dirección del servidor. Para obtener más información, consulte la Guía <i>de instalación y administración de productos de</i>servidor. </p> <p>Si no especifica una ubicación de red, el cliente <span class="keyword"></span> resuelve los nombres comunes utilizando la ubicación de red predeterminada, "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puerto </p> </td> 
   <td colname="col2"> <p>El puerto al que <span class="keyword"> el cliente</span> envía solicitudes. Este número de puerto debe coincidir con el puerto en el que el servidor de Área de trabajo de datos escucha solicitudes. Suele ser 443 para conexiones seguras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dirección proxy </p> </td> 
   <td colname="col2"> <p>Si se necesita un servidor proxy para conectarse a los equipos del servidor del Área de trabajo de datos, debe completar al menos este parámetro y el parámetro de puerto proxy. Opcionalmente, puede completar los parámetros Nombre de usuario proxy y Contraseña de usuario proxy. </p> <p>La dirección del servidor proxy que <span class="keyword"> el cliente</span> debe utilizar para acceder al servidor de Área de trabajo de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contraseña de proxy </p> </td> 
   <td colname="col2"> <p>Opcional. La contraseña del servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Puerto proxy </p> </td> 
   <td colname="col2"> <p>El puerto del servidor proxy. El valor predeterminado es 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre de usuario proxy </p> </td> 
   <td colname="col2"> <p>Opcional. El nombre de usuario del servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Buscar </p> </td> 
   <td colname="col2"> <p>En <span class="filepath"> Insight.cfg</span> (o cualquier archivo <span class="filepath"> .cfg</span> ), puede buscar por nombre de clave, tipo de clave o valor para localizar rápidamente una entrada, con el fin de eliminar la necesidad de desplazarse por archivos extendidos y grandes para obtener información anidada. Puede localizar nombres de dimensión, nombres de servidor, etc. </p> <p>Escriba una frase de búsqueda en este campo para localizar los datos. Según el éxito de una coincidencia, el color del campo cambia. Las coincidencias se muestran resaltadas y las no coincidencias aparecen atenuadas. Si no hay coincidencias, el fondo del campo de búsqueda se vuelve rojo. Al pulsar Intro, el árbol de configuración expande todos los lugares donde hay una coincidencia y se contrae cuando no hay una coincidencia. </p> <p>También puede utilizar expresiones regulares en el campo <span class="wintitle"> Buscar</span> . Por ejemplo, puede utilizar re: <span class="filepath"> *zip.*</span> para cualquier entrada que contenga la palabra "zip". </p> <p>Para borrar una búsqueda, pulse <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores </p> </td> 
   <td colname="col2"> <p>Encabezado vectorizado para conexiones <span class="keyword"> cliente</span> a <span class="keyword"> servidor</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Certificado de cliente SSL </p> </td> 
   <td colname="col2"> <p>Opcional a menos que tenga más de un certificado. Nombre del archivo que contiene el certificado digital para esta copia de Área de trabajo de datos. Este es el archivo que descargó en Descarga e instalación del certificado digital. </p> <p>Ejemplo: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Si deja este parámetro en blanco, <span class="keyword"> el cliente</span> utiliza el certificado que esté presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre común del servidor SSL </p> </td> 
   <td colname="col2"> <p>Nombre común del servidor de Área de trabajo de datos (según se asigna en su certificado digital). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Iconos de la barra de herramientas </p> </td> 
   <td colname="col2"> <p>False desactiva los iconos de la interfaz de usuario de la estación de trabajo y muestra el texto en la barra de herramientas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usar archivo de dirección </p> </td> 
   <td colname="col2"> <p>Especifica si alguna configuración del archivo de direcciones anula la configuración del parámetro Address. Las opciones son true o false. Si se establece en true, la configuración del archivo de direcciones, si está presente, anula la configuración del parámetro Address. El valor predeterminado es true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usar SSL </p> </td> 
   <td colname="col2">Especifica si SSL se utiliza para la comunicación segura entre el servidor de Área de trabajo de datos y <span class="keyword"> el cliente</span>. Las opciones son true o false. El valor predeterminado es true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mostrar todo </p> </td> 
   <td colname="col2"> <p>Opcional. Permite mostrar temporalmente todas las métricas, dimensiones y filtros que se han ocultado mediante cualquiera de las siguientes funciones: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">[Exclusivo] en los archivos <span class="filepath"> order.txt</span> </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Opción Ocultar en los archivos <span class="filepath"> order.txt</span> </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Mostrar parámetro en los archivos <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>y <span class="filepath"> .filter</span> . </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Parámetro oculto en el archivo <span class="filepath"> Transformation.cfg</span> . </li> 
     </ul> </p> <p>Para obtener más información sobre estos métodos, consulte <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Ocultar un elemento</a>de menú. </p> <p>Las opciones son true o false. La configuración predeterminada es false. Cambie este parámetro a true para mostrar temporalmente métricas, dimensiones y filtros ocultos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desbloquear </p> </td> 
   <td colname="col2"> <p>Opcional. Especifica si puede desbloquear espacios de trabajo bloqueados. Las opciones son true y false. True le permite desbloquear cualquier espacio de trabajo bloqueado, mientras que false no lo hace. El valor predeterminado es false. Para obtener más información sobre los espacios de trabajo bloqueados, consulte <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Desbloqueo de un espacio de trabajo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar software </p> </td> 
   <td colname="col2"> <p>Opcional. Especifica si se permite que este <span class="keyword"> software de </span>cliente sea actualizado por el servidor de Área de trabajo de datos. Las opciones son true o false. El valor predeterminado es true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carpeta de usuario </p> </td> 
   <td colname="col2"> <p>Opcional. Especifica el nombre y la ubicación de la carpeta que contiene las copias locales de los espacios de trabajo, métricas, dimensiones o archivos de configuración de cada perfil. La configuración predeterminada es Usuario\\, que especifica la carpeta Usuario dentro del directorio de instalación de Área de trabajo de datos. </p> <p>Cambiar esta configuración resulta útil cuando dos usuarios comparten el mismo equipo. Para dar cabida a ambos usuarios, puede especificar una carpeta compartida a la que ambos tengan acceso. </p> </td> 
  </tr> 
 </tbody> 
</table>

