---
title: Util.cookieWrite
description: Scrive un valore per un cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 2%

---

# Util.cookieWrite

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizza la `Util.cookieWrite()` per impostare un valore su un cookie. È possibile utilizzare [`Util.cookieRead()`](util-cookieread.md) metodo per recuperare i valori impostati con `Util.cookieWrite()`.

## Impostare i cookie utilizzando i tag in Adobe Experience Platform

L’interfaccia utente di raccolta dati non consente di impostare i cookie nell’interfaccia di . Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.Util.cookieWrite() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama il `s.Util.cookieWrite()` per impostare un cookie su un valore desiderato.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

È disponibile un terzo argomento facoltativo che determina la scadenza del cookie. Cookie impostati tramite `s.Util.cookieWrite()` scade alla fine della sessione del browser per impostazione predefinita.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Esempi

È possibile creare un&#39;istanza di una variabile in seguito alla scrittura di un cookie. Questa variabile è booleana.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
