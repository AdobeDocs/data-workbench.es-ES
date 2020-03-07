---
description: El perfil de atribución es un perfil heredado y listo para caer. En combinación con el perfil de Adobe SC y la fuente de datos de Analytics (SC/Insight), el perfil se puede implementar para exponer rápidamente nuevos modelos de atribución en los canales digitales.
title: Implementación del perfil de atribución
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Implementación del perfil de atribución{#deploying-the-attribution-profile}

El perfil de atribución es un perfil heredado y listo para caer. En combinación con el perfil de Adobe SC y la fuente de datos de Analytics (SC/Insight), el perfil se puede implementar para exponer rápidamente nuevos modelos de atribución en los canales digitales.

Después de guardar el perfil de atribución en el servidor primario, se necesitan dos pasos adicionales para integrarlo en el perfil actual dentro del [!DNL Profile] directorio: (1) Configure el archivo Profile.cfg y (2) Declare los campos obligatorios.

## Configuración del archivo Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Al igual que todos los perfiles, el perfil de atribución debe agregarse al [!DNL profile.cfg] archivo. Dado que el perfil de atribución depende del perfil de Adobe SC, el perfil de Adobe SC debe aparecer en primer lugar en el archivo de configuración antes del perfil de atribución.

>[!NOTE]
>
>Estos pasos requerirán una retransformación del conjunto de datos.

1. Abra el [!DNL profile.cfg] archivo en la carpeta de perfiles personalizada. (Abrir en [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Si el perfil de atribución no aparece en el archivo de configuración, agréguelo a la lista. ![](assets/new_profile_cfg.png)

1. Asegúrese de que la **[!UICONTROL Attribution]** cadena aparece debajo de la cadena de **[!UICONTROL Adobe SC]** perfil.

1. Guarde el [!DNL profile.cfg] archivo actualizado y, a continuación, guárdelo en el servidor desde el Administrador de perfiles.

## Declaración de los campos requeridos {#section-23d4273af0c34b7a85ae3430e2c9350e}

El perfil Atribución toma campos predefinidos y con una serie de transformaciones expone esos campos de formas nuevas y útiles a través de dimensiones extendidas. Para proporcionar el valor más inmediato, el perfil de atribución depende de los campos disponibles con el perfil de Adobe SC.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variables predeterminadas </th> 
   <th colname="col2" class="entry"> Nombre de campo y posición del descodificador (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canales de marketing </td> 
   <td colname="col2"> <p>x-va_close_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento de pedido </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchase eid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresos </td> 
   <td colname="col2"> x-ingresos, n.º 205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unidades </td> 
   <td colname="col2"> <p>x-unidades, n.º 204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Compruebe que estos campos están declarados en el grupo de decodificador utilizado para definir el origen de datos de Adobe Analytics. El grupo de decodificadores predeterminado se proporciona en [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Compruebe que estos campos están declarados en la **[!UICONTROL Fields]** sección del [!DNL SC Fields.cfg] archivo. Este archivo se encuentra en [!DNL Dataset\Log Processing\SC Fields.cfg].

## Adición de atribuciones y resolución de problemas {#section-168133a8a1a54e1281e532033878d246}

El perfil Atribución agregó un archivo de configuración, [!DNL 0a_Marketing Channels.cfg]que copia el valor del [!DNL x-va_closer_detail] en un nuevo campo llamado [!DNL x-marketing-channel], cuando el [!DNL x-va_instance_event] campo coincide con &quot;1&quot;. Tanto [!DNL x-va_closer_detail] como [!DNL x-va_instant_event] se descodifican de forma predeterminada y se pasan de la descodificación en los paquetes instalados disponibles al actualizar a la versión 6.2.

El [!DNL x-marketing-channel] campo se utiliza en la dimensión Simple denominada Canal de mercadotecnia.

>[!IMPORTANT]
>
>Si ha modificado los perfiles eliminando los campos que ya no se utilizan, comprobará que los campos [!DNL x-va_closer_detail] y [!DNL x-va_instance_event] se están descodificando y pasando para su uso.

Si faltan campos, recibirá un mensaje con el estado detallado:

```
<b>x-va_closer_detail</b> is not available
```

O bien

```
<b>x-va_instance_event</b> is not available
```

