---
title: linkURL
description: Sostituisci l’AppMeasurement dell’URL di collegamento generato automaticamente utilizzato nelle chiamate di tracciamento dei collegamenti.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 8be75c04177e97949811c17c7a87b04cce7b3de4
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 15%

---

# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, i server di raccolta dati rilevano automaticamente l’URL. Utilizza il `linkURL` per ignorare l&#39;URL rilevato.

In Analysis Workspace non sono presenti dimensioni che generano rapporti su questa variabile. Compila il `page_event_var1` colonna in [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md).

## Collega URL tramite Web SDK

L’URL del collegamento è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` o `data.__adobe.analytics.pev1`

## Collega l’URL tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.linkURL in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkURL` variable è una stringa che contiene l&#39;URL del browser in cui è stato fatto clic sul collegamento. Questa variabile non popola le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se il terzo argomento della [tl()](../functions/tl-method.md) non è impostato, il `linkURL` viene invece utilizzata la variabile.
