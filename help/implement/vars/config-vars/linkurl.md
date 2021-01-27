---
title: linkURL
description: Ignora gli URL del collegamento generato automaticamente che AppMeasurement utilizza nelle chiamate di tracciamento dei collegamenti.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 1%

---


# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata a  Adobe, i server di raccolta dati rilevano automaticamente l’URL. Utilizzate la variabile `linkURL` per sovrascrivere l&#39;URL rilevato.

## URL collegamento in  Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.linkURL nell&#39;editor di codice personalizzato AppMeasurement e Launch

La variabile `s.linkURL` è una stringa, contenente l&#39;URL del browser su cui è stato fatto clic. Questa variabile non compila le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se il terzo argomento del metodo [tl()](../functions/tl-method.md) non è impostato, viene utilizzata la variabile `linkURL`.
