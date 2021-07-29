---
title: cookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il tuo dominio ha un punto nel suo suffisso.
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# fpCookieDomainPeriods

La variabile `fpCookieDomainPeriods` aiuta AppMeasurement a determinare dove vengono impostati i cookie di Analytics, richiamando che il suffisso di dominio contiene un periodo aggiuntivo. Questa variabile consente ad AppMeasurement di contenere il periodo aggiuntivo nel suffisso di dominio e di impostare i cookie nella posizione giusta. Eredita il valore di [`cookieDomainPeriods`](cookiedomainperiods.md), ma è comunque una best practice da impostare se utilizzi un’implementazione di cookie di prime parti.

* Per i domini come `example.com` o `www.example.com`, non è necessario impostare questa variabile. Se necessario, puoi impostare questa variabile su `"2"`.
* Per i domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `fpCookieDomainPeriods` sull&#39;URL dell&#39;esempio `store.toys.example.com`. AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati su `example.com`, anche su URL con molti sottodomini.

## Periodi di dominio di prime parti utilizzando i tag in Adobe Experience Platform

Periodi di dominio di prime parti è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra il campo [!UICONTROL First-party Domain Periods] .

Imposta questo campo su `3` solo sui domini che contengono un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.fpCookieDomainPeriods in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `fpCookieDomainPeriods` è una stringa tipicamente impostata su `"3"`, solo nei domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che gestisce la maggior parte dei domini.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
