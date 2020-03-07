---
description: Para algunos sitios, es necesario utilizar solicitudes de objetos incrustados para pasar información al servidor Web de modo que los detalles sobre la página que se proporcionó en realidad puedan ser adquiridos por Sensor y utilizados para informes y análisis.
solution: Analytics
title: Adquisición de nombres de páginas dinámicos
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adquisición de nombres de páginas dinámicos{#acquiring-dynamic-page-names}

Para algunos sitios, es necesario utilizar solicitudes de objetos incrustados para pasar información al servidor Web de modo que los detalles sobre la página que se proporcionó en realidad puedan ser adquiridos por Sensor y utilizados para informes y análisis.

Esto puede ser necesario si la dirección URL de la página, tal como la ve el servidor web, no indica el contenido de la página que se muestra al explorador. Este caso suele deberse al uso de sistemas de personalización o de administración dinámica de contenido en los que el contenido real que se proporciona en una página se determina sobre la marcha mediante la dirección URL, la cookie, los datos relacionados y la lógica de la aplicación.

La implementación de un objeto incrustado para recopilar mediciones adicionales debería tener un impacto mínimo en el rendimiento general del sitio. Adobe sugiere incrustar un archivo JavaScript como el objeto utilizado para recopilar los atributos extendidos. (Tenga en cuenta que un archivo JavaScript puede incrustarse sin ningún impacto potencial en el diseño y la presentación de la página web, como puede resultar en el uso de una imagen incrustada). Para capturar con precisión la información que se pasa dentro del objeto incrustado, Adobe también sugiere que se utilice un nombre común. Por motivos de nomenclatura, Adobe hace referencia a este objeto como [!DNL zig.js]. El [!DNL zig.js] archivo debe crearse dentro del directorio correspondiente en un servidor web en el que [!DNL Sensor] esté instalado. Este archivo debe existir para que la solicitud no devuelva un código de error 404. El contenido del archivo en sí no es importante. Debe utilizar un archivo en blanco con el nombre [!DNL zig.js] para minimizar la cantidad de tráfico de red que se produce como resultado de la solicitud.

Para [!DNL Sensor] recopilar un nombre utilizable para la página que en realidad se ha servido, se deben agregar algunas líneas de código JavaScript a las páginas dinámicas que desee rastrear o a las que desee agregar un nombre de página único. Este código incrusta un fragmento de JavaScript en la página, lo que provoca que se realice una solicitud de objeto incrustado terciario en el servidor web a medida que se carga la página. Esa solicitud envía detalles sobre la página específica que se ha devuelto al servidor Web. El nombre de la página que se ha servido se devuelve al servidor web como una variable en la cadena de consulta de la solicitud del objeto incrustado (en este caso, JavaScript).

En general, la solicitud de objeto incrustada en cada una de estas páginas HTML debería tener el siguiente aspecto:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] garantiza que [!DNL Sensor] registra la solicitud a pesar de las reglas de filtrado de tipo de [!DNL Sensor] contenido, por el contrario, como el filtrado de solicitudes de imagen y JavaScript antes de que se almacenen. La variable v_pn declarada identifica el nombre del contenido de la página real que se está ofreciendo, de modo que [!DNL Site] conoce el nombre de la página que el visitante realmente vio. El valor v_pn se puede establecer manualmente o mediante otro código de aplicación o secuencia de comandos.

Una vez recopilado el valor, puede configurar el servidor del área de trabajo de datos para que utilice el contenido de la variable de cadena de consulta (nombre=par de valor, por ejemplo, v_pn=Formulario de aplicación) anexado al [!DNL zag.gif] URI (por ejemplo, [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), como un aumento del [!DNL zag.gif] URI. Además de las mediciones de base adquiridas con cada solicitud HTTP, se adquiriría una medición ampliada con esta solicitud.

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_pn= | Valor asociado con la variable de cadena de consulta v_pn | v_pn=Formulario de solicitud |

