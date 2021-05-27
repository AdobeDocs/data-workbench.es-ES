---
description: La transformación AppendURI proporciona una forma de agregar información al valor predeterminado que proviene de las entradas de registro utilizadas para generar el conjunto de datos.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

La transformación AppendURI proporciona una forma de agregar información al valor predeterminado que proviene de las entradas de registro utilizadas para generar el conjunto de datos.

La transformación coloca un par nombre-valor al final del campo interno utilizado para crear la dimensión URI. El par nombre-valor se crea utilizando el parámetro Clave de cadena de consulta como nombre y el valor del parámetro de entrada identificado como valor del par. El comando [!DNL AppendURI] añade cualquier ? y los símbolos y necesarios para separar los pares nombre-valor del sistema [!DNL URI] y de cualquier operación [!DNL AppendURI] anterior que se haya aplicado a la URI.

La transformación [!DNL AppendURI] solo funciona cuando se define en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include].

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | Nombre del campo cuyo valor se anexa al URI. |  |
| Clave de cadena de consulta | Nombre que se va a utilizar en la creación del par nombre-valor que se va a anexar. |  |

Considere un sitio web que se construyó usando un enfoque tradicional de Model-View-Controller. En estos sistemas, es común que una sola página web sea el punto de acceso al sistema. Para un sitio de este tipo, las visualizaciones de patrones de tráfico en el sistema serían poco interesantes y no proporcionarían información sobre la utilización del visitante y el flujo de tráfico. Por ejemplo, imaginemos un sitio web que canaliza todas las solicitudes web a través de un URI del siguiente formulario:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

La página ASP de vista de modelo recibe todo el tráfico y determina sus acciones en función del valor del campo id de la consulta. De forma predeterminada, la dimensión URI contendría una sola entrada:

* [!DNL modelview.asp]

Esto resultaría en una asignación poco interesante del tráfico a través del sitio, ya que todo el tráfico se canaliza a través de un único URI. Para abordar este escenario en particular y proporcionar una vista más informativa sobre la arquitectura subyacente del sitio web, se puede utilizar [!DNL AppendURI] para mover algunos de los pares nombre-valor únicos del campo cs-uri-query a la dimensión URI utilizada para las visualizaciones. La transformación que se muestra a continuación proporciona los detalles de dicha transformación:

![](assets/cfg_TransformationType_AppendURI.png)

En este ejemplo, el sistema utiliza dos páginas para tratar todas las solicitudes: [!DNL modelview.asp] y [!DNL xmlmodelview.asp]. Una página se utiliza para el tráfico del explorador y la otra para las comunicaciones XML de sistema a sistema. El proceso del servidor de aplicaciones utiliza el nombre de id de la consulta cs-uri para determinar qué acción realizar. Por lo tanto, puede extraer el valor del campo id y anexarlo al URI. El resultado es una colección de URI con una gama de variaciones que reflejan el tráfico de los visitantes a través del sitio web. En este caso, una condición [!DNL String Match] determina las entradas de registro a las que se aplica la transformación buscando en el campo cs-uri-stem las dos páginas web de interés e ignorando todas las demás. La entrada (el valor de nuestro par nombre-valor) es el resultado de cs-uri-query(id), que es &quot;login&quot;. Según lo especificado por el parámetro Clave de cadena de consulta, el nombre que se anexa es &quot;id&quot;. Por lo tanto, para el valor cs-uri entrante de nuestro ejemplo, el URI resultante utilizado por la dimensión [!DNL URI] es [!DNL /modelview.asp&id=login].
