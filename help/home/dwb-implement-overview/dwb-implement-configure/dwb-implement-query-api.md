---
description: Guía rápida para la configuración de una API de consulta.
title: Configuración de API de consulta
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Configuración de API de consulta{#query-api-setup}

{{eol}}

Guía rápida para la configuración de una API de consulta.

Siga los siguientes pasos para configurar la API de consulta:

1. Adquisición de certificado de API de consulta

   Enviar un correo electrónico al equipo de operaciones técnicas de correo electrónico de Adobe: `Dataworkbench@adobe.com`.

   Proporcione el nombre CN que desee usar para la API de consulta (proporcione un nombre genérico como `<Client>` API de consulta).

   >[!NOTE]
   >
   >Las operaciones técnicas generarán el certificado y lo cargarán en una dirección URL. Por favor, comunique a los Consultores de Adobe después de recibir la notificación de Tech Ops sobre la generación exitosa del ticket para que ellos le envíen de vuelta el ticket.

1. Descarga y extracción del embudo de API. Reciba el archivo api-stunnel de su consultor.

   Asegúrese de que Perl está instalado en su equipo.

   En la carpeta extraída (la ruta de la carpeta en la que copia el archivo), copie el certificado de API de consulta dentro de la variable *retraso* carpeta.

1. Configuración de Stunnel.conf

   Debe haber un archivo llamado *stunnel.conf* dentro del *Stunnel* carpeta (donde copió el certificado).

   Edite el archivo en el Bloc de notas.

   ![](assets/dwb_impl_API1.png)

   Cambie los parámetros de la siguiente manera: ![](assets/dwb_impl_API2.png)

   Es necesario cambiar dos parámetros en este archivo.

   * *Cert* = El nombre del certificado. En este ejemplo es Aadhithiya Ramani QAPI Client.pem.
   * *Connect* =El nombre del servidor para su DPU principal.

1. Copiar el *Query.pm*.

   La variable *Query.pm* estará disponible en la carpeta de API de Insight.

   Copie el *Query.pm* y péguelo en la carpeta Perl Library (normalmente será *C:\Perl64\lib *, pero compruebe dónde está instalado Perl en su equipo).

1. Modifique el *api-http.pl* file

   El archivo api-http.pl estará disponible en la carpeta api-stunnel .

   Solo se modifica un parámetro

   *Mi $profile* = El nombre del perfil para el que está configurando la API de consulta.

1. Instale la API de consulta.

   Abra el símbolo del sistema en su sistema como &quot;Administrador&quot; y vaya al directorio donde extrajo el *retraso* como se muestra: ![](assets/dwb_impl_API3.png)

   Ejecute el siguiente comando *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   Después de ejecutar el comando, aparece una ventana que indica que la variable *retraso* está instalado.

   >[!NOTE]
   >
   >Después de ejecutar el comando, aparece una ventana que indica que la variable *retraso* está instalado.

1. Prueba de la configuración del embudo de la API de consulta

   El paso final de este proceso será probar la configuración de la API de consulta. En el símbolo del sistema que utilizó para instalar el directorio api-stunnel. ![](assets/dwb_impl_API5.png)

   Ejecute el script Perl disponible en esa carpeta con el siguiente comando* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   Después de ejecutar la secuencia de comandos, los resultados deberían ser como la captura de pantalla a continuación (la fecha y la hora y los valores del resultado variarán según el tiempo y otros parámetros del perfil en el que haya configurado la API de consulta (en el paso 6). ![](assets/dwb_impl_API7.png)
