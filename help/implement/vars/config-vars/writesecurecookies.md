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

La variabile `writeSecureCookies` consente ad AppMeasurement di impostare [Cookie protetti](https://en.wikipedia.org/wiki/Secure_cookie) per Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement che ai cookie impostati con il metodo `Util.CookieWrite()`. Richiede l&#39;AppMeasurement 2.18.0 o versione successiva.

`writeSecureCookies` si applica solo ai cookie impostati da AppMeasurement JavaScript (`s_fid`, `s_cc` e `s_sq`). I cookie impostati dalla risposta `https` (`s_vi` e `s_ecid`) possono essere impostati su &quot;protetti&quot; contattando l&#39;Assistenza clienti Adobe.

Ulteriori informazioni sui cookie di Analytics [qui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>Se abiliti la variabile `writeSecureCookies`, assicurati che tutto il contenuto del sito venga servito in modo sicuro tramite HTTPS. La raccolta dati non funziona correttamente se questa variabile è abilitata e la pagina contiene contenuto non sicuro.

## Utilizzare i cookie protetti con Web SDK

Se il sito utilizza il protocollo HTTPS, l’attributo Secure viene impostato per tutti i cookie impostati dall’SDK web.

## Scrivere cookie protetti utilizzando l’estensione Adobe Analytics

[!UICONTROL Write secure cookies] è una casella di controllo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandere il pannello a soffietto [!UICONTROL Cookies], che mostra la casella di controllo [!UICONTROL Write secure cookies].

## s.writeSecureCookies in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.writeSecureCookies` è un valore booleano che determina se AppMeasurement imposta l&#39;attributo Secure durante la creazione di un cookie. Il valore predefinito è `false`. Impostare questa variabile su `true` se tutto il contenuto del sito è protetto e si desidera che l&#39;attributo Secure sia impostato da AppMeasurement.

```js
s.writeSecureCookies = true;
```
