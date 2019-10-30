---
description: Il modello di file di importazione è progettato per aiutarti a iniziare l'importazione.
seo-description: Il modello di file di importazione è progettato per aiutarti a iniziare l'importazione.
seo-title: Generare un modello di file di importazione
solution: Analytics
subtopic: Origini dati
title: Generare un modello di file di importazione
topic: Sviluppatore e implementazione
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Generare un modello di file di importazione

Il modello di file di importazione è progettato per aiutarti a iniziare l'importazione.

Non sei limitato alle colonne definite nel modello. Puoi aggiungere qualsiasi altra colonna che ti serve, a condizione che la metrica o la definizione sia supportata per il tipo di elaborazione dati selezionato. Puoi visualizzare le metriche e le dimensioni supportate per ogni tipo nelle sezioni seguenti: Registro [](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)Web, [Traffico](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC), [Conversione](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0), ID [](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)transazione, ID [](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)[](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)visitatore, Elaborazione completa). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC).

Una volta creato, puoi scaricare il modello, inserire i dati nel modello, quindi caricare i dati sul sito FTP Origini dati. Una volta elaborati dal server Origini dati, i dati importati sono disponibili per l'utilizzo nei report Analytics.

Il modello Origine dati è un file .txt che puoi aprire con qualsiasi editor di testo. Tuttavia, è più semplice lavorare con il modello utilizzando Microsoft Excel o un'altra applicazione di fogli di calcolo. Il contenuto del modello varia in base alle selezioni nella procedura guidata Attivazione origine dati.

Consulta  [Riferimento file di importazione](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) per ulteriori dettagli.

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

