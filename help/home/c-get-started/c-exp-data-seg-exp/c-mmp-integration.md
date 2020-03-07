---
description: El Área de trabajo de datos permite exportar archivos para integrarlos con Profiles and Audiences Export como parte de una Adobe Experience Cloud integrada.
title: Exportación de perfil de marketing principal
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Exportación de perfil de marketing principal{#master-marketing-profile-export}

El Área de trabajo de datos permite exportar archivos para integrarlos con Perfiles y audiencias como parte de una Adobe Experience Cloud integrada.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profiles and Audiences forma parte del servicio [](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud Identity, un servicio principal de [!DNL Adobe Experience Cloud]. La exportación Perfiles y audiencias permite compartir audiencias en Experience Cloud mediante un ID de Experience Cloud (ECID) único que se asigna a cada visitante y que luego [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)utiliza. La [!DNL ExportIntegration.exe] aplicación ( [!DNL E:\Server\Scripts]) se utiliza para generar exportaciones de MMP y Adobe Target.

**Configuración del servidor FSU para utilizar Profiles and Audiences**

1. Acceda a su servidor FSU.
1. Abra el archivo MMPExport.cfg. `Server/Admin/Export/MMPExport.cfg`.
1. Introduzca valores en todos los campos según sea necesario. Por ejemplo:

   >[!NOTE]
   >
   >La integración de MMP/AAM depende del bucket s3 de Amazon para la transferencia de datos.
   >
   >
   >La información s3 requerida para la transferencia de MMP (s3) puede obtenerse del equipo de Audience Manager.

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >El [!DNL MMPExport.cfg]archivo también permite tomar todos los registros, dividirlos en conjuntos y crear fragmentos de registros. Los trozos de registros se exportan a Amazon S3. Se requieren tres parámetros obligatorios para crear fragmentos de registros: [!DNL numRecordsPerChunk], [!DNL numThreads], y [!DNL maxRetriesOnSendFailure].

**Definición de parámetros**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Bucket s3</i> </td> 
   <td colname="col2"> Cubo AWS S3 al que se transfiere la exportación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Directorio de objetos s3</i> </td> 
   <td colname="col2"> Una ruta para guardar archivos s3. Esto admite subdirectorios. <p> <p>Importante:  No se permiten caracteres de espacio y multibyte en la ruta y se crearán errores en la exportación. (Se permite el guión). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Región de s3</i> </td> 
   <td colname="col2"> Región de AWS s3 a la que se envía la exportación. Por ejemplo: us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Clave de acceso s3</i> </td> 
   <td colname="col2"> Clave de acceso de AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Clave secreta de s3</i> </td> 
   <td colname="col2"> Clave secreta de AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>nombre del proveedor de datos</i> </td> 
   <td colname="col2"> Será el nombre de la carpeta que se utiliza para almacenar segmentos y características en AAM, respectivamente. Debe ser único por cliente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ID de cliente</i> </td> 
   <td colname="col2"> Se trata de un ID de cliente único que se proporciona a un cliente cuando se aprovisiona para MMP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>secreto del cliente</i> </td> 
   <td colname="col2"> <p><i></i>Se trata de un secreto de cliente único que se proporciona a un cliente cuando se le aprovisiona para MMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> Nombre de usuario de MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>password</i> </td> 
   <td colname="col2"> Contraseña de MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>Determina el tamaño del fragmento en términos de número de registros. </p> <p>La implementación recorta el valor especificado por el usuario a mín. = 1000 registros&amp;nbsp;(~trozos de 50 KB)&amp;nbsp;y máx. = 50000 registros (~trozos de 2,5 MB).&amp;nbsp;Se utiliza un valor predeterminado de 10000 en caso de que el usuario no especifique esta propiedad de configuración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThwords</i> </td> 
   <td colname="col2"> <p>Determina el paralelismo de la parte que envía el fragmento. Acepta un valor entre 1 y 24 subprocesos y su valor predeterminado es 12 subprocesos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>Determina el número de intentos de reintento que se deben realizar en caso de errores de envío de fragmentos. El valor predeterminado es 0 y no especifica ningún reintento. </p> <p>El intervalo de espera de 2 segundos se utiliza entre reintentos. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Generación de la exportación de MMP desde el cliente**

1. Desde el cliente, abra un espacio de trabajo y haga clic con el botón derecho **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**.
1. Agregar **nivel**.
1. Haga clic con el botón derecho en el encabezado y seleccione **Agregar atributos**.
1. Haga clic con el botón derecho en el encabezado y seleccione **Nueva exportación** de perfil de marketing principal. ![](assets/mmp_mmp_export.png)
1. Expanda **Consulta**.

   ![](assets/mmp_mmp_query.png)

1. Expanda Configuración **** MMP.
1. (obligatorio) Introduzca el nombre **del segmento** MMP y el campo **ID del visitante de** MMP. Estos parámetros no se pueden dejar vacíos.
1. El nombre **del segmento** MMP debe coincidir con el ID del segmento definido en el MMP.
1. El ID **de visitante de** MMP es la columna de atributos definida en el paso 4 que corresponde al ID **de** visitante.
1. Una vez especificados estos campos, puede guardar la exportación haciendo clic con el botón derecho en el encabezado de la exportación y elegir **Guardar** como &quot;Usuario\.exportar&quot;.
1. Abra **Administrador** > Administrador **de perfiles** y guarde la exportación en el perfil.

   Si todos los datos se introducen correctamente, se generará un archivo de exportación en la FSU ([!DNL Server/Exports]) y también se transferirá la exportación al AWS utilizando la información de la [!DNL MMPExport.cfg]. El registro para esto se proporciona en [!DNL Server/Trace/]. p. ej., [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| Detalles de configuración | Descripción |
|---|---|
| ID de segmento de MMP | Requerido. Es un identificador que se define primero en Audience Manager. |
| Campo de ID de visitante MMP | Asigne el ECID. |

