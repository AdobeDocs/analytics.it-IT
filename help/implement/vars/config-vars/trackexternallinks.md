---
title: trackExternalLinks
description: Abilita o disabilita il tracciamento automatico dei collegamenti per i collegamenti di uscita.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackExternalLinks

Adobe offre la possibilità di tracciare i collegamenti in uscita senza impostare manualmente il [`tl()`](../functions/tl-method.md) metodo per ciascun collegamento in uscita. Abilita questa variabile se desideri usare il tracciamento automatico dei collegamenti per i collegamenti di uscita.

Quando è abilitata, AppMeasurement confronta qualsiasi URL di collegamento su valori in [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). In caso di corrispondenza, viene automaticamente attivata una chiamata di tracciamento dei collegamenti di uscita.

## Tracciare i collegamenti in uscita nel lancio di Adobe Experience Platform

Tieni traccia dei collegamenti in uscita è una casella di controllo nella struttura di [!UICONTROL Link Tracking] navigazione quando configuri l’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espande la [!UICONTROL Link Tracking] fisarmonica, che mostra la [!UICONTROL Track outbound links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di uscita.

## s.trackExternalLinks in AppMeasurement e Launch editor di codice personalizzato

Il valore booleano `s.trackExternalLinks` consente o disabilita il tracciamento automatico dei collegamenti di uscita. Se non si desidera tracciare i collegamenti in uscita o se si preferisce chiamare manualmente il `tl()` metodo per tracciare i collegamenti in uscita, impostare questa variabile su `false`.

```js
s.trackDownloadLinks = true;
```
