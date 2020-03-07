---
description: La transformación AppendURI proporciona una manera de agregar información al valor predeterminado que proviene de las entradas de registro utilizadas para generar el conjunto de datos.
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

La transformación AppendURI proporciona una manera de agregar información al valor predeterminado que proviene de las entradas de registro utilizadas para generar el conjunto de datos.

La transformación coloca un par nombre-valor al final del campo interno utilizado para crear la dimensión URI. El par nombre-valor se genera usando el parámetro de clave de cadena de consulta como nombre y valor del parámetro de entrada identificado como valor del par. El [!DNL AppendURI] comando agrega cualquier ? y &amp; símbolos necesarios para separar los pares nombre-valor de la [!DNL URI] derivación y de cualquier operación anterior [!DNL AppendURI] que se haya aplicado a la URI.

La [!DNL AppendURI] transformación solo funciona cuando se define en el [!DNL Transformation.cfg] archivo o en un [!DNL Transformation Dataset Include] archivo.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | Nombre del campo cuyo valor se anexa al URI. |  |
| Clave de cadena de consulta | Nombre que se va a utilizar en la creación del par nombre-valor que se va a anexar. |  |

Considere un sitio web que se construyó con un enfoque tradicional de Model-View-Controller. En estos sistemas, es común que una sola página web sea el punto de acceso al sistema. Para un sitio de este tipo, las visualizaciones de patrones de tráfico en el sistema serían muy poco interesantes y no proporcionarían perspectivas sobre la utilización del visitante y el flujo de tráfico. Por ejemplo, imaginemos un sitio web que canaliza todas las solicitudes web a través de un URI del siguiente formulario:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

La página ASP de vista de modelo recibe todo el tráfico y determina sus acciones en función del valor del campo de identificación en la consulta. De forma predeterminada, la dimensión URI contendría una sola entrada:

* [!DNL modelview.asp]

Esto resultaría en una asignación bastante poco interesante del tráfico a través del sitio, ya que todo el tráfico se canaliza a través de un único URI. Para abordar este escenario en particular y proporcionar una vista más informativa sobre la arquitectura subyacente del sitio web, [!DNL AppendURI] se puede utilizar para mover algunos de los pares nombre-valor únicos del campo cs-uri-query a la dimensión URI utilizada para las visualizaciones. La transformación que se muestra a continuación proporciona los detalles de dicha transformación:

![](assets/cfg_TransformationType_AppendURI.png)

En este ejemplo, el sistema utiliza dos páginas para tratar todas las solicitudes: [!DNL modelview.asp] y [!DNL xmlmodelview.asp]. Una página se utiliza para el tráfico del explorador y la otra para las comunicaciones XML de sistema a sistema. El proceso del servidor de aplicaciones utiliza el nombre de identificación de la consulta cs-uri para determinar qué acción realizar. Por lo tanto, puede extraer el valor del campo id y anexarlo al URI. El resultado es una colección de URI con una variedad de variaciones que reflejan el tráfico de visitantes a través del sitio web. Aquí, una [!DNL String Match] condición determina las entradas de registro a las que se aplica la transformación buscando en el campo cs-uri-stem las dos páginas web de interés e ignorando todas las demás. La entrada (el valor de nuestro par nombre-valor) es el resultado de cs-uri-query(id), que es &quot;login&quot;. Tal como especifica el parámetro de clave de cadena de consulta, el nombre que se anexa es &quot;id&quot;. Por lo tanto, para el valor cs-uri entrante de nuestro ejemplo, el URI resultante utilizado por la [!DNL URI] dimensión es [!DNL /modelview.asp&id=login].
