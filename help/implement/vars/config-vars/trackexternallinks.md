---
title: trackExternalLinks
description: Attiva o disattiva il tracciamento automatico dei collegamenti per i collegamenti di uscita.
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# trackExternalLinks

Adobe offre la possibilità di tracciare i collegamenti in uscita senza impostare manualmente il metodo [`tl()`](../functions/tl-method.md) per ogni collegamento in uscita. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di uscita.

Quando abilitato, AppMeasurement confronta qualsiasi URL di collegamento selezionato con valori in [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se c&#39;è una corrispondenza, una chiamata di tracciamento del collegamento di uscita si attiva automaticamente.

## Tracciare i collegamenti in uscita utilizzando i tag in Adobe Experience Platform

Tieni traccia dei collegamenti in uscita è una casella di controllo nel pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Link Tracking] pannello a soffietto, che mostra la casella di controllo [!UICONTROL Track outbound links].

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di uscita.

## s.trackExternalLinks in AppMeasurement e nell&#39;editor di codice personalizzato

Il valore `s.trackExternalLinks` è booleano che abilita o disabilita il tracciamento automatico dei collegamenti di uscita. Se non desideri tenere traccia dei collegamenti in uscita o preferisci chiamare manualmente il metodo `tl()` per tracciare i collegamenti in uscita, imposta questa variabile su `false`.

```js
s.trackExternalLinks = true;
```
