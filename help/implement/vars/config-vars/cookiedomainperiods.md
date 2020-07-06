---
title: cookieDomainPeriods
description: Aiuta AppMeasurement a capire quale dominio memorizzare i cookie se il dominio ha un punto nel suo suffisso.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---


# cookieDomainPeriods

AppMeasurement determina la posizione del cookie osservando il suffisso del dominio e del dominio. Per domini come `example.com`, AppMeasurement imposta i cookie nella posizione corretta. Tuttavia, per altri domini come `example.co.uk`, AppMeasurement può impostare erroneamente i cookie su `co.uk`. La maggior parte dei browser rifiuta i cookie impostati su questo dominio non valido, causando problemi con l&#39;identificazione del visitatore.

La `cookieDomainPeriods` variabile aiuta AppMeasurement a determinare dove  i cookie Analytics vengono impostati, indicando che il suffisso del dominio contiene un periodo aggiuntivo. Questa variabile consente ad AppMeasurement di contenere il periodo aggiuntivo nel suffisso del dominio e di impostare i cookie nella posizione giusta.

* Per domini come `example.com` o `www.example.com`, questa variabile non deve essere impostata. Se necessario, potete impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.

>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostate `cookieDomainPeriods` sull’URL di esempio `store.toys.example.com`. AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati `example.com`, anche sugli URL con molti sottodomini.

## Periodi di dominio  lancio Adobe Experience Platform

Periodi di dominio è un campo situato sotto la struttura di [!UICONTROL Cookies] navigazione quando si configura l’estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandere la [!UICONTROL Cookies] struttura a soffietto, che mostra il [!UICONTROL Domain Periods] campo.

Impostate questo campo `3` solo sui domini che contengono un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## s.cookieDomainPeriods in AppMeasurement e Avvia editor di codice personalizzato

La `cookieDomainPeriods` variabile è una stringa solitamente impostata su `"3"`, solo per i domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che contiene la maggior parte dei domini.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
