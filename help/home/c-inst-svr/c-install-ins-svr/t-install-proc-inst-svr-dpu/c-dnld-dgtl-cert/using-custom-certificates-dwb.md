---
description: Instrucciones para usar certificados personalizados.
title: Uso de certificados personalizados en Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Uso de certificados personalizados en Data Workbench{#using-custom-certificates-in-data-workbench}

{{eol}}

Instrucciones para usar certificados personalizados.

Un certificado utilizado por el cliente de Data Workbench o el servidor debe estar firmado por una CA de confianza (entidad emisora de certificados). Los clientes de Data Workbench reciben certificados firmados por Visual Sciences CA. Estos certificados son de confianza para el software de Data Workbench, ya que la variable [!DNL trust_ca_cert.pem] (se proporciona junto con el software de Insight y se almacena en la variable **Certificados** directorio de tanto servidores como clientes) contiene un *Certificado CA raíz* para Visual Sciences CA. Estos certificados se utilizan tanto para la licencia del software como para la autenticación cuando los clientes y servidores se comunican entre sí mediante SSL. Sólo los certificados emitidos por Visual Sciences CA pueden utilizarse para la concesión de licencias, pero otros certificados pueden utilizarse para la comunicación y la autenticación. Los certificados emitidos por entidades emisoras distintas de Visual Sciences se mencionan a continuación como *certificados personalizados.*

**Nota importante:** Para servidores y clientes, el software de Data Workbench utiliza los archivos de certificado instalados en el cliente o el servidor **Certificados** directorio o certificados explícitamente identificados en su configuración. Sin embargo, también puede usar la variable [Almacén de certificados de Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) para clientes.

Las siguientes instrucciones describen los procedimientos que se deben seguir para utilizar certificados personalizados para la comunicación entre clientes de Data Workbench y servidores. No todos los detalles son un requisito difícil y se pueden utilizar diferentes variaciones en el proceso. Sin embargo, los procedimientos que figuran a continuación se han puesto a prueba para que funcionen.

## Configuración de certificados de cliente personalizados {#section-2083fd41973e451fa404e7a4ae4da591}

1. Agregue el certificado de la CA emisora al [!DNL trust_cert_ca.pem], que se instala en el **Certificados** del cliente y del de cada servidor de cada clúster al que se vaya a acceder mediante este certificado personalizado.

1. Obtenga un certificado personalizado para cada servidor del clúster con las siguientes condiciones:

   1. El certificado tiene el formato de [!DNL .pem] certificado.
   1. El certificado contiene su clave y no está cifrado (es decir, no tiene ninguna frase de contraseña/contraseña).

      Un certificado contiene su clave con una de las siguientes líneas:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Una forma de quitar la frase de contraseña de una [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. El certificado tiene las letras CN, O, OU, etc. según sea necesario para este cliente en los servidores de [!DNL Access Control.cfg] archivo.
   1. El certificado se emitió con un *propósito&#42;&#42;&#42;* de *cliente* (o ambas *server* **y** *cliente*).

      Para verificar que un certificado tiene un código de propósito de servidor o cliente, se pueden utilizar los siguientes comandos:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para los certificados de servidor, ambos comandos deben arrojar:

      ```
      custom_communications_cert.pem: OK
      ```

      Para un certificado de cliente, solo se requiere el segundo comando para generar [!DNL OK].

1. Coloque el certificado en el **Certificados** directorio.
1. En [!DNL Insight.cfg] en el *serverInfo* para cada clúster que desee utilizar este certificado, asegúrese de que la variable *certificado de cliente personalizado* tiene un nombre, como:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configuración de certificados de servidor personalizados {#setting-up-custom-server-certificates}

En esta sección se asume que tiene un clúster que está en funcionamiento, que utiliza certificados emitidos por Visual Sciences y que la configuración sigue prácticas comunes (como la *Componentes para servidores de procesamiento* el directorio del maestro se sincroniza con el *Componentes* directorios de todas las DPU).

1. Agregue el certificado de la CA emisora al [!DNL trust_cert_ca.pem] que se instala en todos los servidores del clúster y en todos los clientes que necesitan comunicarse con este clúster.
1. Obtenga un certificado personalizado para cada servidor del clúster con estos requisitos:

   1. El certificado personalizado tiene el formato de [!DNL .pem] certificado.
   1. El certificado contiene su clave y no está cifrado (es decir, no tiene ninguna frase de contraseña/contraseña).

      Un certificado contiene su clave si tiene una línea como:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Una forma de quitar la frase de contraseña de una [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. El certificado tiene el mismo CN que el [!DNL server_cert.pem] instalado actualmente en el servidor.
   1. El certificado se expidió con el fin de *server* y *cliente*.

      Para verificar que un certificado tiene un código de propósito de servidor o cliente, se pueden utilizar los siguientes comandos:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para los certificados de servidor, ambos comandos deben arrojar:

      ```
      custom_communications_cert.pem: OK
      ```

      Para un certificado de cliente, solo se requiere el segundo comando para generar [!DNL OK].

1. Instale cada certificado personalizado del servidor en la variable **Certificados** directorio del servidor como [!DNL custom_communications_cert.pem].

1. Con un editor de texto, agregue la línea siguiente a **Communications.cfg** en *Componentes* y *Componentes para servidores de procesamiento* directamente debajo de la primera línea ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Reinicie todos los servidores.

**Acerca de la advertencia de errores de certificados**

Cuando el servidor o cliente de Insight está buscando un **licencia** en el **Certificados** , intenta validar todos los certificados (excepto [!DNL trust_ca_cert.pem]), frente a una copia codificada del certificado de Insight CA, que falla en cualquier certificado personalizado presente en el directorio. El servidor emite esta advertencia:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Esta advertencia se puede ignorar con seguridad.
