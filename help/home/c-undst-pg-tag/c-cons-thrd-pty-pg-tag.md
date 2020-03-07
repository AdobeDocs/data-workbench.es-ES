---
description: Información conceptual sobre el etiquetado de terceros y la prevención del bloqueo de cookies mediante P3P.
solution: Analytics
title: Consideraciones P3P para el etiquetado de páginas de terceros
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Consideraciones P3P para el etiquetado de páginas de terceros{#p-p-considerations-for-third-party-page-tagging}

Información conceptual sobre el etiquetado de terceros y la prevención del bloqueo de cookies mediante P3P.

## Explicación del etiquetado de páginas de terceros {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

En la mayoría de las implementaciones, la cookie persistente de Adobe se ve como una cookie de origen. Las cookies de origen se definen como las asociadas al dominio host.

Supongamos que un usuario visita http://www.example.com/. Suponiendo que un sensor está instalado y en funcionamiento en el servidor web que aloja el dominio, se establece una cookie persistente de Adobe y se ve como una cookie de origen. Sin embargo, es posible que desee recopilar datos de medición de un sitio de terceros mediante el uso de objetos incrustados, que se solicitan y se cargan desde el servidor que se está ejecutando [!DNL Sensor] en lugar de hacerlo desde el servidor de terceros que aloja la página o el programa de publicidad. Por ejemplo, http://www.example2.com/ proporciona una página web con una solicitud de objeto incrustado servida desde http://www.example.com/. La solicitud del objeto incrustado de http://www.example.com/ da como resultado que se establezca una cookie; sin embargo, en este contexto, el navegador web o el agente de usuario ven la cookie como una cookie de terceros.

En exploradores web más recientes, como IE6 de Microsoft, las características de privacidad filtran las cookies en función de sus directivas compactas enviadas en el encabezado de respuesta HTTP desde el servidor web. En la configuración predeterminada de IE6, que la mayoría de los usuarios no cambia, las cookies de terceros se bloquean cuando tienen directivas compactas inexistentes o insatisfactorias. La mayoría de los sitios que experimentan problemas de bloqueo de cookies tienen cookies de terceros en su sitio que no tienen las directivas compactas apropiadas que se envían en el encabezado de respuesta HTTP. Además, algunos problemas de bloqueo de cookies se producen cuando otro sitio enmarca un sitio. Por ejemplo: una tienda en línea que forme parte de un portal de compras en línea puede aparecer en un marco proporcionado por el portal. Desde la perspectiva del navegador, el contenido de la tienda puede parecer contenido de terceros cuando está enmarcado por el portal. Sin embargo, si un visitante va directamente a la tienda en línea sin pasar por el portal, el contenido será de origen. Por lo tanto, la tienda en línea encuentra que sus cookies están bloqueadas sólo cuando los visitantes ingresan a través del portal.

Los sistemas de correo basados en la Web causan un problema similar. Si un visitante de un sitio web envía una página web por correo electrónico a un amigo que utiliza un sistema de correo web, el mensaje de correo electrónico aparece como contenido de terceros en el explorador del amigo porque está enmarcado por el sistema de correo electrónico. Si hay cookies asociadas con la página que se envió por correo electrónico, IE6 las trata como cookies de terceros.

## Uso de P3P para prevenir el bloqueo de cookies {#section-96831cad887649f295aec6931750e41a}

P3P proporciona una forma estándar para que los sitios Web codificen sus políticas de privacidad en un formato XML legible por ordenador. Los navegadores web activados por P3P y otros agentes de usuario P3P recuperan automáticamente las políticas de privacidad de P3P, las analizan y las comparan con las preferencias de privacidad de un usuario.

Para evitar que IE6 bloquee las cookies del sitio, debe asegurarse de lo siguiente:

1. Todas las cookies que se están configurando en un contexto de terceros tienen directivas compactas P3P asociadas.
1. La directiva compacta adecuada se envía mediante un encabezado de respuesta HTTP personalizado.
1. Estas políticas compactas se consideran satisfactorias en IE6.
1. Si otra empresa está configurando las cookies de terceros, es posible que tenga que solicitarles que habiliten P3P y establezcan directivas compactas P3P. Cualquier host que establezca una directiva compacta P3P también debe tener una directiva P3P completa correspondiente. Los usuarios pueden cambiar la configuración de IE6 para que las cookies también se bloqueen en otras condiciones; sin embargo, la colocación de políticas compactas satisfactorias en cookies de terceros evita el bloqueo de la mayoría de las cookies IE6.

A continuación se muestra un ejemplo de un encabezado P3P de este tipo:

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

En este ejemplo, el archivo [!DNL p3p.xml] se utiliza para hacer referencia a un [!DNL policy.xml] archivo asociado que reside en el servidor web y que denota los tipos de información que recopila el sitio web, los métodos de resolución de conflictos a los que se adhiere la organización, la forma en que se utilizan los datos recopilados, quién es el propietario de los datos y otra información estándar relacionada con la privacidad de Internet. Los tres códigos de caracteres que siguen a &quot;CP&quot; son los códigos de política compactos que emulan lo que se indica en el [!DNL policy.xml] archivo.

Todas las políticas compactas y los archivos XML de políticas deben adaptarse a la organización respectiva para la que se implementan, especificando con precisión sus políticas de privacidad internas con respecto a la recopilación de datos del sitio web. Se puede encontrar una gran cantidad de editores de directivas P3P en línea junto con información más detallada sobre la implementación de una política de privacidad adecuada en su sitio web.

Para obtener más información sobre cómo Internet Explorer 6 gestiona los encabezados P3P, visite:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
