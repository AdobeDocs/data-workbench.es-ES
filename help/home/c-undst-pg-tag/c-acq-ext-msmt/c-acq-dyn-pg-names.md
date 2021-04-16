---
description: En algunos sitios, es necesario utilizar solicitudes de objetos incrustados para pasar información al servidor web, de modo que el sensor pueda adquirir los detalles sobre la página que se proporcionó y utilizarlos para la generación de informes y el análisis.
title: Adquisición de nombres de páginas dinámicos
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Adquisición de nombres de páginas dinámicos{#acquiring-dynamic-page-names}

En algunos sitios, es necesario utilizar solicitudes de objetos incrustados para pasar información al servidor web, de modo que el sensor pueda adquirir los detalles sobre la página que se proporcionó y utilizarlos para la generación de informes y el análisis.

Esto puede ser necesario si la dirección URL de la página, tal como la ve el servidor web, no indica el contenido de la página que se muestra al explorador. Este caso suele deberse al uso de sistemas de personalización o de administración dinámica de contenido en los que el contenido real servido en una página se determina sobre la marcha según la dirección URL, la cookie, los datos relacionados y la lógica de la aplicación.

La implementación de un objeto incrustado para recopilar mediciones adicionales debería tener un impacto mínimo en el rendimiento general del sitio. El Adobe sugiere que incruste un archivo JavaScript como el objeto utilizado para recopilar los atributos ampliados. (Tenga en cuenta que un archivo JavaScript se puede incrustar sin ningún impacto potencial en el diseño y la presentación de la página web, como puede resultar con el uso de una imagen incrustada). Para capturar con precisión la información pasada dentro del objeto incrustado, Adobe también sugiere que se utilice un nombre común. Para fines de asignación de nombres, Adobe hace referencia a este objeto como [!DNL zig.js]. El archivo [!DNL zig.js] debe crearse dentro del directorio correspondiente en un servidor web en el que esté instalado [!DNL Sensor]. Este archivo debe existir para que la solicitud no devuelva un código de error 404. El contenido del archivo en sí no es importante. Debe utilizar un archivo en blanco denominado [!DNL zig.js] para minimizar la cantidad de tráfico de red en la que se incurrió como resultado de la solicitud.

Para que [!DNL Sensor] recopile un nombre utilizable para la página que realmente se proporcionó, se deben agregar algunas líneas de código JavaScript a las páginas dinámicas que desee rastrear o a las que desee agregar un nombre de página único. Este código incrusta un fragmento de JavaScript en la página, lo que hace que se realice una solicitud de objeto incrustado terciario en el servidor web a medida que se carga la página. Esa solicitud envía detalles sobre la página específica que se devolvió al servidor web. El nombre de la página servida se devuelve al servidor web como una variable en la cadena de consulta de la solicitud del objeto incrustado (en este caso, JavaScript).

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

[!DNL Log=1] garantiza que  [!DNL Sensor] registra la solicitud a pesar de las reglas de filtrado de tipo de  [!DNL Sensor] contenido en sentido contrario, como el filtrado de JavaScript y las solicitudes de imagen antes de almacenarlas. La variable v_pn declarada identifica el nombre del contenido de la página real que se está sirviendo, de modo que [!DNL Site] sepa el nombre de la página que el visitante realmente vio. El valor v_pn puede establecerse manualmente o mediante otro código de aplicación o secuencia de comandos.

Una vez recopilado el valor, se puede configurar el servidor de Data Workbench para que utilice el contenido de la variable de cadena de consulta (par name=value, por ejemplo, v_pn=Application Form) anexado al URI [!DNL zag.gif] (por ejemplo, [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]) como aumento del URI [!DNL zag.gif]. Además de las mediciones de base adquiridas con cada solicitud HTTP, se adquiriría una medición ampliada con esta solicitud.

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_pn= | Valor asociado con la variable de cadena de consulta v_pn | v_pn=Formulario de aplicación |
