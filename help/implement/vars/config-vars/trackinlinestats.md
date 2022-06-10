---
title: trackInlineStats
description: Attiva o disattiva Activity Map nella tua implementazione.
keywords: disabilita activity map
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# trackInlineStats

Activity Map è una funzione di Adobe Analytics che raccoglie dati su dove i visitatori cliccano e su cosa fanno clic. Puoi visualizzare questi dati nei rapporti di Analytics o utilizzando una sovrapposizione di estensione del browser. Abilita questa variabile se desideri utilizzare le funzioni di Activity Map .

Quando abilitato, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic sono memorizzate in un cookie etichettato `s_sq`.

## Activity Map tramite l’SDK per web

L’SDK per web non supporta ancora la raccolta dati di Activity Map.

## Abilita Clickmap utilizzando l&#39;estensione Adobe Analytics

[!UICONTROL Enable Clickmap] è una casella di controllo sotto [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Enable Clickmap] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento della mappa attività.

## s.trackInlineStats in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.trackInlineStats` è un valore booleano che abilita o disabilita il tracciamento Activity Map. Il valore predefinito è `false`. Imposta questo valore su `true` se desideri abilitare la raccolta dati Activity Map.

```js
s.trackInlineStats = true;
```
