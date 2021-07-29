---
title: trackInlineStats
description: Attiva o disattiva Activity Map nella tua implementazione.
keywords: disabilita activity map
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# trackInlineStats

Activity Map è una funzione di Adobe Analytics che raccoglie dati su dove i visitatori cliccano e su cosa fanno clic. Puoi visualizzare questi dati nei rapporti di Analytics o utilizzando una sovrapposizione di estensione del browser. Abilita questa variabile se desideri utilizzare le funzioni di Activity Map .

Quando abilitato, AppMeasurement raccoglie informazioni sul collegamento e invia tali dati nella richiesta di immagine successiva. Le informazioni di ogni clic vengono memorizzate in un cookie con etichetta `s_sq`.

## Abilita Clickmap utilizzando i tag in Adobe Experience Platform

[!UICONTROL Enable Clickmap] è una casella di controllo nel  [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Link Tracking] pannello a soffietto, che mostra la casella di controllo [!UICONTROL Enable Clickmap].

Fai clic sulla casella di controllo per abilitare il tracciamento della mappa attività.

## s.trackInlineStats in AppMeasurement e nell&#39;editor di codice personalizzato

Il valore `s.trackInlineStats` è booleano che abilita o disabilita il tracciamento Activity Map. Il valore predefinito è `false`. Imposta questo valore su `true` se desideri abilitare la raccolta dati Activity Map.

```js
s.trackInlineStats = true;
```
