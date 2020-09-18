---
title: linkInternalFilters
description: Utilizza la variabile linkInternalFilters per facilitare il tracciamento automatico dei collegamenti in uscita.
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 1%

---


# linkInternalFilters

AppMeasurement offre la possibilità di tracciare automaticamente i collegamenti che puntano all&#39;esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) è abilitata, una richiesta di immagine viene inviata a  diritto di Adobe quando un visitatore fa clic su un collegamento per uscire dal sito. Le [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` le variabili determinano quali collegamenti vengono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un inserire nell&#39;elenco Bloccati . Se un clic di collegamento non corrisponde ad alcun `linkInternalFilters` valore, viene considerato un collegamento di uscita. L’intero URL viene analizzato rispetto a questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitata, viene esaminata anche la stringa di query.

Se utilizzate sia `linkInternalFilters` che `linkExternalFilters` simultaneamente, il collegamento su cui avete fatto clic deve corrispondere `linkExternalFilters` e non deve corrispondere **** `linkInternalFilters` a quello su cui avete fatto clic per essere considerato un collegamento di uscita. Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

Activity Map utilizza questa variabile per determinare quali collegamenti sono interni al sito.  Adobe consiglia di impostare questa variabile per le implementazioni che utilizzano Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni sono funzioni distinte che soddisfano scopi separati. La `linkInternalFilters` variabile funziona in modo specifico per il tracciamento dei collegamenti di uscita. I filtri URL interni sono un&#39;impostazione Amministratore che consente di gestire le dimensioni delle origini del traffico come Dominio di riferimento.

## Collegamenti in uscita - Non tenere traccia  Adobe Experience Platform Launch

Il campo Mai traccia è un elenco separato da virgole di filtri (in genere domini) sotto la [!UICONTROL Link Tracking] struttura di navigazione durante la configurazione dell’estensione Adobe Analytics .

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto  Adobe Analytics.
4. Espandere la [!UICONTROL Link Tracking] struttura a soffietto, che mostra il [!UICONTROL Outbound Links - Never Track] campo.

Inserite in questo campo i filtri che non devono mai essere tracciati come collegamenti di uscita. Separa più domini con una virgola senza uno spazio.

## s.linkInternalFilters in AppMeasurement e Launch editor di codice personalizzato

La `s.linkInternalFilters` variabile è una stringa contenente filtri (ad esempio domini) che vengono considerati interni al sito. Separate più filtri utilizzando una virgola senza spazi.

```js
s.linkInternalFilters = "example.com,example.net";
```

Considerate il seguente esempio di implementazione come se fosse attivato `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
