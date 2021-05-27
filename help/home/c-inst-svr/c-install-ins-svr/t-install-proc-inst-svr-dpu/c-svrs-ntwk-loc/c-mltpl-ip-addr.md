---
description: Si los clientes pueden acceder a un servidor de Insight a través de varias redes (por ejemplo, a través de la intranet corporativa y a través de Internet), el archivo de dirección debe definir una ubicación de red independiente para cada una de las direcciones IP del servidor.
title: Varias direcciones IP para un servidor de Insight
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Varias direcciones IP para un servidor de Insight{#multiple-ip-addresses-for-an-insight-server}

Si los clientes pueden acceder a un servidor de Insight a través de varias redes (por ejemplo, a través de la intranet corporativa y a través de Internet), el archivo de dirección debe definir una ubicación de red independiente para cada una de las direcciones IP del servidor.

Por ejemplo, si el servidor [!DNL VS01.myCompany.com] tiene una dirección IP de 10.2.1.70 en una red interna y una dirección IP de 65.196.125.167 en Internet, el archivo de dirección incluiría una ubicación de red para cada una de las direcciones, como se ilustra en el ejemplo siguiente:

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
1 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 65.196.125.167
      Name = string: VS01.myCompany.com
  Name = string: Internet
  Parent = string:
```

Cuando los usuarios se conectan a un [!DNL Insight Server], utilizan el parámetro NetworkLocation (en la interfaz de usuario del cliente) para especificar la ubicación de red a través de la cual desean que se resuelva el nombre común del servidor. Por ejemplo, dado un archivo de dirección con los dos NetworkLocations mostrados arriba, un usuario establecería el parámetro NetworkLocation en &quot;MyCorporate Intranet&quot; para conectarse a [!DNL Insight Server] a través de la red interna y a &quot;Internet&quot; para conectarse al servidor a través de Internet.
