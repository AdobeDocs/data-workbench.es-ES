---
description: La comercialización del sitio web puede implicar la colocación de anuncios en forma de imagen u otros archivos multimedia enriquecidos (servidos desde el servidor web) en sitios web de terceros.
title: Medición de la impresión de publicidad
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# Medición de la impresión de publicidad{#measuring-advertisement-impression}

La comercialización del sitio web puede implicar la colocación de anuncios en forma de imagen u otros archivos multimedia enriquecidos (servidos desde el servidor web) en sitios web de terceros.

En estos casos, es posible que desee medir tanto la impresión del anuncio en un explorador como la posterior pulsación, si se produce, en la dirección URL de destino del anuncio en su sitio web.

En el caso de anuncios en forma de imágenes, anexar [!DNL Log=1] a la cadena de consulta resulta en la solicitud de imagen y, por lo tanto, en la impresión de anuncio, que [!DNL Sensor] captura con fines de análisis.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_ic= | Valor que indica la campaña de impresión | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Valor que indica el recurso de campaña de impresión | v_ica=&quot;72890ab&quot; |
| v_icr= | Valor que indica el referente de campaña de impresión | v_icr=&quot;http://money.cnn.com/markets/ |

Además de adjuntar [!DNL Log=1] a la solicitud de imagen, se debe agregar un identificador a la dirección URL que comienza desde el anuncio a la página de destino dentro del sitio web para rastrear el anuncio que generó la pulsación y para rastrear la pulsación hasta la campaña en particular para ese anuncio.

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
   <td colname="col2"> Valor que indica el recurso de campaña de pulsación </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Valor que indica el referente de campaña de pulsaciones </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>mercados/ </p> </td> 
  </tr> 
 </tbody> 
</table>
