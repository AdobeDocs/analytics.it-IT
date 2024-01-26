---
title: linkExternalFilters
description: Utilizza la variabile linkExternalFilters per facilitare il tracciamento automatico dei collegamenti di uscita.
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 10%

---

# linkExternalFilters

AppMeasurement offre la possibilità di tenere traccia automaticamente dei collegamenti che puntano all’esterno del sito. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackexternallinks.md) (Web SDK) è abilitato, viene inviata una richiesta di immagine all&#39;Adobe destro quando un visitatore fa clic su un collegamento per uscire dal sito. Il `linkExternalFilters` e [`linkInternalFilters`](linkinternalfilters.md) Le variabili determinano quali collegamenti sono considerati interni/esterni.

Se questa variabile contiene un valore, il tracciamento automatico dei collegamenti di uscita si comporta come un elenco consentiti. Se un clic del collegamento non corrisponde a nessuno `linkExternalFilters` non è considerato un collegamento di uscita. L’intero URL viene esaminato a fronte di questa variabile. Se [`linkLeaveQueryString`](linkleavequerystring.md) è attivato, viene esaminata anche la stringa di query.

>[!TIP]
>
>Utilizza questa variabile solo se sai esattamente quali domini vuoi considerare come collegamenti di uscita. Molte organizzazioni rilevano che utilizzando `linkInternalFilters` è sufficiente per le loro esigenze di tracciamento dei collegamenti di uscita e non utilizza `linkExternalFilters`.

Se usa entrambi `linkInternalFilters` e `linkExternalFilters` contemporaneamente, il collegamento su cui è stato fatto clic deve corrispondere `linkExternalFilters` **e** non corrisponde `linkInternalFilters` per essere considerato un collegamento di uscita. Se un collegamento cliccato corrisponde ai criteri del collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Collegamenti di uscita nel Web SDK

I collegamenti vengono automaticamente qualificati come collegamento di uscita se il dominio di destinazione del collegamento è diverso dal dominio corrente `window.location.hostname`. L’SDK per web non offre variabili di configurazione per modificare il rilevamento automatico dei collegamenti di uscita. Se devi personalizzare i domini idonei come collegamento di uscita, puoi utilizzare la logica personalizzata nel `onBeforeEventSend` callback.

Consulta [Tracciamento automatico dei collegamenti](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Collegamenti in uscita: tieni traccia dell’utilizzo dell’estensione Adobe Analytics

Il campo Traccia è un elenco separato da virgole di filtri (in genere domini) sotto il [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo [!UICONTROL Outbound Links - Track].

Inserisci i filtri che desideri considerare sempre esterni in questo campo. Separa più domini con una virgola senza uno spazio.

## s.linkExternalFilters in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkExternalFilters` variabile è una stringa contenente filtri (come domini) che consideri collegamenti di uscita. Separa più domini utilizzando una virgola senza spazi.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considera il seguente esempio di implementazione come se fosse attivo `adobe.com`:

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
