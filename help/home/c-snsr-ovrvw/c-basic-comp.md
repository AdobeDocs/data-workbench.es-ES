---
description: 'El sensor consta de tres componentes principales: Recopilador de datos, Cola de discos y Transmisor de datos.'
title: ¿Qué son los componentes básicos?
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ¿Qué son los componentes básicos?{#what-are-basic-components}

El sensor consta de tres componentes principales: Recopilador de datos, Cola de discos y Transmisor de datos.

![](assets/Visual-Sensor.png)

## Recopilador de datos {#section-f970eaff30364a3c8106d5ec9c1b5caa}

El recopilador de datos (recopilador) es un servlet de filtro NSAPI, ISAPI, J2EE o Apache que se ejecuta dentro del proceso del servidor Web.

Captura los datos de eventos sin procesar de cada solicitud HTTP que el servidor web procesa y deposita esa información en la cola de discos. Si ejecuta varias instancias de un servidor web en el mismo equipo, cada instancia carga su propia instancia del módulo de recopilación; sin embargo, todas las instancias del recopilador escriben sus datos de eventos en la misma cola de discos.

## Cola de discos {#section-41aac77ab30e48478d1b31eac288df05}

La cola de discos (cola) es un archivo de cola con memoria asignada FIFO (primero de entrada, primero de salida) y tolerante a errores que almacena en búfer los datos de eventos sin procesar que Sensor recopila, lo que proporciona almacenamiento temporal para los datos de eventos recopilados en el servidor web donde se instalan.

Para evitar que la cola se expanda sin restricciones (y, por lo tanto, consume todo el espacio disponible en disco), la cola se mantiene en un archivo de tamaño fijo, lo que significa que sólo contiene tantos datos de eventos como se le ha dado la capacidad de retener. El tamaño del archivo de cola se configura en el parámetro QueueSize del archivo de configuración Sensor, txlogd.conf, cuando se instala el Sensor. Para obtener información sobre los parámetros txlogd.conf, consulte Parámetros del archivo Sensor Txlogd.conf.

Una vez establecido, la longitud física del archivo no aumenta ni disminuye. El recolector simplemente deposita nuevos datos de eventos en la cola y el transmisor extrae eventos de ellos. Si el selector llega al final del archivo, deja de escribir en el archivo de cola.

Generalmente, el transmisor extrae eventos de la cola tan rápido como los deposita el receptor. Sin embargo, si la conexión entre el transmisor y Insight Server es lenta o no está disponible, la cola puede llenarse de eventos no transmitidos. En este caso, el recopilador deja de recopilar datos hasta que el transmisor desciende la cola. La información sobre las solicitudes que el servidor web procesa durante este tiempo se pierde de forma permanente.

**Determinación del tamaño de la cola**

Antes de instalar Sensor, debe determinar el tamaño que debe tener la cola. Para evitar la pérdida permanente de datos, es importante crear una cola lo suficientemente grande como para dar cabida al número de eventos que podrían acumularse durante la interrupción más prolongada probable de la conexión con el servidor de Insight (es decir, almacenamiento suficiente para varios días de actividad máxima). La cola debe configurarse para que contenga suficientes datos de eventos para que los administradores del sistema tengan tiempo de restaurar la accesibilidad de la red al servidor de Insight de destino, o de reparar o reemplazar el servidor de Insight sin perder ningún dato. Si el sensor ha fallado y no hay un archivo de cola válido y accesible disponible para contener los datos del evento, se perderán los datos posteriores.

>[!NOTE]
>
>Es importante que los administradores de cada equipo en el que se ejecuta Sensor entiendan la naturaleza única del archivo de cola local para asegurarse de que no lo tratan como un archivo de registro ordinario que puede eliminarse, archivarse o comprimirse.

Adobe recomienda configurar la cola para que contenga al menos diez (10) días pico de datos de eventos producidos por el servidor en el que está instalado el sensor. Es decir, tome la cantidad de datos de eventos de cualquier día récord del año pasado y multiplíquelo por diez.

Esta recomendación supone lo siguiente:

* El equipo de tecnología de la información de su empresa está supervisando cada sensor de la manera detallada en la sección de administración de sensores de esta guía y lo está haciendo al menos una vez al día. De no ser así, este plazo debería ampliarse adecuadamente.
* El equipo de tecnología de la información de su empresa puede restaurar la accesibilidad de la red o reemplazar o reparar los servidores Insight instalados en un plazo de 72 horas. De no ser así, este plazo debería ampliarse adecuadamente.
* La configuración del sensor sigue siendo la misma.
* Ningún evento externo (por ejemplo, una campaña de mercadotecnia de gran tamaño) hará que la cantidad de datos de eventos que generan los servidores Web aumente significativamente.

La elección del tamaño de la cola depende en gran medida del nivel deseado de supervisión del sistema, a la luz de las prácticas y políticas de su empresa en cuanto a los tiempos de respuesta y la administración del sistema de fin de semana y festivos. A medida que los tamaños de cola sean mayores, Adobe recomienda que su empresa haga que la cola sea lo más grande posible.

>[!NOTE]
>
>Los tamaños de archivo de cola más grandes no afectan al rendimiento.

Para obtener más recomendaciones sobre el tamaño de la cola, póngase en contacto con los servicios de consultoría de Adobe.

## Transmisor de datos {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

El transmisor es un proceso independiente (por ejemplo, un demonio en un equipo basado en UNIX o un servicio en un equipo Windows) que se ejecuta en el mismo equipo que el servidor Web.

El transmisor lee los datos de eventos de la cola de discos, los comprime y los envía mediante HTTP/S al servidor de Insight que ha especificado, donde se procesa y almacena en archivos **.vsl** .
