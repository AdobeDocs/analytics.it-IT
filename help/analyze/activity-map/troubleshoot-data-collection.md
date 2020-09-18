---
title: Risoluzione dei problemi  raccolta dei dati Activity Map
description: Determinare il motivo per cui non è possibile visualizzare  dati Activity Map nelle richieste di immagini
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---


# Risoluzione dei problemi  raccolta dei dati Activity Map

Se non visualizzi dati per  dimensioni Activity Map, utilizza questa pagina per determinare il motivo.

## Conferma della raccolta dei dati tramite il debugger

Innanzitutto, accertatevi che AppMeasurement raccolga correttamente  dati Activity Map.

1. Download and install the [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/it-IT/debugger/using/experience-cloud-debugger.html).
2. Passate alla pagina Web, quindi fate clic su un collegamento.
3. Quando viene caricata la pagina successiva, apri il debugger. Convalidare la visualizzazione  variabili di dati contestuali Activity Map tra `activitymap.` e `.activitymap`:

![Dati debugger](assets/debugger.png)

## Possibili ragioni per cui  dati Activity Map non sono presenti

Per verificare che  componenti Activity Map siano presenti, effettuate le seguenti operazioni:

* **Versione** AppMeasurement:  Activity Map è supportato nella versione 1.6 e successive. Molti problemi relativi ai casi periferici vengono risolti quando si esegue l’aggiornamento all’ultima versione stabile di AppMeasurement.
* **Modulo** Activity Map : Verificate la presenza del `AppMeasurement_Module_Activity_Map` modulo nel `AppMeasurement.js` file. Se l&#39;implementazione utilizza  Adobe Experience Platform Launch, accertati che **[!UICONTROL Enable ClickMap]** sia selezionato quando configuri l&#39;estensione Analytics in **[!UICONTROL Link tracking]**.
* **Il`s_sq`cookie**:  Activity Map dipende dal `s_sq` cookie per la raccolta dei dati.
   * Accertatevi che la `cookieDomainPeriods` variabile sia impostata correttamente, in particolare per i domini regionali quali `*.co.uk` o `*.co.jp`.
   * Accertatevi che la `linkInternalFilters` variabile sia impostata sui valori desiderati. Se un collegamento selezionato non corrisponde ai filtri interni,  Activity Map lo considera un collegamento di uscita e non raccoglie dati.
* **Sovrapposizione Activity Map  in esecuzione**: AppMeasurement non tiene traccia dei dati di clic per la pagina Web quando la sovrapposizione Activity Map  è abilitata.
