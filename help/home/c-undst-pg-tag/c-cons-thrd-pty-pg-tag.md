---
description: Información conceptual sobre el etiquetado de terceros y la prevención del bloqueo de cookies mediante P3P.
title: Consideraciones P3P para el etiquetado de páginas de terceros
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Consideraciones P3P para el etiquetado de páginas de terceros{#p-p-considerations-for-third-party-page-tagging}

Información conceptual sobre el etiquetado de terceros y la prevención del bloqueo de cookies mediante P3P.

## Explicación del etiquetado de páginas de terceros {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

En la mayoría de las implementaciones, la cookie persistente de Adobe se ve como una cookie de origen. Las cookies de origen se definen como las asociadas al dominio de host.

Supongamos que un usuario visita https://www.example.com/. Suponiendo que un sensor esté instalado y funcione en el servidor web que aloja el dominio, se establece una cookie persistente de Adobe que se ve como cookie de origen. Sin embargo, es posible que desee recopilar datos de medición de un sitio de terceros mediante el uso de objetos incrustados, que se solicitan y cargan desde el servidor que ejecuta [!DNL Sensor] en lugar del servidor de terceros que aloja la página o el programa publicitario. Por ejemplo, https://www.example2.com/ sirve para una página web con una solicitud de objeto incrustado procedente de https://www.example.com/. La solicitud del objeto incrustado de https://www.example.com/ provoca que se establezca una cookie; sin embargo, en este contexto, el navegador web o el agente de usuario ven la cookie como una cookie de terceros.

En exploradores web más recientes, como IE6 de Microsoft, las funciones de privacidad filtran las cookies según sus políticas compactas enviadas en el encabezado de respuesta HTTP desde el servidor web. En la configuración predeterminada de IE6, que la mayoría de los usuarios no cambian nunca, las cookies de terceros se bloquean cuando no existen políticas compactas o no son satisfactorias. La mayoría de los sitios que experimentan problemas de bloqueo de cookies tienen cookies de terceros en el sitio que no tienen las políticas compactas adecuadas que se envían en el encabezado de respuesta HTTP. Además, se producen algunos problemas de bloqueo de cookies cuando otro sitio enmarca un sitio. Por ejemplo, una tienda en línea que forme parte de un portal de compras en línea puede aparecer en un marco proporcionado por el portal. Desde la perspectiva del navegador, el contenido de la tienda puede parecer contenido de terceros cuando lo enmarca el portal. Sin embargo, si un visitante va directamente a la tienda en línea sin pasar por el portal, el contenido será de origen. Por lo tanto, la tienda en línea encuentra que sus cookies solo están bloqueadas cuando los visitantes acceden a través del portal.

Los sistemas de correo basados en Web causan un problema similar. Si un visitante de un sitio web envía un correo electrónico de una página web a un amigo que utiliza un sistema de correo electrónico basado en web, el mensaje de correo electrónico aparece como contenido de terceros en el explorador del amigo porque está enmarcado por el sistema de correo electrónico. Si hay cookies asociadas con la página que se envió por correo electrónico, IE6 las trata como cookies de terceros.

## Uso de P3P para evitar el bloqueo de cookies {#section-96831cad887649f295aec6931750e41a}

P3P proporciona una forma estándar para que los sitios web codificen sus políticas de privacidad en un formato XML legible por ordenador. Los navegadores web habilitados para P3P y otros agentes de usuario P3P recuperan automáticamente las políticas de privacidad P3P, las analizan y las comparan con las preferencias de privacidad de un usuario.

Para evitar que IE6 bloquee las cookies en su sitio, debe asegurarse de lo siguiente:

1. Todas las cookies que se configuran en un contexto de terceros tienen directivas compactas P3P asociadas.
1. La directiva compacta adecuada se envía mediante un encabezado de respuesta HTTP personalizado.
1. La IE6 considera que esas políticas compactas son satisfactorias.
1. Si otra empresa está configurando las cookies de terceros, es posible que tenga que pedirles que habiliten P3P y que establezcan directivas compactas P3P. Cualquier host que establezca una directiva compacta P3P también debe tener una directiva P3P completa correspondiente. Los usuarios pueden cambiar su configuración de IE6 para que las cookies también se bloqueen en otras condiciones; sin embargo, la colocación de políticas compactas satisfactorias en cookies de terceros evita la mayoría de los bloqueos de cookies de IE6.

El siguiente es un ejemplo de un encabezado P3P de este tipo:

```
P3P: policyref=” https://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

En este ejemplo, el archivo [!DNL p3p.xml] se utiliza para hacer referencia a un archivo [!DNL policy.xml] asociado que reside en el servidor web y que indica los tipos de información que recopila el sitio web, los métodos de resolución de disputas a los que se adhiere la organización, cómo se utilizan los datos recopilados, quién posee los datos y otra información estándar relacionada con la privacidad de Internet. Los tres códigos de caracteres que siguen a &quot;CP&quot; son los códigos de directiva compactos que emulan lo que se indica dentro del archivo [!DNL policy.xml].

Todas las políticas compactas y los archivos XML de políticas deben adaptarse a la organización respectiva para la que se implementan, especificando con precisión sus políticas de privacidad internas con respecto a la recopilación de datos de sitios web. Encontrará una gran cantidad de editores de directivas P3P en línea junto con información más detallada sobre la implementación de una política de privacidad adecuada en su sitio web.

Para obtener más información sobre cómo gestiona Internet Explorer 6 los encabezados P3P, visite:

[https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
