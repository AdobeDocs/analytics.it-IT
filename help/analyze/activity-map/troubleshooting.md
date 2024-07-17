---
title: Risoluzione dei problemi di raccolta dati Activity Map
description: Determinare il motivo per cui non è possibile visualizzare i dati Activity Map nelle richieste di immagini
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 11%

---

# Risoluzione dei problemi di raccolta dati Activity Map

Se non trovi i dati per le dimensioni Activity Map, utilizza questa pagina per determinare il motivo.

## Conferma la raccolta dati utilizzando il debugger

Innanzitutto, assicurati che AppMeasurement raccolga correttamente i dati Activity Map.

1. Scarica e installa l&#39;estensione per Chrome [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/home).
2. Passa alla pagina web, quindi fai clic su un collegamento.
3. Quando viene caricata la pagina successiva, apri il debugger. Convalidare la visualizzazione delle variabili di dati di contesto Activity Map tra `activitymap.` e `.activitymap`:

## Possibili motivi per cui i dati Activity Map non sono presenti

Verifica che siano presenti i componenti Activity Map:

* **AppMeasurement di versione**: l&#39;Activity Map è supportato nelle versioni 1.6 e successive. Molti problemi relativi ai casi edge vengono risolti quando esegui l’aggiornamento alla versione stabile più recente di AppMeasurement.
* **Modulo Activity Map**: verifica se il modulo `AppMeasurement_Module_Activity_Map` è presente nel file `AppMeasurement.js`. Se l&#39;implementazione utilizza Adobe Experience Platform per raccogliere i dati, assicurati che **[!UICONTROL Enable ClickMap]** sia controllato durante la configurazione dell&#39;estensione Analytics in **[!UICONTROL Link tracking]**.
* **Cookie `s_sq`**: Activity Map dipende dal cookie `s_sq` per la raccolta dati.
   * Verificare che la variabile `cookieDomainPeriods` sia impostata correttamente, in particolare per i domini regionali come `*.co.uk` o `*.co.jp`.
   * Verificare che la variabile `linkInternalFilters` sia impostata sui valori desiderati. Se un collegamento su cui è stato fatto clic non corrisponde ai filtri interni, l’Activity Map lo considera un collegamento di uscita e non raccoglie dati.
* **Sovrapposizione Activity Map in esecuzione**: l&#39;AppMeasurement non tiene traccia dei dati di clic per la pagina Web quando la sovrapposizione Activity Map è abilitata.

Mostra i parametri del browser non compatibili con l’utilizzo di Activity Map. L&#39;Adobe consiglia di disattivare queste impostazioni.

## Chrome

![](assets/Chrome1.png)

![](assets/Chrome2.png)

![](assets/Chrome3.png)

## Firefox

![](assets/Firefox.png)

## Safari

![](assets/Safari1.png)

![](assets/Safari2.png)

## Internet Explorer

![](assets/IE1.png)


**Convalida**

Interagisci con le chiamate tramite la scheda di rete di Developer Console:

1. Carica lo script di avvio per lo sviluppo sul sito.
1. Su Fai clic sugli elementi, cerca “/ee” nella scheda di rete

Adobe Experience Platform Debugger

1. Scarica e installa [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Passa a [!UICONTROL Logs] > [!UICONTROL Edge] > [!UICONTROL Connect to Edge].

* **La chiamata di interazione non viene attivata nella scheda Rete**: la raccolta dati di clic in una chiamata di raccolta, filtro con `"/ee"` o `"collect?"`.
* **Nessun payload visualizzato per la chiamata di raccolta**: la chiamata di raccolta è progettata in modo tale che il tracciamento non influisca sulla navigazione ad altri siti, pertanto la funzione di scaricamento del documento è applicabile alle chiamate di raccolta. Questa funzione non influisce sulla raccolta di dati, ma se devi convalidare a pagina, aggiungi `target="_blank"` al rispettivo elemento. Il collegamento viene aperto in una nuova scheda.
