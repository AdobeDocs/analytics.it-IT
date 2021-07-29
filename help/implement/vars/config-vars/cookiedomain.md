---
title: cookieDomain
description: La variabile cookieDomain consente di determinare il dominio in cui impostare i cookie.
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# cookieDomain

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizza invece [`trackingServer`](trackingserver.md) .

La variabile `cookieDomain` determina il dominio in cui AppMeasurement imposta i cookie. Puoi utilizzare questa variabile per impostare esplicitamente il dominio dei cookie invece di utilizzare la variabile [`cookieDomainPeriods`](cookiedomainperiods.md) .

Questa variabile deve essere utilizzata solo quando **sia** che sono soddisfatte le seguenti condizioni:

* Se l’implementazione utilizza cookie di prime parti. Questa variabile non è obbligatoria per le implementazioni che utilizzano un valore [`trackingServer`](trackingserver.md) contenente `sc.adobedc.net`.
* Se il dominio ha un punto nel suo suffisso. Ad esempio, `example.co.uk` potrebbe utilizzare la variabile `cookieDomain` per indicare esplicitamente che il dominio del cookie è `example.co.uk` e non `co.uk`.

Solo un piccolo numero di implementazioni ha utilizzato per la variabile `cookieDomain` e anche allora è possibile utilizzare variabili alternative come [`cookieDomainPeriods`](cookiedomainperiods.md).

## Dominio cookie che utilizza i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.cookieDomain in AppMeasurement e nell’editor di codice personalizzato

La variabile `cookieDomain` è una stringa e viene impostata sul dominio in cui si desidera memorizzare i cookie.

```js
s.cookieDomain = "stats.example.com";
```
