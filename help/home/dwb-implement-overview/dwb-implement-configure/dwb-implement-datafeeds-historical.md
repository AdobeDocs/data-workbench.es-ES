---
description: Una guía rápida de los pasos mínimos necesarios para validar y configurar fuentes de datos históricas.
title: Validación de fuentes de datos históricas
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# Validación de fuentes de datos históricas{#validating-historical-data-feeds}

{{eol}}

Una guía rápida de los pasos mínimos necesarios para validar y configurar fuentes de datos históricas.

## Pasos de validación para la coherencia de las fuentes de datos {#section-777b2c627a354627a02feb9461e23038}

1. Inicie sesión en *dientes* (https://oasis.omniture.com/drteeth/)
1. Vaya a Administración de SiteCatalyst -> Definición de fuente de datos (nuevo)
1. Saltar a la ubicación del servidor (por ejemplo Dallas, Londres...) Según la ubicación de su organización.
1. Proporcione RSID y seleccione el tipo de fuente Insight y haga clic en *búsqueda*.

   ![](assets/dwb_impl_historical.png)

1. Identifique el nombre real de la fuente para su cliente.
1. Haga clic en Historial en la sección Acciones. ![](assets/dwb_impl_historical1.png)

   Compruebe si hay errores en el campo de estado y, en caso de que alguna fuente esté en estado de error, seleccione la fuente y haga clic en reprocesar. Si el error se ha producido en varias solicitudes, envíe un correo electrónico a *`dataworkbench@adobe.com`* con los detalles ID de fuente y Grupo de informes para volver a procesarlos.

1. La posvalidación comprueba los registros en la carpeta sin procesar de la ubicación NAS.
