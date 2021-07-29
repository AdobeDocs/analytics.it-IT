---
title: linkInternalFilters
description: Utilizza la variabile linkInternalFilters per facilitare l'uscita automatica del tracciamento dei collegamenti.
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# linkInternalFilters

AppMeasurement offre la possibilità di tracciare automaticamente i collegamenti che puntano all&#39;esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) è abilitato, una richiesta di immagine viene inviata all’Adobe a destra quando un visitatore fa clic su un collegamento per uscire dal sito. Le variabili [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinano quali collegamenti vengono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un inserire nell&#39;elenco Bloccati. Se un clic su un collegamento non corrisponde ad alcun valore `linkInternalFilters`, viene considerato un collegamento di uscita. L’intero URL viene esaminato rispetto a questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitato, viene esaminata anche la stringa di interrogazione.

Se utilizzi contemporaneamente sia `linkInternalFilters` che `linkExternalFilters` , il collegamento selezionato deve corrispondere a `linkExternalFilters` **e** non corrispondere a `linkInternalFilters` per essere considerato un collegamento di uscita. Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

Activity Map utilizza questa variabile per determinare quali collegamenti sono interni al sito. Adobe consiglia di impostare questa variabile per le implementazioni che utilizzano Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e i  [filtri URL ](/help/admin/admin/internal-url-filter-admin.md) interni sono funzionalità separate che soddisfano scopi separati. La variabile `linkInternalFilters` funziona in modo specifico per il tracciamento dei collegamenti in uscita. I filtri URL interni sono un’impostazione Admin che consente di gestire le dimensioni delle origini di traffico come Dominio di riferimento.

## Collegamenti in uscita - Non tenere traccia dell’utilizzo dei tag in Adobe Experience Platform

Il campo Never Track è un elenco di filtri separati da virgole (solitamente domini) sotto il pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Link Tracking] pannello a soffietto, che mostra il campo [!UICONTROL Outbound Links - Never Track] .

Posiziona in questo campo i filtri che non dovranno mai essere tracciati come collegamenti di uscita. Separa più domini con una virgola senza uno spazio.

## s.linkInternalFilters in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.linkInternalFilters` è una stringa contenente filtri (come i domini) considerati interni al sito. Separa più filtri utilizzando una virgola senza spazi.

```js
s.linkInternalFilters = "example.com,example.net";
```

Prendi in considerazione il seguente esempio di implementazione come se fosse su `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
