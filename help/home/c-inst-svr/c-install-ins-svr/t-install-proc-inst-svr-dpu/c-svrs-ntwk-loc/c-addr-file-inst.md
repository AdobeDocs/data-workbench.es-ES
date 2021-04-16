---
description: El archivo de direcciones instalado en Insight Server contiene cuatro ubicaciones de red predefinidas.
title: El archivo de direcciones instalado en el servidor de Insight
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# El archivo de direcciones instalado en el servidor de Insight{#the-address-file-installed-on-insight-server}

El archivo de direcciones instalado en Insight Server contiene cuatro ubicaciones de red predefinidas.

El procedimiento de la siguiente sección describe cómo configurar este archivo.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 es una ubicación de red vacía y sin nombre que edita para asociar el nombre común de su [!DNL Insight Server] a su dirección IP. Si el servidor tiene varias direcciones IP, debe crear NetworkLocations adicionales.
* NetworkLocation 1 es la ubicación de red [!DNL Insight]. Si no establece explícitamente el parámetro NetworkLocation , [!DNL Insight] resuelve los nombres comunes a través de esta ubicación de red.

* NetworkLocation 2 es la ubicación de red [!DNL Insight Server]. Cuando [!DNL Insight Servers] opera en un clúster, utilizan esta ubicación de red para resolver nombres comunes para la comunicación entre servidores.

* NetworkLocation 3 es la ubicación de red [!DNL Report] Server. Si no establece explícitamente el parámetro NetworkLocation , [!DNL Report] resuelve los nombres comunes a través de esta ubicación de red.

## Para configurar el archivo de direcciones {#section-10caab9854a244e39b09071946f7bd27}

El siguiente procedimiento describe cómo configurar el archivo de dirección para definir una ubicación de red (o ubicaciones de red) para su [!DNL Insight Server].

1. Vaya a la carpeta [!DNL Addresses] en el directorio donde instaló [!DNL Insight Server] (por ejemplo, [!DNL C:\Adobe\Server\Addresses)].

1. Busque el archivo [!DNL server.address] y cambie el nombre de este archivo para que refleje el nombre común del servidor. Por ejemplo, si el nombre común fuera [!DNL server.mycompany.com], cambiaría el nombre del archivo [!DNL server.mycompany.com.address].

1. Abra el archivo cuyo nombre ha cambiado en un editor de texto como el Bloc de notas.
1. Edite NetworkLocation 0 para especificar el nombre común y la dirección IP del [!DNL Insight Server] como se muestra a continuación. Si su servidor tiene varias direcciones IP, utilice NetworkLocation 0 para especificar la dirección IP del servidor en la red local no enrutable (por ejemplo, su ubicación en la red interna).

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este valor... </th> 
   <th colname="col2" class="entry"> Especifique </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Dirección IP</i> </td> 
   <td colname="col2"> <p>La dirección IP numérica del equipo <span class="keyword"> Insight Server </span>. </p> <p>Ejemplo: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nombre común  </i> </td> 
   <td colname="col2"> <p>El nombre común asignado al certificado digital para <span class="keyword"> Insight Server </span>. </p> <p>Ejemplo: <span class="filepath"> server.mycompany.com </span></p> <p>Nota: Asegúrese de escribir este nombre exactamente como aparece en el certificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nombre de ubicación de red  </i> </td> 
   <td colname="col2"> <p>El nombre que desea asignar a la colección de nombres comunes y direcciones IP que representa NetworkLocation. El nombre debe ser único dentro del archivo de dirección. </p> <p>Ejemplo: Intranet corporativa </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Si su [!DNL Insight Server] tiene direcciones IP adicionales, cree una NetworkLocation adicional para cada dirección. (Una forma sencilla de hacerlo es hacer una copia de NetworkLocation que ha creado anteriormente y actualizar la dirección IP en la copia).

   Puede agregar el nuevo NetworkLocation al final del archivo de dirección o insertarlo entre las definiciones de NetworkLocation existentes. (La posición de un NetworkLocation dentro del archivo de dirección no es significativa; sin embargo, las [!DNL Insight], [!DNL Insight Server] y [!DNL Report] ubicaciones de red del servidor generalmente se colocan al final del archivo).

   Después de agregar las NetworkLocations necesarias, haga lo siguiente para volver a numerar los elementos del archivo:

   1. Actualice el recuento de elementos de la estructura Ubicaciones para que coincida con el número total de definiciones de NetworkLocation en el archivo. Por ejemplo, si el archivo contiene cuatro definiciones de NetworkLocation, la línea Ubicaciones sería la siguiente:

      ```
      Locations = vector: 4 items
      ```

   1. Actualice los números de elemento NetworkLocation para que NetworkLocations se numeren consecutivamente (comenzando por 0).
   Para ver un ejemplo de un archivo de dirección que define un [!DNL Insight Server] con dos direcciones IP, consulte el ejemplo en esta sección.

1. En las ubicaciones de red del [!DNL Insight] y [!DNL Report] Servidor, edite el parámetro Principal como se muestra a continuación para especificar el nombre de NetworkLocation que [!DNL Insight] y [!DNL Report] utilizan como ubicaciones de red predeterminadas. (Para ver un ejemplo del aspecto que tiene el parámetro Parent cuando está configurado, consulte el ejemplo en esta sección).

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   Si su [!DNL Insight Server] tiene una sola dirección IP y, por lo tanto, solo tiene una NetworkLocation, dirija el parámetro Parent a esa NetworkLocation. Si su [!DNL Insight Server] tiene varias direcciones IP, dirija el parámetro Parent a NetworkLocation que define la dirección a la que se conectan sus clientes [!DNL Insight] y [!DNL Report] con mayor frecuencia.

1. En la ubicación de red [!DNL Insight Server], edite el parámetro Parent como se muestra a continuación para señalar a NetworkLocation que el servidor utiliza para resolver nombres comunes de otros [!DNL Insight Servers] cuando opera en un clúster. (Aunque esta ubicación de red no se utiliza a menos que [!DNL Insight Server] funcione en un clúster, es recomendable, incluso en una configuración de servidor única, señalar el parámetro Parent a una ubicación de red que identifique la dirección IP interna del servidor.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

El siguiente ejemplo muestra un archivo de dirección completado. Este archivo define cinco ubicaciones de red.

* Los elementos 0 y 1 de NetworkLocation definen las ubicaciones de red denominadas &quot;MyCorporateIntranet&quot; e &quot;Internet&quot;. Estas ubicaciones de red definen dos direcciones IP diferentes para un servidor denominado [!DNL VS01.myCompany.com].
* El elemento 2 de NetworkLocation es la ubicación de red [!DNL Insight]. Esta es la ubicación de red predeterminada utilizada por [!DNL Insight]. En este ejemplo, la ubicación de red [!DNL Insight] hereda sus AddressDefinitions de NetworkLocation &quot;Internet&quot;.

* El elemento 3 de NetworkLocation es la ubicación de red [!DNL Insight Server]. Esta es la ubicación de red predeterminada que [!DNL Insight Server] utiliza cuando se comunica con otros servidores de un clúster. En este ejemplo, la ubicación de red [!DNL Insight Server] hereda sus AddressDefinitions de NetworkLocation &quot;MyCorporate Intranet&quot;.

* El elemento 4 de NetworkLocation es la ubicación de red [!DNL Report] Server. Esta es la ubicación de red predeterminada utilizada por [!DNL Report]. En este ejemplo, la ubicación de red del servidor [!DNL Report] hereda sus AddressDefinitions de NetworkLocation &quot;Internet&quot;.

   ```
   Locations = vector: 5 items 
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
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```
