---
description: El perfil de atribución es un perfil heredado y listo para soltar. En combinación con el perfil SC de Adobe y la fuente de datos de Analytics (SC/Insight), el perfil se puede implementar para exponer rápidamente nuevos modelos de atribución en los canales digitales.
title: Implementación del perfil de atribución
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# Implementación del perfil de atribución{#deploying-the-attribution-profile}

{{eol}}

El perfil de atribución es un perfil heredado y listo para soltar. En combinación con el perfil SC de Adobe y la fuente de datos de Analytics (SC/Insight), el perfil se puede implementar para exponer rápidamente nuevos modelos de atribución en los canales digitales.

Después de guardar el perfil de atribución en el servidor principal, se necesitan dos pasos adicionales para integrarlo en el perfil actual dentro de [!DNL Profile] directorio: (1) Configure el archivo Profile.cfg y (2) Declare los campos obligatorios.

## Configuración del archivo Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Al igual que todos los perfiles, el perfil de atribución debe agregarse al [!DNL profile.cfg] archivo. Dado que el perfil de atribución depende del perfil SC de Adobe, el perfil SC de Adobe debe aparecer en primer lugar en el archivo de configuración antes del perfil de atribución.

>[!NOTE]
>
>Estos pasos requerirán una retransformación del conjunto de datos.

1. Abra el [!DNL profile.cfg] en la carpeta de perfil personalizada. (Abrir en [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Si el perfil de atribución no aparece en el archivo de configuración, agréguelo a la lista. ![](assets/new_profile_cfg.png)

1. Asegúrese de que la variable **[!UICONTROL Attribution]** La cadena se enumera debajo de la variable **[!UICONTROL Adobe SC]** cadena de perfil.

1. Guarde la actualización [!DNL profile.cfg] y, a continuación, guárdelo en el servidor desde el Administrador de perfiles.

## Declaración de los campos requeridos {#section-23d4273af0c34b7a85ae3430e2c9350e}

El perfil Atribución toma campos predefinidos y con una serie de transformaciones expone esos campos de formas nuevas y útiles a través de dimensiones extendidas. Para proporcionar el valor más inmediato, el perfil de atribución depende de los campos disponibles con el perfil SC de Adobe.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variables predeterminadas </th> 
   <th colname="col2" class="entry"> Nombre de campo y posición del decodificador (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canales de marketing </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento de pedido </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresos </td> 
   <td colname="col2"> x-revenue, n.º 205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unidades </td> 
   <td colname="col2"> <p>x-unidades, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Compruebe que estos campos están declarados en el grupo de decodificadores utilizado para definir el origen de datos de Adobe Analytics. El grupo de decodificadores predeterminado se proporciona en [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Compruebe que estos campos están declarados en la variable **[!UICONTROL Fields]** de la sección [!DNL SC Fields.cfg] archivo. Este archivo se puede encontrar en [!DNL Dataset\Log Processing\SC Fields.cfg].

## Adiciones de atribución y solución de problemas {#section-168133a8a1a54e1281e532033878d246}

El perfil de atribución ha añadido un archivo de configuración, [!DNL 0a_Marketing Channels.cfg], que copia el valor de la variable [!DNL x-va_closer_detail] en un nuevo campo llamado [!DNL x-marketing-channel], cuando la variable [!DNL x-va_instance_event] el campo coincide con &quot;1&quot;. Ambas [!DNL x-va_closer_detail] y [!DNL x-va_instant_event] se descodifican de forma predeterminada y se pasan de la descodificación a los paquetes instalados disponibles al actualizar a la versión 6.2.

La variable [!DNL x-marketing-channel] a continuación, se utiliza en la dimensión Simple denominada Canal de marketing.

>[!IMPORTANT]
>
>Si ha modificado los perfiles eliminando campos que no se usaban anteriormente y que ahora se están utilizando, comprobará que la variable [!DNL x-va_closer_detail] y [!DNL x-va_instance_event] los campos se están descodificando y pasando por ellos para su uso.

Si faltan campos, recibirá un mensaje con su estado detallado:

```
<b>x-va_closer_detail</b> is not available
```

o

```
<b>x-va_instance_event</b> is not available
```
