---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 1%

---

# visitorID

Adobe utilizza diversi metodi per identificare i visitatori sul sito. La variabile `visitorID` sostituisce tutti gli altri metodi di identificazione dei visitatori.

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questa variabile. Utilizza invece il [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## ID visitatore in Adobe Experience Platform Launch

[!UICONTROL Visitor ID] è un campo a  [!UICONTROL Cookies] soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra il campo [!UICONTROL Visitor ID] .

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. Non impostare questo campo su un valore statico.

## s.visitorID nell’editor di codice personalizzato AppMeasurement e Launch

La variabile `s.visitorID` è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evita di usare trattini, spazi, caratteri di sottolineatura o simboli in questa variabile.

>[!WARNING]
>
>Se imposti la parte variabile `visitorID` attraverso una visita, i dati si traducono in due visitatori univoci separati.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Un’implementazione non valida degli ID visitatore personalizzati può causare dati errati e prestazioni di reporting scadenti. Se questa variabile contiene un valore predefinito (ad esempio `"0"` o `"NULL"`), Adobe tratta questi hit come se fossero lo stesso visitatore. Questa situazione si traduce in dati errati, con conteggi bassi dei visitatori e segmenti a livello di visitatore che non funzionano come previsto. Inoltre, gli ID visitatore personalizzati implementati in modo errato generano un carico elevato sui server di elaborazione, con conseguente aumento della [latenza](/help/technotes/latency.md) e riduzione delle prestazioni del rapporto.
