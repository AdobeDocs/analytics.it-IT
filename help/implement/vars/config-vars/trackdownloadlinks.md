---
title: trackDownloadLinks
description: Attiva o disattiva il tracciamento automatico dei collegamenti per i collegamenti per il download.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# trackDownLoadLinks

Adobe offre la possibilità di tenere traccia dei collegamenti per il download senza impostare manualmente i [`tl()`](../functions/tl-method.md) metodo per ogni collegamento di download. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di download.

Quando abilitato, AppMeasurement confronta qualsiasi URL di collegamento cliccato con i valori in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se c&#39;è una corrispondenza, una chiamata di tracciamento del collegamento di download si attiva automaticamente.

## Tracciare i collegamenti di download utilizzando i tag in Adobe Experience Platform

Tieni traccia dei collegamenti di download come casella di controllo [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Track download links] casella di controllo.

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti per il download.

## s.trackDownloadLinks in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.trackDownloadLinks` è booleano che abilita o disabilita il tracciamento automatico dei collegamenti per il download. Se non desideri tenere traccia dei collegamenti per il download, o preferisci chiamare manualmente il `tl()` per tenere traccia dei download, imposta questa variabile su `false`.

```js
s.trackDownloadLinks = true;
```
