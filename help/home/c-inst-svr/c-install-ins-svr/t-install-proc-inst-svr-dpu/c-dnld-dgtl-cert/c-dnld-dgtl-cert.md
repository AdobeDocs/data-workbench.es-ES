---
description: Información general sobre certificados digitales y procedimientos para descargarlos e instalarlos.
solution: Analytics
title: Descarga e instalación de certificados digitales
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: ht
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: ht
source-wordcount: '916'
ht-degree: 100%

---


# Descarga e instalación de certificados digitales {#downloading-and-installing-the-digital-certificates}

Información general sobre certificados digitales y procedimientos para descargarlos e instalarlos.

* [Explicación de los certificados digitales](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificados bloqueados por nodos](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificados actuales](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Uso de certificados digitales en equipos sin acceso a Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procedimientos de instalación de certificados digitales](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Explicación de los certificados digitales {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe utiliza certificados digitales X.509 para identificar y autenticar los componentes de cliente y servidor que conforman una implementación.

Al instalar un componente de servidor ([!DNL Insight Server] o [!DNL Repeater]), debe instalar el certificado digital emitido por Adobe para el componente. Si necesita migrar la aplicación de Adobe a otro equipo, debe obtener un nuevo certificado de Adobe. Para ello, contacte con el Servicio de atención al cliente de Adobe.

El nombre común que aparece en este certificado identifica al servidor por un nombre de dominio especificado (por ejemplo, [!DNL vs001a.mycompany.com]). Cuando un cliente de servidor se conecta a este servidor, el servidor presenta este certificado como prueba de que es realmente el servidor solicitado por el cliente.

Del mismo modo, al instalar un cliente de servidor (por ejemplo, [!DNL Insight] o [!DNL Report]), debe instalar el certificado digital que autoriza a un individuo con nombre (por ejemplo, Jane Smith) a utilizar la aplicación cliente instalada. Si necesita migrar la aplicación Adobe a otro equipo u otro usuario designado, debe obtener un nuevo certificado de Adobe. Para ello, contacte con el Servicio de atención al cliente de Adobe.

La aplicación cliente presenta este certificado digital para obtener acceso a un componente de servidor. Un administrador del componente de servidor puede restringir el acceso a los recursos del servidor en función del nombre común o los valores de unidad organizativa que aparecen en el certificado del cliente.

Los certificados digitales X.509 instalados con las aplicaciones de Adobe también permiten que sus componentes de cliente y servidor intercambien información a través de Secure Sockets Layer (SSL). SSL asegura las transmisiones a través de HTTP mediante un sistema de cifrado de claves públicas y privadas. La implementación de SSL por parte de Adobe admite claves RSA de 1024 bits y utiliza un algoritmo de cifrado RC4 de 128 bits.

Además de la seguridad, los certificados digitales que instale también funcionan como claves de licencia que le permiten ejecutar el software de Adobe instalado. Para funcionar correctamente, un certificado digital debe estar bloqueado por nodos y ser actual y válido o la aplicación no se podrá iniciar.

## Cifrado de cadenas {#section-8abe6b2d95704d38a04137d5c4602f0b}

Consulte [Cifrado de cadenas](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) para cifrar contraseñas.

## Certificados bloqueados por nodos {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Un certificado bloqueado por nodos es un certificado digital que se ha registrado en el equipo en el que está instalado. El bloqueo de nodos asocia permanentemente un certificado con un identificador de nodo específico (un valor que identifica de forma exclusiva a un equipo concreto). Para que el nodo bloquee el certificado, el equipo debe tener acceso a Internet al servidor de licencias de Adobe o a un servidor proxy que tenga acceso al servidor de licencias.

Si va a realizar la instalación en un equipo que no puede acceder a Internet, debe obtener e instalar un certificado prebloqueado especial, tal como se describe en [Uso de certificados digitales en equipos sin acceso a Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

Si realiza la instalación en un equipo que puede acceder a Internet, el certificado digital se bloquea automáticamente la primera vez que inicie el producto de Adobe. Después de estar bloqueado por nodos, el certificado no se puede usar en ningún otro equipo. Si necesita migrar el producto de Adobe a otro equipo, debe obtener un certificado nuevo y desbloqueado de Adobe.

## Certificados actuales {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Además de estar bloqueado por nodos, un certificado digital debe estar actualizado. Para mantenerse actualizado, el certificado debe volverse a validar de forma regular (generalmente cada 30 días, pero puede variar según el acuerdo con Adobe). Si el equipo tiene acceso a Internet, el proceso de validación es completamente transparente. El producto de Adobe se conecta automáticamente al servidor de licencias y vuelve a validar el certificado cuando es necesario. Si el equipo no tiene acceso a Internet, debe instalar manualmente los certificados actualizados tal y como se describe en la sección siguiente.

## Uso de certificados digitales en equipos sin acceso a Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Si está realizando la instalación en un equipo que no puede acceder a Internet, debe solicitar un certificado prebloqueado para la instalación de [!DNL Insight Server]. Un certificado prebloqueado es un certificado digital que Adobe fija manualmente al identificador de nodo del equipo.

Para solicitar un certificado prebloqueado, debe enviar el identificador de nodo y el número de certificado al Servicio de atención al cliente de Adobe. Para obtener el identificador de nodo de su equipo, contacte con el Servicio de atención al cliente de Adobe para solicitar la utilidad Identificador de nodo de Adobe. También puede obtener el identificador de nodo de la alerta que el software de Adobe emite al intentar conectarse al servidor de licencias y no poder hacerlo.

Cuando reciba el certificado prebloqueado, instálelo tal como se describe en los dos últimos pasos de los [procedimientos de instalación de certificados digitales](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). Cuando sea necesario volver a validar el certificado, debe descargar un certificado nuevo y validado del servidor de licencias y volver a instalarlo en el equipo.

## Procedimientos de instalación de certificados digitales {#section-19f31676aad344a98e26e4fca1fad03b}

**Para descargar e instalar el certificado digital**

1. Abra el explorador web y vaya a [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Es posible que el explorador le pida que presente un certificado digital en este momento. Si es así, haga clic en **[!UICONTROL Cancel]** para cerrar el cuadro de diálogo.

1. En la pantalla de inicio de sesión, introduzca el **[!UICONTROL Account Name]** y el **[!UICONTROL Password]** que recibió de Adobe y, a continuación, haga clic en **[!UICONTROL login]**.

1. Busque el certificado que se ha emitido para su [!DNL Insight Server] y, a continuación, haga clic en el icono asociado a dicho certificado.

   >[!NOTE]
   >
   >Anote el nombre común asignado a este certificado. Este nombre se utiliza en un paso posterior.

1. Cuando se le pregunte si desea guardar el certificado, haga clic en **[!UICONTROL Save]**. (Tenga en cuenta que el nombre del archivo coincide con el nombre común asociado al certificado).
1. Descargue el archivo en la carpeta [!DNL Certificates] del directorio donde instaló [!DNL Insight Server]. Esta carpeta ya contiene un archivo de certificado denominado [!DNL trust_ca_cert.pem]. Este archivo de certificado siempre debe estar presente.

1. Cambie el nombre del archivo de certificado descargado a:

[!DNL server_cert.pem]

