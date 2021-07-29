---
title: pageURL
description: Ignora l’URL della pagina raccolto automaticamente sul sito.
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# pageURL

AppMeasurement raccoglie automaticamente l&#39;URL della pagina in ogni hit. Se desideri ignorare l’URL della pagina raccolto automaticamente da AppMeasurement, puoi utilizzare questa variabile. Nella maggior parte dei casi non è necessario impostare questa variabile.

>[!NOTE]
>
>Questa variabile non è una dimensione disponibile in Analysis Workspace. È disponibile solo nei feed di dati e Data Warehouse. Inoltre, i server di raccolta dati di Adobe rimuovono questa dimensione da tutte le richieste di immagini [tracciamento collegamenti](/help/implement/vars/functions/tl-method.md). Se desideri utilizzare l’URL della pagina come dimensione in Analysis Workspace o desideri che questa dimensione sia negli hit di tracciamento dei collegamenti, considera il passaggio della variabile `pageURL` in un [eVar](evar.md) su ogni hit.

## URL della pagina utilizzando i tag in Adobe Experience Platform

L’interfaccia utente di raccolta dati popola automaticamente l’URL della pagina. Tuttavia, puoi impostare l’override dell’URL della pagina durante la configurazione dell’estensione Analytics (variabili globali) o in base alle regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda **[!UICONTROL Rules]** , quindi fai clic sulla regola desiderata (o crea una regola).
4. In **[!UICONTROL Actions]**, fai clic su un&#39;azione **[!UICONTROL Adobe Analytics - Set Variables]** esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa **[!UICONTROL Extension]** su Adobe Analytics e **[!UICONTROL Action Type]** su **[!UICONTROL Set Variables]**.
6. Individua la sezione **[!UICONTROL Page URL]** .

Puoi impostare l’URL della pagina su qualsiasi valore stringa.

## s.pageURL in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.pageURL` è una stringa che contiene l&#39;URL della pagina. AppMeasurement raccoglie automaticamente questa variabile, tuttavia puoi modificarne il valore se necessario.

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
