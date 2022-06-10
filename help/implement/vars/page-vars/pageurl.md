---
title: pageURL
description: Ignora l’URL della pagina raccolto automaticamente sul sito.
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# pageURL

AppMeasurement raccoglie automaticamente l&#39;URL della pagina in ogni hit. Se desideri ignorare l’URL della pagina raccolto automaticamente da AppMeasurement, puoi utilizzare questa variabile. Nella maggior parte dei casi non è necessario impostare questa variabile.

>[!NOTE]
>
>Questa variabile non è una dimensione disponibile in Analysis Workspace. È disponibile solo nei feed di dati e Data Warehouse. Inoltre, i server di raccolta dati di Adobe rimuovono questa dimensione da tutte le [tracciamento dei collegamenti](/help/implement/vars/functions/tl-method.md) richieste di immagini. Se desideri utilizzare l’URL della pagina come dimensione in Analysis Workspace o desideri che questa dimensione sia negli hit di tracciamento dei collegamenti, considera il passaggio della `pageURL` in un [eVar](evar.md) su ogni hit.

## URL della pagina utilizzando l’SDK per web

L&#39;URL della pagina è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) nel campo XDM `web.webPageDetails.URL`.

## URL della pagina utilizzando l’estensione Adobe Analytics

L’estensione Analytics in Adobe Experience Platform Data Collection popola automaticamente l’URL della pagina. Tuttavia, puoi impostare l’override dell’URL della pagina durante la configurazione dell’estensione Analytics (variabili globali) o in base alle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a **[!UICONTROL Rules]** , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto **[!UICONTROL Actions]**, fai clic su un **[!UICONTROL Adobe Analytics - Set Variables]** fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la **[!UICONTROL Extension]** del menu a discesa Adobe Analytics e **[!UICONTROL Action Type]** a **[!UICONTROL Set Variables]**.
6. Individua il **[!UICONTROL Page URL]** sezione .

Puoi impostare l’URL della pagina su qualsiasi valore stringa.

## s.pageURL in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.pageURL` è una stringa che contiene l&#39;URL della pagina. AppMeasurement raccoglie automaticamente questa variabile, tuttavia puoi modificarne il valore se necessario.

```js
s.pageURL = "https://example.com";
```

Se desideri utilizzare l’URL della pagina come dimensione nei rapporti, considera l’utilizzo di quanto segue nell’implementazione:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Se utilizzi `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
