---
description: Sensor le permite adquirir datos de solicitud web (datos de evento o registro), así como datos de medición extendidos.
solution: Analytics
title: ¿Qué tipo de datos puedo adquirir?
topic: Data workbench
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ¿Qué tipo de datos puedo adquirir?{#what-kind-of-data-can-i-acquire}

Sensor le permite adquirir datos de solicitud web (datos de evento o registro), así como datos de medición extendidos.

Los datos de medición extendidos no están disponibles para los servidores web como parte de su funcionamiento normal.

Se describen los siguientes temas:

## Datos de solicitud Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permite adquirir y transportar automáticamente datos de solicitud Web (datos de registro o evento) a una ubicación central para almacenamiento y procesamiento para análisis. A menos que elija filtrar específicamente determinados tipos de solicitudes y no recopile datos sobre esos tipos de solicitudes, [!DNL Sensor] captura datos sobre todas las solicitudes GET realizadas de los servidores Web en los que está instalado.

[!DNL Sensor] automatiza este proceso de adquisición de datos para todas las solicitudes GET que se realizan en los servidores y ofrece importantes ventajas comerciales y técnicas en comparación con los métodos alternativos de adquisición de datos de solicitud de sitio web. Estos beneficios incluyen:

* Las solicitudes que no sean necesarias para el análisis y la generación de informes se pueden filtrar antes de incurrir en gastos de adquisición, transporte, almacenamiento y procesamiento.
* Los administradores del sitio no tienen que rotar los archivos de registro por lotes, ya sea manualmente o mediante secuencia de comandos.
* [!DNL Sensor] agrega archivos de registro en una ubicación central para facilitar el acceso al procesamiento.
* [!DNL Sensor] organiza y almacena los archivos de registro en un formato común de conservación de datos, lo que elimina la necesidad de preprocesarlos antes de que se puedan utilizar con fines de análisis e informes.
* Las instancias de ciertos tipos de contenido se pueden incluir en los archivos de registro aunque la mayoría de las solicitudes de un determinado tipo de contenido se filtren automáticamente.
* [!DNL Sensor] comprime entradas de archivos de registro, lo que requiere mucho menos espacio de almacenamiento, lo que reduce los costos y permite que los datos se mantengan disponibles para análisis durante períodos de tiempo más largos.
* [!DNL Sensor’s] las características tolerantes a errores permiten fallas en el sistema y en la red, al tiempo que garantizan la entrega de los datos de registro a un repositorio central.
* [!DNL Sensor] permite la implementación de experimentos controlados con contenido web, procesos y campañas de marketing.
* [!DNL Sensor] las entradas de registro de marcas de hora en unidades de 100 ns, lo que permite nuevos tipos de funcionalidad analítica.
* [!DNL Sensor] permite a los propietarios del sitio agregar datos (mediciones) a las entradas de registro después de la implementación inicial para su consideración en análisis e informes.

Para obtener más información sobre la adquisición de datos de medición extendidos, consulte [Adquisición de mediciones](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe)de línea base.

## Datos de medición extendidos {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] también admite el uso de etiquetas de página (o solicitudes de objetos incrustados) para adquirir datos de medición que no están disponibles para los servidores web como parte de su operación normal. Las etiquetas de página se utilizan habitualmente para medir:

* Visualización de una página lógica en un sitio web dinámico.
* Visualización de contenido o anuncios en un sitio web controlado por terceros.
* Visualización del contenido que se proporciona desde una caché del explorador o CDN.
* Información detallada sobre el explorador de un visitante, que incluye medidas como el tiempo de carga de la página, la resolución de la pantalla, los campos de formulario que el visitante ha rellenado, etc.
* Otros datos que los navegadores no envían a sus servidores Web.

[!DNL Sensor] recopila cualquier información colocada en cualquier solicitud GET realizada a un servidor Web que se esté ejecutando [!DNL Sensor]. Estas solicitudes pueden proceder de solicitudes de objetos incrustados de cualquier tipo, ya sea para simplemente medir que la solicitud fue realizada en un momento determinado por un determinado explorador o para pasar otros datos de medición al flujo de recopilación de datos a fin de que puedan procesarse con fines de análisis e informes.

[!DNL Sensor] proporciona lo mejor de los mundos de adquisición de datos del lado del cliente y del servidor: adquiere los datos del registro web del lado del servidor y recopila las medidas del lado del cliente, del sitio de terceros o de eliminación de caché tomadas por las solicitudes de objetos incrustados. En otras palabras, [!DNL Sensor] adquiere los datos de solicitud que normalmente conocen los servidores web (mediciones del lado del servidor) y cualquier dato de medición adicional que recopile mediante el uso de etiquetas de página (mediciones del lado del cliente) que envían sus datos a cualquier servidor web que se ejecute [!DNL Sensor]. Estos servidores web pueden dedicarse a recopilar mediciones del lado del cliente, pero no es necesario.

Para obtener más información sobre la adquisición de datos de medición extendidos, consulte [Adquisición de mediciones](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944)extendidas.
