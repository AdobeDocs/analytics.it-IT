---
title: cookieDomain
description: La variabile cookieDomain consente di determinare il dominio su cui impostare i cookie.
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 13%

---

# cookieDomain

>[!IMPORTANT]
>
>Questa variabile viene ritirata. Al suo posto, utilizza [`trackingServer`](trackingserver.md).

Il `cookieDomain` determina il dominio in cui AppMeasurement imposta i cookie. È possibile utilizzare questa variabile per impostare in modo esplicito il dominio del cookie anziché utilizzare [`cookieDomainPeriods`](cookiedomainperiods.md) variabile.

Questa variabile deve essere utilizzata solo quando **entrambi** delle seguenti condizioni sono soddisfatte:

* Se la tua implementazione utilizza cookie di prime parti. Questa variabile non è necessaria per le implementazioni che utilizzano un [`trackingServer`](trackingserver.md) valore contenente `sc.adobedc.net`.
* Se il tuo dominio ha un punto nel suo suffisso. Ad esempio: `example.co.uk` potrebbe utilizzare il `cookieDomain` variabile per indicare esplicitamente che il dominio del cookie è `example.co.uk` e non `co.uk`.

Solo un piccolo numero di implementazioni hanno utilizzato per `cookieDomain` variabile e anche in questo caso, variabili alternative come [`cookieDomainPeriods`](cookiedomainperiods.md) può essere utilizzato al suo posto.

## Dominio dei cookie tramite Web SDK

L’SDK per web può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Dominio dei cookie tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.cookieDomain in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `cookieDomain` la variabile è una stringa e viene impostata sul dominio in cui desideri memorizzare i cookie.

```js
s.cookieDomain = "stats.example.com";
```
