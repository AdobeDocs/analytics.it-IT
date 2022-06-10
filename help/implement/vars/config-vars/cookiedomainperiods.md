---
title: cookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il tuo dominio ha un punto nel suo suffisso.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---


# cookieDomainPeriods

AppMeasurement determina la posizione del cookie guardando il suffisso di dominio e dominio. Per domini come `example.com`, AppMeasurement imposta i cookie nella posizione corretta. Tuttavia, per altri domini come `example.co.uk`, AppMeasurement può impostare per errore i cookie su `co.uk`. La maggior parte dei browser rifiuta i cookie impostati su questo dominio non valido, causando problemi con l&#39;identificazione dei visitatori.

La `cookieDomainPeriods` aiuta AppMeasurement a determinare dove vengono impostati i cookie di Analytics richiamando che il suffisso di dominio contiene un periodo aggiuntivo. Questa variabile consente ad AppMeasurement di contenere il periodo aggiuntivo nel suffisso di dominio e di impostare i cookie nella posizione giusta.

* Per domini come `example.com` o `www.example.com`, questa variabile non deve essere impostata. Se necessario, puoi impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `cookieDomainPeriods` sull’URL di esempio `store.toys.example.com`. AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati in `example.com`, anche sugli URL con molti sottodomini.

## Periodi di dominio che utilizzano l’SDK per web

L&#39;SDK per web può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Periodi di dominio con l’estensione Adobe Analytics

Periodi di dominio è un campo sotto [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
1. Espandi la [!UICONTROL Cookies] fisarmonica, che rivela [!UICONTROL Domain Periods] campo .

Imposta questo campo su `3` solo nei domini che contengono un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.cookieDomainPeriods in AppMeasurement e nell’editor di codici personalizzati dell’estensione Analytics

La `cookieDomainPeriods` è una stringa generalmente impostata su `"3"`, solo nei domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che gestisce la maggior parte dei domini.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
