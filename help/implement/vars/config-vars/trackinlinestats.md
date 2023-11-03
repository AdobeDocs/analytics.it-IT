---
title: trackInlineStats
description: Abilita o disabilita le ClickMap nell'implementazione.
keywords: disattiva clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 18%

---

# trackInlineStats

>[!IMPORTANT]
>
>Questa variabile viene ritirata. Consulta [Abilita Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) invece.

ClickMap è una funzione ritirata di Adobe Analytics che raccoglie dati su dove i visitatori fanno clic e su ciò che fanno clic. La funzione è stata sostituita con [Activity Map](/help/analyze/activity-map/activity-map.md).

Quando è abilitato, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic vengono memorizzate in un cookie etichettato `s_sq`.

## Abilitare ClickMap tramite l’estensione Adobe Analytics

[!UICONTROL Enable ClickMap] è una casella di controllo sotto [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi [!UICONTROL Link Tracking] Pannello a soffietto, che mostra [!UICONTROL Enable ClickMap] casella di controllo.

>[!NOTE]
>
>Questa casella di controllo è diversa da [!UICONTROL Use Activity Map] , che si trova sotto il [!UICONTROL Library management] soffietto.

## s.trackInlineStats in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackInlineStats` è un valore booleano che abilita o disabilita il tracciamento delle ClickMap. Poiché la funzione è stata ritirata, Adobe sconsiglia di impostare questa variabile. Il valore predefinito è `false`.

```js
s.trackInlineStats = false;
```
