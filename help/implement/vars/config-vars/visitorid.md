---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 3%

---

# visitorID

Adobe utilizza diversi metodi per identificare i visitatori sul sito. La `visitorID` sostituisce tutti gli altri metodi di identificazione dei visitatori.

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questa variabile. Utilizza la [Servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) invece.

## ID visitatore tramite tag in Adobe Experience Platform

[!UICONTROL Visitor ID] è un campo sotto [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Cookies] fisarmonica, che rivela [!UICONTROL Visitor ID] campo .

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. Non impostare questo campo su un valore statico.

## s.visitorID in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.visitorID` è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evita di usare trattini, spazi, caratteri di sottolineatura o simboli in questa variabile.

>[!WARNING]
>
>Se imposti la `visitorID` passaggio variabile all’interno di una visita, i dati si traducono in due visitatori univoci separati.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Un’implementazione non valida degli ID visitatore personalizzati può causare dati errati e prestazioni di reporting scadenti. Se questa variabile contiene un valore predefinito, ad esempio `"0"` o `"NULL"`), Adobe tratta questi hit come se fossero lo stesso visitatore. Questa situazione si traduce in dati errati, con conteggi bassi dei visitatori e segmenti a livello di visitatore che non funzionano come previsto. Inoltre, gli ID visitatore personalizzati implementati in modo errato generano un carico elevato sui server di elaborazione, con un aumento [latenza](/help/technotes/latency.md) e riduzione delle prestazioni dei rapporti.
