---
title: linkExternalFilters
description: Utilizza la variabile linkExternalFilters per facilitare l'uscita automatica del tracciamento dei collegamenti.
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# linkExternalFilters

AppMeasurement offre la possibilità di tracciare automaticamente i collegamenti che puntano all&#39;esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) è abilitata, una richiesta di immagine viene inviata all’Adobe a destra quando un visitatore fa clic su un collegamento per uscire dal sito. La `linkExternalFilters` e [`linkInternalFilters`](linkinternalfilters.md) le variabili determinano quali collegamenti sono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un inserire nell&#39;elenco Consentiti. Se un clic su un collegamento non corrisponde ad alcun `linkExternalFilters` non è considerato un collegamento di uscita. L’intero URL viene esaminato rispetto a questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitata, viene esaminata anche la stringa di query.

>[!TIP]
>
>Utilizza questa variabile solo se sai esattamente quali domini desideri considerare come collegamenti di uscita. Molte organizzazioni trovano che utilizzando `linkInternalFilters` è sufficiente per le loro esigenze di tracciamento dei collegamenti in uscita e non utilizza `linkExternalFilters`.

Se utilizzi entrambi `linkInternalFilters` e `linkExternalFilters` contemporaneamente, il collegamento selezionato deve corrispondere a `linkExternalFilters` **e** non corrispondente `linkInternalFilters` da considerare un collegamento di uscita. Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Collegamenti in uscita - Tracciamento tramite tag in Adobe Experience Platform

Il campo Track è un elenco di filtri separati da virgole (in genere domini) sotto [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Outbound Links - Track] campo .

Posiziona i filtri che desideri considerare sempre esterni in questo campo. Separa più domini con una virgola senza uno spazio.

## s.linkExternalFilters in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.linkExternalFilters` è una stringa contenente filtri (ad esempio domini) che considera collegamenti di uscita. Separa più domini utilizzando una virgola senza spazi.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Prendi in considerazione il seguente esempio di implementazione come se fosse attivato `adobe.com`:

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
