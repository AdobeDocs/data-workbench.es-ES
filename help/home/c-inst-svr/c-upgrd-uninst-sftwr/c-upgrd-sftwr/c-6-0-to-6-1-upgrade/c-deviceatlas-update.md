---
description: El archivo JSON de DeviceAtlas ahora se distribuirá en un archivo .bundle (un archivo .tar.gz renombrado) junto con los archivos DeviceAtlas.dll y DeviceAtlas64.dll.
solution: Analytics
title: Distribución de DeviceAtlas
topic: Data workbench
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribución de DeviceAtlas{#deviceatlas-distribution}

El archivo JSON de DeviceAtlas ahora se distribuirá en un archivo .bundle (un archivo .tar.gz renombrado) junto con los archivos DeviceAtlas.dll y DeviceAtlas64.dll.

Cuando el administrador actualiza Insight Server a la versión 6.0, el archivo DeviceAtlas.bundle se incluye con el paquete de actualización en el perfil Software y Docs (perfil de softdocs) ubicado en:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

El archivo DeviceAtlas.bundle se extrae en [!DNL Server\Lookups\DeviceAtlas].

El archivo DeviceAtlas.bundle debe colocarse en un directorio sincronizado con los DPU y el archivo DeviceAtlas.cfg correspondiente al nuevo DeviceAtlasComponent debe colocarse en el directorio &quot;Componentes para servidores de procesamiento&quot; del maestro de sincronización. Cuando se cambia el archivo DeviceAtlas.bundle, la próxima llamada de búsqueda de DeviceAtlas obtendrá resultados basados en la API o el archivo JSON actualizados.

## Modificar el archivo Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

Las transformaciones de DeviceAtlas ya no necesitarán especificar la ruta al archivo JSON. Cualquier DeviceAtlasTransformation anterior definida en el archivo conversion.cfg ya no debe incluir el parámetro File que apunta al archivo JSON confundido.

Este ejemplo de archivo Transformation.cfg muestra el argumento File que se debe eliminar para evitar confusiones. (Dejarlo allí no causará daño, sino confusión potencial porque será ignorado).

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## Modificar el archivo DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Este es un ejemplo del [!DNL component] argumento requerido en el archivo DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Este archivo DeviceAtlas.bundle se tratará como un archivo de configuración desde la perspectiva de la función de sincronización de perfiles. Además, los datos JSON y la DLL se utilizarán en el nivel de componente en lugar de en el nivel de transformación individual.

Un nuevo DeviceAtlasComponent, al iniciar, busca el conglomerado .bundle, desconfunde el archivo JSON en la memoria, extrae los archivos en un directorio temporal y carga la DLL adecuada para la plataforma en ejecución. Este componente también supervisa los cambios en el archivo del paquete y vuelve a cargar automáticamente el archivo DLL y .cfg si cambia.

## Ejecución de DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

La configuración adecuada marca una gran diferencia en el tiempo necesario para la transformación. La transformación se puede configurar para que se ejecute sólo una vez por visitante por sesión a fin de permitir que DeviceAtlas acelere el proceso.

**Si se implementa mediante Log Processing.cfg**:

Ejecute las transformaciones dos veces.

1. Busque únicamente el [!DNL mobile id] campo y
1. Cree condiciones para ignorar el [!DNL mobile id] y, a continuación, busque el resto de los campos.

**Si se implementa con Transformation.cfg**:

Implemente como en el paso 1 en Procesamiento de registros anterior, o utilice filas cruzadas para admitir una configuración condicional.

* Filas cruzadas (Cross-Rows): permite tomar la clave de sesión anterior. A continuación, identifique si la clave de sesión actual es diferente de la que se encuentra con las filas cruzadas. Si es así, la transformación DeviceAtlas solo se ejecutará en un registro por sesión.

