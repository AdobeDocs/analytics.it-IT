---
title: trackDownloadLinks
description: Abilita o disabilita il tracciamento automatico dei collegamenti per i collegamenti di download.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/mH9olBbVVqz9WCBCWiZuDe9JcljL0ADOesKSfEE6gkA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 326
ht-degree: 16%

---

# trackDownloadLinks

Adobe offre la possibilità di tenere traccia dei collegamenti di download senza impostare manualmente il metodo [`tl()`](../functions/tl-method.md) per ogni collegamento di download. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di download.

Quando è abilitata, AppMeasurement confronta qualsiasi URL di collegamento su cui è stato fatto clic con i valori in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se viene trovata una corrispondenza, viene automaticamente attivata una chiamata di tracciamento del collegamento di download.

## Abilitare o disabilitare la raccolta di clic tramite l&#39;estensione Web SDK

Utilizzare la casella di controllo [!UICONTROL Enable click data collection] durante la configurazione del Web SDK. Questa casella di controllo gestisce sia i collegamenti di uscita che quelli di download.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection], fare clic sulla casella di controllo **[!UICONTROL Enable click data collection]**.

## Attivare o disattivare la raccolta di clic implementando manualmente il Web SDK

Configurare SDK utilizzando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it#clickCollectionEnabled). Il campo è di tipo booleano e determina se i dati associati ai clic sui collegamenti vengono raccolti automaticamente. Il valore predefinito è `true`. Impostare questo valore su `false` se si desidera disabilitare il tracciamento automatico dei collegamenti. Questa impostazione gestisce il tracciamento automatico dei collegamenti sia per i collegamenti di download che per quelli di uscita.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Tracciare i collegamenti di download utilizzando l’estensione Adobe Analytics

Tracciare i collegamenti di download è una casella di controllo nel Pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandere il pannello a soffietto [!UICONTROL Link Tracking], che mostra la casella di controllo [!UICONTROL Track download links].

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di download.

## s.trackDownloadLinks in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

`s.trackDownloadLinks` è un valore booleano che abilita o disabilita il tracciamento automatico dei collegamenti di download. Se non si desidera tenere traccia dei collegamenti di download o si preferisce chiamare manualmente il metodo `tl()` per tenere traccia dei download, impostare questa variabile su `false`. La variabile [linkDownloadFileTypes](linkdownloadfiletypes.md) deve essere impostata anche per il funzionamento del tracciamento automatico dei collegamenti di download.

```js
s.trackDownloadLinks = true;
```
