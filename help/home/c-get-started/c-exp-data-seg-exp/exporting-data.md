---
description: Ahora puede usar CSV, TSV, Exportación de segmentos y Exportación de segmentos con encabezado usando los protocolos FTP y SFTP para exportar archivos de segmentos desde el cliente (estación de trabajo) al servidor.
title: Exportación de un segmento mediante el envío S/FTP
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
exl-id: 0f1dc0a1-f376-47fb-887c-612a654ed0f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 4%

---

# Exportación de un segmento mediante el envío S/FTP{#export-a-segment-using-s-ftp-delivery}

{{eol}}

Ahora puede usar CSV, TSV, Exportación de segmentos y Exportación de segmentos con encabezado usando los protocolos FTP y SFTP para exportar archivos de segmentos desde el cliente (estación de trabajo) al servidor.

**Configuración de archivos de configuración de exportación S/FTP**

Para establecer la configuración de exportación, se agregaron dos nuevos archivos de configuración de exportación para configurar una conexión FTP o SFTP, lo que permite elegir los detalles del servidor en la *FTPServerInfo.cfg* y las credenciales se seleccionarán de *FTPUserCredentials* carpeta (correspondiente al nombre de servidor indicado en los argumentos de comando).

* Configure las variables **FTPServerInfo.cfg** archivo.

   Introduzca la información del servidor FTP y establezca los reintentos de conexión permitidos desde la estación de trabajo. Edite desde la estación de trabajo o el servidor en  [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]**archivo.

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* Configure las variables **FTPUserCredentials.cfg** archivo.

   Introduzca las credenciales de usuario para conectarse a los servidores mediante el  [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]**archivo. Este archivo contiene las credenciales de usuario necesarias para conectarse a los servidores y solo se puede editar desde el servidor y no desde la estación de trabajo (cliente).

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >Asegúrese de que las claves SSH que genere para la autenticación tengan el formato idéntico al que se genera cuando utiliza el comando SSH Keygen.
   >
   >Ejemplo de generación de claves SSH mediante keygen:
   >
   >
   ```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Hay seis parámetros en la variable **FTPUserCredentials.cfg** archivo necesario para varias transferencias FTP o SFTP.

   1. *Nombre de usuario*
   1. *Contraseña de usuario*
   1. *Nombre del servidor*
   1. *Ruta de clave pública*
   1. *Ruta de clave privada*
   1. *Frase de contraseña*

   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protocol </th> 
      <th colname="col2" class="entry"> Parámetros </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>Defina los parámetros 1, 2 y 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP mediante autenticación de contraseña </p> </td> 
      <td colname="col2"> <p>Establezca los parámetros 1, 2, 3 cuando la transferencia utiliza autenticación de contraseña (-p en los argumentos de comando). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP mediante autenticación de claves </p> </td> 
      <td colname="col2"> <p>Establezca los parámetros 1, 2, 3, 4, 5, 6 cuando la transferencia utiliza autenticación de claves (-k en los argumentos de comando). </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Configuración de los comandos de exportación de FTP y SFTP**

1. Abra una tabla de exportación.

   En la estación de trabajo, haga clic con el botón derecho en un *Tabla de detalles* y elija uno de los tipos de exportación: CSV , TSV, Exportación de segmentos o Exportación de segmentos con encabezado. O abra el [!DNL .export] desde un símbolo del sistema y edite (consulte [Configuración de segmentos para exportación](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. En el *Comando* , configúrelo para que apunte al ejecutable de exportación:

   ```
   ExportIntegration.exe
   ```

1. Configure las variables *Argumentos de comando* campos como se muestra a continuación para el protocolo y la autenticación necesarios:

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (si se utiliza una contraseña para la autenticación)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** (si se utilizan claves para la autenticación)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

Todos los argumentos de comando son obligatorios y deben introducirse como se muestra.

## Exportación S/FTP con claves privadas/públicas {#section-0534424d79a54a47b82594cfa7b3c17f}

Para implementar la exportación FTP y SFTP mediante claves privadas y públicas, coloque los archivos de configuración en estas carpetas:

* Lugar **FTPServerInfo.cfg** en el [!DNL Server/Addresses/Export/] carpeta.
* Lugar **FTPUserCredentials.cfg** en el [!DNL Server/Admin/Export/] carpeta.

Se incluyen seis parámetros en la variable **FTPServerInfo.cfg** archivo:

1. *Nombre de usuario*
1. *Contraseña de usuario*
1. *Nombre del servidor*
1. *Ruta de clave pública*
1. *Ruta de acceso de clave privada —* Coloque la ruta de la clave privada en el archivo de configuración sin la extensión, por ejemplo:

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Frase de contraseña*

FTP utiliza los parámetros 1, 2 y 3.

SFTP utiliza los parámetros 1, 2 y 3 cuando la transferencia utiliza la autenticación mediante contraseña.

SFTP utiliza los seis parámetros cuando la transferencia se realiza mediante autenticación de claves. Por ejemplo, si utiliza claves para la autenticación:

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

Los archivos de configuración deben estar en la ubicación correcta.

>[!NOTE]
>
>Las claves públicas deben señalar a una **.pem** y no a una ubicación de carpeta. Puede crear claves utilizando una función de generación de claves SSH de aplicaciones como Cygwin. (Putty genera claves en un formato .ppk que no se admite.)
