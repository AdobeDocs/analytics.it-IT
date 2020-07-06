---
title: linkLeaveQueryString
description: Consente di mantenere le stringhe di query nelle dimensioni del tracciamento dei collegamenti.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---


# linkLeaveQueryString

Per impostazione predefinita, AppMeasurement elimina le stringhe di query dagli URL di tracciamento dei collegamenti. Utilizzate la `linkLeaveQueryString` variabile per mantenere le stringhe di query nelle dimensioni di tracciamento dei collegamenti.

Per alcuni collegamenti di uscita e di download, la parte importante dell’URL può essere rappresentata dalla stringa di query. Ad esempio, un collegamento di download, come `https://example.com/download.asp?filename=myfile.exe` contiene informazioni importanti sul collegamento nella stringa di query.

Se le informazioni sul tracciamento dei collegamenti non sono negli URL del sito, l’utilizzo di questa variabile non è necessario. Strappare le stringhe di query dagli URL di tracciamento dei collegamenti per limitare il numero di valori univoci contenuti nella dimensione.

L’abilitazione `linkLeaveQueryString` si applica a tutte le dimensioni di tracciamento dei collegamenti (inclusi collegamenti personalizzati, collegamenti di uscita e collegamenti per il download).

>[!TIP]
>
>Questa variabile non influisce sulle dimensioni al di fuori del tracciamento dei collegamenti. Riguarda solo i collegamenti personalizzati, i collegamenti di uscita e i collegamenti per il download.

## Mantieni parametri URL nel lancio  Adobe Experience Platform

[!UICONTROL Keep URL Parameters] è una casella di controllo sotto la struttura di [!UICONTROL Link Tracking] navigazione quando si configura l&#39;estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espande la [!UICONTROL Link Tracking] fisarmonica, che mostra la [!UICONTROL Keep URL Parameters] casella di controllo.

Selezionare questa casella se si desidera includere le stringhe di query nelle dimensioni del tracciamento dei collegamenti.

## s.linkLeftQueryString nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.linkLeaveQueryString` variabile è booleana. Its default value is `false`.

* Se questa variabile è impostata su `true`, le stringhe di query vengono mantenute negli URL di tracciamento dei collegamenti.
* Se questa variabile è impostata su `false` o non è definita, le stringhe di query vengono eliminate dagli URL di tracciamento dei collegamenti.

```js
s.linkLeaveQueryString = true;
```

## Esempio

Presta attenzione quando imposti questa variabile su true, in quanto può influenzare filtri di tracciamento dei collegamenti come [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md)e [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Considerare l&#39;esempio seguente come se fosse in `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
