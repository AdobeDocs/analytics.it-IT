---
title: trackInlineStats
description: Abilitare o disabilitare Activity Map nella tua implementazione.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

Activity Map è una funzione di Adobe Analytics che raccoglie i dati su dove i visitatori fanno clic e su cosa fanno clic. Puoi visualizzare questi dati nei report di Analytics o utilizzando una sovrapposizione di estensione del browser. Abilitate questa variabile se desiderate utilizzare le funzioni Activity Map.

Quando abilitata, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic vengono memorizzate in un&#39;etichetta con la relativa etichetta `s_sq`.

## Abilita Clickmap nel lancio della piattaforma Adobe Experience

[!UICONTROL Enable Clickmap] è una casella di controllo sotto la struttura di [!UICONTROL Link Tracking] navigazione quando si configura l&#39;estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espande la [!UICONTROL Link Tracking] fisarmonica, che mostra la [!UICONTROL Enable Clickmap] casella di controllo.

Fate clic sulla casella di controllo per abilitare il tracciamento delle mappe attività.

## s.trackInlineStats in AppMeasurement e Launch editor di codice personalizzato

Il `s.trackInlineStats` valore booleano consente o disabilita il tracciamento delle mappe attività. Its default value is `false`. Impostate questo valore su `true` se desiderate abilitare la raccolta dati Activity Map.

```js
s.trackInlineStats = true;
```
