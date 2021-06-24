---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l’attributo Secure.
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: b93cd06c2a8867f4848dc317e426b73dcfbb5dfd
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 1%

---

# writeSecureCookies

La variabile `writeSecureCookies` consente ad AppMeasurement di impostare [cookie protetti](https://en.wikipedia.org/wiki/Secure_cookie) per Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement sia ai cookie impostati utilizzando il metodo `Util.CookieWrite()` . Richiede AppMeasurement 2.18.0 o versione successiva.

`writeSecureCookies` si applica solo ai cookie impostati da JavaScript AppMeasurement (`s_fid`,  `s_cc` e  `s_sq`). I cookie impostati dalla risposta `https` (`s_vi` e `s_ecid`) possono essere impostati su &quot;Secure&quot; contattando l’Assistenza clienti Adobe.

Ulteriori informazioni sui cookie di Analytics [qui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!IMPORTANT]
>
>Se abiliti la variabile `writeSecureCookies` , assicurati che tutti i contenuti del sito siano protetti tramite HTTPS. AppMeasurement non funziona se questa variabile è abilitata e sulla pagina è presente contenuto non sicuro.

## Scrivere cookie sicuri in Adobe Experience Platform Launch

[!UICONTROL Write secure cookies] è una casella di controllo nel  [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra la casella di controllo [!UICONTROL Write secure cookies].

## s.writeSecureCookies nell&#39;editor di codice personalizzato AppMeasurement e Launch

La variabile `s.writeSecureCookies` è booleana che determina se AppMeasurement imposta l&#39;attributo Secure durante la creazione di un cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se tutto il contenuto del sito è protetto e desideri che nei cookie impostati da AppMeasurement sia presente l’attributo Secure .

```js
s.writeSecureCookies = true;
```
