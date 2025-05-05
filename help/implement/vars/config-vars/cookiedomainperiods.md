---
title: cookieDomainPeriods
description: (Obsoleto) AppMeasurement di aiuto per determinare dove memorizzare i cookie quando il dominio di primo livello di un sito web contiene un punto.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 10%

---

# cookieDomainPeriods

>[!IMPORTANT]
>Questa variabile è obsoleta. Se usa uno dei seguenti:
>
>* AppMeasurement v2.26.x o successivo
>* Estensione Adobe Analytics v1.9.4 o successiva
>* Servizio Adobe Experience Cloud ID
>
>Questa variabile non esegue alcuna operazione, in quanto la libreria applicabile rileva automaticamente il dominio su cui impostare i cookie.

La variabile `cookieDomainPeriods` ha aiutato AppMeasurement a determinare dove impostare i cookie di Analytics indicando che il dominio di primo livello conteneva un periodo aggiuntivo. Questa variabile consente all’AppMeasurement di inserire il periodo aggiuntivo nel dominio di primo livello e impostare i cookie nella posizione corretta. Se il dominio di primo livello del sito web non include un periodo aggiuntivo, questa variabile non è necessaria.

* Per domini come `example.co.uk` o `www.example.co.jp`, impostare questa variabile su `"3"`.
* Per domini come `example.nsw.gov.au`, impostare questa variabile su `"4"`.
* Per domini come `example.com` o `products.example.org`, omettere di impostare questa variabile o impostarla su `"2"`.

>[!TIP]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `cookieDomainPeriods` sull&#39;URL di esempio `store.toys.example.com`. AppMeasurement riconosce che i cookie sono memorizzati in `example.com`, anche su URL con molti sottodomini.

Per le implementazioni in AppMeasurement v2.26.x o versione successiva, il cookie [`s_ac`](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/cookies/analytics) viene utilizzato per determinare automaticamente il dominio del cookie corretto. La libreria tenta prima di scrivere un cookie che include due periodi di dominio. Se l’impostazione di questo cookie non riesce, viene eseguito un nuovo tentativo, includendo più periodi di dominio fino a quando non riesce. Questo cookie viene eliminato immediatamente una volta impostato.

## Periodi del dominio dei cookie tramite Web SDK

L’SDK per web determina automaticamente il dominio corretto per impostare i cookie.

## Periodi del dominio dei cookie tramite l’estensione Adobe Analytics

**[!UICONTROL Domain Periods]** è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Domain Periods].

Impostare questo campo su `3` solo per i domini di primo livello contenenti un punto. In caso contrario, questo campo può essere lasciato vuoto.

## Periodi di dominio dei cookie in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `cookieDomainPeriods` è una stringa in genere impostata su `"3"` solo nei domini di primo livello che contengono un punto. Il valore predefinito è `"2"`, che ospita la maggior parte dei domini di primo livello come `.com` e `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
