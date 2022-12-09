---
title: linkInternalFilters
description: Utilizza la variabile linkInternalFilters per facilitare l'uscita automatica del tracciamento dei collegamenti.
feature: Variables
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 9%

---

# linkInternalFilters

AppMeasurement offre la possibilità di tracciare automaticamente i collegamenti che puntano all&#39;esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) è abilitato e viene inviata una richiesta di immagine all’Adobe a destra quando un visitatore fa clic su un collegamento per uscire dal sito. La [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` le variabili determinano quali collegamenti sono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un elenco Bloccati. Se un clic su un collegamento non corrisponde ad alcun `linkInternalFilters` viene considerato un collegamento di uscita. L’intero URL viene esaminato rispetto a questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitata, viene esaminata anche la stringa di query.

Se utilizzi entrambi `linkInternalFilters` e `linkExternalFilters` contemporaneamente, il collegamento selezionato deve corrispondere a `linkExternalFilters` **e** non corrispondente `linkInternalFilters` da considerare un collegamento di uscita. Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

Activity Map utilizza questa variabile per determinare quali collegamenti sono interni al sito. Adobe consiglia di impostare questa variabile per le implementazioni che utilizzano Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) sono caratteristiche separate che soddisfano scopi separati. La `linkInternalFilters` Questa variabile funziona in modo specifico per il tracciamento dei collegamenti in uscita. I filtri URL interni sono un’impostazione Admin che consente di gestire le dimensioni delle origini di traffico come Dominio di riferimento.

## Esci dai collegamenti nell’SDK per web

I collegamenti si qualificano automaticamente come collegamento di uscita se il dominio di destinazione del collegamento è diverso da quello corrente `window.location.hostname`. L&#39;SDK per web non offre variabili di configurazione per modificare il rilevamento automatico dei collegamenti di uscita. Se devi personalizzare i domini che si qualificano come collegamento di uscita, puoi utilizzare la logica personalizzata nel `onBeforeEventSend` callback.

Vedi [Tracciamento automatico dei collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) per ulteriori informazioni, consulta la documentazione SDK per web .

## Collegamenti in uscita - Non tenere traccia dell’utilizzo dell’estensione Adobe Analytics

Il campo Never Track è un elenco di filtri separati da virgole (in genere domini) sotto [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo [!UICONTROL Outbound Links - Never Track].

Posiziona in questo campo i filtri che non dovranno mai essere tracciati come collegamenti di uscita. Separa più domini con una virgola senza uno spazio.

## s.linkInternalFilters in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.linkInternalFilters` è una stringa contenente filtri (come i domini) considerati interni al sito. Separa più filtri utilizzando una virgola senza spazi.

```js
s.linkInternalFilters = "example.com,example.net";
```

Prendi in considerazione il seguente esempio di implementazione come se fosse attivato `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
