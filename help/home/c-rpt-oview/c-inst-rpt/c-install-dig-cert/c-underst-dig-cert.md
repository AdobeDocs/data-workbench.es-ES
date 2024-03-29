---
description: Adobe utiliza certificados digitales X.509 para identificar y autenticar los componentes de cliente y servidor que conforman una implementación.
title: Explicación de los certificados digitales
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 54%

---

# Explicación de los certificados digitales{#understanding-digital-certificates}

{{eol}}

Adobe utiliza certificados digitales X.509 para identificar y autenticar los componentes de cliente y servidor que conforman una implementación.

Al instalar [!DNL Report Server], debe instalar el certificado digital que autoriza a un individuo con nombre (por ejemplo, Jane Smith) a utilizar la aplicación cliente instalada.

>[!NOTE]
>
>Si necesita migrar [!DNL Report Server] a otro equipo u otro usuario designado, debe obtener un nuevo certificado de Adobe. Para ello, contacte con el Servicio de atención al cliente de Adobe.

[!DNL Report Server] presenta este certificado digital para obtener acceso a un componente de servidor. Un administrador del componente de servidor puede restringir el acceso a los recursos del servidor en función del nombre común o los valores de unidad organizativa que aparecen en el certificado del cliente.

Los certificados digitales X.509 instalados con las aplicaciones de Adobe también permiten que sus componentes de cliente y servidor intercambien información a través de Secure Sockets Layer (SSL). SSL asegura las transmisiones a través de HTTP mediante un sistema de cifrado de claves públicas y privadas. La implementación de SSL por parte de Adobe admite claves RSA de 1024 bits y utiliza un algoritmo de cifrado RC4 de 128 bits.

Además de la seguridad, el certificado digital que instale también funciona como una clave de licencia que le permite ejecutar el [!DNL Report Server]. Para funcionar correctamente, un certificado digital debe estar bloqueado por nodos y ser actual, o la aplicación no se iniciará.

## Certificados bloqueados por nodos {#section-3338f1558e7844888dced8f395888744}

Un certificado bloqueado por nodos es un certificado digital que se ha registrado en el equipo en el que está instalado. El bloqueo de nodos asocia permanentemente un certificado con un identificador de nodo específico (un valor que identifica de forma exclusiva a un equipo concreto). Para que el nodo bloquee el certificado, el equipo debe tener acceso a Internet al servidor de licencias de Adobe o a un servidor proxy que tenga acceso al servidor de licencias.

Si está realizando la instalación en un equipo que no puede acceder a Internet, debe obtener e instalar un certificado prebloqueado especial, tal como se describe en [Uso de certificados digitales en equipos sin acceso a Internet](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) en esta página.

Si va a realizar la instalación en un equipo que pueda acceder a Internet, el certificado digital se bloquea automáticamente la primera vez que se inicie [!DNL Report Server]. Después de estar bloqueado por nodos, el certificado no se puede usar en ningún otro equipo. Si necesita migrar [!DNL Report Server] a otro equipo, debe obtener un certificado nuevo y desbloqueado de Adobe.

## Certificados actuales {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Además de estar bloqueado por nodos, un certificado digital debe estar actualizado. Para mantenerse actualizado, el certificado debe revalidarse de forma regular (generalmente cada 30 días, pero puede variar según el acuerdo con el Adobe). Si el equipo tiene acceso a Internet, el proceso de validación es completamente transparente. [!DNL Report Server] se conecta automáticamente al servidor de licencias y vuelve a validar el certificado cuando es necesario. Si el equipo no tiene acceso a Internet, debe instalar manualmente los certificados actualizados tal y como se describe en la sección siguiente.

## Uso de certificados digitales en equipos sin acceso a Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Si está realizando la instalación en un equipo que no puede acceder a Internet, debe solicitar un certificado prebloqueado para la instalación de [!DNL Report Server]. Un certificado prebloqueado es un certificado digital que Adobe fija manualmente al identificador de nodo del equipo.

Para solicitar un certificado prebloqueado, debe enviar el identificador de nodo y el número de certificado al Servicio de atención al cliente de Adobe. Para obtener el identificador de nodo de su equipo, póngase en contacto con el servicio de atención al cliente de Adobe para solicitar el Adobe [!DNL Node Identifier] utilidad. También puede obtener el identificador de nodo de la alerta que [!DNL Report Server] problemas cuando intenta conectarse al servidor de licencias y no puede. Cuando reciba el certificado prebloqueado, instálelo tal como se describe en los dos últimos pasos de los [procedimientos de instalación de certificados digitales](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

Cuando sea necesario volver a validar el certificado, debe descargar un nuevo certificado validado del servidor de licencias y volver a instalarlo en el equipo (a menos que el acuerdo con el Adobe establezca lo contrario).
