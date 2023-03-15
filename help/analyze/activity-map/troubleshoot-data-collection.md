---
title: Risoluzione dei problemi di raccolta dati Activity Map
description: Determinare il motivo per cui non è possibile visualizzare i dati Activity Map nelle richieste di immagini
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 2%

---

# Risoluzione dei problemi di raccolta dati Activity Map

Se non trovi i dati per le dimensioni Activity Map, utilizza questa pagina per determinare il motivo.

## Conferma la raccolta dati utilizzando il debugger

Innanzitutto, assicurati che AppMeasurement raccolga correttamente i dati Activity Map.

1. Scarica e installa [Estensione Adobe Experience Cloud Debugger di Chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it).
2. Passa alla pagina web, quindi fai clic su un collegamento.
3. Quando viene caricata la pagina successiva, apri il debugger. Verifica di visualizzare le variabili dei dati di contesto Activity Map inserite tra `activitymap.` e `.activitymap`:

![Dati debugger](assets/debugger.png)

## Possibili motivi per cui i dati Activity Map non sono presenti

Verifica che siano presenti i componenti Activity Map:

* **Versione AppMeasurement**: Activity Map è supportato nelle versioni v1.6 e successive. Molti problemi relativi ai casi limite vengono risolti quando esegui l’aggiornamento alla versione stabile più recente di AppMeasurement.
* **Modulo Activity Map**: controlla se `AppMeasurement_Module_Activity_Map` è presente nel tuo `AppMeasurement.js` file. Se la tua implementazione utilizza Adobe Experience Platform per raccogliere i dati, assicurati che **[!UICONTROL Enable ClickMap]** è selezionato durante la configurazione dell&#39;estensione Analytics in **[!UICONTROL Link tracking]**.
* **Il `s_sq` cookie**: l’Activity Map dipende da `s_sq` cookie per la raccolta dati.
   * Assicurati che il `cookieDomainPeriods` è impostata correttamente, in particolare per i domini regionali come `*.co.uk` o `*.co.jp`.
   * Assicurati che il `linkInternalFilters` è impostata sui valori desiderati. Se un collegamento su cui è stato fatto clic non corrisponde ai filtri interni, l’Activity Map lo considera un collegamento di uscita e non raccoglie dati.
* **Sovrapposizione Activity Map in esecuzione**: AppMeasurement non tiene traccia dei dati di clic per la pagina web quando la sovrapposizione Activity Map è abilitata.
