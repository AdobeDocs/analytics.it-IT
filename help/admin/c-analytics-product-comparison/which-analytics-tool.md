---
description: Questa pagina dell’Aiuto contiene casi d’uso consigliati per ogni strumento di Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le tue esigenze, passa a quello successivo.
title: Quale strumento Adobe Analytics usare?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 97%

---


# Quale strumento Adobe Analytics usare?

Questa pagina dell’Aiuto contiene casi d’uso consigliati per ogni strumento di Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le tue esigenze, passa a quello successivo.

Per ulteriori informazioni su un confronto tra i vari prodotti Adobe Analytics, consulta [questo articolo](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfacce utente di Adobe Analytics per la generazione di rapporti {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)**deve essere l’interfaccia utente di riferimento per tutte le tue esigenze di reporting e analisi. Adobe continua a investire in questo prodotto e a rilasciare aggiornamenti mensili. Se non è possibile eseguire una specifica attività in Analysis Workspace, considera le altre interfacce riportate di seguito.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**è indicato per:

* Utenti principianti che devono accedere a rapporti pregenerati facili da consultare
* Accedere ai dati in tempo reale nell’interfaccia utente
* Impostare eventi di Calendario
* Impostare le destinazioni
* Visualizzare i rapporti generati da bot
* Accedere a visualizzazioni video univoche per visualizzatori simultanei, video Daypart e abbandono dei visualizzatori
* Sfruttare gli elenchi di pubblicazione nei rapporti pianificati

**[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**è indicato per:

* Esportare 50.000 righe di dati
* Organizzare il lavoro del progetto in schede diverse
* Utilizzare il rapporto Analisi del sito (rapporto “3D-pathing”)

**[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**è indicato per:

* Usufruire dell’opzione più flessibile tra gli strumenti Analytics (analisi a livello di visitatore e di hit)
* Creare un dataset multicanale di interazioni online e offline da CRM a POS a Web
* Attribuzione avanzata (modelli algoritmici e basati su regole)
* Modellazione statistica predittiva (punteggio tendenza, clustering, correlazioni, ecc.)
* Analisi della latenza (tempo prima/dopo un evento)
* Identificare ed esportare segmenti complessi in Adobe Experience Cloud

## Importazione di dati in Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

Le **[classificazioni](/help/components/c-classifications2/c-classifications.md)**sono indicate nei seguenti casi:

* In presenza di metadati da associare a un valore di raccolta (eVar, prop, canale di marketing)
* Opzioni:

   * Generatore di regole: utile quando si raccolgono valori formattati prevedibili per una variabile, ad esempio valori delimitati. Questo approccio consente di impostare le regole una volta e applicarle poi senza ulteriori interventi.
   * Importazione browser: utile quando non si dispone di valori prevedibili o quando si dispone di un elenco finito di valori che richiede un aggiornamento una tantum. Questo approccio richiede un monitoraggio continuo delle classificazioni per i nuovi valori.

Le **[origini dati](/help/import/c-data-sources/datasrc-home.md)**sono utili nei seguenti casi:

* In presenza di dati offline che devono essere scritti in modo permanente in Adobe Analytics
* Opzioni:

   * Riepilogo: caricamenti di dati semplici, per giorno o di dimensioni limitate
   * ID transazione: caricamenti di dati che collegano un endpoint online a dati offline e associano completamente i dati importati a uno snapshot visitatore acquisito online (ad esempio, ordini completati online e restituiti offline)
   * Elaborazione completa: origini dati con marca temporale, elaborate come gli hit raccolti dai server Adobe. Ad esempio, i dati vengono inseriti direttamente nel percorso del visitatore.

**[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(noti in precedenza come Genesis)**sono indicati nei seguenti casi:

* Quando interagisci con un provider di terze parti che ha creato una connessione supportata con Adobe Analytics. In genere, i Data Connectors incorporano dati di riepilogo in Adobe Analytics in modo permanente e automatico, su base periodica.

**[Data Insertion API](/help/import/c-data-insertion-api/c-data-insertion-api.md)**è indicato nei seguenti casi:

* Quando devi caricare dei dati in Adobe Analytics e non puoi usare il codice di Adobe AppMeasurement o Mobile SDK.

Gli **[Attributi cliente](https://docs.adobe.com/content/help/it-IT/core-services/interface/customer-attributes/attributes.html)**sono indicati nei seguenti casi:

* Se acquisisci dati cliente Enterprise in un database CRM (Customer Relationship Management) e vuoi caricarli in Experience Cloud.
* Se desideri utilizzare i dati CRM per analisi più approfondite in Analytics o come criteri di targeting in Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**è indicato nei seguenti casi:

* Se desideri incorporare in un flusso di lavoro Analytics dei dati sul pubblico da Adobe Audience Manager (AAM) come informazioni demografiche (ad esempio, genere o fascia di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM o dati di impressioni di annunci.
* Se vuoi che i dati CRM caricati siano basati su tempo, perché questa integrazione invia nuove informazioni ad Analytics hit per hit.

## Esportazione di dati da Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

**[Report Builder](/help/analyze/report-builder/home.md)**è indicato nei seguenti casi:

* Se le opzioni di layout personalizzate di Workspace non sono sufficienti (con Report Builder è possibile realizzare qualsiasi tipo di rapporto, entro i limiti di Excel).
* Per collegare liberamente ai dati Adobe i dati provenienti dall’input degli utenti e da origini dati offline (impressioni, costo). Una soluzione più permanente per il collegamento dei dati è Origini dati (consulta Importazione di dati in Analytics).
* Per unire i dati da diversi rapporti dimensionali (ad esempio, per unire un rapporto sulle impressioni promozionali a uno sui dati “dal clic alla conversione”).
* Per ottenere viste con diverse suite di rapporti.
* Se intendi automatizzare le operazioni tramite pianificazione (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**è indicato nei seguenti casi:

* Per accedere alle variabili altrimenti nascoste nell’interfaccia utente (indirizzo IP, Experience Cloud ID, ID visitatore di Analytics, URL pagina)
* Per accedere a dati più granulari rispetto a quelli accessibili dall’interfaccia (visualizzazione tabellare denormalizzata)
* Per scaricare i dati in un formato adatto per l’input in una tabella pivot
* Se il cliente desidera inserire dati Adobe in uno strumento di visualizzazione dati di terze parti (leggermente riepilogati e non a livello di hit)
* Per accedere a tutti gli elementi di dimensione univoci se ti trovi in &quot;Basso traffico&quot; in Adobe  Analytics

**[Feed dati di Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**è indicato nei seguenti casi:

* Per utilizzare un feed di dati quanto più granulare possibile fornire (ID visitatore, hit)
* Se il cliente desidera che i dati Adobe siano memorizzati in un database lato client, con il massimo della granularità
* Se il cliente desidera sviluppare uno strumento di Business Intelligence (BI) o immettere dati Adobe a livello di hit in uno strumento di terze parti

Utilizza le **[API di reporting](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)**quando le altre opzioni di visualizzazione non soddisfano le tue esigenze. Le 3 opzioni di API includono:

* **Dati con elaborazione completa**: per dati completi (compresi visite, visitatori e segmenti). Si tratta solitamente di dati di riepilogo dall’interfaccia utente di Analytics, disponibili entro circa 30-90 minuti. Possono essere utilizzati tramite Report Builder.
* **Dati in tempo reale**: per visualizzare alcune metriche e dimensioni con pochi secondi di latenza. Si tratta di dati limitati, parzialmente elaborati e di riepilogo disponibili entro circa 30 secondi. Includono algoritmi univoci per dati di tipo Più popolari, Più redditizi e Meno redditizi. Possono essere utilizzati tramite Report Builder.
* **[!UICONTROL Live Stream]**: quando desideri un flusso di dati Analytics a livello di hit parzialmente elaborati entro pochi secondi dalla raccolta. Si tratta di dati parzialmente elaborati disponibili entro circa 30 secondi. Disponibile solo per Analytics Premium. Richiede un modo per visualizzare i dati, in genere tramite il coinvolgimento del team Adobe Engineering Services.

## Soluzioni personalizzate {#section_4A212F26A15947599DFB0399A0440CB6}

È possibile rivolgersi al team Adobe Engineering Services nei seguenti casi:

* Quando gli altri strumenti Adobe non soddisfano le tue esigenze
* Quando desideri ottenere un’esperienza personalizzata
* Quando ti serve una soluzione completamente automatizzata
* Quando vuoi raggiungere molti dispositivi
* In presenza di più origini dati
* In presenza di requisiti di dati ETL (Extract-Transform-Load) complessi
* Quando desideri una soluzione con branding personalizzato
* Quando vuoi visualizzare [!UICONTROL Analytics Live Stream]
