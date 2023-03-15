---
title: trackExternalLinks
description: Abilita o disabilita il tracciamento automatico dei collegamenti per i collegamenti di uscita.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 20%

---

# trackExternalLinks

Adobe offre la possibilità di tenere traccia dei collegamenti in uscita senza impostare manualmente il [`tl()`](../functions/tl-method.md) per ogni collegamento di uscita. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di uscita.

Quando è abilitata, AppMeasurement confronta qualsiasi URL di collegamento su cui è stato fatto clic con i valori in [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se viene rilevata una corrispondenza, viene attivata automaticamente una chiamata di tracciamento del collegamento di uscita.

## Abilitare o disabilitare la raccolta di clic con l’estensione Web SDK

Utilizza il [!UICONTROL Enable click data collection] durante la configurazione di Web SDK. Questa casella di controllo gestisce sia i collegamenti di uscita che quelli di download.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], fare clic su **[!UICONTROL Enable click data collection]** casella di controllo.

## Abilitare o disabilitare la raccolta di clic implementando manualmente l’SDK per web

Configurare l’SDK tramite [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Il campo è di tipo booleano e determina se i dati associati ai clic sui collegamenti vengono raccolti automaticamente. Il valore predefinito è `true`. Imposta questo valore su `false` per disattivare il tracciamento automatico dei collegamenti. Questa impostazione gestisce il tracciamento automatico dei collegamenti sia per i collegamenti di download che per quelli di uscita.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Tracciare i collegamenti in uscita utilizzando l’estensione Adobe Analytics

Tracciare i collegamenti in uscita è una casella di controllo sotto [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi [!UICONTROL Link Tracking] Pannello a soffietto, che mostra [!UICONTROL Track outbound links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di uscita.

## s.trackExternalLinks in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackExternalLinks` è un valore booleano che abilita o disabilita il tracciamento automatico dei collegamenti di uscita. Se non desideri tenere traccia dei collegamenti in uscita o preferisci chiamare manualmente il `tl()` per tenere traccia dei collegamenti di uscita, impostare questa variabile su `false`.

```js
s.trackExternalLinks = true;
```
