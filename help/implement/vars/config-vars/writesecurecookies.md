---
title: writeSecureCookies
description: Consente ad AppMeasurement di impostare i cookie con l’attributo Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# writeSecureCookies

La `writeSecureCookies` permette ad AppMeasurement di impostare [Cookie protetti](https://en.wikipedia.org/wiki/Secure_cookie) per Analytics. Questa impostazione si applica sia ai cookie ID visitatore impostati da AppMeasurement che ai cookie impostati utilizzando `Util.CookieWrite()` metodo . Richiede AppMeasurement 2.18.0 o versione successiva.

`writeSecureCookies` si applica solo ai cookie impostati da JavaScript AppMeasurement (`s_fid`, `s_cc` e `s_sq`). Cookie impostati da `https` response (`s_vi` e `s_ecid`) può essere impostato su &quot;sicuro&quot; contattando l’Assistenza clienti di Adobe.

Ulteriori informazioni sui cookie di Analytics [qui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!IMPORTANT]
>
>Se si abilita `writeSecureCookies` assicurati che tutti i contenuti del sito siano protetti tramite HTTPS. AppMeasurement non funziona se questa variabile è abilitata e sulla pagina è presente contenuto non sicuro.

## Scrivere cookie sicuri utilizzando i tag in Adobe Experience Platform

[!UICONTROL Write secure cookies] è una casella di controllo sotto [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Cookies] fisarmonica, che rivela [!UICONTROL Write secure cookies] casella di controllo.

## s.writeSecureCookies in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.writeSecureCookies` è un valore booleano che determina se AppMeasurement imposta l&#39;attributo Secure durante la creazione di un cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se tutto il contenuto del sito è protetto e desideri che nei cookie impostati da AppMeasurement sia presente l’attributo Secure .

```js
s.writeSecureCookies = true;
```
