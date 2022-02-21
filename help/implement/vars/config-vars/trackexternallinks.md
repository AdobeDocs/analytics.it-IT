---
title: trackExternalLinks
description: Attiva o disattiva il tracciamento automatico dei collegamenti per i collegamenti di uscita.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# trackExternalLinks

Adobe offre la possibilità di tracciare i collegamenti in uscita senza impostare manualmente la variabile [`tl()`](../functions/tl-method.md) metodo per ogni collegamento di uscita. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di uscita.

Quando abilitato, AppMeasurement confronta qualsiasi URL di collegamento cliccato con i valori in [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se c&#39;è una corrispondenza, una chiamata di tracciamento del collegamento di uscita si attiva automaticamente.

## Tracciare i collegamenti in uscita utilizzando i tag in Adobe Experience Platform

Tracciare i collegamenti in uscita è una casella di controllo sotto al [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Track outbound links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti di uscita.

## s.trackExternalLinks in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.trackExternalLinks` è un valore booleano che abilita o disabilita il tracciamento automatico dei collegamenti di uscita. Se non desideri tenere traccia dei collegamenti in uscita o preferisci chiamare manualmente il `tl()` metodo per tracciare i collegamenti di uscita, imposta questa variabile su `false`.

```js
s.trackExternalLinks = true;
```
