---
description: Pasos utilizados para facilitar la recopilación de clics en vínculos mediante el uso de la etiqueta de página de referencia.
title: Rastreo de clics en vínculos
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# Rastreo de clics en vínculos{#tracking-link-clicks}

Pasos utilizados para facilitar la recopilación de clics en vínculos mediante el uso de la etiqueta de página de referencia.

Mediante la implementación de [!DNL Reference Page Tag], es posible recopilar datos de medición que denoten los vínculos (o valores href) en los que los visitantes hacen clic mientras visitan páginas en particular. Normalmente, esta colección no implica la implementación de identificadores de vínculo adicionales en las páginas de HTML.

Para facilitar la recopilación de clics en vínculos mediante el uso de [!DNL Reference Page Tag], complete los siguientes pasos:

1. Copie el siguiente código en el archivo existente llamado [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG
   //INITIATE FUNCTIONS ONLOAD
   function addEvent(obj, evType, fn){
    if (obj.addEventListener){
      obj.addEventListener(evType, fn, false);
      return true;
    } else if (obj.attachEvent){
      var r = obj.attachEvent("on"+evType, fn);
      return r;
    } else {
      return false;
    }
   }
   addEvent(window, 'load', startCapture);
   addEvent(window, 'load', startCapture);
   function startCapture(){
   //TO CAPTURE LINK CLICKS
     if (vlc == "1"){captureLink();}
     //TO CAPTURE FORM FIELD CLICKS
     if (vfc == "1"){captureForm();}
   }
   //BEGIN LINK CAPTURE PAGE TAG
   function captureLink(){
     if (document.links[0]){
       if (document.links){
         var links = document.links, link, k=0;
         while(link=links[k++]) {
           link.onclick = captureLinkName;
    }
       }
     }
   }
   function captureLinkName() {
     var lc=new Image();
     this.parent = this.parentNode;
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime();
   }
   //END LINK CAPTURE PAGE TAG
   //BEGIN FORM CLICK CAPTURE PAGE TAG
   function captureForm(){
     if (document.forms[0]) {
       if(document.forms){
    for(i=0; i<document.forms[0].elements.length; i++){
           var forms = document.forms[0].elements[i];
           forms.onfocus = captureFormName;
         }
       }
     }
   }
   function captureFormName() {
     var fc=new Image();
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime();
   }
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Cree o coloque el archivo de imagen de 1 píxel por 1 píxel llamado [!DNL zag2.gif] en un directorio presente en el servidor web.
1. Modifique la variable [!DNL lc.src] para hacer referencia al dominio apropiado del sitio web desde el cual se hace referencia al archivo [!DNL zag2.gif].

1. Asegúrese de que se hayan establecido los encabezados de control de caché adecuados para los archivos [!DNL zag.gif] y [!DNL zig.js].

1. Dentro de los archivos de HTML desde los que desea recopilar los valores de clics en vínculos, el [!DNL Reference Page Tag Execution Call] debe modificarse para informar al [!DNL Page Tag Execution Script] a fin de capturar los clics en vínculos para esa página. Para ello, cambie el valor de la variable vlc a &quot;1&quot; como se indica en el siguiente ejemplo de código:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE
var v = {};
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_ln= | Valor que indica la campaña de impresión | v_ln=&quot;About%20Us&quot; |
