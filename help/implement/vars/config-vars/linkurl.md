---
title: linkURL
description: Sostituisci l’AppMeasurement dell’URL di collegamento generato automaticamente utilizzato nelle chiamate di tracciamento dei collegamenti.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 17%

---

# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, i server di raccolta dati rilevano automaticamente l’URL. Utilizza il `linkURL` per ignorare l&#39;URL rilevato.

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
