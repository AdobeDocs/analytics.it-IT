---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l’attributo Secure.
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# writeSecureCookies

La variabile `writeSecureCookies` consente ad AppMeasurement di impostare [cookie protetti](https://en.wikipedia.org/wiki/Secure_cookie) per Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement sia ai cookie impostati utilizzando il metodo `Util.CookieWrite()` . Richiede AppMeasurement 2.18.0 o versione successiva.

`writeSecureCookies` si applica solo ai cookie impostati da JavaScript AppMeasurement (`s_fid`,  `s_cc` e  `s_sq`). I cookie impostati dalla risposta `https` (`s_vi` e `s_ecid`) possono essere impostati su &quot;Secure&quot; contattando l’Assistenza clienti Adobe.

Ulteriori informazioni sui cookie di Analytics [qui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!IMPORTANT]
>
>Se abiliti la variabile `writeSecureCookies` , assicurati che tutti i contenuti del sito siano protetti tramite HTTPS. AppMeasurement non funziona se questa variabile è abilitata e sulla pagina è presente contenuto non sicuro.

## Scrivere cookie sicuri utilizzando i tag in Adobe Experience Platform

[!UICONTROL Write secure cookies] è una casella di controllo nel  [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra la casella di controllo [!UICONTROL Write secure cookies].

## s.writeSecureCookies in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.writeSecureCookies` è booleana che determina se AppMeasurement imposta l&#39;attributo Secure durante la creazione di un cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se tutto il contenuto del sito è protetto e desideri che nei cookie impostati da AppMeasurement sia presente l’attributo Secure .

```js
s.writeSecureCookies = true;
```
