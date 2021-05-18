---
description: Il modello di file di importazione è progettato per aiutarti a iniziare l'importazione.
subtopic: Data sources
title: Generare un modello di file di importazione
topic-fix: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
exl-id: c2717936-a011-4224-8a9e-94753abbcb33
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 68%

---

# Generare un modello di file di importazione

Il modello di file di importazione è progettato per aiutarti a iniziare l&#39;importazione.

Non sei limitato alle colonne definite nel modello. Puoi aggiungere qualsiasi altra colonna che ti serve, a condizione che la metrica o la definizione sia supportata per il tipo di elaborazione dati selezionato. Puoi visualizzare le metriche e le dimensioni supportate per ogni tipo nelle sezioni seguenti:  [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md),  [traffico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md),  [conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), ID  [transazione](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), ID  [visitatore](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md), elaborazione  [completa](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)). Ad esempio, per un tipo di dati traffico, puoi aggiungere una colonna per qualsiasi metrica o dimensione elencata in [Traffico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Una volta creato, puoi scaricare il modello, inserire i dati nel modello, quindi caricare i dati sul sito FTP Origini dati. Una volta elaborati dal server Origini dati, i dati importati sono disponibili per l&#39;utilizzo nei rapporti di Analytics.

Il modello Origine dati è un file .txt che puoi aprire con qualsiasi editor di testo. Tuttavia, è più semplice lavorare con il modello utilizzando Microsoft Excel o un&#39;altra applicazione di fogli di calcolo. Il contenuto del modello varia in base alle selezioni nella procedura guidata Attivazione origine dati.

Consulta  [Riferimento file di importazione](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) per ulteriori dettagli.

1. Accedi ad Analytics.
1. Nell’intestazione della suite, seleziona **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.
1. Nella scheda **[!UICONTROL Data Sources Create]** , seleziona una categoria e un tipo di modello.
1. Controlla le istruzioni/informazioni di attivazione, quindi fai clic su **[!UICONTROL Activate]**.

   Passaggio 1: Seleziona le opzioni di generazione modello nella procedura guidata Attivazione origine dati.

   | Pagina della procedura guidata | Campo | Descrizione |
   |--- |--- |--- |
   | 1 | Nome | Il nome del modello visualizzato da Analytics in Origini dati Manager. |
   | 1 | E-mail | L&#39;indirizzo e-mail che riceve tutte le notifiche correlate all&#39;utilizzo di questo modello Origine dati. |
   | 1 | Casella di controllo Associated Fees (Spese associate) | Seleziona la casella di controllo per indicare l’accettazione delle tariffe associate all’utilizzo di questo modello Origine dati. |
   | 2 | Choose Metrics (Scegli metrica) | Seleziona la metrica da importare utilizzando questa Origine dati. Analytics consiglia alcune metriche in base alla categoria e al tipo di origine dati selezionati al passaggio 3.  Per specificare una metrica diversa, digita il nome in un campo vuoto e seleziona la casella di controllo per attivare la metrica. |
   | 3 | Map Metrics (Mappa metrica) | Seleziona un evento di Analytics per ricevere ogni metrica importata selezionata nella procedura guidata a pagina 2.  Devono essere eventi nuovi e non assegnati a cui in precedenza sono stati assegnati nomi corrispondenti ai dati della metrica importati che riceveranno tramite Origine Dati.  Se una variabile eVar, Prodotto o Codice di tracciamento è una variabile di destinazione e i valori caricati corrispondono ai valori acquisiti esistenti, gli eventi caricati aggiungono fondamentalmente le metriche ai valori esistenti. Ad esempio, puoi creare una metrica &quot;Ordini offline&quot; con una dimensione dati Prodotti che ha già Visualizzazioni prodotto, Pagamenti e Ordini come metriche esistenti. |
   | 4 | Choose Data Dimensions (Scegli dimensioni dati) | Seleziona le dimensioni dei dati per suddividere le metriche importate da questa Origine dati. Analytics consiglia alcune dimensioni dati in base al tipo di origine dati selezionato al passaggio 3.  Per specificare una dimensione dati diversa, digita il nome in un campo vuoto e seleziona la casella di controllo per attivare la dimensione dati. |
   | 5 | Map Data Dimensions (Mappa dimensioni dati) | Seleziona un rapporto standard o eVar per ricevere ogni dimensione dati importata selezionata nella procedura guidata a pagina 4. |

1. Dopo la generazione del modello, copia i dati nelle colonne opportune del modello Origine dati, verificando di rispettare il formato dati richiesto per tale colonna di dati.

   Passaggio 1: Salva il file Origini dati utilizzando una convenzione di denominazione prescelta. Adobe consiglia di utilizzare una convenzione di denominazione coerente per tutti i file Origini dati. Utilizza un’estensione file comune, ad esempio .txt o .tsv (o non utilizzare estensioni).
