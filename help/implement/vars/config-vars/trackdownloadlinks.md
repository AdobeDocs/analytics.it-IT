---
title: trackDownloadLinks
description: Abilita o disabilita il tracciamento automatico dei collegamenti per i collegamenti di download.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 16%

---

# trackDownLoadLinks

Adobe offre la possibilità di tenere traccia dei collegamenti di download senza impostare manualmente il [`tl()`](../functions/tl-method.md) metodo per ciascun collegamento di download. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di download.

Quando è abilitato, AppMeasurement confronta qualsiasi URL di collegamento su cui è stato fatto clic con i valori in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se viene trovata una corrispondenza, viene automaticamente attivata una chiamata di tracciamento del collegamento di download.

## Abilitare o disabilitare la raccolta di clic con l’estensione Web SDK

Utilizza il [!UICONTROL Enable click data collection] durante la configurazione di Web SDK. Questa casella di controllo gestisce sia i collegamenti di uscita che quelli di download.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], fare clic su **[!UICONTROL Enable click data collection]** casella di controllo.

## Abilitare o disabilitare la raccolta di clic implementando manualmente l’SDK per web

Configurare l’SDK tramite [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). Il campo è di tipo booleano e determina se i dati associati ai clic sui collegamenti vengono raccolti automaticamente. Il valore predefinito è `true`. Imposta questo valore su `false` per disattivare il tracciamento automatico dei collegamenti. Questa impostazione gestisce il tracciamento automatico dei collegamenti sia per i collegamenti di download che per quelli di uscita.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Tracciare i collegamenti di download utilizzando l’estensione Adobe Analytics

Tracciare i collegamenti di download è una casella di controllo sotto [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi [!UICONTROL Link Tracking] Pannello a soffietto, che mostra [!UICONTROL Track download links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di download.

## s.trackDownloadLinks in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackDownloadLinks` è un valore booleano che abilita o disabilita il tracciamento automatico dei collegamenti di download. Se non desideri tenere traccia dei collegamenti di download o preferisci chiamare manualmente il `tl()` per tenere traccia dei download, imposta questa variabile su `false`.

```js
s.trackDownloadLinks = true;
```
