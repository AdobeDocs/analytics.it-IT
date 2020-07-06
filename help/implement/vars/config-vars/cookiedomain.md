---
title: cookieDomain
description: La variabile cookieDomain consente di determinare il dominio in cui impostare i cookie.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---


# cookieDomain

>[!IMPORTANT]
>
>Questa variabile è ritirata. Usa [`trackingServer`](trackingserver.md) invece.

La `cookieDomain` variabile determina il dominio in cui AppMeasurement imposta i cookie. È possibile utilizzare questa variabile per impostare esplicitamente il dominio dei cookie invece di utilizzare la [`cookieDomainPeriods`](cookiedomainperiods.md) variabile.

Questa variabile deve essere utilizzata solo se sono soddisfatte **entrambe** le seguenti condizioni:

* Se l’implementazione utilizza cookie di prime parti. Questa variabile non è obbligatoria per le implementazioni che utilizzano un [`trackingServer`](trackingserver.md) valore contenente `sc.omtrdc.net`.
* Se il dominio ha un punto nel relativo suffisso. Ad esempio, `example.co.uk` potrebbe utilizzare la `cookieDomain` variabile per indicare esplicitamente che il dominio del cookie è `example.co.uk` e non è `co.uk`.

Per la `cookieDomain` variabile è stato utilizzato solo un numero limitato di implementazioni, e anche in seguito è possibile utilizzare variabili alternative come [`cookieDomainPeriods`](cookiedomainperiods.md) ad esempio.

## Dominio cookie in  Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.cookieDomain nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `cookieDomain` variabile è una stringa ed è impostata sul dominio in cui memorizzare i cookie.

```js
s.cookieDomain = "stats.example.com";
```
