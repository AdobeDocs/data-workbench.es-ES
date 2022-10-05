---
description: Las operaciones booleanas combinan los resultados de las operaciones de prueba, que funcionan como elementos secundarios de las operaciones booleanas.
title: Operaciones booleanas
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Operaciones booleanas{#boolean-operations}

{{eol}}

Las operaciones booleanas combinan los resultados de las operaciones de prueba, que funcionan como elementos secundarios de las operaciones booleanas.

Para obtener información sobre las operaciones de prueba, consulte [Operaciones de prueba](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Al definir un [!DNL boolean] , puede definir cero o más elementos secundarios para la operación.

**Adición de una condición secundaria a una operación booleana**

1. Haga clic con el botón derecho en el nombre o en el número correspondiente a la variable [!DNL Boolean] operación.
1. Haga clic en **[!UICONTROL Add new child]** y elija uno de los tipos de condiciones disponibles para agregar.
1. Repita los pasos 1 y 2 hasta que haya agregado todas las condiciones secundarias deseadas para la variable [!DNL Boolean] operación.

   >[!NOTE]
   >
   >Cuando haga clic con el botón derecho en el nombre o en el número correspondiente a un [!DNL Boolean] , verá la variable [!DNL Add new sibling] para abrir el Navegador. Un hermano es otra condición en la misma posición relativa en la jerarquía de condiciones que el [!DNL Boolean] operación en la que hizo clic con el botón derecho. Adición de un nuevo elemento secundario para un [!DNL Boolean] es lo mismo que agregar una nueva condición haciendo clic con el botón derecho en la variable [!DNL Condition] o [!DNL Log Entry Condition] parámetro.

**Para quitar una condición secundaria de una operación booleana:**

1. Haga clic con el botón derecho en el nombre de la condición secundaria o en el número correspondiente a la condición secundaria que desea eliminar de la [!DNL Boolean] operación.
1. Haga clic en **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, donde número es el número correspondiente a la condición secundaria que desea eliminar.

Esta sección trata sobre las siguientes condiciones:

* [Y](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Ni](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [o](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Y {#section-a14dba4b07cc4ab9aeb20868f773db7c}

La variable [!DNL And] puede tener cero o más condiciones secundarias y devuelve el valor &quot;True&quot; cuando ninguno de sus nodos secundarios devuelve el valor &quot;False&quot;.

La variable [!DNL And] condition forma la operación raíz de todas las pruebas de condición dentro del servidor de Data Workbench. Si la variable [!DNL And] la condición no contiene elementos secundarios, la condición se evalúa como verdadera y se ejecuta la operación asociada. Por este motivo, las acciones que solo tienen la variable [!DNL And] condición, ya que la prueba de condición siempre se ejecuta y por qué se utiliza como raíz para todas las pruebas de condición.

Este ejemplo muestra cómo una [!DNL And] se usa para asegurarse de que la variable [!DNL Copy] la transformación se produce cuando sólo la fecha de la entrada de registro se produjo en el año 2006 y la página solicitada se [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Ni {#section-7e48b61266aa43ecbc48b979bf5e939b}

La variable [!DNL Neither] puede tener cero o más condiciones secundarias y devuelve falso si alguna de sus condiciones secundarias se evalúa como verdadera. Si la variable [!DNL Neither] condición no contiene elementos secundarios, ninguno de los elementos secundarios puede devolver el valor &quot;true&quot;. Como resultado, la variable [!DNL Neither] condition se evalúa como true.

El siguiente ejemplo muestra una [!DNL Neither] condición con dos [!DNL Range] condiciones como sus hijos. Según se define, la variable [!DNL Neither] condición excluye las entradas de registro que se produjeron entre el 1 de enero de 2007 y el 10 de enero de 2007 o entre el 12 de enero de 2007 y el 14 de enero de 2007. Esta condición podría utilizarse como el [!DNL Log Entry Condition] para eliminar transacciones de un conjunto de datos durante periodos en los que hubo un problema conocido con los datos recopilados.

![](assets/cfg_Condition_NeitherCondition.png)

## o {#section-a3aa0f56b6234f2680fa81939228326b}

La variable [!DNL Or] puede tener cero o más condiciones secundarias y devuelve el valor &quot;True&quot; si al menos una de sus condiciones secundarias se evalúa como &quot;True&quot;. Si la variable [!DNL Or] condición no contiene elementos secundarios, ninguno de los elementos secundarios puede devolver el valor &quot;true&quot;. Como resultado, la variable [!DNL Or] se evalúa como false.

Este ejemplo muestra la variable [!DNL Or] condición con un [!DNL String Match] condición y [!DNL Range] como sus hijos. La variable [!DNL Or] la condición solo se cumple si la entrada de registro tiene la variable [!DNL x-hasproblem] establecido en yes o la entrada de registro se produjo durante el intervalo de tiempo comprendido entre el 1 de enero de 2007 y el 10 de enero de 2007.

![](assets/cfg_Condition_OrCondition.png)
