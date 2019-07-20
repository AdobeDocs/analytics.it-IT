---
description: Questa pagina di aiuto contiene casi d'uso consigliati per ciascun strumento Adobe Analytics. Gli strumenti devono essere considerati nell'ordine in cui sono elencati. Se un determinato strumento non soddisfa le necessità, passate a quello successivo.
seo-description: Questa pagina di aiuto contiene casi d'uso consigliati per ciascun strumento Adobe Analytics. Gli strumenti devono essere considerati nell'ordine in cui sono elencati. Se un determinato strumento non soddisfa le necessità, passate a quello successivo.
seo-title: Quale strumento Adobe Analytics devo usare?
title: Quale strumento Adobe Analytics devo usare?
uuid: 1179 e 49 d -3 cfc -4 abd-a 8 eb -35 c 5 ae 380 c 16
translation-type: tm+mt
source-git-commit: bf9152741507c75e1f92e8d5d515127eadf5d590

---


# Quale strumento Adobe Analytics devo usare?

Questa pagina di aiuto contiene casi d'uso consigliati per ciascun strumento Adobe Analytics. Gli strumenti devono essere considerati nell'ordine in cui sono elencati. Se un determinato strumento non soddisfa le necessità, passate a quello successivo.

For more on Adobe Analytics Product Comparisons, go [here](../../admin/c-analytics-product-comparison/analytics-product-comparison.md#concept_D9DB9FA42CA04F4C97765B6B31A0005D).

## Adobe Analytics Reporting User Interfaces {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)** deve essere l'interfaccia utente di accesso per tutte le tue esigenze di reporting e analisi. Adobe continua a investire e rilasciare aggiornamenti mensili a questo prodotto. Se non è disponibile un'attività in Analysis Workspace, prendi in considerazione le altre interfacce di seguito. **

**[Devono essere utilizzati Reporting e analisi](/help/analyze/reports-analytics/overview/report-overview.md)** :

* Per utenti principianti che richiedono l'accesso a rapporti pregenerati più facili da navigare.
* Per contare accuratamente A 4 T Activity Impression &amp; Conversions (Conversioni attività e conversioni).
* Per comprendere l'attività di Target (Analytics for Target/A 4 T) e la confidenza.
* Per accedere ai dati in tempo reale nell'interfaccia utente.
* Per configurare eventi calendario.
* Per configurare Target.
* Per visualizzare i rapporti bot.
* Per esaminare più suite di rapporti in una singola dashboard dell'interfaccia utente.
* Per accedere alle visualizzazioni video univoche di Visualizzatore simultaneo, Parte Daypart e Drop-off del visualizzatore.
* Per sfruttare la pubblicazione di elenchi nel reporting programmato.

**[L'interfaccia utente](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)** di Mobile Services deve essere utilizzata:

* Se desideri visualizzare una visualizzazione in silos dei dati App mobili.
* Per gestire l'implementazione dell'SDK per app mobili.
* Per configurare la pubblicità per dispositivi mobili, ad esempio messaggistica in-app, messaggi push e targeting delle posizioni.
* Se sono desiderate visualizzazioni interattive per i dati App (Sunburst).
* Per visualizzare i punti di interesse su una mappa.
* Per metriche Valore ciclo di vita.

**[È necessario utilizzare Analisi](/help/analyze/ad-hoc-analysis/adhoc-home.md)** ad hoc:

* Se è desiderata la funzionalità di generazione di tabelle true. Ad esempio, a) Analysis Workspace non è in grado di supportare ciò che è necessario creare, b) se desideri controllare quando la tabella ricrea, c) vuoi che la tabella ricordi i vari livelli di suddivisione che desideri applicare a tutte le righe, d) che desideri ordinare manualmente le righe di metrica
* Per esportare 50,000 righe di dati
* Se l'organizzazione della scheda del progetto è desiderata.
* Per utilizzare il rapporto Analisi sito (rapporto 3 D).

**[È](https://marketing.adobe.com/resources/help/en_US/insight/)** necessario utilizzare Workbench dati:

* Come opzione di strumento Analytics più flessibile (fino a un'analisi a livello di visitatore e a livello di visitatore).
* Per creare un set di dati multicanale di interazioni online e offline da CRM a POS su Web.
* Per attribuzione avanzata (modelli algoritmici e basati su regole).
* Per predittivi, modellazione statistica (punteggio tendenza, clustering, correlazioni ecc.).
* Per l'analisi della latenza (tempo prima/dopo un evento).
* Identificazione ed esportazione di segmenti complessi in Adobe Experience Cloud.

## Importing Data into Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Devono essere utilizzate le classificazioni](/help/components/c-classifications2/c-classifications.md)** :

* In caso di metadati da associare a un valore di raccolta (evar, prop, canale di marketing)
* Opzioni:

   * Generatore di regole: essere utilizzati quando sono disponibili valori formattati prevedibili per una variabile, ad es. valori delimitati. Questo approccio consente di impostare regole una volta e in gran parte "impostare e dimenticare".
   * Importazione browser: utilizzato quando non si hanno valori prevedibili o se si dispone di un elenco finito di valori che richiedono un aggiornamento una tantum. Questo approccio richiede il monitoraggio continuo delle classificazioni per i nuovi valori.

**[Devono](/help/import/c-data-sources/datasrc-home.md)** essere utilizzate Origini dati:

* Quando sono presenti dati offline che si desidera scrivere in modo permanente in Adobe Analytics
* Opzioni:

   * Riepilogo: semplici caricamenti di dati, per giorno o dimensioni limitate
   * ID transazione: caricamenti di dati che collegano un endpoint online a dati offline e associano completamente i dati importati a un'istantanea acquisita online (ad es. ordini completi online e restituiti offline)
   * Elaborazione completa: origini dati con marca temporale elaborate come se si trattasse di un hit raccolto dai server Adobe. I dati vengono inseriti direttamente nel percorso del visitatore.

**[Devono](https://www.adobeexchange.com/experiencecloud.html)essere utilizzati Connettori dati (precedentemente noti come Genesis)** :

* Quando si entra in contatto con un fornitore 3 rd-party che ha creato una connessione supportata con Adobe Analytics. In genere, i connettori dati incorporano in Adobe Analytics dati a livello di riepilogo in modo permanente e automatico.

**[È](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)** necessario utilizzare l'API di inserimento dati:

* Quando devi caricare dati in Adobe Analytics e non puoi usare il codice SDK di Adobe appmeasurement o Mobile.

**[Devono essere utilizzati gli attributi](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)** del cliente:

* Se acquisisci dati del cliente di livello Enterprise in un database CRM (Customer Relationship Management) e desideri caricare i dati in Experience Cloud.
* Se desideri utilizzare dati CRM per approfondire l'analisi in Analytics o come criteri di targeting in Adobe Target.

**[Deve essere utilizzato l'Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** :

* Se vuoi incorporare dati di audience di Adobe Audience Manager (AAM) come informazioni demografiche (ad es. genere o livello di entrate), informazioni psicografiche (ad es. interessi e hobby), dati CRM o dati di impressioni in qualsiasi flusso di lavoro Analytics.
* Se desiderate che i dati CRM caricati siano temporizzati, perché questa integrazione invia nuove informazioni ad Analytics hit by hit.

## Exporting Data from Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[È necessario utilizzare il Generatore](/help/analyze/report-builder/home.md)** di report:

* Se le opzioni di layout personalizzate di Workspace sono limitate (qualsiasi cosa sia possibile nel Generatore di report, entro i limiti di Excel).
* Per collegare in modo approssimativo input utente o origini dati offline (impression, costo) ai dati Adobe. La soluzione più permanente per il tocco nei dati è Origini dati (vedi Importazione di dati in Analytics).
* Unione di dati da rapporti dimensionali diversi (ad es. report di impressioni promozionali uniti con report di click-to-conversion).
* Per visualizzazioni multi-rapporto.
* Se l'automazione tramite la pianificazione è desiderata (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[È](/help/export/data-warehouse/data-warehouse.md)** necessario utilizzare Data Warehouse:

* Per accedere alle variabili in altro modo nascoste nell'interfaccia utente, indirizzo IP, Experience Cloud ID, ID visitatore Analytics, URL pagina)
* Per accedere a dati più granulari rispetto all'interfaccia utente (visualizzazione tabella denorizzata)
* Per scaricare dati in un formato adatto per un input Tabella pivot
* Se il client desidera inserire dati Adobe in uno strumento di visualizzazione dati 3 rd-party (leggermente riepilogato e non a livello di hit)
* Per accedere a tutti i valori di dimensioni univoci, se in Adobe Analytics si eseguono «Traffico basso»

**[È necessario utilizzare Feed](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** dati di Analytics:

* Per utilizzare il feed di dati più dettagliato possiamo fornire (ID visitatore, hit).
* Se il client desidera archiviare i dati Adobe in un database lato client, al livello più granulare che possiamo inviare.
* Se il client desidera sviluppare uno strumento di Business Intelligence (BI) o inserire dati Adobe di livello hit in uno strumento 3 rd-party.

**[Le API di reporting](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)** devono essere utilizzate quando le altre opzioni di visualizzazione non soddisfano le tue esigenze. Le opzioni API 3 includono:

* **Elaborato completamente**: Quando desideri dati ricchi di funzioni (comprese visite, visitatori e segmenti). Si tratta di dati riepilogati nell'interfaccia utente di Analytics standard, disponibili entro ~ 30-90 minuti. Può essere usato tramite Generatore di report.
* **Real-Time**: quando desideri visualizzare alcune metriche e dimensioni con secondi di latenza. Si tratta di dati limitati, elaborati parzialmente, che sono disponibili entro ~ 30 secondi. Include algoritmi univoci di più popolari, gainer e lochi. Può essere usato tramite Generatore di report.
* **[!UICONTROL Live Stream]**: quando desideri un flusso di dati Analytics parzialmente elaborati entro i secondi della raccolta. Si tratta di dati elaborati parzialmente, disponibili entro ~ 30 secondi. Disponibile solo per Analytics Premium. Richiede un po' di visualizzazione dei dati, in genere tramite un coinvolgimento di Servizi tecnici.

## Custom Solutions {#section_4A212F26A15947599DFB0399A0440CB6}

I servizi tecnici devono essere utilizzati quando:

* Gli altri strumenti Adobe non soddisfano le tue esigenze.
* Si desidera un'esperienza personalizzata.
* Vuoi una soluzione completamente automatizzata.
* Desiderate raggiungere molti dispositivi.
* Hai più origini dati.
* Disponete di requisiti ETL (Extract-Transform-Load) complessi.
* Personalizzazione personalizzata.
* You want to visualize [!UICONTROL Analytics Live Stream].
