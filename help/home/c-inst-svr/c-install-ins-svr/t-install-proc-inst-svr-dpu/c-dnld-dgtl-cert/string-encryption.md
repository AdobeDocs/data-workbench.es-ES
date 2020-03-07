---
description: Codificar contraseñas y otras cadenas al comunicarse entre el cliente y el servidor.
title: Cifrado de cadenas
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Cifrado de cadenas{#string-encryption}

Codificar contraseñas y otras cadenas al comunicarse entre el cliente y el servidor.

Al comunicarse entre el cliente de Área de trabajo de datos (estación de trabajo) y el servidor, puede guardar un parámetro Value (como una contraseña) con el tipo de *EncryptedString*. Esto oculta el parámetro y guarda la cadena en el almacén de credenciales de *Windows* en el servidor con la clave correspondiente devuelta. Principalmente almacena las credenciales utilizadas en las exportaciones, pero se pueden usar para cifrar cualquier parámetro.

* Se agregó una nueva carpeta en Server\**EncryptStrings**.

   Aquí es donde se establece el archivo de configuración para cifrar cadenas.

* Se ha añadido un nuevo archivo de configuración en Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Este archivo sondea la carpeta *Server*\*EncryptStrings* para los archivos de configuración de codificación.

**Para cifrar una cadena**:

1. Cree un archivo de configuración **EncryptedStrings.cfg** para una cadena con estos campos definidos:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Valor* : este campo contiene la cadena de texto sin formato que debe cifrarse.

      Solo es cifrado del lado del servidor. La configuración del *valor* solo se cifra en el equipo servidor.

   * *Nombre* : este campo contiene un valor que identifica la cadena cifrada.
   * *EncryptValue* : este campo se dejará vacío en el archivo de configuración de entrada. El valor cifrado se devolverá en este campo.
   Puede agregar varios valores **NameEncryptValuePair** para distintos campos de codificación.

   >[!NOTE]
   >
   >Se eliminarán todos los campos de valor vacíos.

1. Guarde el archivo **EncryptedStrings.cfg** en la carpeta Server\**EncryptStrings**.

**Archivo de salida**

Se generará un archivo de salida con el mismo nombre que el archivo de entrada con un &lt;*nombre de archivo*>.*extensión cifrada* . Por ejemplo, si el nombre del archivo de entrada es *sample.cfg* , el nombre del archivo de salida será *sample.cfg.encrypt*.
