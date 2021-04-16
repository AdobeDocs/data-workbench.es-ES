---
description: Sensor le permite adquirir datos de solicitud web (datos de evento o registro), así como datos de medición extendidos.
title: ¿Qué tipo de datos puedo adquirir?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# ¿Qué tipo de datos puedo adquirir?{#what-kind-of-data-can-i-acquire}

Sensor le permite adquirir datos de solicitud web (datos de evento o registro), así como datos de medición extendidos.

Los datos de medición extendidos no están disponibles para los servidores web como parte de su funcionamiento normal.

Se describen los siguientes temas:

## Datos de solicitud web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permite que los datos de solicitud web (datos de evento o registro) se adquieran y transporten automáticamente a una ubicación central para su almacenamiento y procesamiento para su análisis. A menos que elija filtrar específicamente ciertos tipos de solicitudes y no recopilar datos sobre esos tipos de solicitudes, [!DNL Sensor] captura datos sobre todas las solicitudes de GET realizadas de los servidores web en los que está instalada.

[!DNL Sensor] automatiza este proceso de adquisición de datos para todas las solicitudes de GET que se realizan en sus servidores y ofrece importantes ventajas comerciales y técnicas sobre los métodos alternativos de adquisición de datos de solicitudes de sitios web. Estas ventajas incluyen las siguientes:

* Las solicitudes que no son necesarias para análisis e informes se pueden filtrar antes de incurrir en costes de adquisición, transporte, almacenamiento y procesamiento.
* Los administradores del sitio no tienen que rotar los archivos de registro en lote, ya sea manualmente o mediante secuencia de comandos.
* [!DNL Sensor] agrega archivos de registro en una ubicación central para permitir un acceso fácil para el procesamiento.
* [!DNL Sensor] organiza y almacena los archivos de registro en un formato común que preserva los datos, lo que elimina la necesidad de preprocesarlos antes de que se puedan utilizar con fines de análisis e informes.
* Las instancias de ciertos tipos de contenido se pueden incluir en los archivos de registro, aunque la mayoría de las solicitudes de un determinado tipo de contenido se filtran automáticamente.
* [!DNL Sensor] comprime las entradas del archivo de registro, lo que requiere mucho menos espacio de almacenamiento, lo que reduce los costos y permite que los datos se mantengan disponibles para análisis durante períodos de tiempo más largos.
* [!DNL Sensor’s] las funciones tolerantes a errores permiten fallas en el sistema y la red, mientras se garantiza el envío de los datos de registro a un repositorio central.
* [!DNL Sensor] permite la implementación de experimentos controlados con contenido web, procesos y campañas de marketing.
* [!DNL Sensor] las marcas de tiempo registran entradas en unidades de 100 ns, lo que permite nuevos tipos de funcionalidad analítica.
* [!DNL Sensor] permite a los propietarios del sitio agregar datos (mediciones) a las entradas de registro después de la implementación inicial para su consideración en análisis e informes.

Para obtener más información sobre la adquisición de datos de medición extendidos, consulte [Adquisición de mediciones de línea de base](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Datos de medición extendidos {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] también admite el uso de etiquetas de página (o solicitudes de objetos incrustados) para adquirir datos de medición que no estén disponibles para los servidores web como parte de su operación normal. Las etiquetas de página se usan habitualmente para medir:

* Visualización de una página lógica en un sitio web dinámico.
* La visualización de contenido o anuncios en un sitio web controlado por terceros.
* La visualización de contenido servido desde una caché de navegador o CDN.
* Información detallada sobre el explorador de un visitante, incluidas medidas como el tiempo de carga de la página, la resolución de la pantalla, los campos de formulario que el visitante ha rellenado, etc.
* Otros datos que los navegadores no envían a sus servidores web.

[!DNL Sensor] recopila la información colocada en cualquier solicitud de GET realizada a un servidor web que se esté ejecutando  [!DNL Sensor]. Estas solicitudes pueden proceder de solicitudes de objetos incrustados de cualquier tipo, ya sea simplemente para medir que la solicitud fue realizada en un momento determinado por un navegador determinado o para pasar otros datos de medición al flujo de recopilación de datos para que se puedan procesar con fines de análisis e informes.

[!DNL Sensor] proporciona lo mejor de los mundos de adquisición de datos del lado del cliente y del lado del servidor: adquiere los datos de registro web del lado del servidor y recopila las mediciones del lado del cliente, del sitio de terceros o de eliminación de caché realizadas por solicitudes de objetos incrustados. En otras palabras, [!DNL Sensor] adquiere los datos de solicitud normalmente conocidos por sus servidores web (mediciones del lado del servidor) y cualquier dato de medición adicional que recopile mediante el uso de etiquetas de página (mediciones del lado del cliente) que envían sus datos a cualquier servidor web que ejecute [!DNL Sensor]. Estos servidores web pueden estar dedicados a recopilar mediciones del lado del cliente, pero no es necesario.

Para obtener más información sobre la adquisición de datos de medición extendidos, consulte [Adquisición de mediciones extendidas](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
