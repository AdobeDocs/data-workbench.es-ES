---
description: Instale y configure Sensor para Microsoft IIS 7.x u 8.x que se ejecute en Microsoft Windows Server 2008 o posterior.
title: Microsoft IIS en Windows Server 2008 o posterior
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
exl-id: cc909daa-60c0-4188-8e90-035c41bf3105
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 1%

---

# Microsoft IIS en Windows Server 2008 o posterior{#microsoft-iis-on-windows-server-or-later}

Instale y configure Sensor para Microsoft IIS 7.x u 8.x que se ejecute en Microsoft Windows Server 2008 o posterior.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

1. [Instalación de los archivos de programa](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [Edición del archivo de configuración del sensor](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [Inicie el transmisor y cree la cola de discos](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [Añadir el selector al servidor web](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [Capturar datos adicionales](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## Instalación de los archivos de programa {#section-cb51e5932a6d40c5b00758a7a51b7578}

Al ejecutar Sensor en Windows IIS, los archivos de programa y el archivo de la cola de discos deben residir en el mismo directorio.

Antes de instalar los archivos de programa, determine primero dónde desea mantener la cola de disco porque es allí donde debe instalar los archivos de programa.

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

## Edición del archivo de configuración del sensor {#section-1e1590a92222430e92066292512ae0df}

El archivo txlogd.conf contiene los parámetros de configuración para Sensor.

Debe editar el archivo para especificar, entre otras cosas, el tamaño de la cola de disco, la dirección de Insight Server y el ID que se adjuntará a los datos producidos por este sensor. El archivo de configuración contiene los parámetros necesarios y los parámetros opcionales.

* **Los** parámetros requeridos son configuraciones que debe especificar al instalar Sensor. Sin estos ajustes, el sensor no se ejecuta correctamente.
* **Los** parámetros opcionales son configuraciones que se establecen de forma predeterminada en valores predefinidos (que puede modificar) o que habilitan funciones opcionales.

**Para editar el archivo de configuración del sensor**

1. Abra el archivo `<SensorDirectory>/txlogd.conf` en un editor de texto y establezca los parámetros necesarios, así como los parámetros opcionales que desee.

   Para obtener descripciones de los parámetros [!DNL txlogd.conf], consulte [Parámetros de archivo Txlogd.conf del sensor](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed).

1. Guarde y cierre el archivo.

## Inicie el transmisor y cree la cola de discos {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

Después de configurar el archivo [!DNL txlogd.conf]puede iniciar el programa del transmisor, registrarlo como un servicio de Windows y crear la cola de discos.

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
1. Compruebe que el transmisor ha creado la cola de discos (Diskq2008.log) en el directorio donde instaló los archivos de programa Sensor y que es el tamaño especificado en el parámetro QueueSize del archivo txlogd.conf.

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

## Añadir el selector al servidor web {#section-088960c986cf449cb712152298b3518d}

Para IIS, el recolector es un filtro ISAPI que se agrega al servidor web en IIS.

1. Abra el Administrador de IIS mediante **Inicio > Herramientas administrativas > Administrador de Internet Information Services (IIS)**.
1. Expanda los nodos **Equipo local** y **Sitios**.
1. Seleccione el sitio web y, en el panel derecho, haga doble clic en **Filtros ISAPI**.
1. En el panel **Acciones**, haga clic en **Agregar**.

1. En el campo **Filter Name**, introduzca un nombre para mostrar para el filtro. El nombre de filtro sugerido es &quot;Sensor&quot;.
1. Haga clic en **Browse**, seleccione el archivo qlog.dll (ubicado en el directorio donde instaló Sensor) y haga clic en **OK**.

1. Haga clic en **OK** para agregar el filtro.

   Después de agregar el filtro, el recolector funciona inmediatamente y está listo para recopilar datos.

Si la flecha verde no aparece después de que el tráfico fluya al recolector, complete los siguientes pasos:

1. Haga clic en Inicio > Herramientas administrativas > Visor de eventos para comprobar si hay errores en el Visor de eventos.

   >[!NOTE]
   >
   >Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

1. En el panel izquierdo de la ventana Visor de eventos, seleccione el registro **Application**.
1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la columna **Origen**.
1. Si encuentra un error, haga doble clic en el error para mostrar la ventana **Propiedades del evento**.

## Capturar datos adicionales {#section-98db9625efdc4b60bfd76f7adf4af74d}

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

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->
