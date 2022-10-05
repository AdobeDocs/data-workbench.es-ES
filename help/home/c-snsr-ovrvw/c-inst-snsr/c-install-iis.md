---
description: Instrucciones sobre cómo instalar y configurar Sensor para Servicios de Internet Information Server (IIS) 5.x o 6.x que se ejecutan en Microsoft Windows Server 2000 o posterior.
title: Microsoft IIS en Windows Server 2000 o posterior
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
exl-id: e4b5ac44-b0ac-43be-9b9c-180a64354081
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 1%

---

# Microsoft IIS en Windows Server 2000 o posterior{#microsoft-iis-on-windows-server-or-later}

{{eol}}

Instrucciones sobre cómo instalar y configurar Sensor para Servicios de Internet Information Server (IIS) 5.x o 6.x que se ejecutan en Microsoft Windows Server 2000 o posterior.

Cuando se utiliza IIS 6.x, el registro debe estar habilitado para que Sensor funcione correctamente. Si ha deshabilitado el registro para reducir la E/S de disco, puede habilitar el registro sin escribir datos en los registros. Para ello, habilite el registro y, a continuación, borre todos los campos de la ficha Avanzado de Propiedades para el formato de archivo de registro ampliado W3C. Si necesita ayuda, póngase en contacto con los servicios de consultoría de Adobe.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

## 1. Instale los archivos de programa {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

Al ejecutar Sensor en Windows IIS, los archivos de programa y el archivo de la cola de discos deben residir en el mismo directorio.

Por lo tanto, antes de instalar los archivos de programa, debe determinar dónde desea mantener la cola de disco, ya que también es allí donde debe instalar los archivos de programa.

Utilice el siguiente procedimiento para extraer e instalar los archivos de programa para Sensor.

1. En el equipo Windows, cree un directorio en el que instalar los archivos de programa Sensor. Tenga en cuenta que la cola de discos también reside en este directorio, por lo que asegúrese de que el dispositivo que elija tenga espacio suficiente para guardar una cola del tamaño que necesita.

   Por ejemplo: C:\VisualSensor

1. Extraiga el contenido del archivo de instalación en el directorio que acaba de crear. Durante este paso, Sensor instala los siguientes archivos:

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Archivo </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> EventMessages.dll </td>
   <td colname="col2"> Mensajes del visor de eventos. </td>
  </tr>
  <tr>
   <td colname="col1"> qlog.dll </td>
   <td colname="col2"> Módulo de recolector (filtro ISAPI). </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>Archivo de hoja de cálculo de Excel que los arquitectos pueden utilizar para configurar un experimento controlado. </p> <p>El sensor no utiliza este archivo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> Certificado utilizado para validar el certificado digital que presenta Insight Server durante el proceso de conexión. </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> El programa del transmisor. </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> El archivo de configuración del sensor. </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo denominado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El propio sensor no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que sus arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

## 2. Editar el archivo de configuración {#section-206daf855e664f16af9a96a5cd3e62b1}

El archivo txlogd.conf contiene los parámetros de configuración para Sensor.

Debe editar el archivo para especificar, entre otras cosas, el tamaño de la cola de disco, la dirección de Insight Server y el ID que se adjuntará a los datos producidos por este sensor. El archivo de configuración contiene los parámetros necesarios y los parámetros opcionales.

* **Parámetros necesarios** son ajustes que debe especificar al instalar Sensor. Sin estos ajustes, el sensor no se ejecuta correctamente.
* **Parámetros opcionales** son configuraciones que se establecen de forma predeterminada en valores predefinidos (que puede modificar) o habilitar funciones opcionales.

**Para editar el archivo de configuración del sensor**

1. Abra el `<SensorDirectory>/txlogd.conf` en un editor de texto y establezca los parámetros necesarios, así como los parámetros opcionales que desee.

   Para obtener descripciones de los parámetros txlogd.conf, consulte Parámetros del archivo Txlogd.conf del sensor.

   Para ver ejemplos de archivos de configuración completados, consulte Archivos de configuración de muestra de sensor.

1. Guarde y cierre el archivo.

## 3. Inicie el transmisor y cree la cola de disco {#section-a0af390ee1954109bcff5d9f09798683}

Después de configurar el archivo txlogd.conf, puede iniciar el programa del transmisor, registrarlo como un servicio de Windows y crear la cola de discos.

1. En el menú Inicio de Windows, seleccione Accesorios > Símbolo del sistema.
1. En la ventana del símbolo del sistema, vaya al directorio en el que instaló Sensor y ejecute el siguiente comando:

   ```
   txlog /regserver
   ```

   Este comando inicia el transmisor, crea la cola de discos y registra Sensor como un servicio de Windows.

1. Para confirmar que el transmisor se está ejecutando correctamente, haga clic en Inicio > Panel de control de Campaign > Herramientas administrativas > Servicios.

   >[!NOTE]
   >
   >Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En la lista de servicios, localice la entrada para Sensor y confirme que su estado es Started y que su tipo de inicio es Automatic.
   1. Cierre el panel de control de Servicios.

1. Para comprobar si el transmisor ha experimentado algún error durante el inicio, haga clic en Inicio > Panel de control de Campaign > Herramientas administrativas > Visor de eventos para abrir el Visor de eventos.

   >[!NOTE]
   >
   >Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo de la ventana Visor de eventos, seleccione el registro Aplicaciones .
   1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la columna Origen.
   1. Si encuentra un error de &quot;Adobe&quot;, haga doble clic en el error para mostrar la ventana Propiedades del evento. Esta ventana proporciona información detallada sobre el error.

1. Cuando termine de examinar el registro de aplicaciones, cierre el Visor de eventos.
1. Compruebe que el transmisor ha creado la cola de discos (Diskq2000.log) en el directorio donde instaló los archivos de programa Sensor y que es el tamaño especificado en el parámetro QueueSize del archivo txlogd.conf.

   Si la cola no se ha creado correctamente:

   1. Examine el archivo txtlogd.conf y verifique que el parámetro QueueSize esté configurado correctamente.
   1. Compruebe que el dispositivo en el que instaló el sensor tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Con el panel de control de Servicios en Windows, detenga el transmisor.
   1. Elimine el archivo de cola.
   1. Vuelva a registrar Sensor como un servicio de Windows: en el menú Inicio de Windows, seleccione Accesorios > Símbolo del sistema. En la ventana del símbolo del sistema, vaya al directorio en el que instaló Sensor y ejecute el siguiente comando:

      ```
      txlog /regserver
      ```

El transmisor está diseñado para funcionar continuamente. Si reinicia la máquina, el transmisor se reinicia automáticamente. Si necesita iniciar y detener el transmisor manualmente, puede hacerlo usando el panel de control de Servicios en Windows.

## Agregar el recopilador al servidor web {#section-682dc480e5574791ac18da104daf7906}

Para IIS, el recolector es un filtro ISAPI que se agrega al servidor web en IIS.

1. Abra el Administrador de IIS mediante Inicio > Herramientas administrativas > Administrador de Internet Information Services (IIS).
1. Expanda los nodos Equipo local y Sitios web .
1. Haga clic con el botón derecho en el sitio web al que desee agregar el selector y seleccione Propiedades.
1. Seleccione la ficha Filtros ISAPI y haga clic en Agregar.
1. En el campo Nombre del filtro , introduzca un nombre para mostrar para el filtro. El nombre de filtro sugerido es &quot;Sensor&quot;.
1. Haga clic en Examinar, seleccione el archivo qlog.dll (ubicado en el directorio donde instaló Sensor) y haga clic en Aceptar.
1. Haga clic en OK para añadir el filtro.

   Después de agregar el filtro, el recolector funciona inmediatamente y está listo para recopilar datos. Debe aparecer una flecha verde hacia arriba en la columna Estado de la ficha Filtros ISAPI del Administrador de IIS. Es posible que no vea la flecha verde hasta que el tráfico fluya por el filtro. En este caso, debe enviar una solicitud al servidor web para confirmar que el recolector funciona correctamente.

Si la flecha verde no aparece después de que el tráfico fluya al recolector, complete los siguientes pasos:

1. Haga clic en Inicio > Herramientas administrativas > Visor de eventos para comprobar si hay errores en el Visor de eventos.

   >[!NOTE]
   >
   >Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

1. En el panel izquierdo de la ventana Visor de eventos, seleccione el registro de aplicación.
1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la columna Origen.
1. Si encuentra un error, haga doble clic en el error para mostrar la ventana Propiedades del evento .

## Captura de datos adicionales {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

Las páginas web suelen estructurarse con un lenguaje de programación ASP (páginas de Active Server).

ASP es una tecnología de Microsoft que se ejecuta dentro de IIS. Cuando un explorador solicita un archivo ASP, IIS pasa la solicitud al motor ASP. El motor ASP lee el archivo ASP línea a línea y ejecuta las secuencias de comandos del archivo. Finalmente, el archivo ASP se devuelve al explorador como HTML sin formato. ASP proporciona objetos RESPOND o REQUEST que, además de otras aplicaciones, permiten la respuesta o solicitud de consultas de usuario o datos enviados desde formularios de HTML.

En algunos casos, es posible que no desee anexar los valores introducidos en los formularios a la dirección URL que se muestra en la barra de direcciones del explorador de un usuario o que se puede ver en el propio código del HTML. El script ASP simple del lado del servidor permite anexar al archivo de registro nombres de campo de formulario y sus valores respectivos sin ponerlos a disposición en el explorador del usuario ni insertarlos en el archivo HTML. Para capturar los valores de formulario reales introducidos en formularios concretos dentro del sitio web, se deben agregar algunas líneas de código para anexar los valores de formulario a la solicitud de registro.

En la página de procesamiento de un formulario, incluya el siguiente código para anexar los valores de formulario introducidos a los datos de solicitud (además de escribir los valores de formulario enviados en una base de datos externa u otra ubicación):

```
var sName= Request.Form("Name");
var sCity= Request.Form("City");
var sState= Request.Form("State");
var sZip= Request.Form("Zip");

Response.AppendToLog("&v_1=" +  sName);
Response.AppendToLog("&v_2=" +  sCity);
Response.AppendToLog("&v_3=" +  sState);
Response.AppendToLog("&v_4=" +  sZip);
```

Este proceso anexaría los valores del formulario tal como se definen a los datos de solicitud de la página Procesamiento de formularios . Dentro de los datos de registro, los valores añadidos estarían disponibles como cadenas de consulta en la página Procesamiento de formularios, como se ilustra a continuación. Por ejemplo, v_1, v_2, v_3 y v_4 ahora serían cadenas de consulta que contengan los datos introducidos en los campos de formulario correspondientes. La sintaxis descrita en el ejemplo anterior se puede duplicar para cualquier campo de formulario adicional y valor que desee capturar:

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si desea que todos los campos y valores del formulario se capturen y estén disponibles para su análisis, puede utilizar la siguiente sintaxis:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

En este ejemplo se tomarían todos los campos de formulario presentes en el HTML junto con sus valores respectivos y se adjuntarían como cadenas de consulta a la entrada de registro de la página Procesamiento de formularios . Tenga en cuenta que esto incluiría cualquier campo oculto presente en el formulario.

Los datos de registro se aumentarían como se detalla en la siguiente tabla:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado a la cadena de consulta NAME | v_1=John Smith |
| v_2 | Valor asociado con la cadena de consulta CITY | v_2=Los Ángeles |
| v_3 | Valor asociado con la cadena de consulta STATE | v_3=California |
| v_4 | Valor asociado con la cadena de consulta ZIP | v_4=90210 |
