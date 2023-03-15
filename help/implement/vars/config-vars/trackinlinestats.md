---
title: trackInlineStats
description: Abilita o disabilita Activity Map nella tua implementazione.
keywords: disabilita activity map
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 15%

---

# trackInlineStats

Activity Map è una funzione di Adobe Analytics che raccoglie dati su dove i visitatori fanno clic e su cosa fanno clic. Puoi visualizzare questi dati nei rapporti di Analytics o utilizzando una sovrapposizione dell’estensione del browser. Abilita questa variabile se desideri utilizzare le funzioni di Activity Map.

Quando è abilitata, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic vengono memorizzate in un cookie etichettato `s_sq`.

## Activity Map tramite Web SDK

L’SDK per web non supporta ancora la raccolta dati Activity Map.

## Abilitare Clickmap tramite l’estensione Adobe Analytics

[!UICONTROL Enable Clickmap] è una casella di controllo sotto [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi [!UICONTROL Link Tracking] Pannello a soffietto, che mostra [!UICONTROL Enable Clickmap] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento di Activity Map.

## s.trackInlineStats in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackInlineStats` è un valore booleano che abilita o disabilita il tracciamento di Activity Map. Il valore predefinito è `false`. Imposta questo valore su `true` se desideri abilitare la raccolta dati Activity Map.

```js
s.trackInlineStats = true;
```
