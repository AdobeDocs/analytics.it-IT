---
title: cookieDomain
description: (Ritirato) Consente di determinare il dominio su cui impostare i cookie.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 13%

---

# cookieDomain

>[!IMPORTANT]
>Questa variabile viene ritirata. Al suo posto, utilizza [`trackingServer`](trackingserver.md).

La variabile `cookieDomain` determina il dominio in cui AppMeasurement imposta i cookie. È possibile utilizzare questa variabile per impostare in modo esplicito il dominio del cookie anziché utilizzare la variabile [`cookieDomainPeriods`](cookiedomainperiods.md).

Questa variabile deve essere utilizzata solo quando sono soddisfatte **entrambe** le seguenti condizioni:

* Se la tua implementazione utilizza cookie di prime parti. Questa variabile non è necessaria per le implementazioni che utilizzano un valore [`trackingServer`](trackingserver.md) contenente `sc.adobedc.net`.
* Se il tuo dominio ha un punto nel suo suffisso. Ad esempio, `example.co.uk` potrebbe utilizzare la variabile `cookieDomain` per indicare esplicitamente che il dominio del cookie è `example.co.uk` e non `co.uk`.

Solo un numero limitato di implementazioni ha utilizzato per la variabile `cookieDomain` e anche in questo caso è possibile utilizzare variabili alternative come [`cookieDomainPeriods`](cookiedomainperiods.md).

## Dominio dei cookie con Web SDK

Il Web SDK può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Dominio dei cookie tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.cookieDomain in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `cookieDomain` è una stringa ed è impostata sul dominio in cui si desidera memorizzare i cookie.

```js
s.cookieDomain = "stats.example.com";
```
