---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l’attributo Secure.
feature: Appmeasurement Implementation
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Eifs1WrhCzcOdHJ2HJADqZrIkNFgC7h76do3W56otjA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 12%

---

# writeSecureCookies

La variabile `writeSecureCookies` consente ad AppMeasurement di impostare [Cookie protetti](https://en.wikipedia.org/wiki/Secure_cookie) per Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement che ai cookie impostati con il metodo `Util.CookieWrite()`. Richiede AppMeasurement 2.18.0 o versione successiva.

`writeSecureCookies` si applica solo ai cookie impostati da AppMeasurement JavaScript (`s_fid`, `s_cc` e `s_sq`). I cookie impostati dalla risposta `https` (`s_vi` e `s_ecid`) possono essere impostati su &quot;protetti&quot; contattando l&#39;Assistenza clienti di Adobe.

Ulteriori informazioni sui cookie di Analytics [qui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!WARNING]
>
>Se abiliti la variabile `writeSecureCookies`, assicurati che tutto il contenuto del sito venga servito in modo sicuro tramite HTTPS. La raccolta dati non funziona correttamente se questa variabile è abilitata e la pagina contiene contenuto non sicuro.

## Utilizzare i cookie protetti con il Web SDK

Se il sito utilizza il protocollo HTTPS, l&#39;attributo Secure viene impostato per tutti i cookie impostati da Web SDK.

## Scrivere cookie protetti utilizzando l’estensione Adobe Analytics

[!UICONTROL Write secure cookies] è una casella di controllo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandere il pannello a soffietto [!UICONTROL Cookies], che mostra la casella di controllo [!UICONTROL Write secure cookies].

## s.writeSecureCookies in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.writeSecureCookies` è un valore booleano che determina se AppMeasurement imposta l&#39;attributo Secure durante la creazione di un cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se tutto il contenuto del sito è protetto e desideri che l&#39;attributo Secure sia impostato da AppMeasurement.

```js
s.writeSecureCookies = true;
```
