---
description: El almacén de certificados de Windows le permite almacenar el certificado y la clave privada del cliente en el almacén de certificados de Windows para la comunicación SSL con los servidores.
title: Almacén de certificados de Windows
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Almacén de certificados de Windows{#windows-certificate-store}

El almacén de certificados de Windows le permite almacenar el certificado y la clave privada del cliente en el almacén de certificados de Windows para la comunicación SSL con los servidores.

El almacén de certificados de Windows para el cliente es una nueva característica que le permite almacenar el certificado de comunicación SSL y la clave privada en el almacén de certificados de Windows en lugar de en el `Insight/Certificates/<CertName>.pem` archivo. Puede que sea preferible utilizar el almacén de certificados de Windows si utiliza el almacén de certificados para otras aplicaciones y desea realizar la administración de certificados en un lugar o para usuarios que disfrutan del registro de auditoría de Windows adicional que proporciona el almacén de certificados de Windows.

>[!NOTE]
>
>Las licencias con el servidor de licencias aún se mantienen mediante el `<Common Name>.pem` archivo existente y el certificado obtenido del almacén de certificados solo se utilizará para la comunicación con los servidores especificados.

## Requisitos previos {#section-69b18600052145ff8e5299b7123e69c5}

1. Debe tener acceso al [!DNL certmgr.msc] archivo con la capacidad de importar un certificado y una clave en el almacén **personal** . (Esto debería ser true de forma predeterminada para la mayoría de los usuarios de Windows).

1. El usuario que realiza la configuración debe tener una copia de la herramienta de línea de comandos **OpenSSL** .
1. El servidor y el cliente ya deben estar configurados para utilizar un certificado SSL personalizado, como se describe en [Uso de certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)personalizados, dando instrucciones para almacenar el certificado de cliente en el almacén de certificados de Windows en lugar de almacenarlo en el directorio **Certificados** .

## Configuración del almacén de certificados de Windows {#section-3629802122e947d4b4f63e8b732cfe27}

El almacén de certificados de Windows para clientes está habilitado siguiendo estos pasos:

**Paso 1: Importe el certificado SSL y la clave privada del usuario en el almacén de certificados de Windows.**

Al [usar certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) personalizados, se le indica que coloque el certificado SSL y la clave en el siguiente directorio:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

El nombre del certificado es `<Common Name>.pem` (por ejemplo, [!DNL Analytics Server 1.pem](no el [!DNL trust_ca_cert.pem] archivo).

Para poder importar el certificado y la clave privada, deben convertirse desde . [!DNL pem] a un [!DNL .pfx] formato, como [!DNL pkcs12.pfx] ).

1. Abra un símbolo del sistema o terminal y vaya al directorio:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
   ```

1. Ejecute [!DNL openssl] con los siguientes argumentos (con el nombre real del [!DNL .pem] archivo):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Si se le solicita, pulse **Intro** para omitir la introducción de una contraseña de exportación.

1. Ejecute [!DNL certmgr.msc] desde el símbolo del sistema, el menú de inicio o la línea de comandos.
1. Abra el almacén de certificados **personales** para el usuario actual.

   ![](assets/6_5_crypto_api_0.png)

1. Haga clic con el botón secundario en **Certificados** y, a continuación, haga clic en **Todas las tareas** > **Importar**.

   Asegúrese de que la opción Usuario **** actual está seleccionada y haga clic en **Siguiente**.

   ![](assets/6_5_crypto_api_4.png)

1. Haga clic en **Examinar** y seleccione el `<CommonName>.pfx` archivo que creó anteriormente. Para poder verla, deberá cambiar el cuadro desplegable de extensión de archivo de un certificado X.509 a Intercambio **de información** personal o a **Todos los archivos** .

   Seleccione el archivo, haga clic en **Abrir** y, a continuación, en **Siguiente**.

1. No introduzca una contraseña y asegúrese de que solo están seleccionadas las opciones **Marcar esta clave como exportable** e **Incluir todas las propiedades** extendidas.

   ![](assets/6_5_crypto_api_3.png)

   Haga clic en **Siguiente**.

1. Asegúrese de que está seleccionada la opción **Colocar todos los certificados en el almacén** siguiente y que el almacén de certificados que aparece es **personal**. (Si es un usuario avanzado, puede seleccionar otra tienda en este momento, pero tendrá que cambiar la configuración más adelante).

1. Haga clic en **Siguiente** y, a continuación, en **Finalizar**. Debe ver un cuadro de diálogo que le indica que la importación se ha realizado correctamente y ver el certificado en la carpeta Certificados del almacén.

   >[!NOTE]
   >
   >Preste especial atención a los campos **Emitidos** y **Emitidos por** . Los necesitarás en el próximo paso.

**Paso 2: Edite el archivo Insight.cfg.**

El [!DNL Insight.cfg] archivo debe editarse para dirigir el Área de trabajo de datos a fin de utilizar la función Almacén de certificados de Windows. Cada entrada de servidor de este archivo debe tener algunos parámetros adicionales especificados. Si se omiten los parámetros, la estación de trabajo utilizará de forma predeterminada la configuración de certificado existente. Si los parámetros están especificados pero tienen valores incorrectos, la estación de trabajo introducirá un estado de error y deberá consultar el archivo de registro para obtener información sobre el error.

1. Abra el archivo **Insight.cfg** (ubicado en el directorio de instalación de **Insight** ).

1. Desplácese hacia abajo hasta la entrada de servidor que desee configurar. Si desea utilizar el almacén de certificados de Windows para cada servidor, debe realizar estas modificaciones en cada entrada del vector de [!DNL serverInfo] objetos.
1. Agregue estos parámetros a su [!DNL Insight.cfg] archivo. Puede hacerlo desde la estación de trabajo o manualmente agregando los siguientes parámetros al [!DNL serverInfo] objeto. (Asegúrese de utilizar espacios en lugar de caracteres de tabulación y no cometa otros errores tipográficos o de sintaxis en este archivo. )

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   El valor booleano activa o desactiva la función. El nombre del certificado coincide con **Issuer To** en el administrador de certificados. El nombre del emisor del certificado coincide con **Emitido por** y el nombre **del** almacén debe coincidir con el nombre del almacén de certificados.

   >[!NOTE]
   >
   >El nombre &quot;Personal&quot; en el Administrador de certificados (certmgr.msc) hace referencia al almacén de certificados denominado **My.** En consecuencia, si importa el certificado de comunicación SSL y la clave (.PFX) en el almacén de certificados **personales** como se recomienda, debe establecer la cadena **SSL CryptoAPI Cert Store Name** en &quot;My&quot;. No funcionará establecer este parámetro en &quot;Personal&quot;. Es una característica del almacén de certificados de Windows.

   Puede obtener una lista completa de los almacenes de sistemas predefinidos aquí: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Es posible que el sistema tenga almacenes de certificados adicionales. Si desea utilizar una tienda que no sea &quot;Personal&quot; (como **Mi**), debe obtener el nombre canónico del almacén de certificados y proporcionarlo en el [!DNL Insight.cfg] archivo. (El nombre del almacén de sistemas &quot;Mi&quot; se denomina incoherentemente &quot;Mi&quot; y &quot;MI&quot; en la documentación de Windows. El parámetro no parece distinguir entre mayúsculas y minúsculas).

1. Después de agregar estos parámetros y comprobar que los valores coinciden con la lista en el Administrador de certificados de Windows, guarde el [!DNL Insight.cfg] archivo.

Ahora puede iniciar la estación de trabajo (o desconectar/volver a conectar con el servidor). El Área de trabajo de datos debe cargar el certificado y la clave desde el almacén de certificados y conectarse normalmente.

## Salida de registro {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Cuando no se encuentra un certificado o no es válido, se envía este mensaje de error al [!DNL HTTP.log] archivo.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>El marco de registro L4 puede habilitarse configurando el [!DNL L4.cfg] archivo (consulte con el administrador de cuentas para configurarlo).
