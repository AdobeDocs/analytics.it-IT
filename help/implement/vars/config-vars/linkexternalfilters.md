---
title: linkExternalFilters
description: Utilizza la variabile linkExternalFilters per facilitare l'uscita automatica del tracciamento dei collegamenti.
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# linkExternalFilters

AppMeasurement offre la possibilità di tracciare automaticamente i collegamenti che puntano all&#39;esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) è abilitato, una richiesta di immagine viene inviata all’Adobe a destra quando un visitatore fa clic su un collegamento per uscire dal sito. Le variabili `linkExternalFilters` e [`linkInternalFilters`](linkinternalfilters.md) determinano quali collegamenti vengono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un inserire nell&#39;elenco Consentiti. Se un clic su un collegamento non corrisponde ad alcun valore `linkExternalFilters`, non viene considerato un collegamento di uscita. L’intero URL viene esaminato rispetto a questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitato, viene esaminata anche la stringa di interrogazione.

>[!TIP]
>
>Utilizza questa variabile solo se sai esattamente quali domini desideri considerare come collegamenti di uscita. Molte organizzazioni ritengono che l’utilizzo di `linkInternalFilters` sia sufficiente per le loro esigenze di tracciamento dei collegamenti in uscita e non utilizzi `linkExternalFilters`.

Se utilizzi contemporaneamente sia `linkInternalFilters` che `linkExternalFilters` , il collegamento selezionato deve corrispondere a `linkExternalFilters` **e** non corrispondere a `linkInternalFilters` per essere considerato un collegamento di uscita. Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Collegamenti in uscita - Tracciamento tramite tag in Adobe Experience Platform

Il campo Track è un elenco di filtri separati da virgole (solitamente domini) sotto il pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Link Tracking] pannello a soffietto, che mostra il campo [!UICONTROL Outbound Links - Track] .

Posiziona i filtri che desideri considerare sempre esterni in questo campo. Separa più domini con una virgola senza uno spazio.

## s.linkExternalFilters in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.linkExternalFilters` è una stringa contenente filtri (come i domini) che consideri collegamenti di uscita. Separa più domini utilizzando una virgola senza spazi.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Prendi in considerazione il seguente esempio di implementazione come se fosse su `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
