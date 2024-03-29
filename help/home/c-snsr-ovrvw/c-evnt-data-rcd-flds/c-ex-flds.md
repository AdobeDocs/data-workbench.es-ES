---
description: El sensor, cuando se utiliza en un servidor, puede recopilar campos de datos de evento de cualquier solicitud HTTP válida, encabezado de respuesta o variable disponible para él a través de la API del servidor.
title: Campos ampliables
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# Campos ampliables{#extensible-fields}

{{eol}}

El sensor, cuando se utiliza en un servidor, puede recopilar campos de datos de evento de cualquier solicitud HTTP válida, encabezado de respuesta o variable disponible para él a través de la API del servidor.

Para recopilar estos campos de datos, debe especificar los campos de encabezado o las variables que desee en la variable [!DNL txlogd.conf] archivo de configuración para [!DNL Sensor].

* [Solicitar encabezados](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variables de servidor](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Solicitar encabezados {#section-22766692b45546d8bfc93dbe3bc9368f}

A continuación se muestra la sintaxis para especificar un campo de encabezado de solicitud que se va a recopilar (por ejemplo, host, aceptar-codificación, mantener activo, etc.) en [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Los datos recopilados se registran mediante [!DNL Sensor] a un campo denominado &quot;cs(RequestHeaderName)&quot; en la variable [!DNL .vsl] archivos creados por el [!DNL data workbench server]. Por ejemplo, para recopilar el valor del encabezado de solicitud específico del encabezado de solicitud &quot;Host&quot;, debe escribir &quot;Host LogHeader&quot; en [!DNL txlogd.conf]. Los datos se registran en el campo &quot;cs(Host)&quot; del registro de datos del evento.

## Variables de servidor {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] puede recopilar campos de datos de encabezados de respuesta o variables de servidor accesibles desde API utilizando entradas de SpecialLogField que incluya en el [!DNL txlogd.conf] archivo. También puede usar entradas &quot;SpecialLogField&quot; además o en lugar de entradas &quot;LogHeader&quot; para recopilar encabezados de solicitud. Consulte [Solicitar encabezados](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). La opción de encabezados de solicitud permanece disponible para la compatibilidad con versiones anteriores.

A continuación se muestra la sintaxis para especificar un &quot;SpecialLogField&quot; en [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

La siguiente tabla incluye descripciones de los componentes de una entrada &quot;SpecialLogField&quot;.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(campo de registro) </td> 
   <td colname="col2"> El nombre del campo en el que se registran los datos recopilados en el registro de datos de evento y el <span class="filepath"> .vsl </span> archivos creados por el <span class="keyword"> servidor de data workbench </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Cualquier variable de servidor disponible para <span class="wintitle"> Sensor </span> a través de la API del servidor </p> <p>Ejemplo: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log o vys_cookie </p> <p>Para especificar el escenario, es necesario que sepa qué variables de servidor están disponibles para vys_log y vys_cookie. </p> <p>Ejemplo: Para serverVariable response.p3p, debe introducir vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obtener ayuda sobre la configuración [!DNL Sensor] para recopilar campos de registro de datos de evento ampliables, póngase en contacto con los servicios de consultoría de Adobe.
