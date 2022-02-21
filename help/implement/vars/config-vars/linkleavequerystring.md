---
title: linkLeaveQueryString
description: Consente la conservazione delle stringhe di query nelle dimensioni di tracciamento dei collegamenti.
feature: Variables
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# linkLeaveQueryString

Per impostazione predefinita, AppMeasurement elimina le stringhe di query dagli URL di tracciamento dei collegamenti. Utilizza la `linkLeaveQueryString` per mantenere le stringhe query nelle dimensioni di tracciamento dei collegamenti.

Per alcuni collegamenti di uscita e collegamenti di download, la parte importante dell’URL può trovarsi nella stringa di query. Ad esempio, un collegamento per il download, come `https://example.com/download.asp?filename=myfile.exe` contiene informazioni importanti sul collegamento nella stringa query.

Se le informazioni di tracciamento dei collegamenti non sono negli URL sul sito, non è necessario utilizzare questa variabile. L’eliminazione delle stringhe di query dagli URL di tracciamento dei collegamenti consente di limitare il numero di valori univoci contenuti nella dimensione.

Abilitazione `linkLeaveQueryString` si applica a tutte le dimensioni di tracciamento dei collegamenti (inclusi collegamenti personalizzati, collegamenti di uscita e collegamenti per il download).

>[!TIP]
>
>Questa variabile non influisce sulle dimensioni al di fuori del tracciamento dei collegamenti. Riguarda solo i collegamenti personalizzati, i collegamenti di uscita e i collegamenti per il download.

## Mantieni i parametri URL utilizzando i tag in Adobe Experience Platform

[!UICONTROL Keep URL Parameters] è una casella di controllo sotto [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Keep URL Parameters] casella di controllo.

Seleziona questa casella se desideri includere stringhe di query nelle dimensioni di tracciamento dei collegamenti.

## s.linkLeaveQueryString in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.linkLeaveQueryString` è una variabile booleana. Il valore predefinito è `false`.

* Se questa variabile è impostata su `true`, le stringhe di query vengono mantenute negli URL di tracciamento dei collegamenti.
* Se questa variabile è impostata su `false` oppure non definite, le stringhe di query vengono spogliate dagli URL di tracciamento dei collegamenti.

```js
s.linkLeaveQueryString = true;
```

## Esempio

Presta attenzione quando imposti questa variabile su true, in quanto può influenzare i filtri di tracciamento dei collegamenti come [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md)e [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Prendi in considerazione l’esempio seguente come se fosse attivato `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
