---
description: La mercadotecnia de su sitio Web puede implicar la colocación de anuncios en forma de imágenes u otros archivos de medios enriquecidos (que se proporcionen desde su servidor Web) en sitios Web de terceros.
solution: Analytics
title: Medición de la impresión de publicidad
topic: Data workbench
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Medición de la impresión de publicidad{#measuring-advertisement-impression}

La mercadotecnia de su sitio Web puede implicar la colocación de anuncios en forma de imágenes u otros archivos de medios enriquecidos (que se proporcionen desde su servidor Web) en sitios Web de terceros.

En estos casos, es posible que desee medir tanto la impresión del anuncio en un navegador como la pulsación subsiguiente, si se produce alguna, en la dirección URL de destino del anuncio en el sitio web.

Para los anuncios en forma de imágenes, anexar [!DNL Log=1] a la cadena de consulta resulta en la solicitud de imagen y, por lo tanto, en la impresión de anuncio, que se captura [!DNL Sensor] con fines de análisis.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_ic= | Valor que indica la campaña Impresión | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Valor que indica el recurso de la campaña Impresión | v_ica=&quot;72890ab&quot; |
| v_icr= | Valor que indica el referente de la campaña Impresión | v_icr=&quot;http://money.cnn.com/markets/ |

Además de anexar [!DNL Log=1] a la solicitud de imagen, se debe agregar un identificador a la dirección URL que lleva desde el anuncio a la página de destino dentro del sitio web para rastrear el anuncio que condujo a la pulsación y para rastrear la pulsación de regreso a la campaña en particular para ese anuncio.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datos recopilados </th> 
   <th colname="col2" class="entry"> Explicación </th> 
   <th colname="col3" class="entry"> Ejemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> Valor que indica la campaña de pulsaciones </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Valor que indica el recurso de campaña de pulsaciones </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Valor que indica el referente de campaña de pulsaciones </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>mercados/ </p> </td> 
  </tr> 
 </tbody> 
</table>

