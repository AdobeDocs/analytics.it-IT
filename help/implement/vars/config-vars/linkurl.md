---
title: linkURL
description: Ignora gli utilizzi del collegamento generato automaticamente da AppMeasurement nelle chiamate di tracciamento dei collegamenti.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, i server di raccolta dati rilevano automaticamente l&#39;URL. Utilizza la `linkURL` per ignorare l&#39;URL rilevato.

## Collegamento URL tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.linkURL in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.linkURL` è una stringa contenente l&#39;URL del browser quando hai fatto clic sul collegamento. Questa variabile non popola le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se il terzo argomento del [tl()](../functions/tl-method.md) non è impostato, il `linkURL` viene invece utilizzata.
