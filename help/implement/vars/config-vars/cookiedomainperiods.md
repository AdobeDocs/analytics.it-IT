---
title: cookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il tuo dominio ha un punto nel suo suffisso.
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# cookieDomainPeriods

AppMeasurement determina la posizione del cookie guardando il suffisso di dominio e dominio. Per domini come `example.com`, AppMeasurement imposta i cookie nella posizione corretta. Tuttavia, per altri domini come `example.co.uk`, AppMeasurement può impostare i cookie in modo errato su `co.uk`. La maggior parte dei browser rifiuta i cookie impostati su questo dominio non valido, causando problemi con l&#39;identificazione dei visitatori.

La variabile `cookieDomainPeriods` aiuta AppMeasurement a determinare dove vengono impostati i cookie di Analytics, richiamando che il suffisso di dominio contiene un periodo aggiuntivo. Questa variabile consente ad AppMeasurement di contenere il periodo aggiuntivo nel suffisso di dominio e di impostare i cookie nella posizione giusta.

* Per i domini come `example.com` o `www.example.com`, non è necessario impostare questa variabile. Se necessario, puoi impostare questa variabile su `"2"`.
* Per i domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `cookieDomainPeriods` sull&#39;URL dell&#39;esempio `store.toys.example.com`. AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati su `example.com`, anche su URL con molti sottodomini.

## Periodi di dominio in Adobe Experience Platform Launch

Periodi di dominio è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Vai a `experience.adobe.com` e accedi quando richiesto.
1. Select [!UICONTROL Launch / Data Collection].
1. Fare clic su [!UICONTROL Go to Launch / Data Collection], quindi selezionare [!UICONTROL Tags].
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
1. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra il campo [!UICONTROL Domain Periods] .

Imposta questo campo su `3` solo sui domini che contengono un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.cookieDomainPeriods in AppMeasurement e nell’editor di codice personalizzato

La variabile `cookieDomainPeriods` è una stringa tipicamente impostata su `"3"`, solo nei domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che gestisce la maggior parte dei domini.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
