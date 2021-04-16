---
description: Los equipos de Target Insight Server que ejecuten el servicio de replicación de Insight Server deben poder leer los archivos de registro en este servidor repetidor.
title: Configuración del control de acceso para equipos de destino
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# Configuración del control de acceso para equipos de destino{#configuring-access-control-for-target-machines}

Los equipos de Target Insight Server que ejecuten el servicio de replicación de Insight Server deben poder leer los archivos de registro en este servidor repetidor.

El acceso a los equipos de destino se concede mediante el archivo [!DNL Access Control.cfg].

**Para configurar Control de acceso para el acceso por  [!DNL Insight Server] equipos de destino**

1. Vaya a la carpeta [!DNL Access Control] en el directorio donde instaló la funcionalidad del repetidor.

   Ejemplo: [!DNL D:\Adobe\Repeater\Access Control]

1. Abra [!DNL Access Control.cfg] en un editor de texto como el Bloc de notas.
1. Cree un grupo de acceso para las máquinas [!DNL Insight Server] que deben acceder a los archivos de registro de este servidor repetidor. Asigne un nombre a este grupo de acceso similar a &quot;Destinos de replicación&quot;.

   El siguiente fragmento de archivo muestra el aspecto que debe tener el grupo de acceso.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. En la sección Miembros , especifique la dirección IP de cada equipo.
   1. Actualice el recuento de elementos para el vector Members para reflejar el número de direcciones IP de equipo que insertó.
   1. En la sección Acceso de solo lectura , especifique la ubicación de los datos de evento a los que accede la replicación. Utilice barras inclinadas en la especificación de ruta (/). La ubicación predeterminada es la carpeta [!DNL Logs] del equipo repetidor (/Logs/).
   1. Actualice el recuento de elementos para el vector de acceso de solo lectura para reflejar el número de ubicaciones que insertó.

1. Actualice el número de grupos de acceso en el vector Grupos de control de acceso en la parte superior del archivo para reflejar la adición del nuevo grupo de acceso.

   ```
   Access Control Groups = vector: n items
   ```

1. Guarde el archivo.
