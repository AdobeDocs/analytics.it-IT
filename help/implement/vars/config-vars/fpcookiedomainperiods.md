---
title: fpcookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il tuo dominio ha un punto nel suo suffisso.
feature: Appmeasurement Implementation
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 13%

---

# fpCookieDomainPeriods

La variabile `fpCookieDomainPeriods` consente ad AppMeasurement di determinare dove vengono impostati i cookie di Analytics, richiamando l&#39;attenzione sul fatto che il suffisso di dominio contiene un punto aggiuntivo. Questa variabile consente ad AppMeasurement di inserire il periodo aggiuntivo nel suffisso di dominio e impostare i cookie nella posizione giusta. Eredita il valore di [`cookieDomainPeriods`](cookiedomainperiods.md), ma è comunque una best practice da impostare se utilizzi un&#39;implementazione di cookie di prima parte.

* Per domini come `example.com` o `www.example.com`, non è necessario impostare questa variabile. Se necessario, è possibile impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`, impostare questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `fpCookieDomainPeriods` sull&#39;URL di esempio `store.toys.example.com`. Per impostazione predefinita, AppMeasurement riconosce che i cookie devono essere memorizzati in `example.com`, anche su URL con molti sottodomini.

## Periodi di dominio di prime parti tramite Web SDK

Il Web SDK può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Periodi di dominio di prime parti tramite l’estensione Adobe Analytics

Periodi di dominio di prime parti è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL First-party Domain Periods].

Impostare questo campo su `3` solo per i domini che contengono un punto nel suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.fpCookieDomainPeriods in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `fpCookieDomainPeriods` è una stringa in genere impostata su `"3"` solo nei domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che supporta la maggior parte dei domini.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
