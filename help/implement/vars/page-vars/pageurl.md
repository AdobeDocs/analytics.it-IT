---
title: pageURL
description: Sostituisci l’URL della pagina raccolto automaticamente sul tuo sito.
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 297
ht-degree: 16%

---

# pageURL

AppMeasurement raccoglie automaticamente l’URL della pagina in ogni hit. Se desideri ignorare l’URL della pagina raccolto automaticamente da AppMeasurement, puoi utilizzare questa variabile. Nella maggior parte dei casi non è necessario impostare questa variabile.

>[!NOTE]
>
>Questa variabile non è una dimensione disponibile in Analysis Workspace. È disponibile solo in Data Warehouse e Feed dati. Inoltre, i server di raccolta dati di Adobe eliminano questa dimensione da tutte le [richieste di immagini di tracciamento dei collegamenti](/help/implement/vars/functions/tl-method.md). Se desideri utilizzare l&#39;URL della pagina come dimensione in Analysis Workspace o desideri questa dimensione negli hit di tracciamento dei collegamenti, puoi passare la variabile `pageURL` in un [eVar](evar.md) per ogni hit.

## URL della pagina utilizzando il Web SDK

L’URL della pagina è mappato sulle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` o `data.__adobe.analytics.g`

## URL della pagina utilizzando l’estensione Adobe Analytics

L’estensione Analytics in Adobe Experience Platform Data Collection compila automaticamente l’URL della pagina. Tuttavia, puoi impostare la sostituzione dell’URL della pagina sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda **[!UICONTROL Rules]**, quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione **[!UICONTROL Actions]**, fai clic su un’azione **[!UICONTROL Adobe Analytics - Set Variables]** esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa **[!UICONTROL Extension]** su Adobe Analytics e **[!UICONTROL Action Type]** su **[!UICONTROL Set Variables]**.
6. Individua la sezione **[!UICONTROL Page URL]**.

Puoi impostare l’URL della pagina su qualsiasi valore stringa.

## s.pageURL in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.pageURL` è una stringa che contiene l&#39;URL della pagina. AppMeasurement raccoglie automaticamente questa variabile, tuttavia se lo desideri puoi sovrascrivere il valore.

```js
s.pageURL = "https://example.com";
```

Se desideri utilizzare l’URL della pagina come dimensione nei rapporti, considera l’utilizzo di quanto segue nell’implementazione:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Se si utilizza il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
