---
title: fpcookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il tuo dominio ha un punto nel suo suffisso.
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 13%

---

# fpCookieDomainPeriods

Il `fpCookieDomainPeriods` Questa variabile consente ad AppMeasurement di determinare dove vengono impostati i cookie di Analytics, richiamando l’attenzione sul fatto che il suffisso di dominio contiene un periodo aggiuntivo. Questa variabile consente ad AppMeasurement di memorizzare il periodo aggiuntivo nel suffisso di dominio e impostare i cookie nella posizione giusta. Eredita il valore di [`cookieDomainPeriods`](cookiedomainperiods.md), ma è comunque una best practice da impostare se utilizzi un’implementazione di cookie di prima parte.

* Per domini come `example.com` o `www.example.com`, non è necessario impostare questa variabile. Se necessario, puoi impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `fpCookieDomainPeriods` sull’URL di esempio `store.toys.example.com`. AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati su `example.com`, anche su URL con molti sottodomini.

## Periodi del dominio di prime parti tramite Web SDK

L’SDK per web può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Periodi di dominio di prime parti tramite l’estensione Adobe Analytics

Periodi di dominio di prime parti è un campo sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL First-party Domain Periods].

Imposta questo campo su `3` solo sui domini contenenti un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.fpCookieDomainPeriods in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `fpCookieDomainPeriods` variabile è una stringa in genere impostata su `"3"`, solo sui domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che ospita la maggior parte dei domini.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
