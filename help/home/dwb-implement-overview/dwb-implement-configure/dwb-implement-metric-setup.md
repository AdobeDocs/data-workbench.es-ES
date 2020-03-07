---
description: En esta sección se explica cómo crear métricas en el área de trabajo de datos.
title: Configuración de métricas
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Configuración de métricas{#metrics-setup}

En esta sección se explica cómo crear métricas en el área de trabajo de datos.

## Explicación de las métricas {#section-f0412e851fcb4ac9886dca4003d42cec}

Las métricas son información cuantitativa sobre la actividad del cliente, como vistas, pedidos, número de llamadas realizadas e ingresos. Las métricas son la base de los informes y le ayudan a ver y comprender las relaciones de datos.

La dimensión de métrica permite agrupar los recuentos de métricas por un nivel específico. También permite agrupar los recuentos de métricas por un nivel específico.

## Creación de nuevas métricas {#section-60a413899d1b4707965e06fb5ef7fc4e}

Siga los pasos a continuación para crear una nueva métrica:

1. Haga clic en **Herramienta** > Editor **de métricas**.

1. En el editor de métricas, introduzca el nombre y la fórmula de la nueva métrica. ![](assets/dwb_impl_metrics1.png)

1. Guárdela en la carpeta Métricas. ![](assets/dwb_impl_metrics2.png)

## Creación y edición de métricas derivadas {#section-ebdcd3ec652f485e90e001d694eab6d0}

Utilice un Editor de métricas para definir una nueva métrica por nombre, fórmula y formato, que se guarda en la [!DNL User\profile_name\Metrics] carpeta para su uso posterior.

1. Abra un nuevo Editor de métricas utilizando la opción de menú **Administración > Perfil** o haciendo clic con el botón secundario en la columna Usuario de la carpeta en la que desee crear la métrica y haciendo clic en **Crear > Nueva métrica**. Se muestra un Editor de métricas.

1. En el parámetro *Name* , escriba un nombre para la nueva métrica.

   >[!NOTE]
   >
   >Tenga en cuenta que se permiten espacios ( ) mientras que los caracteres de subrayado (_) no. Además, no puede utilizar los siguientes símbolos: + - * /

   ![](assets/dwb_impl_metrics3.png)

1. En el parámetro *Fórmula* , escriba una expresión para la nueva métrica.

   >[!NOTE]
   Los filtros deben definirse entre corchetes [ ] en la expresión. Para obtener más reglas de sintaxis de expresiones de métricas, consulte [Sintaxis para expresiones de métricas.](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   Esta tabla proporciona expresiones de ejemplo para métricas extendidas. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   Cuando se introduce una expresión adecuada, la línea de vista previa muestra el valor de la nueva métrica. Si hay un error en la expresión, la línea de vista previa muestra un mensaje de error.

1. Haga clic con el botón derecho y seleccione **Guardar**. Al guardar la métrica, se crea en el equipo un archivo que representa la nueva métrica en la carpeta \User\profile name\Metrics *del directorio de* instalación de DWB.

## Edición de métricas derivadas existentes {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. En el Administrador de perfiles o el Administrador de métricas, en la columna del nombre del perfil, haga clic con el botón secundario en la marca de verificación del archivo de métrica que desee editar y haga clic en **Convertir en local**.
1. Haga clic con el botón secundario en la marca de verificación del archivo de métrica en la columna Usuario y haga clic en **Abrir** desde el área de trabajo.

   >[!NOTE]
   También puede abrir un Editor de métricas haciendo clic con el botón derecho en cualquier área relacionada con la métrica dentro de una visualización para mostrar el menú de la métrica.

1. En el Editor **de** métricas, edite y guarde la definición de la métrica según sea necesario mediante los pasos 2 a 4 en *Creación de nuevas métricas* derivadas.

   Si desea que todos los usuarios del perfil utilicen la métrica que editó, debe publicarla en el perfil de trabajo mediante el Administrador de perfiles.

Consulte la documentación para obtener más ayuda:

[Sintaxis para expresiones de métricas](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[Creación y edición de métricas derivadas](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
