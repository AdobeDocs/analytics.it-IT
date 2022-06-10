---
title: trackExternalLinks
description: Attiva o disattiva il tracciamento automatico dei collegamenti per i collegamenti di uscita.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# trackExternalLinks

Adobe offre la possibilità di tracciare i collegamenti in uscita senza impostare manualmente la variabile [`tl()`](../functions/tl-method.md) metodo per ogni collegamento di uscita. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di uscita.

Quando abilitato, AppMeasurement confronta qualsiasi URL di collegamento cliccato con i valori in [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se c&#39;è una corrispondenza, una chiamata di tracciamento del collegamento di uscita si attiva automaticamente.

## Attivare o disattivare la raccolta di clic utilizzando l&#39;estensione SDK per web

Utilizza la [!UICONTROL Enable click data collection] durante la configurazione dell’SDK per web. Questa casella di controllo gestisce i collegamenti di uscita e di download.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], fai clic su **[!UICONTROL Enable click data collection]** casella di controllo.

## Attivare o disattivare la raccolta di clic manualmente per l&#39;implementazione dell&#39;SDK per web

Configurare l&#39;SDK utilizzando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Il campo è booleano che determina se i dati associati ai clic sul collegamento vengono raccolti automaticamente. Il valore predefinito è `true`. Imposta questo valore su `false` per disattivare il tracciamento automatico dei collegamenti. Questa impostazione gestisce il tracciamento automatico dei collegamenti sia per i collegamenti di download che per quelli di uscita.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Tracciare i collegamenti in uscita utilizzando l’estensione Adobe Analytics

Tracciare i collegamenti in uscita è una casella di controllo sotto al [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Track outbound links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di uscita.

## s.trackExternalLinks in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.trackExternalLinks` è un valore booleano che abilita o disabilita il tracciamento automatico dei collegamenti di uscita. Se non desideri tenere traccia dei collegamenti in uscita o preferisci chiamare manualmente il `tl()` metodo per tracciare i collegamenti di uscita, imposta questa variabile su `false`.

```js
s.trackExternalLinks = true;
```
