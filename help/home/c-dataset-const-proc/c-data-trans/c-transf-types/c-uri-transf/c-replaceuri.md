---
description: La transformación ReplaceURI cambia el valor de la dimensión URI interna a un nuevo valor.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

{{eol}}

La transformación ReplaceURI cambia el valor de la dimensión URI interna a un nuevo valor.

If [!DNL URI Prefix] se especifica, el valor resultante es simplemente el prefijo URI concatenado con el valor de entrada proporcionado.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | El valor para reemplazar el URI. |  |
| Prefijo URI | El valor (cadena) que se va a anteponer al valor de la variable [!DNL Input] campo . |  |

>[!NOTE]
>
>Antes de aplicar [!DNL ReplaceURI] transformaciones, debe crear una nueva dimensión simple con un elemento principal de [!DNL Page View]de una copia de cs-uri-stem o cs-uri. Para obtener ayuda con esto, póngase en contacto con el Adobe.

Este ejemplo muestra el uso de [!DNL ReplaceURI] para reemplazar la &quot;página=&quot;*pageid*&quot; cadenas de consulta con &quot; [!DNL homepage.html]&quot; *pageid* indica que se ha visto la página principal del sitio web. El resultado final es una vista más fácil de usar del URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Para la transformación mostrada, la página

* [!DNL www.examplesite.com/info.html?page=1550]

cambiaría a

* [!DNL www.examplesite.com/homepage.html]
