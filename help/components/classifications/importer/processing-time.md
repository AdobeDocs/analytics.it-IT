---
title: Tempo di elaborazione importatore classificazione
description: Comprendere l'intervallo di tempo  Adobe elabora i file di classificazione e come ridurre al minimo il tempo di elaborazione.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---


# Tempo di elaborazione importatore classificazione

Il tempo di elaborazione di un file di classificazione varia in base alle dimensioni del file e al numero totale di file  processi di Adobe. Le classificazioni in genere non richiedono più di 72 ore. Tuttavia, i periodi di uso intensivo delle classificazioni tra le organizzazioni che utilizzano  Adobe Analytics possono causare l&#39;utilizzo di file per più di 72 ore.  Adobe vede un uso pesante della classificazione nei mesi che precedono la stagione delle vacanze.

Per verificare se un file di classificazione è terminato, effettuate le seguenti operazioni:

1. Accedete a  Adobe Analytics, quindi selezionate **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Seleziona la suite di rapporti e il set di dati in questione.
3. Se l&#39;elaborazione non è ancora completa, viene visualizzato uno dei seguenti messaggi:

   * ![Avviso](assets/icon_notice_notice.gif) Il rapporto selezionato presenta un&#39;importazione di classificazione in fase di elaborazione.
   * ![Avviso](assets/icon_notice_notice.gif) Il report selezionato contiene dati di classificazione non ancora propagati a tutti i server.

Per ridurre al minimo i tempi di importazione delle classificazioni,  Adobe consiglia vivamente di attenersi alle seguenti linee guida:

* **Quando possibile**, usate il generatore di regole di classificazione: Il generatore di regole di classificazione elabora i dati in modo diverso rispetto all&#39;importatore di classificazione tradizionale. Se i dati di classificazione seguono pattern specifici, si consiglia vivamente di utilizzare questa funzionalità.
* **Carica solo righe** modificate: Questa procedura riduce notevolmente il tempo necessario per elaborare i file di classificazione, poiché non consente di ordinare le righe rimaste immutate.  Adobe consiglia di caricare solo le righe modificate.
* **Pianificare in anticipo**: Iniziate a caricare i dati di classificazione il prima possibile, specialmente se questi dati vengono utilizzati durante le vacanze.
* **Combinare, se possibile**, i file di classificazione: Se una singola variabile ha più classificazioni, caricate un singolo file con tutte le classificazioni applicabili. Evitare di caricare più classificazioni per la stessa variabile.
* **Evitate di caricare file di dimensioni superiori a 500 MB**: Se si tratta di grandi quantità di dati di classificazione,  Adobe consiglia di suddividere i file in file da 100 MB a 500 MB.
* **Evitate di caricare grandi quantità di file su FTP**: Se intendete caricare gli stessi file in molte suite di rapporti tramite FTP, limitate il numero di file caricati alla volta.  Adobe raccomanda che il numero di file moltiplicato per il numero di suite di rapporti applicabili sia inferiore a 1000. Se è necessario caricare 100 file in 100 suite di rapporti, il numero totale di file è 10.000. Invece di caricare tutti e 100 i file contemporaneamente, suddividetelo in 10 gruppi di 10 file alla volta.
* **Caricate i file di piccole dimensioni tramite Importazione** browser: Se si dispone di un file inferiore a 1 MB (meno di 50.000 righe),  Adobe consiglia di utilizzare la funzione di importazione browser. Le importazioni dal browser sono quasi sempre più veloci delle importazioni FTP.
