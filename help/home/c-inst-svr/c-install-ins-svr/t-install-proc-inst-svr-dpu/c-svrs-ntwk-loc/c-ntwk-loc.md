---
description: Conceptualmente, el archivo de dirección tiene el mismo propósito que el archivo ETC&bsol;HOSTS en una máquina en red.
title: Ubicaciones de red
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Ubicaciones de red{#network-locations}

{{eol}}

Conceptualmente, el archivo de dirección tiene el mismo propósito que el archivo ETC&amp;bsol;HOSTS en una máquina en red.

Sin embargo, a diferencia del archivo HOSTS, que describe una sola colección de nombres, el archivo de dirección contiene varias colecciones de nombres denominadas ubicaciones de red.

Una ubicación de red es una colección con nombre de definiciones de direcciones. Cada definición de dirección de la colección asocia un nombre común con una dirección IP.

En el archivo de dirección, se define una ubicación de red en una estructura denominada NetworkLocation. En el siguiente ejemplo, NetworkLocation define una ubicación de red denominada &quot;MyCorporate Intranet&quot;. Contiene una definición de dirección que asigna el nombre común [!DNL VS01.myCompany.com] a la dirección IP &quot;10.2.1.70&quot;.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Como se muestra en el ejemplo anterior, la estructura NetworkLocation consta de tres parámetros principales:

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Direcciones </td> 
   <td colname="col2"> Define cero o más definiciones de dirección. Cada AddressDefine asocia un nombre común con una dirección IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Asigna un nombre a NetworkLocation. El nombre asignado a NetworkLocation debe ser único dentro del archivo de dirección. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> <p>Especifica el nombre de otro NetworkLocation cuyos miembros están incluidos en este NetworkLocation. Este parámetro permite que un NetworkLocation amplíe otro. </p> <p>Puede establecer el parámetro Principal en "DNS" para ampliar NetworkLocation al sistema DNS normal del cliente. </p> <p>Ejemplo: Principal = cadena: DNS </p> <p>Cuando DNS es el principal, los clientes intentan resolver un nombre común usando el sistema DNS del equipo cliente cuando no pueden resolver el nombre a través de NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>
