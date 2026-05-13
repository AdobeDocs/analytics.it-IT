---
title: trackInlineStats
description: (Ritirato) Abilita o disabilita ClickMap nell’implementazione.
keywords: disattiva clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: https://experienceleague.adobe.com/K6rwl-ZECfoMLfC0Z25PPq2jV1FBo0cTsl1YfDeNpBQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 179
ht-degree: 18%

---

# trackInlineStats

>[!IMPORTANT]
>
>Questa variabile viene ritirata e non viene più utilizzata.

ClickMap è una funzione ritirata di Adobe Analytics che raccoglie dati su dove i visitatori fanno clic e su ciò che fanno clic. La funzionalità è stata sostituita con [Activity Map](/help/analyze/activity-map/overview.md).

Quando è abilitata, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic vengono memorizzate in un cookie con etichetta `s_sq`.

## Abilitare ClickMap tramite l’estensione Adobe Analytics

[!UICONTROL Enable ClickMap] è una casella di controllo nel pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandere il pannello a soffietto [!UICONTROL Link Tracking], che mostra la casella di controllo [!UICONTROL Enable ClickMap].

>[!NOTE]
>
>Questa casella di controllo è diversa dalla casella di controllo [!UICONTROL Use Activity Map], che si trova nel pannello a soffietto [!UICONTROL Library management].

## s.trackInlineStats in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

`s.trackInlineStats` è un valore booleano che abilita o disabilita il tracciamento di ClickMap. Poiché la funzione è stata ritirata, Adobe sconsiglia di impostare questa variabile. Il valore predefinito è `false`.

```js
s.trackInlineStats = false;
```
