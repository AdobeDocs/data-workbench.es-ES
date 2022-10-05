---
description: Compruebe si el recolector se está ejecutando con métodos diferentes.
title: Confirmación de la ejecución del recopilador de datos
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Confirmación de la ejecución del recopilador de datos{#confirming-that-the-data-collector-is-running}

{{eol}}

Compruebe si el recolector se está ejecutando con métodos diferentes.

**Frecuencia recomendada:** Cada 5-10 minutos

* [Utilice la funcionalidad de prueba del sitio en el transmisor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Compruebe si [!DNL Sensor] está configurando una cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Uso de la prueba del sitio {#section-a5a697c3252e40f184c0b662926170f2}

Una forma de verificar que el recolector se está ejecutando es habilitar la función de prueba del sitio en el transmisor. Cuando habilita la Prueba del sitio, el transmisor envía periódicamente (cada 60 segundos) una solicitud de GET al servidor web en el que se ejecuta el recopilador. Si la prueba del sitio no obtiene una respuesta del servidor web, escribe un mensaje de error en syslog y envía un mensaje de error al [!DNL data workbench server] (que se escribe en el archivo de registro de sensor).

Si la prueba del sitio recibe una respuesta del servidor web, busca en el archivo de cola un paquete del servidor web. Si el paquete no aparece (indicando que el recolector no se estaba ejecutando para capturar el evento), Site Test escribe un mensaje de error en syslog y envía un mensaje de error al Adobe (que también se escribe en el archivo de registro de sensor).

En las solicitudes que envía la prueba del sitio al servidor web, la prueba del sitio establece el valor User-Agent en &quot; [!DNL Sensor] Probar&quot;. Si no desea que estas solicitudes aparezcan en su conjunto de datos, agregue la variable [!DNL Sensor] Probar&quot; Agente-Usuario al [!DNL Baseline Robots List.txt] o [!DNL Extended Robots List.txt] en el [!DNL Lookups] en la carpeta [!DNL data workbench server].

**Para habilitar la prueba del sitio en el transmisor**

1. Busque la variable [!DNL txlogd.conf] en el equipo donde [!DNL Sensor] se está ejecutando y se abre en un editor de texto.

1. En el [!DNL txlogd.conf] , busque la línea &quot;SiteTest&quot; y configúrela como se muestra a continuación. Si su [!DNL txlogd.conf] no incluye la línea &quot;SiteTest&quot;, simplemente agregue la línea al final del archivo de configuración.

   SiteTest http, *serverAddress*, *puerto*, *recurso*

   donde *serverAddress* es el nombre o la dirección IP del servidor web, *puerto* es el puerto de escucha HTTP del servidor, y *recurso* es el recurso específico que desea que la prueba del sitio solicite al probar el servidor. Tenga en cuenta que *recurso* puede incluir una cadena de consulta.

   Ejemplo: SiteTest http,localhost,80,/index.jsp

   Para probar varios servidores web, simplemente especifique varias líneas de SiteTest.

## Comprobación de una cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Otra forma de verificar que el recolector se está ejecutando en un servidor web es comprobar si [!DNL Sensor] está configurando una cookie en las respuestas que el servidor web devuelve a los clientes. Si el recolector funciona, el servidor web devuelve una cookie &quot;v1st&quot;.

Es posible cambiar el nombre de la cookie. Si lo ha hecho, debe buscar el nombre especificado, no la v1st.

Puede realizar esta comprobación utilizando una secuencia de comandos automatizada o un agente de supervisión. Para obtener un script de ejemplo o ayuda adicional con esta tarea, póngase en contacto con los servicios de consultoría de Adobe.
