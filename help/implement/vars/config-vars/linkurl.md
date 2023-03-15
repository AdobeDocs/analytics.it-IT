---
title: linkURL
description: Sostituisci l’URL di collegamento generato automaticamente utilizzato da AppMeasurement nelle chiamate di tracciamento dei collegamenti.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 22%

---

# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, i server di raccolta dati rilevano automaticamente l’URL. Utilizza il `linkURL` per ignorare l&#39;URL rilevato.

## Collega URL tramite Web SDK

L’URL del collegamento è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webInteraction.URL`.

## Collega l’URL tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.linkURL in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkURL` variable è una stringa che contiene l&#39;URL del browser in cui è stato fatto clic sul collegamento. Questa variabile non popola le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se il terzo argomento della [tl()](../functions/tl-method.md) non è impostato, il `linkURL` viene invece utilizzata la variabile.
