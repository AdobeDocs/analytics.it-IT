---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l'attributo Secure.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 1%

---


# writeSecureCookies

La `writeSecureCookies` variabile consente ad AppMeasurement di impostare cookie [](https://en.wikipedia.org/wiki/Secure_cookie) protetti per  Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement, sia ai cookie impostati con il `Util.CookieWrite()` metodo. Richiede AppMeasurement 2.18.0 o versione successiva.

>[!IMPORTANT]
>
>Se abilitate la `writeSecureCookies` variabile, accertatevi che tutto il contenuto del sito sia protetto tramite HTTPS. AppMeasurement non funziona se questa variabile è abilitata e sulla pagina è presente contenuto non sicuro.

## Scrivi cookie protetti nel lancio  Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.writeSecureCookies in AppMeasurement e Avvia editor di codice personalizzato

La `s.writeSecureCookies` variabile è un valore booleano che determina se AppMeasurement imposta l&#39;attributo Secure al momento della creazione di un cookie. Its default value is `false`. Impostate questa variabile su `true` se tutto il contenuto del sito è protetto e desiderate che i cookie impostati da AppMeasurement dispongano dell’attributo Secure.

```js
s.writeSecureCookies = true;
```
