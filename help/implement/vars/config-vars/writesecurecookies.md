---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l’attributo Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 12%

---

# writeSecureCookies

Il `writeSecureCookies` variabile consente all&#39;AppMeasurement di impostare [Cookie protetti](https://en.wikipedia.org/wiki/Secure_cookie) per Analytics. Questa impostazione si applica sia ai cookie dell’ID visitatore impostati da AppMeasurement, sia ai cookie impostati utilizzando `Util.CookieWrite()` metodo. Richiede l&#39;AppMeasurement 2.18.0 o versione successiva.

`writeSecureCookies` si applica solo ai cookie impostati da AppMeasurement JavaScript (`s_fid`, `s_cc` e `s_sq`). Cookie impostati da `https` risposta (`s_vi` e `s_ecid`) può essere impostato su &quot;protetto&quot; contattando l’Assistenza clienti Adobe.

Ulteriori informazioni sui cookie di Analytics [qui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>Se si abilita `writeSecureCookies` , assicurati che tutto il contenuto del sito venga distribuito in modo sicuro tramite HTTPS. La raccolta dati non funziona correttamente se questa variabile è abilitata e la pagina contiene contenuto non sicuro.

## Utilizzare i cookie protetti con Web SDK

Se il sito utilizza il protocollo HTTPS, l’attributo Secure viene impostato per tutti i cookie impostati dall’SDK web.

## Scrivere cookie protetti utilizzando l’estensione Adobe Analytics

[!UICONTROL Write secure cookies] è una casella di controllo sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi [!UICONTROL Cookies] Pannello a soffietto, che mostra [!UICONTROL Write secure cookies] casella di controllo.

## s.writeSecureCookies in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.writeSecureCookies` La variabile è un valore booleano che determina se AppMeasurement imposta l’attributo Secure durante la creazione di un cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se tutto il contenuto del sito è sicuro e desideri che l’attributo Secure sia impostato dall’AppMeasurement.

```js
s.writeSecureCookies = true;
```
