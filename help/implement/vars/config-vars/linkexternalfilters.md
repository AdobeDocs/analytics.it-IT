---
title: linkExternalFilters
description: Utilizza la variabile linkExternalFilters per facilitare il tracciamento automatico dei collegamenti in uscita.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkExternalFilters

AppMeasurement consente di tenere traccia automaticamente dei collegamenti che puntano all’esterno del sito. In caso `trackExternalLinks` affermativo, `true`viene inviata una richiesta di immagine ad Adobe direttamente quando un visitatore fa clic su un collegamento per uscire dal sito. Le `linkTrackExternalFilters` e `linkTrackInternalFilters` le variabili determinano quali collegamenti vengono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta in modo simile alla whitelist. Se un clic di collegamento non corrisponde ad alcun `linkExternalFilters` valore, non viene considerato un collegamento di uscita. L’intero URL viene analizzato rispetto a questa variabile. Se `linkLeaveQueryString` è `true`, viene esaminata anche la stringa di query.

> [!TIP] Utilizzate questa variabile solo se conoscete esattamente i domini che desiderate considerare come collegamenti di uscita. Molte organizzazioni ritengono che l&#39;uso `linkInternalFilters` sia sufficiente per le loro esigenze di tracciamento dei collegamenti in uscita e non lo utilizzano `linkExternalFilters`.

Se utilizzate sia `linkInternalFilters` che `linkExternalFilters` simultaneamente, il collegamento su cui avete fatto clic deve corrispondere `linkExternalFilters` e non deve corrispondere **** `linkInternalFilters` a quello su cui avete fatto clic per essere considerato un collegamento di uscita. Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Collegamenti in uscita - Track in Adobe Experience Platform Launch

Il campo Track è un elenco di filtri (in genere domini) separati da virgole all’interno del [!UICONTROL Link Tracking] pannello Accordion quando si configura l’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espandere la [!UICONTROL Link Tracking] struttura a soffietto, che mostra il [!UICONTROL Outbound Links - Track] campo.

Posizionare i filtri che si desidera considerare sempre esterni in questo campo. Separa più domini con una virgola senza uno spazio.

## s.linkExternalFilters in AppMeasurement e Launch editor di codice personalizzato

La `s.linkExternalFilters` variabile è una stringa contenente filtri (ad esempio domini) che puoi considerare come collegamenti di uscita. Separate più domini utilizzando una virgola senza spazi.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considerate il seguente esempio di implementazione come se fosse attivato `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is not considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
