---
description: La cadena de consulta (cs-uri-query) la utilizan a menudo las aplicaciones web y los desarrolladores de sitios para pasar información de página en página debido a la naturaleza sin estado de HTTP.
title: Explicación de la cadena de consulta
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Explicación de la cadena de consulta{#understanding-the-query-string}

La cadena de consulta (cs-uri-query) la utilizan a menudo las aplicaciones web y los desarrolladores de sitios para pasar información de página en página debido a la naturaleza sin estado de HTTP.

En muchos casos, la información puede pasarse en la cadena de consulta cuando la adquiere [!DNL Sensor] en el servidor web. Dicha información puede ser utilizada por [!DNL Site] para iluminar la verdadera estructura del sitio, la ruta de los visitantes a través de él, así como otra información.

En algunos sitios web dinámicos, los pares nombre=valor (variables) de la cadena de consulta son importantes para determinar la página que solicita un visitante. En estos casos, las direcciones URL pueden estructurarse de la siguiente manera o de manera similar:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

En este ejemplo, PAGENAME es realmente el indicador de qué página se servirá al solicitante de esta dirección URL. Muchas herramientas y servicios de análisis de registros web limitan la capacidad del operador de un sitio para definir qué es una página de su sitio en función de qué variables de cadena de consulta se producen en las cadenas de consulta de las direcciones URL del sitio. El servidor de Data Workbench y Data Workbench se pueden configurar para utilizar estos nombres de consulta para definir páginas únicas. Esto es importante porque muchos sistemas interpretarían las siguientes direcciones URL como la misma página, pero [!DNL Site] no.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Del mismo modo, los desarrolladores y las aplicaciones de sitios suelen agregar muchas variables de cadena de consulta a las direcciones URL de un sitio que no tienen nada que ver con la identificación de la página real que se solicita. A continuación se muestran algunos ejemplos:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

En este ejemplo, la variable de cadena de consulta CAMPAIGN= se ha agregado a la dirección URL. Esta variable de CAMPAIGN se está utilizando para indicar qué campaña de marketing causó que un visitante seleccione esta dirección URL. [!DNL Site] puede configurarse para utilizar esta información de CAMPAIGN, pero separarla de la definición de la página que vio un visitante para que en su lista de páginas con fines de informes y análisis simplemente vea lo siguiente:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
