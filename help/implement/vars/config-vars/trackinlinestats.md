---
title: trackInlineStats
description: (Ritirato) Abilita o disabilita la ClickMap nell’implementazione.
keywords: disattiva clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 17%

---

# trackInlineStats

>[!IMPORTANT]
>
>Questa variabile viene ritirata e non viene più utilizzata.

ClickMap è una funzione ritirata di Adobe Analytics che raccoglie dati su dove i visitatori fanno clic e su ciò che fanno clic. La funzionalità è stata sostituita con [Activity Map](/help/analyze/activity-map/overview.md).

Quando è abilitato, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic vengono memorizzate in un cookie con etichetta `s_sq`.

## Abilitare ClickMap tramite l’estensione Adobe Analytics

[!UICONTROL Enable ClickMap] è una casella di controllo nel pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandere il pannello a soffietto [!UICONTROL Link Tracking], che mostra la casella di controllo [!UICONTROL Enable ClickMap].

>[!NOTE]
>
>Questa casella di controllo è diversa dalla casella di controllo [!UICONTROL Use Activity Map], che si trova nel pannello a soffietto [!UICONTROL Library management].

## s.trackInlineStats in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

`s.trackInlineStats` è un valore booleano che abilita o disabilita il tracciamento delle ClickMap. Poiché la funzione è stata ritirata, Adobe sconsiglia di impostare questa variabile. Il valore predefinito è `false`.

```js
s.trackInlineStats = false;
```
