---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---


# visitorID

Adobe utilizza diversi metodi per identificare i visitatori sul sito. La `visitorID` variabile ha la priorità su tutti gli altri metodi di identificazione del visitatore.

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questa variabile. Utilizzate invece il servizio [](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) Adobe Experience Cloud Identity.

## ID visitatore  lancio Adobe Experience Platform

[!UICONTROL Visitor ID] è un campo situato sotto la struttura di [!UICONTROL Cookies] navigazione durante la configurazione dell’estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandere la [!UICONTROL Cookies] struttura a soffietto, che mostra il [!UICONTROL Visitor ID] campo.

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. Non impostare questo campo su un valore statico.

## s.visitorID in AppMeasurement e Launch, editor di codice personalizzato

La `s.visitorID` variabile è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evitate di usare trattini, spazi, caratteri di sottolineatura o simboli in questa variabile.

>[!WARNING]
>
>Se imposti la `visitorID` variabile partiway in una visita, i dati generano due visitatori univoci separati.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Un&#39;implementazione non valida degli ID visitatore personalizzati può portare a dati errati e a prestazioni di reporting scadenti. Se questa variabile contiene un valore predefinito (ad esempio `"0"` o `"NULL"`), Adobe considera gli hit come se fossero lo stesso visitatore. Questa situazione genera dati errati, con conteggi bassi dei visitatori e segmenti a livello di visitatore che non funzionano come previsto. Gli ID visitatore personalizzati implementati in modo errato generano anche un carico elevato sui server di elaborazione, un aumento della [latenza](/help/technotes/latency.md) e una riduzione delle prestazioni dei rapporti.
