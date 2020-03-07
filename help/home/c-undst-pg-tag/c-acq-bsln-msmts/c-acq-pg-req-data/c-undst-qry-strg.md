---
description: La cadena de consulta (cs-uri-query) es utilizada a menudo por las aplicaciones web y los desarrolladores de sitios para pasar información de una página a otra debido a la naturaleza apátrida de HTTP.
solution: Analytics
title: Explicación de la cadena de consulta
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de la cadena de consulta{#understanding-the-query-string}

La cadena de consulta (cs-uri-query) es utilizada a menudo por las aplicaciones web y los desarrolladores de sitios para pasar información de una página a otra debido a la naturaleza apátrida de HTTP.

En muchos casos, la información puede pasarse en la cadena de consulta cuando la adquiere [!DNL Sensor] en el servidor Web. Dicha información puede ser utilizada por [!DNL Site] para iluminar la verdadera estructura del sitio, y la ruta de los visitantes a través de él, así como otra información.

En algunos sitios web dinámicos, los pares nombre=valor (variables) de la cadena de consulta son importantes para determinar la página real que solicita un visitante. En estos casos, las direcciones URL pueden estructurarse de la siguiente manera o de manera similar:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

En este ejemplo, PAGENAME es en realidad el indicador de la página que se proporcionará al solicitante de esta dirección URL. Muchas herramientas y servicios de análisis de registros Web limitan la capacidad del operador de sitio para definir qué es una página en su sitio en función de las variables de cadena de consulta que se producen en las cadenas de consulta de las direcciones URL del sitio. El servidor del área de trabajo de datos y el área de trabajo de datos se pueden configurar para utilizar estos nombres de consulta para definir páginas únicas. Esto es importante porque muchos sistemas interpretarían las siguientes direcciones URL como la misma página, pero [!DNL Site] no.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Del mismo modo, los desarrolladores y las aplicaciones del sitio suelen agregar muchas variables de cadena de consulta a las direcciones URL del sitio que no tienen nada que ver con la identificación de la página real que se solicita. A continuación se muestran algunos ejemplos:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

En este ejemplo, la variable de cadena de consulta CAMPAIGN= se ha agregado a la dirección URL. Esta variable CAMPAIGN se está utilizando para indicar qué campaña de mercadotecnia causó que un visitante seleccionara esta dirección URL. [!DNL Site] se puede configurar para utilizar esta información de CAMPAÑA, pero separarla de la definición de la página que vio un visitante para que en la lista de páginas con fines de informes y análisis simplemente vea lo siguiente:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

