---
title: linkInternalFilters
description: Utilizza la variabile linkInternalFilters per facilitare il tracciamento automatico dei collegamenti di uscita.
feature: Appmeasurement Implementation
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 9%

---

# linkInternalFilters

AppMeasurement offre la possibilità di tenere traccia automaticamente dei collegamenti che puntano all’esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) è abilitato, viene inviata una richiesta di immagine a destra di Adobe quando un visitatore fa clic su un collegamento per uscire dal sito. Le variabili [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinano i collegamenti considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un elenco Bloccati. Se un clic di collegamento non corrisponde a nessun valore `linkInternalFilters`, viene considerato un collegamento di uscita. L’intero URL viene esaminato a fronte di questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitato, viene esaminata anche la stringa di query.

Se si utilizzano contemporaneamente `linkInternalFilters` e `linkExternalFilters`, il collegamento su cui è stato fatto clic deve corrispondere a `linkExternalFilters` **e** e non corrispondere a `linkInternalFilters` per essere considerato un collegamento di uscita. Se un collegamento cliccato corrisponde ai criteri del collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

Activity Map utilizza questa variabile per determinare quali collegamenti sono interni al sito. Adobe consiglia di impostare questa variabile per le implementazioni che utilizzano Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e [I filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) sono funzionalità separate che soddisfano scopi separati. La variabile `linkInternalFilters` funziona specificamente per il tracciamento dei collegamenti di uscita. I filtri URL interni sono un’impostazione amministratore utile per le dimensioni delle origini di traffico, come Dominio di riferimento.

## Collegamenti di uscita nel Web SDK

I collegamenti vengono qualificati automaticamente come collegamento di uscita se il dominio di destinazione del collegamento è diverso dall&#39;attuale `window.location.hostname`. Il Web SDK non offre variabili di configurazione per modificare il rilevamento automatico dei collegamenti di uscita. Se è necessario personalizzare i domini qualificati come collegamento di uscita, è possibile utilizzare la logica personalizzata nel callback `onBeforeEventSend`.

Per ulteriori informazioni, vedere [Tracciamento automatico dei collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=it#automaticLinkTracking) nella documentazione di Web SDK.

## Collegamenti in uscita: non tenere mai traccia di utilizzando l’estensione Adobe Analytics

Il campo Never Track è un elenco separato da virgole di filtri (in genere domini) nel Pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo [!UICONTROL Outbound Links - Never Track].

Inserire in questo campo i filtri che non dovranno mai essere tracciati come collegamenti di uscita. Separa più domini con una virgola senza uno spazio.

## s.linkInternalFilters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkInternalFilters` è una stringa contenente i filtri (ad esempio domini) considerati interni al sito. Separa più filtri utilizzando una virgola senza spazi.

```js
s.linkInternalFilters = "example.com,example.net";
```

Considera il seguente esempio di implementazione come se fosse in `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
