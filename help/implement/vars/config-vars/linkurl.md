---
title: linkURL
description: Ignora gli utilizzi del collegamento generato automaticamente da AppMeasurement nelle chiamate di tracciamento dei collegamenti.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 1%

---

# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, i server di raccolta dati rilevano automaticamente l&#39;URL. Utilizza la `linkURL` per ignorare l&#39;URL rilevato.

## URL di collegamento tramite l’SDK per web

L’URL del collegamento è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) nel campo XDM `web.webInteraction.URL`.

## URL di collegamento tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.linkURL in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.linkURL` è una stringa contenente l&#39;URL del browser quando hai fatto clic sul collegamento. Questa variabile non popola le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se il terzo argomento del [tl()](../functions/tl-method.md) non è impostato, il `linkURL` viene invece utilizzata.
