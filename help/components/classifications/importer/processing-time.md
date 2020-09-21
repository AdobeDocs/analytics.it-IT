---
title: Tempo di elaborazione dell’importazione di classificazioni
description: Comprendere l’intervallo di tempo in cui Adobe elabora i file di classificazione e come ridurre al minimo il tempo di elaborazione.
translation-type: ht
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: ht
source-wordcount: '413'
ht-degree: 100%

---


# Tempo di elaborazione dell’importazione di classificazioni

Il tempo di elaborazione di un file di classificazione varia in base alle dimensioni del file e al numero totale di file elaborati da Adobe. Le classificazioni in genere non richiedono più di 72 ore. Tuttavia, periodi di uso intensivo delle classificazioni tra le organizzazioni che utilizzano Adobe Analytics possono causare un aumento del tempo di elaborazione dei file, che possono richiedere più di 72 ore. Adobe riporta un uso intensivo delle classificazioni nei mesi che precedono le feste.

Per verificare se un file di classificazione è stato elaborato, effettua le seguenti operazioni:

1. Accedi ad Adobe Analytics e seleziona **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Seleziona la suite di rapporti e il set di dati in questione.
3. Se l’elaborazione non è ancora completa, viene visualizzato uno dei seguenti messaggi:

   * ![Avviso](assets/icon_notice_notice.gif) Il rapporto selezionato presenta un’importazione di classificazione in fase di elaborazione.
   * ![Avviso](assets/icon_notice_notice.gif) Il rapporto selezionato contiene dati di classificazione non ancora propagati a tutti i server.

Per ridurre al minimo i tempi di importazione delle classificazioni, Adobe consiglia vivamente di attenersi alle seguenti linee guida:

* **Utilizza il generatore di regole di classificazione quando possibile**: il generatore di regole di classificazione elabora i dati in modo diverso rispetto all’importazione di classificazioni tradizionale. Se i dati di classificazione seguono pattern specifici, si consiglia vivamente di utilizzare questa funzionalità.
* **Carica solo le righe modificate**: questa procedura riduce notevolmente il tempo necessario per elaborare i file di classificazione, poiché non passa in rassegna le righe rimaste immutate. Adobe consiglia vivamente di caricare solo le righe modificate.
* **Pianifica in anticipo**: inizia a caricare i dati di classificazione il prima possibile, specialmente se vengono utilizzati durante le feste.
* **Combina i file di classificazione, laddove possibile**: se una singola variabile ha più classificazioni, carica un singolo file con tutte le classificazioni applicabili. Evita di caricare più classificazioni per la stessa variabile.
* **Evita di caricare file di dimensioni superiori a 500 MB**: se gestisci grandi quantità di dati di classificazione, Adobe consiglia di suddividerli in file da 100-500 MB.
* **Evita di caricare grandi quantità di file su FTP**: se hai intenzione di caricare gli stessi file in molte suite di rapporti tramite FTP, limita il numero di file caricati alla volta. Adobe raccomanda che il numero di file moltiplicato per il numero di suite di rapporti applicabili sia inferiore a 1000. Se è necessario caricare 100 file in 100 suite di rapporti, il numero totale di file è 10.000. Invece di caricare tutti e 100 i file contemporaneamente, suddividili in 10 gruppi di 10 file e carica un gruppo alla volta.
* **Carica i file di piccole dimensioni tramite l’importazione browser**: se disponi di un file inferiore a 1 MB (meno di 50.000 righe), Adobe consiglia di utilizzare l’importazione browser. Le importazioni browser sono quasi sempre più veloci delle importazioni FTP.
