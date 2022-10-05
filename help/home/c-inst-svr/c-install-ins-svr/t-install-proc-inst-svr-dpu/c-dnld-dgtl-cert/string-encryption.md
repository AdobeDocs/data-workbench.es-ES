---
description: Codifique contraseñas y otras cadenas al realizar comunicaciones entre el cliente y el servidor.
title: Cifrado de cadenas
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Cifrado de cadenas{#string-encryption}

{{eol}}

Codifique contraseñas y otras cadenas al realizar comunicaciones entre el cliente y el servidor.

Al comunicarse entre el cliente de Data Workbench (estación de trabajo) y el servidor, puede guardar un parámetro Value (como una contraseña) con el Tipo de *EncryptedString*. Esto oculta el parámetro y guarda la cadena en la variable *Almacén de credenciales de Windows* en el servidor con la clave correspondiente devuelta. Esto almacena principalmente las credenciales utilizadas en las exportaciones, pero puede utilizarse para cifrar cualquier parámetro.

* Se ha añadido una nueva carpeta al servidor\**EncryptStrings**.

   Aquí es donde establece el archivo de configuración para cifrar cadenas.

* Se agregó un nuevo archivo de configuración en Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Este archivo sondea la variable *Servidor* Carpeta \*EncryptStrings* para archivos de configuración de cifrado.

**Para cifrar una cadena**:

1. Cree un **EncryptedStrings.cfg** archivo de configuración de una cadena con estos campos definidos:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Valor* - Este campo contiene la cadena de texto sin formato que debe cifrarse.

      Solo es cifrado del lado del servidor. La variable *Valor* esta configuración solo está cifrada en el equipo servidor.

   * *Nombre* - Este campo contiene un valor que identifica la cadena cifrada.
   * *EncryptValue* - Este campo se deja vacío en el archivo de configuración de entrada. El valor cifrado se devuelve en este campo.

   Puede agregar varias **NameEncryptValuePair** para diferentes campos de codificación.

   >[!NOTE]
   >
   >Se eliminarán todos los campos de valor vacíos.

1. Guarde el **EncryptedStrings.cfg** al servidor\**EncryptStrings** carpeta.

**Archivo de salida**

Se generará un archivo de salida con el mismo nombre que el archivo de entrada con un &lt;*filename*>.*cifrados* extensión. Por ejemplo, si el nombre del archivo de entrada es *sample.cfg* entonces se llamará al archivo de salida *sample.cfg.encryption*.
