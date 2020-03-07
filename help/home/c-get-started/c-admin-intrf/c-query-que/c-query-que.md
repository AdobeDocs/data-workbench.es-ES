---
description: Normalmente, el servidor de Área de trabajo de datos responde a las consultas de usuarios entrantes a medida que se reciben y continúa proporcionando resultados y actualizaciones en tiempo real hasta que el usuario ya no las solicita.
solution: Analytics
title: Cola de consultas
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Cola de consultas{#query-queue}

Normalmente, el servidor de Área de trabajo de datos responde a las consultas de usuarios entrantes a medida que se reciben y continúa proporcionando resultados y actualizaciones en tiempo real hasta que el usuario ya no las solicita.

A veces, especialmente en sistemas con muchos usuarios de Área de trabajo de datos, el número de consultas activas requiere más recursos del sistema que los disponibles en el servidor. [!DNL Query Queue] permite al servidor poner algunas consultas temporalmente en espera hasta que los recursos necesarios para proporcionar respuestas estén disponibles. El [!DNL Query Queue] también proporciona funciones para priorizar consultas en base a una variedad de parámetros, de modo que en caso de contención de recursos, las consultas de mayor prioridad se respondan primero.

Las consultas de un solo cliente o servidor de informes se colocan en un grupo y se programan como una unidad. Puede configurar monitores de recursos para limitar la cantidad de determinados recursos del sistema que utilizan las consultas. Cuando los recursos monitoreados permiten la programación de otro grupo de consultas, se programa el grupo de mayor prioridad. Los usuarios cuyas consultas aún no están programadas, debido a limitaciones de recursos, no reciben un error pero se les notifica que sus consultas están en cola y que el usuario puede continuar trabajando en el ejemplo local.

La configuración predeterminada incluye una configuración simple para el [!DNL Query Queue], pero la deja deshabilitada. Los administradores pueden habilitar o deshabilitar el [!DNL Query Queue], configurar monitores de recursos para determinar la cantidad de recursos que se utilizan para realizar consultas y configurar políticas de priorización complejas para distintos usuarios.

**Para configurar el archivo Server.cfg para[!DNL Query Queuing]**

1. Abra [!DNL Server.cfg] haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Haga clic con el botón secundario **[!UICONTROL Server.cfg]** y conviértala en local para la edición.
1. Expandir [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configure los siguientes parámetros:

   * **Grupos de usuarios:** Permite configurar políticas, usuarios y la prioridad de cola. Consulte Grupos [de usuarios de cola de](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) consultas para obtener definiciones.

   * **Activo:** (Vector) Habilita o deshabilita el [!DNL Query Queue]. Los valores válidos son true o false. La configuración predeterminada es false.

   * **Grupo de usuarios predeterminado:** (Cadena) Escriba un nombre del grupo de usuarios al que se agregan los usuarios, si no aparecen en ningún grupo de usuarios.
   * **Monitores de recursos:** (Vector) Haga clic con el botón derecho para agregar un monitor de recursos. Puede especificar si el [!DNL Query Queue] monitor supervisa la memoria o el número de consultas. Haga clic con el botón derecho **[!UICONTROL Resource Monitor]** para elegir Monitor de presupuesto de memoria o Monitor de número de consultas. Consulte Monitores [de recursos de cola de](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) consultas para obtener más información.

   * **Prioridad intocable:** (Int) Especifica que los paquetes con una prioridad buena o igual a este valor nunca tienen prioridad sobre la programación de paquetes de mayor prioridad. Se utiliza junto con los [!DNL Memory Budget Monitor] descritos en la tabla Parámetros del grupo [de usuarios](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).

