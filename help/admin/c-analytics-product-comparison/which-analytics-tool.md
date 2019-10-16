---
description: Questa pagina dell'Aiuto contiene casi d'uso consigliati per ogni strumento Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le esigenze, passare a quello successivo per essere preso in considerazione.
seo-description: Questa pagina dell'Aiuto contiene casi d'uso consigliati per ogni strumento Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le esigenze, passare a quello successivo per essere preso in considerazione.
seo-title: Quale strumento Adobe Analytics usare?
title: Quale strumento Adobe Analytics usare?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: 0b4a0874013b4b62639a845c53cc030b7b8e9160

---


# Quale strumento Adobe Analytics usare?

Questa pagina dell'Aiuto contiene casi d'uso consigliati per ogni strumento Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le esigenze, passare a quello successivo per essere preso in considerazione.

Per ulteriori informazioni sui confronti tra i prodotti Adobe Analytics, consulta [qui](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfacce utente di Adobe Analytics Reporting {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** deve essere l’interfaccia utente di riferimento per tutte le tue esigenze di reporting e analisi. Adobe continua a investire in questo prodotto e a rilasciare aggiornamenti mensili. In caso di attività che non è possibile eseguire in Analysis Workspace, considera le altre interfacce riportate di seguito.**

**[Reporting e analisi](/help/analyze/reports-analytics/overview/report-overview.md)** devono essere utilizzati:

* Per utenti principianti che devono accedere a rapporti pregenerati che sono più facili da consultare.
* Per un conteggio accurato delle impressioni e delle conversioni delle attività A4T.
* Per comprendere l'incremento e la confidenza dell'attività Target (Analytics for Target/A4T).
* Per accedere ai dati in tempo reale nell’interfaccia utente.
* Per impostare gli eventi del calendario.
* Per impostare i target.
* Per visualizzare il reporting dei bot.
* Per esaminare più suite di rapporti in un'unica dashboard dell'interfaccia utente.
* Per accedere a visualizzazioni video univoche di Visualizzatore simultaneo, Daypart video e Visualizzatore Drop-off.
* Per sfruttare gli elenchi di pubblicazione nei report pianificati.

**[Utilizzare l'interfaccia utente](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)** di Mobile Services:

* Se si desidera una visualizzazione silenziata dei dati dell'app mobile.
* Per gestire l’implementazione dell’SDK dell’app mobile.
* Per configurare la pubblicità mobile, ad esempio messaggi in-app, messaggi push e targeting delle posizioni.
* Se per i dati dell'app sono desiderate più visualizzazioni interattive (sunburst).
* Per visualizzare i punti di interesse su una mappa.
* Per le metriche del valore del ciclo di vita.

**[Utilizzare Analisi](/help/analyze/ad-hoc-analysis/adhoc-home.md)** ad hoc:

* Se si desidera utilizzare la funzionalità del generatore di tabelle true. Ad esempio, a) Analysis Workspace non è in grado di supportare ciò che è necessario creare, b) si desidera essere in grado di controllare quando la tabella viene rigenerata, c) si desidera che la tabella ricordi i vari livelli di suddivisione che si desidera applicare a tutte le righe, d) si desidera ordinare manualmente le righe delle metriche
* Per esportare 50.000 righe di dati
* Se si desidera organizzare il lavoro del progetto tramite tabulazioni.
* Per utilizzare il rapporto Analisi sito (rapporto percorsi 3D).

**[Utilizzare Workbench](https://marketing.adobe.com/resources/help/en_US/insight/)** dati:

* Come opzione dello strumento Analytics più flessibile (fino all’analisi a livello di visitatore e a livello di hit).
* Per creare un dataset multicanale di interazioni online e offline da CRM a POS a Web.
* Per l'attribuzione avanzata (modelli algoritmici e basati su regole).
* Per la modellazione statistica predittiva (punteggio tendenza, clustering, correlazioni, ecc.).
* Per l'analisi della latenza (tempo prima/dopo un evento).
* Per identificare ed esportare segmenti complessi in Adobe Experience Cloud.

## Importazione di dati in Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Le classificazioni](/help/components/c-classifications2/c-classifications.md)** devono essere utilizzate:

* In presenza di metadati da associare a un valore di raccolta (eVar, prop, canale di marketing)
* Opzioni:

   * Generatore di regole: utilizzare quando si raccolgono valori formattati prevedibili per una variabile, ad esempio valori delimitati. Questo approccio consente di impostare regole una volta e in gran parte "impostarlo e dimenticarlo".
   * Importazione browser: utilizzate quando non disponete di valori prevedibili o quando disponete di un elenco finito di valori che richiede un aggiornamento una tantum. Questo approccio richiede un monitoraggio continuo delle classificazioni per i nuovi valori.

**[Origini](/help/import/c-data-sources/datasrc-home.md)** dati:

* In presenza di dati offline, è necessario essere scritti in modo permanente in Adobe Analytics
* Opzioni:

   * Riepilogo: caricamenti di dati semplici, per giorno o per dimensioni limitate
   * ID transazione: caricamenti di dati che collegano un endpoint online ai dati offline e associano completamente i dati importati a uno snapshot visitatore acquisito online (ad esempio, ordini completati online e restituiti offline)
   * Elaborazione completa: origini dati con marca temporale, elaborate come se si trattasse di un hit raccolto dai server Adobe. Ad esempio, i dati vengono inseriti direttamente nel percorso del visitatore.

**[È necessario utilizzare i Connettori](https://www.adobeexchange.com/experiencecloud.html)dati (precedentemente noti come Genesis)** :

* Quando interagisci con un provider di terze parti che ha creato una connessione supportata con Adobe Analytics. In genere, i Connettori dati incorporano dati di livello sintetico in Adobe Analytics in modo permanente e automatico, su base periodica.

**[È necessario utilizzare l'API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)** di inserimento dati:

* Quando devi caricare dati in Adobe Analytics e non puoi usare il codice SDK Adobe AppMeasurement o mobile.

**[Attributi](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)** cliente:

* Se acquisisci dati del cliente Enterprise in un database CRM (Customer Relationship Management) e vuoi caricare tali dati in Experience Cloud.
* Se desideri utilizzare i dati CRM per analisi più approfondite in Analytics o come criteri di targeting in Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** deve essere utilizzato:

* Se desideri incorporare dati di audience di Adobe Audience Manager (AAM) come informazioni demografiche (ad esempio, genere o livello di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM o dati di impressioni di annunci in qualsiasi flusso di lavoro Analytics.
* Se vuoi che i dati CRM caricati siano basati su tempo, perché questa integrazione invia nuove informazioni ad Analytics hit per hit.

## Esportazione di dati da Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Generatore](/help/analyze/report-builder/home.md)** di report:

* Se le opzioni di layout personalizzate di Workspace sono limitate (tutto è possibile nel Generatore di report, entro i limiti di Excel).
* Per collegare liberamente gli input degli utenti o le origini dati offline (impression, costo) ai dati Adobe. Una soluzione più permanente per il collegamento dei dati è Origini dati (consulta Importazione di dati in Analytics).
* Unione di dati da diversi rapporti dimensionali (ad es. rapporto sulle impression promozionali unito al rapporto sul click-to-conversion promozionale).
* Per le viste suite per report.
* Se si desidera automatizzare la pianificazione (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** deve essere utilizzato:

* Per accedere alle variabili altrimenti nascoste nell’interfaccia utente (indirizzo IP, ID Experience Cloud, ID visitatore Analytics, URL pagina)
* Accesso a dati più granulari dell'interfaccia (visualizzazione tabella denormalizzata)
* Per scaricare i dati in un formato adatto per l'input di una tabella pivot
* Se il cliente desidera inserire dati Adobe in uno strumento di visualizzazione dati di terze parti (leggermente riepilogati e non a livello di hit)
* Per accedere a tutti i valori di dimensione univoci se ti trovi in "Basso traffico" in Adobe Analytics

**[È necessario utilizzare Feed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** dati di Analytics:

* Per utilizzare il feed di dati più granulare è possibile fornire (ID visitatore, hit).
* Se il cliente desidera che i dati Adobe siano memorizzati in un database lato client, al livello più dettagliato che possiamo inviare.
* Se il cliente desidera sviluppare uno strumento di Business Intelligence (BI) o immettere dati Adobe a livello di hit in uno strumento di terze parti.

**[Le API](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)** di reporting devono essere utilizzate quando le altre opzioni di visualizzazione non soddisfano le tue esigenze. Le 3 opzioni API includono:

* **Elaborazione** Completa: per i dati ricchi di funzionalità (comprese visite, visitatori e segmenti). Si tratta di dati sintetizzati tipici dell'interfaccia utente di Analytics, disponibili entro circa 30-90 minuti. Può essere utilizzato tramite Generatore di report.
* **In Tempo** Reale: per visualizzare alcune metriche e dimensioni con secondi di latenza. Si tratta di dati limitati, parzialmente elaborati e riepilogati disponibili entro circa 30 secondi. Include algoritmi univoci per i più comuni, per i guadagni e per i perdenti. Può essere utilizzato tramite Generatore di report.
* **[!UICONTROL Live Stream]**: quando desideri un flusso di dati Analytics a livello di hit parzialmente elaborati entro pochi secondi dalla raccolta. Questi dati vengono elaborati parzialmente, disponibili entro circa 30 secondi. Disponibile solo per Analytics Premium. Richiede un modo per visualizzare i dati, in genere attraverso un coinvolgimento dei servizi tecnici.

## Soluzioni personalizzate {#section_4A212F26A15947599DFB0399A0440CB6}

I servizi tecnici devono essere utilizzati quando:

* Gli altri strumenti Adobe non soddisfano le tue esigenze.
* Desiderate un'esperienza personalizzata.
* Vuoi una soluzione completamente automatizzata.
* Volete raggiungere molti dispositivi.
* Sono presenti più origini dati.
* Sono presenti requisiti ETL di dati complessi (Extract-Transform-Load).
* Desiderate un marchio personalizzato.
* Vuoi visualizzare [!UICONTROL Analytics Live Stream].
