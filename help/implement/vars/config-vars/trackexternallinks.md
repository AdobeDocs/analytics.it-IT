---
title: trackExternalLinks
description: Abilita o disabilita il tracciamento automatico dei collegamenti per i collegamenti di uscita.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 16%

---

# trackExternalLinks

Adobe offre la possibilità di tenere traccia dei collegamenti in uscita senza impostare manualmente il metodo [`tl()`](../functions/tl-method.md) per ogni collegamento di uscita. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di uscita.

Quando è abilitato, AppMeasurement confronta qualsiasi URL di collegamento su cui è stato fatto clic con i valori in [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se viene rilevata una corrispondenza, viene attivata automaticamente una chiamata di tracciamento del collegamento di uscita.

## Abilitare o disabilitare la raccolta di clic con l’estensione Web SDK

Utilizza la casella di controllo [!UICONTROL Enable click data collection] durante la configurazione dell&#39;SDK Web. Questa casella di controllo gestisce sia i collegamenti di uscita che quelli di download.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection], fare clic sulla casella di controllo **[!UICONTROL Enable click data collection]**.

## Abilitare o disabilitare la raccolta di clic implementando manualmente l’SDK per web

Configurare l&#39;SDK utilizzando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Il campo è di tipo booleano e determina se i dati associati ai clic sui collegamenti vengono raccolti automaticamente. Il valore predefinito è `true`. Impostare questo valore su `false` se si desidera disabilitare il tracciamento automatico dei collegamenti. Questa impostazione gestisce il tracciamento automatico dei collegamenti sia per i collegamenti di download che per quelli di uscita.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Tracciare i collegamenti in uscita utilizzando l’estensione Adobe Analytics

Tracciare i collegamenti in uscita è una casella di controllo nel pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandere il pannello a soffietto [!UICONTROL Link Tracking], che mostra la casella di controllo [!UICONTROL Track outbound links].

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di uscita.

## s.trackExternalLinks in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

`s.trackExternalLinks` è un valore booleano che abilita o disabilita il rilevamento automatico dei collegamenti di uscita. Se non si desidera tenere traccia dei collegamenti in uscita o si preferisce chiamare manualmente il metodo `tl()` per tenere traccia dei collegamenti in uscita, impostare questa variabile su `false`.

```js
s.trackExternalLinks = true;
```
