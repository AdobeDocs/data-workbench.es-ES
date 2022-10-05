---
description: Las alertas administrativas envían notificaciones por correo electrónico a las direcciones de correo electrónico especificadas cuando el servidor de Insight detecta errores durante el curso normal de la operación.
title: Configuración de alertas administrativas
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Configuración de alertas administrativas{#configuring-administrative-alerts}

{{eol}}

Las alertas administrativas envían notificaciones por correo electrónico a las direcciones de correo electrónico especificadas cuando el servidor de Insight detecta errores durante el curso normal de la operación.

**Frecuencia recomendada:** Antes de la producción

>[!NOTE]
>
>El uso de alertas administrativas requiere que [!DNL Insight Server] tiene acceso a un servidor SMTP de reenvío para enviar alertas por correo electrónico.

Los destinatarios de las notificaciones por correo electrónico deben ser el personal de administración de sistemas clave y los principales interesados.

El archivo de Alertas administrativas, [!DNL Administrative Alerts.cfg], se utiliza para configurar las alertas administrativas de [!DNL Insight Server].

>[!NOTE]
>
>Si está ejecutando un clúster, debe crear o modificar alertas en el maestro [!DNL Insight Server] en el clúster.

**Para crear o modificar una alerta administrativa**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Administrative Alerts.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la columna *server name *for [!DNL Administrative Alerts.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Administrative Alerts.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En el [!DNL Administrative Alerts.cfg] ventana, haga clic en **[!UICONTROL component]** para ver su contenido.
1. Complete los parámetros como desee. Para obtener una lista de los parámetros disponibles en este archivo, consulte [Configuración de alertas administrativas](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Información sobre los pasos](assets/cfg_adminalerts_examplevalues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Opcional) Si está trabajando en un clúster y desea que se apliquen las mismas alertas administrativas a cada unidad de procesamiento de datos, debe copiar y pegar la actualización [!DNL Administrative Alerts.cfg] en el [!DNL Components for Processing Servers] carpeta dentro de la carpeta maestra [!DNL Insight Server] directorio de instalación.
