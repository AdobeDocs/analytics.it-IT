---
title: pageURL
description: Sostituisci l’URL della pagina raccolto automaticamente sul tuo sito.
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 15%

---

# pageURL

AppMeasurement raccoglie automaticamente l’URL della pagina in ogni hit. Se desideri ignorare l’URL della pagina raccolto automaticamente da AppMeasurement, puoi utilizzare questa variabile. Nella maggior parte dei casi non è necessario impostare questa variabile.

>[!NOTE]
>
>Questa variabile non è una dimensione disponibile in Analysis Workspace. È disponibile solo in Data Warehouse e Feed dati. Inoltre, i server di raccolta dati di Adobe eliminano questa dimensione da tutti [tracciamento dei collegamenti](/help/implement/vars/functions/tl-method.md) richieste di immagini. Se desideri utilizzare l’URL della pagina come dimensione in Analysis Workspace o desideri questa dimensione negli hit di tracciamento dei collegamenti, puoi valutare la possibilità di trasmettere `pageURL` variabile in un [eVar](evar.md) su ogni hit.

## URL della pagina utilizzando il Web SDK

L’URL della pagina è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webPageDetails.URL`.

## URL della pagina utilizzando l’estensione Adobe Analytics

L’estensione Analytics in Adobe Experience Platform Data Collection compila automaticamente l’URL della pagina. Tuttavia, puoi impostare la sostituzione dell’URL della pagina sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda **[!UICONTROL Rules]**, quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione **[!UICONTROL Actions]**, fai clic su un’azione **[!UICONTROL Adobe Analytics - Set Variables]** esistente o fai clic sull’icona “+”.
5. Imposta il **[!UICONTROL Extension]** in Adobe Analytics e nella sezione **[!UICONTROL Action Type]** a **[!UICONTROL Set Variables]**.
6. Individua la sezione **[!UICONTROL Page URL]**.

Puoi impostare l’URL della pagina su qualsiasi valore stringa.

## s.pageURL in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.pageURL` variabile è una stringa che contiene l’URL della pagina. AppMeasurement raccoglie automaticamente questa variabile, tuttavia se lo desideri puoi sovrascrivere il valore.

```js
s.pageURL = "https://example.com";
```

Se desideri utilizzare l’URL della pagina come dimensione nei rapporti, considera l’utilizzo di quanto segue nell’implementazione:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
