---
description: El Almacén de certificados de Windows le permite almacenar el certificado y la clave privada del cliente en el Almacén de certificados de Windows para la comunicación SSL con los servidores.
title: Almacén de certificados de Windows
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: ht
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Almacén de certificados de Windows {#windows-certificate-store}

El Almacén de certificados de Windows le permite almacenar el certificado y la clave privada del cliente en el Almacén de certificados de Windows para la comunicación SSL con los servidores.

El Almacén de certificados de Windows para el cliente es una nueva funcionalidad que permite almacenar el certificado de comunicación SSL y la clave privada en el Almacén de certificados de Windows en lugar de en el archivo `Insight/Certificates/<CertName>.pem`. Puede que sea preferible utilizar el Almacén de certificados de Windows si utiliza el almacén de certificados para otras aplicaciones y desea realizar la administración de certificados en un lugar o para usuarios que disfrutan del registro de auditoría de Windows adicional que proporciona el Almacén de certificados de Windows.

>[!NOTE]
>
>Las licencias con el servidor de licencias aún se mantienen mediante el archivo `<Common Name>.pem` existente y el certificado obtenido del almacén de certificados solo se utilizará para la comunicación con los servidores especificados.

## Requisitos previos {#section-69b18600052145ff8e5299b7123e69c5}

1. Debe tener acceso al archivo [!DNL certmgr.msc] con la capacidad de importar un certificado y una clave en el almacén **personal**. (Esto debería ser así de forma predeterminada para la mayoría de los usuarios de Windows).

1. El usuario que realiza la configuración debe tener una copia de la herramienta de línea de comandos **OpenSSL**.
1. El servidor y el cliente ya deben estar configurados para utilizar un certificado SSL personalizado, como se describe en [Uso de certificados personalizados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd), dando instrucciones para almacenar el certificado de cliente en el Almacén de certificados de Windows en lugar de almacenarlo en el directorio **Certificados**.

## Configuración del Almacén de certificados de Windows {#section-3629802122e947d4b4f63e8b732cfe27}

El Almacén de certificados de Windows para clientes está habilitado siguiendo estos pasos:

**Paso 1: Importe el certificado SSL y la clave privada del usuario en el Almacén de certificados de Windows.**

En [usar certificados personalizados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd), se le indica que coloque el certificado SSL y la clave en el siguiente directorio:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

El nombre del certificado es `<Common Name>.pem` (por ejemplo, [!DNL Analytics Server 1.pem], no el archivo [!DNL trust_ca_cert.pem]).

Para poder importar el certificado y la clave privada, deben convertirse desde el formato . [!DNL pem] a un formato [!DNL .pfx], como [!DNL pkcs12.pfx]).

1. Abra un símbolo del sistema o terminal y vaya al directorio:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
   ```

1. Ejecute [!DNL openssl] con los siguientes argumentos (con el nombre real del archivo [!DNL .pem]):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Si se le solicita, pulse **Intro** para omitir la introducción de una contraseña de exportación.

1. Ejecute [!DNL certmgr.msc] desde la línea de comandos, el menú de inicio o el símbolo del sistema.
1. Abra el almacén de certificados **personales** para el usuario actual.

   ![](assets/6_5_crypto_api_0.png)

1. Haga clic con el botón secundario en **Certificados** y, a continuación, haga clic en **Todas las tareas** > **Importar**.

   Asegúrese de que la opción **Usuario actual** está seleccionada y haga clic en **Siguiente**.

   ![](assets/6_5_crypto_api_4.png)

1. Haga clic en **Examinar** y seleccione el archivo `<CommonName>.pfx` que creó anteriormente. Para poder verlo, deberá cambiar el cuadro desplegable de extensión de archivo de un certificado X.509 a **Intercambio de información personal** o a **Todos los archivos**.

   Seleccione el archivo y haga clic en **Abrir** y, a continuación, en **Siguiente**.

1. No introduzca una contraseña y asegúrese de que solo están seleccionadas las opciones **Marcar esta clave como exportable** e **Incluir todas las propiedades extendidas**.

   ![](assets/6_5_crypto_api_3.png)

   Haga clic en **Siguiente**.

1. Asegúrese de que está seleccionada la opción **Colocar todos los certificados en el almacén siguiente** y que el almacén de certificados que aparece es **Personal**. (Si es un usuario avanzado, puede seleccionar otro almacén en este momento, pero tendrá que cambiar la configuración más adelante).

1. Haga clic en **Siguiente** y, a continuación, en **Finalizar**. Debe ver un cuadro de diálogo que le indica que la importación se ha realizado correctamente y ver el certificado en la carpeta Certificados del almacén.

   >[!NOTE]
   >
   >Preste especial atención a los campos **Emitidos a** y **Emitidos por**. Los necesitará en el próximo paso.

**Paso 2: Editar el archivo Insight.cfg.**

El archivo [!DNL Insight.cfg] debe editarse para dirigir Data Workbench para que use la función Almacén de certificados de Windows. Cada entrada de servidor de este archivo debe tener algunos parámetros adicionales especificados. Si se omiten los parámetros, la estación de trabajo utilizará de forma predeterminada la configuración de certificado existente. Si los parámetros están especificados pero tienen valores incorrectos, la estación de trabajo introducirá un estado de error y deberá consultar el archivo de registro para obtener información sobre el error.

1. Abra el archivo **Insight.cfg** (ubicado en el directorio de instalación de **Insight**).

1. Vaya hasta la entrada de servidor que desee configurar. Si desea utilizar el Almacén de certificados de Windows para cada servidor, debe realizar estas modificaciones en cada entrada del vector de objetos [!DNL serverInfo].
1. Añada estos parámetros a su archivo [!DNL Insight.cfg]. Puede hacerlo desde la estación de trabajo o manualmente agregando los siguientes parámetros al objeto [!DNL serverInfo]. (Asegúrese de utilizar espacios en lugar de caracteres de tabulación y no cometa otros errores tipográficos o de sintaxis en este archivo).

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   El valor booleano activa o desactiva la función. El nombre del certificado coincide con **Emitido a** en el administrador de certificados. El nombre del emisor del certificado coincide con **Emitido por** y el **Nombre del almacén** debe coincidir con el nombre del almacén de certificados.

   >[!NOTE]
   >
   >El nombre “Personal” en el Administrador de certificados (certmgr.msc) hace referencia al almacén de certificados denominado **My.** En consecuencia, si importa el certificado de comunicación SSL y la clave (.PFX) en el almacén de certificados **Personal**, tal y como se recomienda, debe establecer la cadena **SSL CryptoAPI Cert Store Name** en “My”. Si establece este parámetro en “Personal”, no funcionará. Es una característica del Almacén de certificados de Windows.

   Aquí puede obtener una lista completa de los almacenes de sistemas predefinidos: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Es posible que el sistema tenga almacenes de certificados adicionales. Si desea utilizar un almacén que no sea “Personal” (como **My**), debe obtener el nombre canónico del almacén de certificados y proporcionarlo en el archivo [!DNL Insight.cfg]. (El nombre del almacén de sistemas “My” se denomina como “My” y “MY” en la documentación de Windows. El parámetro no parece distinguir entre mayúsculas y minúsculas).

1. Después de agregar estos parámetros y comprobar que los valores coinciden con la lista en el Administrador de certificados de Windows, guarde el archivo [!DNL Insight.cfg].

Ahora puede iniciar la estación de trabajo (o desconectar/volver a conectar con el servidor). Data Workbench debe cargar el certificado y la clave desde el almacén de certificados y conectarse normalmente.

## Salida de registro {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Cuando no se encuentra un certificado o no es válido, se envía este mensaje de error al archivo [!DNL HTTP.log].

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>El marco de registro L4 puede habilitarse configurando el archivo [!DNL L4.cfg] (consulte con el administrador de cuentas para configurarlo).
