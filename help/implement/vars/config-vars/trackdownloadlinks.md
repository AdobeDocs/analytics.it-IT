---
title: trackDownloadLinks
description: Attiva o disattiva il tracciamento automatico dei collegamenti per i collegamenti per il download.
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# trackDownLoadLinks

Adobe offre la possibilità di tenere traccia dei collegamenti per il download senza impostare manualmente il metodo [`tl()`](../functions/tl-method.md) per ogni collegamento per il download. Abilita questa variabile se desideri utilizzare il tracciamento automatico dei collegamenti per i collegamenti di download.

Quando abilitato, AppMeasurement confronta qualsiasi URL di collegamento selezionato con valori in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se c&#39;è una corrispondenza, una chiamata di tracciamento del collegamento di download si attiva automaticamente.

## Tracciare i collegamenti di download utilizzando i tag in Adobe Experience Platform

Tieni traccia dei collegamenti per il download, è una casella di controllo nel pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Link Tracking] pannello a soffietto, che mostra la casella di controllo [!UICONTROL Track download links].

Fai clic sulla casella di controllo per abilitare il tracciamento automatico dei collegamenti per il download.

## s.trackDownloadLinks in AppMeasurement e nell&#39;editor di codice personalizzato

Il `s.trackDownloadLinks` è un valore booleano che abilita o disabilita il tracciamento automatico dei collegamenti per il download. Se non desideri tenere traccia dei collegamenti di download o preferisci chiamare manualmente il metodo `tl()` per tenere traccia dei download, imposta questa variabile su `false`.

```js
s.trackDownloadLinks = true;
```
