---
description: La transformación ReplaceURI cambia el valor de la dimensión URI interna a un nuevo valor.
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

La transformación ReplaceURI cambia el valor de la dimensión URI interna a un nuevo valor.

Si [!DNL URI Prefix] se especifica, el valor resultante es simplemente el prefijo URI concatenado con el valor de entrada proporcionado.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | El valor que se va a reemplazar al URI. |  |
| Prefijo URI | El valor (cadena) que se va a anteponer al valor del [!DNL Input] campo. |  |

>[!NOTE]
>
>Antes de aplicar [!DNL ReplaceURI] transformaciones, debe crear una nueva dimensión simple con un elemento principal [!DNL Page View]de una copia de cs-uri-stem o cs-uri. Para obtener ayuda con esto, póngase en contacto con Adobe.

En este ejemplo se muestra el uso de [!DNL ReplaceURI] para reemplazar las cadenas de consulta &quot;page=*pageid*&quot; por &quot; [!DNL homepage.html]&quot; siempre que *pageid* indique que se ha visto la página principal del sitio web. El resultado final es una vista más sencilla del URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Para la transformación mostrada, la página

* [!DNL www.examplesite.com/info.html?page=1550]

cambiaría a

* [!DNL www.examplesite.com/homepage.html]

