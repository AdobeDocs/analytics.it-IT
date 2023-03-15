---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 18%

---

# visitorID

In Adobe vengono utilizzati diversi metodi per identificare i visitatori sul sito. Il `visitorID` la variabile sostituisce tutti gli altri metodi di identificazione dei visitatori.

>[!IMPORTANT]
>
>L’Adobe consiglia di non utilizzare questa variabile. Utilizza il [Servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) invece.

## Sostituzione dell’ID visitatore tramite Web SDK

Disponibile a breve!

## ID visitatore tramite l’estensione Adobe Analytics

[!UICONTROL Visitor ID] è un campo sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Visitor ID].

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. Non impostare questo campo su un valore statico.

## s.visitorID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.visitorID` variabile è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evita di usare trattini, spazi, trattini bassi o simboli in questa variabile.

>[!WARNING]
>
>Se si imposta `visitorID` variabile a metà percorso in una visita, i dati generano due visitatori univoci distinti.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Un’implementazione non valida degli ID visitatore personalizzati può portare a dati errati e prestazioni di reporting scadenti. Se questa variabile contiene un valore predefinito (ad esempio `"0"` o `"NULL"`), Adobe tratta questi hit come se fossero lo stesso visitatore. Questa situazione genera dati errati, con un numero basso di visitatori e segmenti a livello di visitatore che non funzionano come previsto. Gli ID visitatore personalizzati implementati in modo non corretto introducono anche un carico pesante sui server di elaborazione, aumentando [latenza](/help/technotes/latency.md) e la riduzione delle prestazioni dei rapporti.
