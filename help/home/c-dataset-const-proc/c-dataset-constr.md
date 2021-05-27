---
description: Un conjunto de datos de Adobe contiene los datos que el servidor de Data Workbench ha cargado y procesado.
title: Explicación de la construcción de conjuntos de datos
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Explicación de la construcción de conjuntos de datos{#understanding-dataset-construction}

Un conjunto de datos de Adobe contiene los datos que el servidor de Data Workbench ha cargado y procesado.

Los pasos involucrados en la carga y el procesamiento de los datos por el servidor de Data Workbench (InsightServer64.exe) conforman el proceso de construcción del conjunto de datos.

>[!NOTE]
>
>Un servidor de Data Workbench que procesa y sirve datos de un conjunto de datos de Adobe se denomina unidad de procesamiento de datos o DPU. A veces se denomina servidor de procesamiento o servidor de consultas. Los clientes de Data Workbench y [!DNL Report] interactúan directamente con las DPU.

Durante la construcción del conjunto de datos, el servidor de Data Workbench lee los datos de origen de los orígenes de registro, aplica transformaciones a campos de datos específicos y define las dimensiones ampliadas que se crearán a partir de los campos transformados. El proceso de construcción se produce en dos fases: *Procesamiento de registros* y *Transformación*. Una vez construido el conjunto de datos, puede utilizar las dimensiones ampliadas del conjunto de datos para crear métricas y dimensiones derivadas para sus fines de análisis específicos.

La construcción de conjuntos de datos es como un proceso de fabricación. Se seleccionan los datos (las materias primas) que se utilizarán para crear el conjunto de datos y se definen las transformaciones de datos (los pasos del proceso) que manipulan la información disponible en los datos para crear dimensiones ampliadas (los productos fabricados).

<!--
c_log_proc.xml
-->

Los registros se filtran y se identifican los campos de datos que se pasarán a la fase de transformación. Al final de la fase de procesamiento del registro, los datos se agrupan por ID de seguimiento (es decir, todas las entradas de registro con el mismo ID de seguimiento se agrupan) y se ordenan a tiempo. Durante la fase de procesamiento del registro, no se puede acceder a los datos procesados que se van a utilizar para el análisis.

## Especificación de fuentes de registro {#section-75279dd6a7304d469735562796741d0f}

Los orígenes de registro son archivos que contienen los datos que se utilizarán para crear un conjunto de datos. Los datos disponibles en las fuentes de registro se denominan datos de evento porque cada registro de datos representa un registro de transacción o una instancia única de un evento. Además, cada registro o entrada de registro contiene un valor denominado ID de seguimiento.

>[!NOTE]
>
>Al seleccionar las fuentes de registro, asegúrese de que cada entrada de registro contiene un ID de seguimiento para la entidad que debe representar el nivel más alto en el que se deben agrupar los datos. Por ejemplo, si está trabajando con datos recopilados del tráfico del sitio web, es probable que elija visitante para que sea esta entidad. Cada visitante tiene un ID de seguimiento único y todos los datos sobre un visitante del sitio en particular se pueden agrupar. Para obtener ayuda, póngase en contacto con el Adobe.

Insight Server recopila en tiempo real los datos de evento de las fuentes de registro [!DNL Sensors] o extrae de las fuentes de datos archivadas. Los datos de evento recopilados por los sensores de HTTP y los servidores de aplicaciones se transmiten a los servidores de Insight, que convierten los datos en archivos de registro ( [!DNL .vsl]) altamente comprimidos. Insight Server lee los datos de evento que residen en un archivo plano, un archivo XML o un origen de datos ODBC y proporciona descodificadores que se definen para extraer un conjunto común de campos de registro de estos diferentes formatos.

## Definición de transformaciones {#section-55a8cdb47379484081e53087f074778d}

Una transformación es un conjunto de instrucciones que puede definir para extraer o manipular información en los datos de evento. Cada transformación que defina se aplicará a cada registro de datos de evento (entrada de registro) para actualizar los campos de registro existentes o producir nuevos campos. Los resultados de las transformaciones se utilizan junto con las condiciones de entrada de registro para evaluar qué entradas de registro se filtran fuera del conjunto de datos durante el procesamiento del registro.

No todos los tipos de transformaciones se pueden utilizar durante la fase de procesamiento de registros del proceso de construcción del conjunto de datos.

## Filtrado de registros {#section-6172ca0fb0eb4177925151bb49fdbc02}

El conjunto de datos contiene varios parámetros utilizados para filtrar los datos que salen de las transformaciones. El filtrado se utiliza para especificar qué entradas de registro se utilizan en los pasos de procesamiento siguientes. Por ejemplo, los filtros pueden definirse por, intervalo de tiempo, el estado de la respuesta del servidor o la dirección IP y la información de usuario-agente. El [!DNL Log Entry Condition] es una prueba de filtrado personalizable. La prueba busca ciertas condiciones en los campos de cada entrada de registro para determinar si la entrada debe continuar en el proceso de construcción del conjunto de datos. Si una entrada de registro no cumple la condición, la entrada se elimina del proceso de construcción.

## Identificación de campos para transformación {#section-eef98ca723e54547b887aefdf0514c47}

Si se va a pasar un campo de datos de la fase de procesamiento de registros a la fase de transformación para un procesamiento posterior, debe identificarlo durante el procesamiento del registro. Este requisito se aplica independientemente de si el campo está disponible desde las fuentes de registro o se crea a partir de transformaciones de datos aplicadas a los datos durante el procesamiento del registro.

<!--
c_transformation.xml
-->

Durante la fase de transformación de la construcción del conjunto de datos, el procesamiento se produce en los datos agrupados y ordenados que se generan a partir del procesamiento del registro. Se realizan transformaciones de datos adicionales y se crean dimensiones de datos ampliadas para su uso en los análisis. Durante la fase de transformación, puede acceder a una muestra estadística de los datos que se hace más grande a medida que la fase de transformación se acerca a completarse.

## Definición de transformaciones {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Puede definir transformaciones que se utilizarán durante la fase de transformación del proceso de construcción del conjunto de datos para facilitar la creación de las dimensiones ampliadas. Cada transformación se aplica a cada registro de datos de evento (entrada de registro) pasado desde el procesamiento de registros.

## Filtrado de registros {#section-3fed0a00ca344a719b5e8db363f64f06}

El [!DNL Log Entry Condition] se puede aplicar durante la transformación para buscar condiciones específicas en los campos de cada entrada de registro proveniente del procesamiento de registros. Si una entrada de registro no cumple la condición, la entrada se elimina del proceso de construcción.

## Definición de dimensiones extendidas {#section-25efafd0bfc84c86b9717d453a88c91b}

Las dimensiones extendidas son los productos finales del proceso de construcción del conjunto de datos. Representan relaciones entre los campos de registro de los datos. Los utiliza para crear visualizaciones, crear métricas extendidas o realizar análisis para comprender las operaciones y los problemas específicos de su negocio.
