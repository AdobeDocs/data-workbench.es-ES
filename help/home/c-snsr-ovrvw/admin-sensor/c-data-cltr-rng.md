---
description: Compruebe si el selector se está ejecutando con métodos diferentes.
solution: Insight
title: Confirmación de la ejecución del recopilador de datos
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confirmación de la ejecución del recopilador de datos{#confirming-that-the-data-collector-is-running}

Compruebe si el selector se está ejecutando con métodos diferentes.

**Frecuencia recomendada:** Cada 5-10 minutos

* [Utilice la funcionalidad Prueba del sitio en el transmisor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Compruebe si [!DNL Sensor] está configurando una cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Uso de la prueba del sitio {#section-a5a697c3252e40f184c0b662926170f2}

Una manera de verificar que el selector se está ejecutando es habilitar la función Prueba del sitio en el transmisor. Cuando habilita la Prueba del sitio, el transmisor envía periódicamente (cada 60 segundos) una solicitud GET al servidor Web en el que se ejecuta el recopilador. Si la prueba del sitio no obtiene una respuesta del servidor web, escribe un mensaje de error en syslog y envía un mensaje de error al [!DNL data workbench server] (que se escribe en el archivo de registro del sensor).

Si la prueba del sitio recibe una respuesta del servidor web, busca en el archivo de cola un paquete del servidor web. Si el paquete no aparece (lo que indica que el recopilador no se estaba ejecutando para capturar el evento), la prueba del sitio escribe un mensaje de error en syslog y envía un mensaje de error a Adobe (que también se escribe en el archivo de registro del sensor).

En las solicitudes que Test del sitio envía al servidor web, Prueba del sitio establece el valor User-Agent en &quot; [!DNL Sensor] Prueba&quot;. Si no desea que estas solicitudes aparezcan en el conjunto de datos, agregue el agente de usuario de &quot; [!DNL Sensor] prueba&quot; al [!DNL Baseline Robots List.txt] archivo o al [!DNL Extended Robots List.txt] archivo de la [!DNL Lookups] carpeta de la [!DNL data workbench server].

**Para habilitar la prueba del sitio en el transmisor**

1. Busque el [!DNL txlogd.conf] archivo en el equipo en el que [!DNL Sensor] se está ejecutando y ábralo en un editor de texto.

1. En el [!DNL txlogd.conf] archivo, ubique la línea &quot;SiteTest&quot; y configúrela como se muestra a continuación. Si el [!DNL txlogd.conf] archivo no incluye la línea &quot;SiteTest&quot;, simplemente agregue la línea al final del archivo de configuración.

   SiteTest http, *serverAddress*, *port*, *resource*

   donde *serverAddress* es el nombre del servidor web o la dirección IP, *port* es el puerto de escucha HTTP del servidor y *resource* es el recurso específico que desea que Site Test solicite al probar el servidor. Tenga en cuenta que *el recurso* puede incluir una cadena de consulta.

   Ejemplo: SiteTest http,localhost,80,/index.jsp

   Para probar varios servidores Web, sólo tiene que especificar varias líneas de SiteTest.

## Comprobación de una cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Otra manera de verificar que el recopilador se esté ejecutando en un servidor Web es comprobar si [!DNL Sensor] está configurando una cookie en las respuestas que el servidor Web está regresando a los clientes. Si el selector funciona, el servidor web devuelve una cookie &quot;v1st&quot;.

Es posible cambiar el nombre de la cookie. Si lo ha hecho, debe buscar el nombre especificado, no v1st.

Puede realizar esta comprobación mediante un script automatizado o un agente de supervisión. Para obtener un script de ejemplo o ayuda adicional con esta tarea, póngase en contacto con los servicios de consultoría de Adobe.
