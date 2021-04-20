---
title: Risolvere i problemi relativi alla raccolta dati di Activity Map
description: Determinare il motivo per cui non è possibile visualizzare i dati di Activity Map nelle richieste di immagini
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---


# Risolvere i problemi relativi alla raccolta dati di Activity Map

Se non visualizzi i dati per le dimensioni di Activity Map, utilizza questa pagina per determinare il perché.

## Conferma la raccolta dati tramite debugger

In primo luogo, assicurati che AppMeasurement raccolga correttamente i dati di Activity Map.

1. Scarica e installa l’ [Estensione Adobe Experience Cloud Debugger Chrome](https://docs.adobe.com/content/help/it-IT/debugger/using/experience-cloud-debugger.html).
2. Passa alla pagina web, quindi fai clic su un collegamento.
3. Al caricamento della pagina successiva, apri il debugger. Verifica di visualizzare le variabili di dati di contesto di Activity Map suddivise tra `activitymap.` e `.activitymap`:

![Dati di Debugger](assets/debugger.png)

## Possibili motivi per cui i dati di Activity Map non sono presenti

Per verificare che i componenti di Activity Map siano presenti, controlla ciascuno dei seguenti elementi:

* **Versione** AppMeasurement: Activity Map è supportato nelle versioni v1.6 e successive. Molti problemi relativi ai casi edge vengono risolti quando esegui l’aggiornamento all’ultima versione stabile di AppMeasurement.
* **Modulo** Activity Map: Controlla se il  `AppMeasurement_Module_Activity_Map` modulo è presente nel tuo  `AppMeasurement.js` file. Se l&#39;implementazione utilizza Adobe Experience Platform Launch, assicurati che **[!UICONTROL Enable ClickMap]** sia selezionato durante la configurazione dell&#39;estensione Analytics in **[!UICONTROL Link tracking]**.
* **Il  `s_sq` cookie**: Activity Map dipende dal  `s_sq` cookie per la raccolta dati.
   * Assicurati che la variabile `cookieDomainPeriods` sia impostata correttamente, soprattutto per i domini regionali come `*.co.uk` o `*.co.jp`.
   * Assicurati che la variabile `linkInternalFilters` sia impostata sui valori desiderati. Se un collegamento selezionato non corrisponde ai filtri interni, Activity Map lo considera un collegamento di uscita e non raccoglie dati.
* **Sovrapposizione Activity Map in esecuzione**: AppMeasurement non tiene traccia dei dati di clic per la pagina web quando la sovrapposizione di Activity Map è abilitata.
