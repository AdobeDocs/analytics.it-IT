---
title: linkExternalFilters
description: Utilizza la variabile linkExternalFilters per facilitare il tracciamento automatico dei collegamenti di uscita.
feature: Appmeasurement Implementation
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 10%

---

# linkExternalFilters

AppMeasurement offre la possibilità di tenere traccia automaticamente dei collegamenti che puntano all’esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackexternallinks.md) (Web SDK) è abilitato, viene inviata una richiesta di immagine a destra di Adobe quando un visitatore fa clic su un collegamento per uscire dal sito. Le variabili `linkExternalFilters` e [`linkInternalFilters`](linkinternalfilters.md) determinano i collegamenti considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un elenco consentiti. Se un clic di collegamento non corrisponde a nessun valore `linkExternalFilters`, non viene considerato un collegamento di uscita. L’intero URL viene esaminato a fronte di questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è abilitato, viene esaminata anche la stringa di query.

>[!TIP]
>
>Utilizza questa variabile solo se sai esattamente quali domini vuoi considerare come collegamenti di uscita. Molte organizzazioni ritengono che l&#39;utilizzo di `linkInternalFilters` sia sufficiente per le proprie esigenze di tracciamento dei collegamenti di uscita e non utilizzano `linkExternalFilters`.

Se si utilizzano contemporaneamente `linkInternalFilters` e `linkExternalFilters`, il collegamento su cui è stato fatto clic deve corrispondere a `linkExternalFilters` **e** e non corrispondere a `linkInternalFilters` per essere considerato un collegamento di uscita. Se un collegamento cliccato corrisponde ai criteri del collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Collegamenti di uscita nel Web SDK

I collegamenti vengono qualificati automaticamente come collegamento di uscita se il dominio di destinazione del collegamento è diverso dall&#39;attuale `window.location.hostname`. Il Web SDK non offre variabili di configurazione per modificare il rilevamento automatico dei collegamenti di uscita. Se è necessario personalizzare i domini qualificati come collegamento di uscita, è possibile utilizzare la logica personalizzata nel callback `onBeforeEventSend`.

Per ulteriori informazioni, vedere [Tracciamento automatico dei collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) nella documentazione di Web SDK.

## Collegamenti in uscita: tieni traccia dell’utilizzo dell’estensione Adobe Analytics

Il campo Track è un elenco separato da virgole di filtri (in genere domini) sotto il pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo [!UICONTROL Outbound Links - Track].

Inserisci i filtri che desideri considerare sempre esterni in questo campo. Separa più domini con una virgola senza uno spazio.

## s.linkExternalFilters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkExternalFilters` è una stringa contenente i filtri (ad esempio domini) considerati per i collegamenti di uscita. Separa più domini utilizzando una virgola senza spazi.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considera il seguente esempio di implementazione come se fosse in `adobe.com`:

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
