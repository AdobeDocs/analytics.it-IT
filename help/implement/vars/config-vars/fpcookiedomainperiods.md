---
title: cookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il dominio ha un punto nel suo suffisso.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 1%

---


# fpCookieDomainPeriods

La `fpCookieDomainPeriods` variabile aiuta AppMeasurement a determinare dove  i cookie Analytics vengono impostati, indicando che il suffisso del dominio contiene un periodo aggiuntivo. Questa variabile consente ad AppMeasurement di contenere il periodo aggiuntivo nel suffisso del dominio e di impostare i cookie nella posizione giusta. Eredita il valore di [`cookieDomainPeriods`](cookiedomainperiods.md), ma è comunque una procedura consigliata se si utilizza un&#39;implementazione di cookie di prime parti.

* Per domini come `example.com` o `www.example.com`, questa variabile non deve essere impostata. Se necessario, potete impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostate `fpCookieDomainPeriods` sull’URL di esempio `store.toys.example.com`. AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati `example.com`, anche sugli URL con molti sottodomini.

## Periodi di dominio di prime parti nel lancio  Adobe Experience Platform

Periodi di dominio di prime parti è un campo situato sotto la struttura di [!UICONTROL Cookies] navigazione durante la configurazione dell&#39;estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandere la [!UICONTROL Cookies] struttura a soffietto, che mostra il [!UICONTROL First-party Domain Periods] campo.

Impostate questo campo `3` solo sui domini che contengono un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.fpCookieDomainPeriods in AppMeasurement e Avvia editor di codice personalizzato

La `fpCookieDomainPeriods` variabile è una stringa solitamente impostata su `"3"`, solo per i domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che contiene la maggior parte dei domini.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
