---
title: linkInternalFilters
description: Utilizza la variabile linkInternalFilters per facilitare il tracciamento automatico dei collegamenti di uscita.
feature: Variables
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 9%

---

# linkInternalFilters

AppMeasurement offre la possibilità di tenere traccia automaticamente dei collegamenti che puntano all’esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) è abilitato, viene inviata una richiesta di immagine all&#39;Adobe destro quando un visitatore fa clic su un collegamento per uscire dal sito. Il [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` Le variabili determinano quali collegamenti sono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un elenco Bloccati. Se un clic del collegamento non corrisponde a nessuno `linkInternalFilters` valori, viene considerato un collegamento di uscita. L’intero URL viene esaminato a fronte di questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è attivato, viene esaminata anche la stringa di query.

Se usa entrambi `linkInternalFilters` e `linkExternalFilters` contemporaneamente, il collegamento su cui è stato fatto clic deve corrispondere `linkExternalFilters` **e** non corrisponde `linkInternalFilters` per essere considerato un collegamento di uscita. Se un collegamento cliccato corrisponde ai criteri del collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

Activity Map utilizza questa variabile per determinare quali collegamenti sono interni al sito. L’Adobe consiglia di impostare questa variabile per le implementazioni che utilizzano Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) sono caratteristiche separate che soddisfano scopi separati. Il `linkInternalFilters` la variabile funziona in modo specifico per il tracciamento dei collegamenti di uscita. I filtri URL interni sono un’impostazione amministratore utile per le dimensioni delle origini di traffico, come Dominio di riferimento.

## Collegamenti di uscita nel Web SDK

I collegamenti vengono automaticamente qualificati come collegamento di uscita se il dominio di destinazione del collegamento è diverso dal dominio corrente `window.location.hostname`. L’SDK per web non offre variabili di configurazione per modificare il rilevamento automatico dei collegamenti di uscita. Se devi personalizzare i domini idonei come collegamento di uscita, puoi utilizzare la logica personalizzata nel `onBeforeEventSend` callback.

Consulta [Tracciamento automatico dei collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Collegamenti in uscita: non tenere mai traccia di utilizzando l’estensione Adobe Analytics

Il campo Never Track è un elenco separato da virgole di filtri (in genere domini) sotto il [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo [!UICONTROL Outbound Links - Never Track].

Inserire in questo campo i filtri che non dovranno mai essere tracciati come collegamenti di uscita. Separa più domini con una virgola senza uno spazio.

## s.linkInternalFilters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkInternalFilters` variabile è una stringa contenente filtri (come domini) considerati interni al sito. Separa più filtri utilizzando una virgola senza spazi.

```js
s.linkInternalFilters = "example.com,example.net";
```

Considera il seguente esempio di implementazione come se fosse attivo `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
