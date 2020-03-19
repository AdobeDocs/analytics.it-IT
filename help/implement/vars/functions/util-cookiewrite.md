---
title: Util.cookieWrite
description: Scrive un valore per un cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieWrite

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizzare il `Util.cookieWrite()` metodo per impostare un valore su un cookie. È possibile utilizzare il [`Util.cookieRead()`](util-cookieread.md) metodo per recuperare i valori impostati utilizzando `Util.cookieWrite()`.

## Configurare i cookie in Adobe Experience Platform Launch

Launch non consente di impostare i cookie nell&#39;interfaccia. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.Util.cookieWrite() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiamate il `s.Util.cookieWrite()` metodo per impostare un cookie sul valore desiderato.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

È disponibile un terzo argomento facoltativo che determina la scadenza del cookie. Per impostazione predefinita, i cookie impostati `s.Util.cookieWrite()` scadono alla fine della sessione del browser.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Esempi

È possibile creare un&#39;istanza di una variabile in caso di esito positivo della scrittura di un cookie. Questa variabile è booleana.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
