---
description: La transformación ReplaceURI cambia el valor de la dimensión URI interna a un nuevo valor.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

La transformación ReplaceURI cambia el valor de la dimensión URI interna a un nuevo valor.

Si se especifica [!DNL URI Prefix], el valor resultante es simplemente el prefijo URI concatenado con el valor de entrada proporcionado.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | El valor para reemplazar el URI. |  |
| Prefijo URI | El valor (cadena) que se va a anteponer al valor del campo [!DNL Input]. |  |

>[!NOTE]
>
>Antes de aplicar transformaciones [!DNL ReplaceURI], debe crear una nueva dimensión simple con un elemento principal de [!DNL Page View]a partir de una copia de cs-uri-stem o cs-uri. Para obtener ayuda con esto, póngase en contacto con el Adobe.

En este ejemplo se muestra el uso de [!DNL ReplaceURI] para reemplazar las cadenas de consulta &quot;page=*pageid*&quot; por &quot; [!DNL homepage.html]&quot; siempre que *pageid* indique que se ha visto la página principal del sitio web. El resultado final es una vista más fácil de usar del URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Para la transformación mostrada, la página

* [!DNL www.examplesite.com/info.html?page=1550]

cambiaría a

* [!DNL www.examplesite.com/homepage.html]
