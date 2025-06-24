---
title: cookieDomain
description: (Ritirato) Consente di determinare il dominio su cui impostare i cookie.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '197'
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
