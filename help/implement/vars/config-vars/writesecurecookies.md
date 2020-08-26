---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l'attributo Secure.
translation-type: tm+mt
source-git-commit: defb701d01747685a421b89a553f47efe40f1432
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 2%

---


# writeSecureCookies

La `writeSecureCookies` variabile consente ad AppMeasurement di impostare cookie [](https://en.wikipedia.org/wiki/Secure_cookie) protetti per Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement, sia ai cookie impostati con il `Util.CookieWrite()` metodo. Richiede AppMeasurement 2.18.0 o versione successiva.

>[!IMPORTANT]
>
>Se abilitate la `writeSecureCookies` variabile, accertatevi che tutto il contenuto del sito sia protetto tramite HTTPS. AppMeasurement non funziona se questa variabile è abilitata e sulla pagina è presente contenuto non sicuro.

## Scrivi cookie protetti in  Adobe Experience Platform Launch

[!UICONTROL Write secure cookies] è una casella di controllo sotto la struttura di [!UICONTROL Cookies] navigazione quando si configura l&#39;estensione Adobe Analytics .

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto  Adobe Analytics.
4. Espande la [!UICONTROL Cookies] fisarmonica, che mostra la [!UICONTROL Write secure cookies] casella di controllo.

## s.writeSecureCookies in AppMeasurement e Avvia editor di codice personalizzato

La `s.writeSecureCookies` variabile è un valore booleano che determina se AppMeasurement imposta l&#39;attributo Secure al momento della creazione di un cookie. Its default value is `false`. Impostate questa variabile su `true` se tutto il contenuto del sito è protetto e desiderate che i cookie impostati da AppMeasurement dispongano dell&#39;attributo Secure.

```js
s.writeSecureCookies = true;
```
