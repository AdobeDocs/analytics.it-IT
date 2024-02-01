---
description: Questa pagina dell’Aiuto contiene casi d’uso consigliati per ogni strumento di Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le tue esigenze, passa a quello successivo.
title: Quale strumento Adobe Analytics usare?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: ee4772913c8b702658646755a2a11598c8530236
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 92%

---

# Quale strumento Adobe Analytics usare?

Questa pagina dell’Aiuto contiene casi d’uso consigliati per ogni strumento di Adobe Analytics. Gli strumenti devono essere considerati nell’ordine in cui sono elencati. Se un determinato strumento non soddisfa le tue esigenze, passa a quello successivo.

Per ulteriori informazioni sul confronto tra i prodotti Adobe Analytics, consulta [Confronto tra i prodotti Analytics](/help/analyze/get-started/analytics-product-comparison.md).

Questo video mette a confronto diversi strumenti di Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27220/?quality=12)

## Interfacce utente di Adobe Analytics per la generazione di rapporti {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** deve essere l’interfaccia utente di riferimento per tutte le tue esigenze di reporting e analisi. Adobe continua a investire in questo prodotto e a rilasciare aggiornamenti mensili. Se non è possibile eseguire una specifica attività in Analysis Workspace, considera le altre interfacce riportate di seguito.**

**[Dashboard di Adobe Analytics](/help/analyze/mobile-app/home.md)** consente agli utenti di accedere a scorecard intuitive da dispositivi mobili. Le scorecard sono una raccolta di metriche chiave e di altri componenti presentati in un layout a sezioni che puoi toccare per visualizzare raggruppamenti più dettagliati e rapporti sulle tendenze. L’app mobile è supportata sia su sistemi operativi iOS che Android.

**[Report Builder](/help/analyze/report-builder/home.md)** è un componente aggiuntivo per Microsoft Excel. Consente di generare richieste personalizzate partendo da dati di Adobe Analytics, che puoi inserire in fogli di lavoro Excel. Le richieste possono fare riferimento in maniera dinamica a celle presenti nel tuo foglio di lavoro, inoltre hai la possibilità di aggiornare e personalizzare la presentazione dei dati da parte del Report Builder.

**[Activity Map](/help/analyze/activity-map/activity-map.md)** è una funzione all’interno di Adobe Analytics che fornisce una rappresentazione visiva del coinvolgimento degli utenti su pagine web e app mobili. Consente agli esperti di marketing e agli analisti di monitorare e analizzare le interazioni degli utenti, ad esempio clic, passaggi al passaggio del mouse e comportamenti di scorrimento.

## Importazione di dati in Adobe Analytics {#import}

Le **[classificazioni](/help/components/classifications/c-classifications.md)** sono indicate nei seguenti casi:

* In presenza di metadati da associare a un valore di raccolta (eVar, prop, canale di marketing)
* Opzioni:

   * Generatore di regole: utile quando si raccolgono valori formattati prevedibili per una variabile, ad esempio valori delimitati. Questo approccio consente di impostare le regole una volta e applicarle poi senza ulteriori interventi.
   * Importazione browser: utile quando non si dispone di valori prevedibili o quando si dispone di un elenco finito di valori che richiede un aggiornamento una tantum. Questo approccio richiede un monitoraggio continuo delle classificazioni per i nuovi valori.

Le **[origini dati](/help/import/data-sources/overview.md)** sono utili nei seguenti casi:

* In presenza di dati offline che devono essere scritti in modo permanente in Adobe Analytics
* Opzioni:

   * Riepilogo: caricamenti di dati semplici, per giorno o di dimensioni limitate
   * ID transazione: caricamenti di dati che collegano un endpoint online a dati offline e associano completamente i dati importati a uno snapshot visitatore acquisito online (ad esempio, ordini completati online e restituiti offline)
   * Elaborazione completa: origini dati con marca temporale, elaborate come gli hit raccolti dai server Adobe. Ad esempio, i dati vengono inseriti direttamente nel percorso del visitatore.

**[Le integrazioni Adobe Exchange](https://www.adobeexchange.com/experiencecloud.html)** devono essere utilizzate:

* Quando interagisci con un provider di terze parti che ha creato una connessione supportata con Adobe Analytics. In genere, le app di integrazione incorporano dati di riepilogo in Adobe Analytics in modo permanente e automatico, su base periodica.

**[Data Insertion API](/help/import/c-data-insertion-api/c-data-insertion-api.md)** è indicato nei seguenti casi:

* Quando devi caricare dati in Adobe Analytics e non puoi utilizzare il codice Adobe AppMeasurement o Mobile SDK. È consigliabile utilizzare l’API di inserimento dati in blocco (vedi di seguito).

**[API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* L’API di inserimento dati e l’API di inserimento dati in blocco sono entrambi metodi per inviare i dati di raccolta lato server ad Adobe Analytics. Le chiamate API di inserimento dati vengono effettuate un evento alla volta. L’API di inserimento dati in blocco accetta file in formato CSV contenenti dati evento, un evento per riga. Se stai lavorando a una nuova implementazione della raccolta lato server, ti consigliamo di utilizzare l’API di inserimento dati in blocco.

Gli **[Attributi cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=it)** sono indicati per i seguenti casi:

* Se acquisisci dati cliente Enterprise in un database CRM (Customer Relationship Management) e vuoi caricarli in Experience Cloud.
* Se desideri utilizzare i dati CRM per analisi più approfondite in Analytics o come criteri di targeting in Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** è indicato nei seguenti casi:

* Se desideri incorporare in un flusso di lavoro Analytics dei dati sul pubblico da Adobe Audience Manager come informazioni demografiche (ad esempio, genere o fascia di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM o dati di impressioni di annunci.
* Se vuoi che i dati CRM caricati siano basati su tempo, perché questa integrazione invia nuove informazioni ad Analytics hit per hit.

## Esportazione di dati da Adobe Analytics {#export}

**[Report Builder](/help/analyze/report-builder/home.md)** è indicato nei seguenti casi:

* Se le opzioni di layout personalizzate di Workspace non sono sufficienti (con Report Builder è possibile realizzare qualsiasi tipo di rapporto, entro i limiti di Excel).
* Per collegare liberamente ai dati Adobe i dati provenienti dall’input degli utenti e da origini dati offline (impressioni, costo). Una soluzione più permanente per il collegamento dei dati è Origini dati (consulta Importazione di dati in Analytics).
* Per unire i dati da diversi rapporti dimensionali (ad esempio, per unire un rapporto sulle impressioni promozionali a uno sui dati “dal clic alla conversione”).
* Unione dei dati da suite di rapporti diverse, tramite la somma o la visualizzazione affiancata nella stessa tabella.
* Se intendi automatizzare le operazioni tramite pianificazione (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** è indicato nei seguenti casi:

* Per accedere alle variabili altrimenti nascoste nell’interfaccia utente (indirizzo IP, Experience Cloud ID, ID visitatore di Analytics, URL pagina)
* Per accedere a dati più granulari rispetto a quelli accessibili dall’interfaccia (visualizzazione tabellare denormalizzata)
* Per scaricare i dati in un formato adatto per l’input in una tabella pivot
* Se il cliente desidera inserire dati Adobe in uno strumento di visualizzazione dati di terze parti (leggermente riepilogati e non a livello di hit)
* Per accedere a tutti gli elementi dimensionali univoci nei casi di “traffico ridotto” in Adobe Analytics

**[Feed dati di Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)** è indicato nei seguenti casi:

* Per utilizzare un feed di dati quanto più granulare possibile fornire (ID visitatore, hit)
* Se il cliente desidera che i dati Adobe siano memorizzati in un database lato client, con il massimo della granularità
* Se il cliente desidera sviluppare uno strumento di Business Intelligence (BI) o immettere dati Adobe a livello di hit in uno strumento di terze parti

Utilizza le **[API di reporting](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** quando le altre opzioni di visualizzazione non soddisfano le tue esigenze. Le 3 opzioni di API includono:

* **Dati con elaborazione completa**: per dati completi (compresi visite, visitatori e segmenti). Si tratta solitamente di dati di riepilogo dall’interfaccia utente di Analytics, disponibili entro circa 30-90 minuti. Possono essere utilizzati tramite Report Builder.
* **Dati in tempo reale**: per visualizzare alcune metriche e dimensioni con pochi secondi di latenza. Si tratta di dati limitati, parzialmente elaborati e di riepilogo disponibili entro circa 30 secondi. Includono algoritmi univoci per dati di tipo Più popolari, Più redditizi e Meno redditizi. Possono essere utilizzati tramite Report Builder.
* **[!UICONTROL Live Stream]**: quando desideri un flusso di dati Analytics a livello di hit parzialmente elaborati entro pochi secondi dalla raccolta. Si tratta di dati parzialmente elaborati disponibili entro circa 30 secondi. Disponibile solo per Analytics Premium. Richiede un modo per visualizzare i dati, in genere tramite il coinvolgimento del team Adobe Engineering Services.

## Soluzioni personalizzate {#custom-solutions}

È possibile rivolgersi al team Adobe Engineering Services nei seguenti casi:

* Quando gli altri strumenti Adobe non soddisfano le tue esigenze
* Quando desideri ottenere un’esperienza personalizzata
* Quando ti serve una soluzione completamente automatizzata
* Quando vuoi raggiungere molti dispositivi
* In presenza di più origini dati
* In presenza di requisiti di dati ETL (Extract-Transform-Load) complessi
* Quando desideri una soluzione con branding personalizzato
* Quando vuoi visualizzare [!UICONTROL Analytics Live Stream]
