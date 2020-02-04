---
title: linkURL
description: Ignora gli URL del collegamento generato automaticamente che AppMeasurement utilizza nelle chiamate di tracciamento dei collegamenti.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, i server di raccolta dati rilevano automaticamente l’URL. Utilizzate la `linkURL` variabile per sovrascrivere l’URL rilevato.

## URL collegamento in Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.linkURL nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.linkURL` variabile è una stringa contenente l’URL del browser su cui è stato fatto clic. Questa variabile non compila le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se la `linkName` variabile non è impostata per una chiamata di tracciamento dei collegamenti, viene utilizzata la `linkURL` variabile.
