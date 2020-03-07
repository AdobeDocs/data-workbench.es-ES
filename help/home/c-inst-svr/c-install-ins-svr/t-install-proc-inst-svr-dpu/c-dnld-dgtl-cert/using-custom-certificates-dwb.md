---
description: Instrucciones para usar certificados personalizados.
title: Uso de certificados personalizados en el área de trabajo de datos
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Uso de certificados personalizados en el área de trabajo de datos{#using-custom-certificates-in-data-workbench}

Instrucciones para usar certificados personalizados.

Un certificado utilizado por el cliente o el servidor de Área de trabajo de datos debe estar firmado por una CA de confianza (entidad emisora de certificados). Los clientes de Área de trabajo de datos reciben certificados firmados por la CA de Visual Sciences. El software Área de trabajo de datos confía en estos certificados, ya que el [!DNL trust_ca_cert.pem] (proporcionado junto con el software Insight y almacenado en el directorio **Certificados** de servidores y clientes) contiene un certificado *de CA* raíz para la CA de Visual Sciences. Estos certificados se utilizan tanto para la licencia del software como para la autenticación cuando los clientes y servidores se comunican entre sí mediante SSL. Solo los certificados emitidos por Visual Sciences CA pueden utilizarse para la licencia, pero otros certificados pueden utilizarse para la comunicación y la autenticación. Los certificados emitidos por entidades emisoras de certificados distintas de Visual Sciences se denominan a continuación certificados *personalizados.*

**Nota importante:** Para servidores y clientes, el software de Área de trabajo de datos utiliza los archivos de certificado instalados en el directorio de **certificados** del cliente o servidor o los certificados identificados explícitamente en su configuración. Sin embargo, también puede usar el almacén [de certificados de](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) Windows para clientes.

Las siguientes instrucciones describen los procedimientos que deben seguirse para utilizar los certificados personalizados para la comunicación entre los clientes y los servidores del área de trabajo de datos. No todos los detalles son un requisito difícil y se pueden utilizar variaciones diferentes en el proceso. Sin embargo, los procedimientos que figuran a continuación se han puesto a prueba para que funcionen.

## Configuración de certificados de cliente personalizados {#section-2083fd41973e451fa404e7a4ae4da591}

1. Agregue el certificado de la CA emisora al [!DNL trust_cert_ca.pem], que está instalado en el directorio de **certificados** del cliente y el de todos los servidores de cada clúster a los que se vaya a acceder mediante este certificado personalizado.

1. Obtenga un certificado personalizado para cada servidor del clúster con las siguientes condiciones:

   1. El certificado tiene el formato de [!DNL .pem] certificado.
   1. El certificado contiene su clave y no está cifrado (es decir, no tiene contraseña ni frase de contraseña).

      Un certificado contiene su clave con una de las siguientes líneas:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Una forma de eliminar la frase de contraseña de un [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. El certificado tiene el código NC, O, OU, etc. según sea necesario para este cliente en el archivo [!DNL Access Control.cfg] de los servidores.
   1. El certificado se emitió con un *propósito **** de *cliente* (o tanto *servidor* **como** *cliente*).

      Para verificar que un certificado tiene un código de propósito de servidor o cliente, se pueden utilizar los siguientes comandos:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para los certificados de servidor, ambos comandos deben generar:

      ```
      custom_communications_cert.pem: OK
      ```

      Para un certificado de cliente, solo se requiere el segundo comando para generar [!DNL OK].

1. Coloque el certificado en el directorio de **certificados** del cliente.
1. En [!DNL Insight.cfg] la sección *serverInfo* de cada clúster que desee utilizar este certificado, asegúrese de que se asigna un nombre al certificado de cliente *personalizado* , como:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configuración de certificados de servidor personalizados {#setting-up-custom-server-certificates}

En esta sección se asume que tiene un clúster que está activo y en ejecución, mediante certificados emitidos por Visual Sciences, y que la configuración sigue prácticas comunes (como el directorio *Componentes para Procesar Servidores* del maestro se sincroniza con los directorios *Componentes* de todos los DPU).

1. Agregue el certificado de la CA emisora al [!DNL trust_cert_ca.pem] que está instalado en todos los servidores del clúster y todos los clientes que necesitan comunicarse con este clúster.
1. Obtenga un certificado personalizado para cada servidor del clúster con estos requisitos:

   1. El certificado personalizado tiene el formato de [!DNL .pem] certificado.
   1. El certificado contiene su clave y no está cifrado (es decir, no tiene contraseña ni frase de contraseña).

      Un certificado contiene su clave si tiene una línea como:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Una forma de eliminar la frase de contraseña de un [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. El certificado tiene el mismo CN que el [!DNL server_cert.pem] instalado actualmente en el servidor.
   1. El certificado se emitió con un propósito de *servidor* y *cliente*.

      Para verificar que un certificado tiene un código de propósito de servidor o cliente, se pueden utilizar los siguientes comandos:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para los certificados de servidor, ambos comandos deben generar:

      ```
      custom_communications_cert.pem: OK
      ```

      Para un certificado de cliente, solo se requiere el segundo comando para generar [!DNL OK].

1. Instale el certificado personalizado de cada servidor en el directorio **Certificados** del servidor como [!DNL custom_communications_cert.pem].

1. Con un editor de texto, agregue la línea siguiente al archivo **Communications.cfg** en los directorios *Componentes* y *Componentes para Servidores* de procesamiento, directamente debajo de la primera línea ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Reinicie todos los servidores.

**Advertencia de error de certificado**

Cuando el servidor o cliente de Insight busca un certificado de **licencia** en el directorio de **certificados** , intenta validar todos los certificados (excepto [!DNL trust_ca_cert.pem]) con una copia codificada del certificado de CA de Insight, que falla en cualquier certificado personalizado presente en el directorio. El servidor emite esta advertencia:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Esta advertencia se puede ignorar de forma segura.
