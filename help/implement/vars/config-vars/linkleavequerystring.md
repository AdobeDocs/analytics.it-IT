---
title: linkLeaveQueryString
description: Consente la conservazione delle stringhe di query nelle dimensioni di tracciamento dei collegamenti.
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# linkLeaveQueryString

Per impostazione predefinita, AppMeasurement elimina le stringhe di query dagli URL di tracciamento dei collegamenti. Utilizza la variabile `linkLeaveQueryString` per mantenere le stringhe di query nelle dimensioni di tracciamento dei collegamenti.

Per alcuni collegamenti di uscita e collegamenti di download, la parte importante dell’URL può trovarsi nella stringa di query. Ad esempio, un collegamento di download come `https://example.com/download.asp?filename=myfile.exe` contiene informazioni importanti sul collegamento nella stringa di query.

Se le informazioni di tracciamento dei collegamenti non sono negli URL sul sito, non è necessario utilizzare questa variabile. L’eliminazione delle stringhe di query dagli URL di tracciamento dei collegamenti consente di limitare il numero di valori univoci contenuti nella dimensione.

L’abilitazione di `linkLeaveQueryString` si applica a tutte le dimensioni di tracciamento dei collegamenti (inclusi collegamenti personalizzati, collegamenti di uscita e collegamenti per il download).

>[!TIP]
>
>Questa variabile non influisce sulle dimensioni al di fuori del tracciamento dei collegamenti. Riguarda solo i collegamenti personalizzati, i collegamenti di uscita e i collegamenti per il download.

## Mantieni i parametri URL utilizzando i tag in Adobe Experience Platform

[!UICONTROL Keep URL Parameters] è una casella di controllo nel  [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Link Tracking] pannello a soffietto, che mostra la casella di controllo [!UICONTROL Keep URL Parameters].

Seleziona questa casella se desideri includere stringhe di query nelle dimensioni di tracciamento dei collegamenti.

## s.linkLeaveQueryString in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.linkLeaveQueryString` è booleana. Il valore predefinito è `false`.

* Se questa variabile è impostata su `true`, le stringhe di query vengono mantenute negli URL di tracciamento dei collegamenti.
* Se questa variabile è impostata su `false` o non è definita, le stringhe di query vengono tolte dagli URL di tracciamento dei collegamenti.

```js
s.linkLeaveQueryString = true;
```

## Esempio

Presta attenzione quando imposti questa variabile su true, in quanto può influenzare i filtri di tracciamento dei collegamenti come [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md) e [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Considera l&#39;esempio seguente come se si trovasse su `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
