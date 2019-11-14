---
description: Il modello di file di importazione è progettato per aiutarti a iniziare l'importazione.
solution: Analytics
subtopic: Data sources
title: Generare un modello di file di importazione
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Generare un modello di file di importazione

Il modello di file di importazione è progettato per aiutarti a iniziare l'importazione.

Non sei limitato alle colonne definite nel modello. Puoi aggiungere qualsiasi altra colonna che ti serve, a condizione che la metrica o la definizione sia supportata per il tipo di elaborazione dati selezionato. Puoi visualizzare le metriche e le dimensioni supportate per ogni tipo nelle sezioni seguenti: Registro [](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)Web, [Traffico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), ID [](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)transazione, ID [](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)visitatore, Elaborazione completa). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Una volta creato, puoi scaricare il modello, inserire i dati nel modello, quindi caricare i dati sul sito FTP Origini dati. Una volta elaborati dal server Origini dati, i dati importati sono disponibili per l'utilizzo nei report Analytics.

Il modello Origine dati è un file .txt che puoi aprire con qualsiasi editor di testo. Tuttavia, è più semplice lavorare con il modello utilizzando Microsoft Excel o un'altra applicazione di fogli di calcolo. Il contenuto del modello varia in base alle selezioni nella procedura guidata Attivazione origine dati.

Consulta  [Riferimento file di importazione](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) per ulteriori dettagli.

1. Effettuate l'accesso ad Analytics.
1. Nell’intestazione Suite, selezionate **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. Nella **[!UICONTROL Data Sources Create]** scheda, selezionate una categoria e un tipo di modello.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   Passaggio 1. Seleziona le opzioni di generazione modello nella procedura guidata Attivazione origine dati.

   | Pagina della procedura guidata | Campo | Descrizione |
   |--- |--- |--- |
   | 1 | Nome | Nome del modello visualizzato da Analytics in Origini dati Manager. |
   | 1 | E-mail | L'indirizzo e-mail che riceve tutte le notifiche correlate all'utilizzo di questo modello Origine dati. |
   | 1 | Casella di controllo Associated Fees (Spese associate) | Seleziona la casella di controllo per indicare l'accettazione delle tariffe associate all'utilizzo di questo modello Origine dati. |
   | 2 | Choose Metrics (Scegli metrica) | Seleziona la metrica da importare utilizzando questa Origine dati. Analytics consiglia determinate metriche in base alla categoria e al tipo Origine dati selezionati al Passaggio 3.  Per specificare una metrica diversa, digita il nome in un campo vuoto e seleziona la casella di controllo per attivare la metrica. |
   | 3 | Map Metrics (Mappa metrica) | Selezionate un evento di Analytics per ricevere ogni metrica importata selezionata nella procedura guidata a pagina 2.  Devono essere eventi nuovi e non assegnati a cui in precedenza sono stati assegnati nomi corrispondenti ai dati della metrica importati che riceveranno tramite Origine Dati.  Se una variabile eVar, Prodotto o Codice di tracciamento è una variabile di destinazione e i valori caricati corrispondono ai valori acquisiti esistenti, gli eventi caricati aggiungono fondamentalmente le metriche ai valori esistenti. Ad esempio, puoi creare una metrica "Ordini offline" con una dimensione dati Prodotti che ha già Visualizzazioni prodotto, Checkout e Ordini come metriche esistenti. |
   | 4 | Choose Data Dimensions (Scegli dimensioni dati) | Seleziona le dimensioni dei dati per suddividere le metriche importate da questa Origine dati. Analytics consiglia determinate dimensioni dati in base al Tipo origine dati selezionato al Passaggio 3.  Per specificare una dimensione dati diversa, digita il nome in un campo vuoto e seleziona la casella di controllo per attivare la dimensione dati. |
   | 5 | Map Data Dimensions (Mappa dimensioni dati) | Seleziona un rapporto standard o eVar per ricevere ogni dimensione dati importata selezionata nella procedura guidata a pagina 4. |

1. Dopo la generazione del modello, copia i dati nelle colonne opportune del modello Origine dati, verificando di rispettare il formato dati richiesto per tale colonna di dati.

   Passaggio 1. Salva il file Origini dati utilizzando una convenzione di denominazione prescelta. Adobe consiglia di utilizzare una convenzione di denominazione coerente per tutti i file Origini dati. Utilizzate un'estensione file comune come .txt o .tsv (o non utilizzate estensioni).

