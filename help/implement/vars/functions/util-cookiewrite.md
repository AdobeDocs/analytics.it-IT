---
title: Util.cookieWrite
description: Scrive un valore per un cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 2%

---

# Util.cookieWrite

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizza il `Util.cookieWrite()` per impostare un valore su un cookie. È possibile utilizzare [`Util.cookieRead()`](util-cookieread.md) metodo per recuperare i valori impostati mediante `Util.cookieWrite()`.

## Impostare i cookie utilizzando l’estensione Adobe Analytics e l’estensione Web SDK

La funzione Raccolta dati di Adobe Experience Platform non consente di impostare i cookie nell’interfaccia.

## s.Util.cookieWrite() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.Util.cookieWrite()` per impostare un cookie sul valore desiderato.

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

Puoi creare un’istanza di una variabile al completamento della scrittura di un cookie. Questa variabile è booleana.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
