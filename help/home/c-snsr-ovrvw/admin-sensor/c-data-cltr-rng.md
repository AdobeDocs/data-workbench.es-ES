---
description: Compruebe si el recolector se está ejecutando con métodos diferentes.
title: Confirmación de la ejecución del recopilador de datos
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Confirmación de la ejecución del recopilador de datos{#confirming-that-the-data-collector-is-running}

Compruebe si el recolector se está ejecutando con métodos diferentes.

**Frecuencia recomendada:** cada 5-10 minutos

* [Utilice la funcionalidad de prueba del sitio en el transmisor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Compruebe si [!DNL Sensor] está configurando una cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Uso de la prueba del sitio {#section-a5a697c3252e40f184c0b662926170f2}

Una forma de verificar que el recolector se está ejecutando es habilitar la función de prueba del sitio en el transmisor. Cuando habilita la Prueba del sitio, el transmisor envía periódicamente (cada 60 segundos) una solicitud de GET al servidor web en el que se ejecuta el recopilador. Si la prueba del sitio no obtiene una respuesta del servidor web, escribe un mensaje de error en syslog y envía un mensaje de error a [!DNL data workbench server] (que se escribe en el archivo de registro del sensor).

Si la prueba del sitio recibe una respuesta del servidor web, busca en el archivo de cola un paquete del servidor web. Si el paquete no aparece (indicando que el recolector no se estaba ejecutando para capturar el evento), Site Test escribe un mensaje de error en syslog y envía un mensaje de error al Adobe (que también se escribe en el archivo de registro de sensor).

En las solicitudes que envía la prueba del sitio al servidor web, esta establece el valor de Agente-Usuario en &quot;Prueba[!DNL Sensor]&quot;. Si no desea que estas solicitudes aparezcan en su conjunto de datos, agregue el User-Agent &quot;[!DNL Sensor] Test&quot; al archivo [!DNL Baseline Robots List.txt] o al archivo [!DNL Extended Robots List.txt] de la carpeta [!DNL Lookups] en la [!DNL data workbench server].

**Para habilitar la prueba del sitio en el transmisor**

1. Localice el archivo [!DNL txlogd.conf] en el equipo donde se está ejecutando [!DNL Sensor] y ábralo en un editor de texto.

1. En el archivo [!DNL txlogd.conf], busque la línea &quot;SiteTest&quot; y configúrela como se muestra a continuación. Si el archivo [!DNL txlogd.conf] no incluye la línea &quot;SiteTest&quot;, simplemente agregue la línea al final del archivo de configuración.

   SiteTest http, *serverAddress*, *port*, *resource*

   donde *serverAddress* es el nombre del servidor web o la dirección IP, *port* es el puerto de escucha HTTP del servidor y *resource* es el recurso específico que desea que Test del sitio solicite al probar el servidor. Tenga en cuenta que *resource* puede incluir una cadena de consulta.

   Ejemplo: SiteTest http,localhost,80,/index.jsp

   Para probar varios servidores web, simplemente especifique varias líneas de SiteTest.

## Comprobación de una cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Otra forma de verificar que el recolector se está ejecutando en un servidor web es comprobar si [!DNL Sensor] está configurando una cookie en las respuestas que el servidor web está devolviendo a los clientes. Si el recolector funciona, el servidor web devuelve una cookie &quot;v1st&quot;.

Es posible cambiar el nombre de la cookie. Si lo ha hecho, debe buscar el nombre especificado, no la v1st.

Puede realizar esta comprobación utilizando una secuencia de comandos automatizada o un agente de supervisión. Para obtener un script de ejemplo o ayuda adicional con esta tarea, póngase en contacto con los servicios de consultoría de Adobe.
