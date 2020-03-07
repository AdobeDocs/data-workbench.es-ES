---
description: Un conjunto de datos de Adobe contiene los datos que el servidor del área de trabajo de datos ha cargado y procesado.
solution: Analytics
title: Explicación de la construcción de conjuntos de datos
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de la construcción de conjuntos de datos{#understanding-dataset-construction}

Un conjunto de datos de Adobe contiene los datos que el servidor del área de trabajo de datos ha cargado y procesado.

Los pasos involucrados en la carga y el procesamiento de los datos por parte del servidor del área de trabajo de datos (InsightServer64.exe) conforman el proceso de construcción del conjunto de datos.

>[!NOTE]
>
>Un servidor del área de trabajo de datos que procesa y sirve datos de un conjunto de datos de Adobe se denomina unidad de procesamiento de datos o DPU. A veces se denomina servidor de procesamiento o servidor de consultas. El área de trabajo de datos y [!DNL Report] los clientes interactúan directamente con las DPU.

Durante la construcción de conjuntos de datos, el servidor del área de trabajo de datos lee datos de origen de orígenes de registro, aplica transformaciones a campos de datos específicos y define dimensiones ampliadas que se crearán a partir de los campos transformados. El proceso de construcción se desarrolla en dos fases: Procesamiento *y* transformación *del registro*. Una vez construido el conjunto de datos, puede utilizar las dimensiones ampliadas del conjunto de datos para crear métricas y dimensiones derivadas para sus fines de análisis específicos.

La construcción de conjuntos de datos es como un proceso de fabricación. Se seleccionan los datos (las materias primas) que se utilizarán para generar el conjunto de datos y se definen las transformaciones de datos (los pasos del proceso) que manipulan la información disponible en los datos para crear dimensiones extendidas (los productos fabricados).

<!--
c_log_proc.xml
-->

Los registros se filtran y se identifican los campos de datos que se pasarán a la fase de transformación. Al final de la fase de procesamiento del registro, los datos se agrupan por ID de seguimiento (es decir, todas las entradas de registro con el mismo ID de seguimiento se agrupan) y se ordenan a tiempo. Durante la fase de procesamiento del registro, no se puede acceder a los datos procesados para utilizarlos en el análisis.

## Especificación de fuentes de registro {#section-75279dd6a7304d469735562796741d0f}

Los orígenes de registro son archivos que contienen los datos que se utilizarán para generar un conjunto de datos. Los datos disponibles en las fuentes de registro se denominan datos de eventos porque cada registro de datos representa un registro de transacciones o una sola instancia de un evento. Además, cada registro, o entrada de registro, contiene un valor denominado ID de seguimiento.

>[!NOTE]
>
>Al seleccionar orígenes de registro, asegúrese de que cada entrada de registro contiene un ID de seguimiento para la entidad que representa el nivel más alto en el que se van a agrupar los datos. Por ejemplo: si está trabajando con datos recopilados a partir del tráfico del sitio web, es probable que elija visitante para que sea esta entidad. Cada visitante tiene una ID de seguimiento única y todos los datos sobre un visitante del sitio en particular se pueden agrupar. Para obtener ayuda, póngase en contacto con Adobe.

Insight Server recopila datos de eventos de fuentes de registro en tiempo real por fuentes de datos archivadas [!DNL Sensors] o extraídos de ellas. Los datos de eventos recopilados por los sensores desde HTTP y los servidores de aplicaciones se transmiten a los servidores de Insight, que convierten los datos en archivos de registro ( [!DNL .vsl]) muy comprimidos. Insight Server lee los datos de eventos que residen en un archivo sin formato, un archivo XML o un origen de datos ODBC y proporciona descodificadores que se definen para extraer un conjunto común de campos de registro de estos diferentes formatos.

## Definición de transformaciones {#section-55a8cdb47379484081e53087f074778d}

Una transformación es un conjunto de instrucciones que puede definir para extraer o manipular información en los datos del evento. Cada transformación que defina se aplicará a cada registro de datos del evento (entrada de registro) para actualizar los campos de registro existentes o generar nuevos campos. Los resultados de las transformaciones se utilizan junto con las condiciones de entrada de registro para evaluar qué entradas de registro se filtran fuera del conjunto de datos durante el procesamiento del registro.

No todos los tipos de transformaciones se pueden utilizar durante la fase de procesamiento del registro del proceso de construcción del conjunto de datos.

## Filtrado de registros {#section-6172ca0fb0eb4177925151bb49fdbc02}

El conjunto de datos contiene varios parámetros utilizados para filtrar los datos que salen de las transformaciones. El filtrado se utiliza para especificar qué entradas de registro se utilizan en los pasos de procesamiento posteriores. Por ejemplo, los filtros se pueden definir por, intervalo de tiempo, el estado de la respuesta del servidor o la dirección IP y la información de usuario-agente. La [!DNL Log Entry Condition] es una prueba de filtrado personalizable. La prueba busca ciertas condiciones en los campos de cada entrada de registro para determinar si esa entrada debe continuar en el proceso de construcción del conjunto de datos. Si una entrada de registro no cumple la condición, la entrada se elimina del proceso de construcción.

## Identificación de campos para la transformación {#section-eef98ca723e54547b887aefdf0514c47}

Si se va a pasar un campo de datos desde la fase de procesamiento del registro a la fase de transformación para un procesamiento posterior, debe identificarlo durante el procesamiento del registro. Este requisito se aplica independientemente de si el campo está disponible desde los orígenes de registro o se ha creado a partir de transformaciones de datos aplicadas a los datos durante el procesamiento del registro.

<!--
c_transformation.xml
-->

Durante la fase de transformación de la construcción de conjuntos de datos, el procesamiento se produce en los datos agrupados y ordenados que se generan a partir del procesamiento de registros. Se realizan transformaciones de datos adicionales y se crean dimensiones de datos ampliadas para su uso en los análisis. Durante la fase de transformación, puede acceder a una muestra estadística de los datos que se amplía a medida que se acerca la finalización de la fase de transformación.

## Definición de transformaciones {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Puede definir las transformaciones que se utilizarán durante la fase de transformación del proceso de construcción del conjunto de datos para facilitar la creación de las dimensiones ampliadas. Cada transformación se aplica a cada registro de datos del evento (entrada de registro) pasado desde el procesamiento del registro.

## Filtrado de registros {#section-3fed0a00ca344a719b5e8db363f64f06}

El [!DNL Log Entry Condition] se puede aplicar durante la transformación para buscar condiciones específicas en los campos de cada entrada de registro que provenga del procesamiento del registro. Si una entrada de registro no cumple la condición, la entrada se elimina del proceso de construcción.

## Definición de dimensiones extendidas {#section-25efafd0bfc84c86b9717d453a88c91b}

Las dimensiones extendidas son los productos finales del proceso de construcción del conjunto de datos. Representan relaciones entre los campos de registro de los datos. Las utiliza para crear visualizaciones, generar métricas ampliadas o realizar análisis para comprender las operaciones y los problemas específicos de su negocio.
