---
title: trackDownloadLinks
description: Abilita o disabilita il tracciamento automatico dei collegamenti per i collegamenti di download.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe offre la possibilità di tenere traccia dei collegamenti di download senza impostare manualmente il [`tl()`](../functions/tl-method.md) metodo per ciascun collegamento di download. Abilita questa variabile se desideri usare il tracciamento automatico dei collegamenti per i collegamenti di download.

Quando abilitata, AppMeasurement confronta qualsiasi URL di collegamento su cui è stato fatto clic con valori in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). In presenza di una corrispondenza, viene automaticamente attivata una chiamata di tracciamento dei collegamenti di download.

## Tracciare i collegamenti di download in Adobe Experience Platform Launch

I collegamenti per il download dei brani sono una casella di controllo sotto la struttura di [!UICONTROL Link Tracking] navigazione quando si configura l&#39;estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espande la [!UICONTROL Link Tracking] fisarmonica, che mostra la [!UICONTROL Track download links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti per il download.

## s.trackDownloadLinks in AppMeasurement e Launch editor di codice personalizzato

Il `s.trackDownloadLinks` valore booleano consente o disabilita il tracciamento automatico dei collegamenti per il download. Se non desiderate tenere traccia dei collegamenti di download o preferite chiamare manualmente il `tl()` metodo per tracciare i download, impostate questa variabile su `false`.

```js
s.trackDownloadLinks = true;
```
