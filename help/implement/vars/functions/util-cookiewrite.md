---
title: Util.cookieWrite
description: Scrive un valore per un cookie.
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/VxNoO8-K6rE8NdIgQSA0ubuBwaHXu2OPLCexzNCXdHQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 2%

---

# Util.cookieWrite

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizzare il metodo `Util.cookieWrite()` per impostare un valore su un cookie. È possibile utilizzare il metodo [`Util.cookieRead()`](util-cookieread.md) per recuperare i valori impostati utilizzando `Util.cookieWrite()`.

## Impostare i cookie utilizzando l’estensione Adobe Analytics e l’estensione Web SDK

La funzione Raccolta dati di Adobe Experience Platform non consente di impostare i cookie nell’interfaccia.

## s.Util.cookieWrite() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare il metodo `s.Util.cookieWrite()` per impostare un cookie sul valore desiderato.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

È disponibile un terzo argomento facoltativo che determina la scadenza del cookie. Per impostazione predefinita, i cookie impostati con `s.Util.cookieWrite()` scadono alla fine della sessione del browser.

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
