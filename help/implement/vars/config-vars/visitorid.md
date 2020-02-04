---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

Adobe utilizza diversi metodi per identificare i visitatori sul sito. La `visitorID` variabile ha la priorità su tutti gli altri metodi di identificazione del visitatore.

> [!IMPORTANT] Adobe consiglia di non utilizzare questa variabile. Utilizzate invece il servizio [](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud Identity.

## ID visitatore in Adobe Experience Platform Launch

[!UICONTROL Visitor ID] è un campo situato sotto la [!UICONTROL Cookies] struttura di navigazione durante la configurazione dell’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espandere la [!UICONTROL Cookies] struttura a soffietto, che mostra il [!UICONTROL Visitor ID] campo.

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. Non impostare questo campo su un valore statico.

## s.visitorID in AppMeasurement e Launch, editor di codice personalizzato

La `s.visitorID` variabile è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evitate di usare trattini, spazi, caratteri di sottolineatura o simboli in questa variabile.

> [!WARNING] Se imposti la `visitorID` variabile partiway in una visita, i dati generano due visitatori univoci separati.

```js
s.visitorID = "abc123";
```
