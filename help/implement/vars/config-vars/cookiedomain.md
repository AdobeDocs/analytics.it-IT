---
title: cookieDomain
description: La variabile cookieDomain consente di determinare il dominio in cui impostare i cookie.
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# cookieDomain

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizzo [`trackingServer`](trackingserver.md) invece.

La `cookieDomain` determina il dominio in cui AppMeasurement imposta i cookie. Puoi utilizzare questa variabile per impostare esplicitamente il dominio dei cookie invece di utilizzare il [`cookieDomainPeriods`](cookiedomainperiods.md) variabile.

Questa variabile deve essere utilizzata solo quando **entrambi** sono soddisfatte le seguenti condizioni:

* Se l’implementazione utilizza cookie di prime parti. Questa variabile non è necessaria per le implementazioni che utilizzano un [`trackingServer`](trackingserver.md) valore contenente `sc.adobedc.net`.
* Se il dominio ha un punto nel suo suffisso. Ad esempio: `example.co.uk` potrebbe utilizzare `cookieDomain` per indicare esplicitamente che il dominio del cookie è `example.co.uk` e non `co.uk`.

Solo un numero limitato di implementazioni ha utilizzato per `cookieDomain` e anche allora variabili alternative come [`cookieDomainPeriods`](cookiedomainperiods.md) possono essere invece utilizzati.

## Dominio cookie che utilizza i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.cookieDomain in AppMeasurement e nell’editor di codice personalizzato

La `cookieDomain` è una stringa e viene impostata sul dominio in cui si desidera memorizzare i cookie.

```js
s.cookieDomain = "stats.example.com";
```
