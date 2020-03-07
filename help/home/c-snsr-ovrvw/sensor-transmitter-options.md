---
description: Información sobre los comandos de inicio del transmisor de sensores para UNIX y para Windows.
title: Opciones de la línea de comandos del transmisor de sensores
uuid: 8d077d76-a709-494e-a176-07ca3e761662
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opciones de la línea de comandos del transmisor de sensores{#sensor-transmitter-command-line-options}

Información sobre los comandos de inicio del transmisor de sensores para UNIX y para Windows.

## Comando de inicio para UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Para iniciar el transmisor Sensor en un sistema UNIX, utilice el siguiente comando:

```
txlogd -f configFileName
```

donde configFileName es el nombre completo del archivo de configuración del transmisor (txlogd.conf).

De forma predeterminada, el transmisor se ejecuta como un proceso en segundo plano (un demonio) y escribe mensajes operativos en syslog.

A continuación se muestra una lista completa de los conmutadores de la línea de comandos para txlogd:

| Conmutación | Descripción |
|---|---|
| -f | Especifica el nombre completo del archivo de configuración (txlogd.conf). Si no especifica este conmutador, el transmisor busca txlogd.conf en el directorio actual. |
| -n | Inicia el transmisor en modo interactivo (no como proceso de fondo). |
| -i | Inicia el transmisor en modo interactivo y dirige la salida de depuración a stdout. |
| -d | Inicia el transmisor como un proceso en segundo plano y dirige la salida de depuración a txlogd-debug.log en el directorio actual. |
| -c | Inicia el transmisor y crea el archivo de cola de discos si no existe. Si la cola de discos ya existe, se omite este parámetro. |
| -x | Inicia el transmisor y hace que se salga después de transmitir el último paquete en la cola de discos. Puede utilizar esta opción para vaciar la cola como preparación para una operación administrativa, como la creación de un nuevo archivo de cola. |

## Comando de inicio para Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Para iniciar Sensor y registrarlo como un servicio en un sistema Windows, utilice el siguiente comando:

```
txlog /regserver
```

