---
description: 'El sensor consta de tres componentes principales: Recopilador de datos, Cola de discos y Transmisor de datos.'
title: ¿Cuáles son los componentes básicos?
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
exl-id: aee6a601-590a-43e0-aeeb-42a4522e55c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# ¿Cuáles son los componentes básicos?{#what-are-basic-components}

{{eol}}

El sensor consta de tres componentes principales: Recopilador de datos, cola de disco y transmisor de datos.

![](assets/Visual-Sensor.png)

## Recopilador de datos {#section-f970eaff30364a3c8106d5ec9c1b5caa}

El recopilador de datos (recopilador) es un módulo NSAPI, ISAPI, servlet de filtro J2EE o Apache que se ejecuta dentro del proceso del servidor web.

Captura los datos de evento sin procesar de cada solicitud HTTP que el servidor web procesa y deposita esa información en la cola de discos. Si ejecuta varias instancias de un servidor web en el mismo equipo, cada instancia carga su propia instancia del módulo de recopilación; sin embargo, todas las instancias del recolector escriben sus datos de evento en la misma cola de disco.

## Cola de discos {#section-41aac77ab30e48478d1b31eac288df05}

La cola de discos (cola) es un archivo de cola con memoria asignada FIFO (primero en, primero en salir) y tolerante a errores que almacena en búfer los datos de eventos sin procesar que recopila Sensor, lo que proporciona almacenamiento temporal para los datos de eventos recopilados en el servidor web donde está instalado.

Para evitar que la cola se expanda sin restricciones (y consuma todo el espacio disponible en disco), la cola se mantiene en un archivo de tamaño fijo, lo que significa que solo contiene tantos datos de evento como se le ha dado capacidad de retención. El tamaño del archivo de cola se configura en el parámetro QueueSize del archivo de configuración Sensor, txlogd.conf, cuando se instala el Sensor. Para obtener información sobre los parámetros txlogd.conf, vea Parámetros del archivo Txlogd.conf del sensor.

Una vez establecido, la longitud física del archivo no aumenta ni disminuye. El recolector simplemente deposita nuevos datos de evento en la cola y el transmisor extrae eventos de él. Si el recolector llega al final del archivo, deja de escribir en el archivo de cola.

Generalmente, el transmisor extrae eventos de la cola tan rápido como los deposita el recolector. Sin embargo, si la conexión entre el transmisor y Insight Server es lenta o no está disponible, la cola puede llenarse de eventos no transmitidos. En este caso, el recolector deja de recopilar datos hasta que el transmisor traza la cola. La información sobre las solicitudes que procesa el servidor web durante este tiempo se pierde de forma permanente.

**Determinación del tamaño de la cola**

Antes de instalar Sensor, debe determinar el tamaño de la cola. Para evitar la pérdida permanente de datos, es importante crear una cola lo suficientemente grande como para dar cabida al número de eventos que podrían acumularse durante la interrupción más larga probable de la conexión con el servidor de Insight (es decir, suficiente almacenamiento para varios días de actividad máxima). La cola debe estar configurada para contener suficientes datos de evento de modo que los administradores del sistema tengan tiempo de restaurar la accesibilidad de red al servidor de Insight de destino, o de reparar o reemplazar el servidor de Insight sin perder ningún dato. Si el sensor ha fallado y no hay un archivo de cola válido y accesible disponible para albergar los datos del evento, se perderán los datos siguientes.

>[!NOTE]
>
>Es importante que los administradores de cada equipo en el que se ejecuta Sensor entiendan la naturaleza única del archivo de cola local para asegurarse de que no lo tratan como un archivo de registro normal que se puede eliminar, archivar o comprimir.

Adobe recomienda que la cola esté configurada para contener al menos diez (10) días pico de datos de eventos que produce el servidor donde está instalado el sensor. Es decir, tome la cantidad de datos de eventos de cualquier día pico en el último año y multiplíquelo por diez.

Esta recomendación supone lo siguiente:

* El equipo de tecnología de la información de su empresa está monitorizando cada sensor de la manera detallada en la Administración del sensor de esta guía y lo está haciendo al menos una vez al día. Si no es así, este plazo debería prorrogarse adecuadamente.
* El equipo de tecnología de la información de su empresa puede restaurar la accesibilidad de la red, reemplazar o reparar cualquier servidor de Insight instalado en un plazo de 72 horas. Si no es así, este plazo debería prorrogarse adecuadamente.
* La configuración del sensor sigue siendo la misma.
* Ningún evento externo (por ejemplo, una campaña de marketing de gran tamaño) hará que la cantidad de datos de evento que generan los servidores web aumente significativamente.

La elección del tamaño de la cola depende en gran medida del nivel deseado de supervisión del sistema, en función de las prácticas y políticas de su empresa con respecto a los tiempos de respuesta y la administración del sistema de fin de semana/vacaciones. Como los tamaños de cola más grandes son mejores, Adobe recomienda que su empresa haga la cola lo más grande posible.

>[!NOTE]
>
>Los tamaños de archivo de cola más grandes no afectan al rendimiento.

Para obtener más recomendaciones sobre cómo cambiar el tamaño de la cola, póngase en contacto con los servicios de consultoría de Adobe.

## Transmisor de datos {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

El transmisor es un proceso independiente (por ejemplo, un demonio en un equipo basado en UNIX o un servicio en un equipo Windows) que se ejecuta en el mismo equipo que el servidor web.

El transmisor lee los datos de evento de la cola de discos, los comprime y los envía por HTTP/S al servidor de Insight especificado, donde se procesa y almacena en **.vsl** archivos.
