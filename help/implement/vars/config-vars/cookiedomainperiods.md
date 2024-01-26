---
title: cookieDomainPeriods
description: AppMeasurement di aiuto per capire quale dominio memorizzare i cookie se nel dominio è presente un punto nel suffisso.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 12%

---


# cookieDomainPeriods

AppMeasurement determina la posizione del cookie osservando il dominio e il suffisso di dominio. Per domini come `example.com`, AppMeasurement imposta i cookie nella posizione corretta. Tuttavia, per altri domini come `example.co.uk`, AppMeasurement può erroneamente impostare i cookie su `co.uk`. La maggior parte dei browser rifiuta i cookie impostati su questo dominio non valido, causando problemi con l’identificazione dei visitatori.

Il `cookieDomainPeriods` La variabile aiuta AppMeasurement a determinare dove vengono impostati i cookie di Analytics richiamando l’attenzione sul fatto che il suffisso di dominio contiene un punto aggiuntivo. Questa variabile consente ad AppMeasurement di inserire il periodo aggiuntivo nel suffisso di dominio e impostare i cookie nella posizione giusta.

* Per domini come `example.com` o `www.example.com`, non è necessario impostare questa variabile. Se necessario, puoi impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `cookieDomainPeriods` sull’URL di esempio `store.toys.example.com`. L’AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati su `example.com`, anche su URL con molti sottodomini.

## Periodi di dominio con Web SDK

L’SDK per web può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Periodi di dominio tramite l’estensione Adobe Analytics

Periodi di dominio è un campo sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Domain Periods].

Imposta questo campo su `3` solo sui domini contenenti un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.cookieDomainPeriods in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `cookieDomainPeriods` variabile è una stringa in genere impostata su `"3"`, solo sui domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che ospita la maggior parte dei domini.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
