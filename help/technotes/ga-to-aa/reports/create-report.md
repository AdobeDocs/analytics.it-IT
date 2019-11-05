---
title: Creare un rapporto di base in Analysis Workspace
description: Scopri come creare un rapporto di base in Analysis Workspace in un formato adatto agli utenti che conoscono strumenti di terze parti come Google Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics

Analysis Workspace (una delle funzioni principali di Adobe Analytics) offre a un utente un’area solida per acquisire qualsiasi approfondimento sui dati raccolti. Reporting è molto diverso tra Google Analytics e Adobe Analytics:

* La struttura di reporting in Google Analytics consente di selezionare un particolare tipo di dati, ad esempio geolocalità o traffico di riferimento. La piattaforma utilizza una visualizzazione di reporting prefabbricata basata sul modo migliore previsto per visualizzare tali dati.
* La struttura di reporting in Analysis Workspace fornisce un quadro vuoto, fornendo maggiore flessibilità nel soddisfare esigenze di reporting esatte.

Poiché Analysis Workspace funziona più come un quadro che come rapporti prefabbricati, ricreare rapporti da Google Analytics è semplicemente una questione di utilizzare le visualizzazioni e i componenti giusti.

## Termini chiave utilizzati in Workspace

* **I pannelli** sono gli elementi costitutivi principali dell’area di lavoro. In quasi tutti gli scenari, viene utilizzato un pannello a forma libera.
* **Le visualizzazioni** compongono tutti i pannelli a forma libera. Lo scopo è quello di rappresentare i dati in diversi formati. La maggior parte del tempo quel formato è una tabella, ma altre volte può essere come una ciambella o un grafico a linee. Molti report in Google Analytics sono fatti dell'equivalente di due visualizzazioni: un grafico a linee e una tabella a forma libera.
* **I componenti** vengono inseriti in una visualizzazione per restituire i dati. I componenti possono essere combinati in molti modi diversi per soddisfare le esigenze di reporting.
   * **Le dimensioni** sono valori variabili e in genere contengono testo. Alcuni esempi includono il nome della pagina, il referente o il paese geografico. Sono in genere elencate come righe in una tabella.
   * **Le metriche** in genere indicano un evento o una conversione di qualche tipo. Alcuni esempi includono eventi comuni come una visualizzazione di pagina o qualcosa di più significativo come un acquisto o una registrazione. Sono generalmente viste come colonne nelle tabelle per mostrare il numero di volte in cui si è verificato l’evento per dimensione.
   * **I segmenti** sono un sottoinsieme dei dati e si comportano in modo simile ai segmenti in Google Analytics. Consentono di creare filtri personalizzati, che consentono di concentrarsi su una parte specifica dei dati.
   * **Gli intervalli** di date consentono di organizzare i dati in base al momento in cui si è verificato un evento. Sono la spina dorsale della visualizzazione delle tendenze nel tempo e sono generalmente abbinati a una metrica.

## Creare un rapporto di base in Workspace

Per creare un rapporto Tutte le pagine (simile a quello di Google Analytics), trascinate i componenti giusti su un’area di lavoro.

1. Accedete a [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali ID Adobe.
2. Fate clic sull'icona di 9 quadrati in alto a destra, quindi fate clic sul logo Analytics colorato.
3. Nella barra di navigazione superiore, fate clic su Area di lavoro.
4. Fate clic sul pulsante "Crea nuovo progetto".
5. Nella finestra a comparsa modale, assicurarsi che sia selezionato "Progetto vuoto", quindi fare clic su Crea.
6. A sinistra viene visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individuate la dimensione Pagine (arancione colorata) e trascinatela nell’area di lavoro con l’etichetta "Rilascia qui una dimensione".
7. È possibile visualizzare un rapporto che mostra le pagine principali per questo mese. Analysis Workspace compila automaticamente il rapporto con la metrica [Occorrenze](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Una tabella in Google Analytics in genere contiene 7-8 metriche. Individuate la metrica Frequenza rimbalzi (verde colorato) e trascinatela accanto all’intestazione della metrica Occorrenze. Se trascinate la metrica Frequenza rimbalzi accanto a Occorrenze, entrambe le metriche vengono visualizzate affiancate.
9. Molte metriche possono essere affiancate trascinando le metriche accanto alle intestazioni delle metriche esistenti. Per informazioni su come ottenere le metriche tipicamente utilizzate in Google Analytics, consultate [le metriche](common-metrics.md) più utilizzate.

   ![Nuova metrica](/help/technotes/ga-to-aa//assets/new_metric.png)

## Iniziare con un modello di rapporto predefinito in Workspace

Create il modello Consumo di contenuto (simile al rapporto Tutte le pagine in Google Analytics) accedendo a un modello di progetto.

1. Fate clic sul pulsante "Crea nuovo progetto".
2. Individuate e fate doppio clic sull'icona "Consumo di contenuto (Web)" elencata in Tutti i modelli.
3. Scorri tutte le visualizzazioni già create: Flusso pagina di immissione, Tabella pagine principali, Flusso pagina di uscita, Flusso sezione sito di entrata e Tabella sezioni sito principali.

   ![Selezione di modelli](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Sperimentare con lo strumento

Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci sono ripercussioni sul trascinamento indiscriminato di componenti in un progetto per vedere cosa funziona. Trascina nel progetto dell’area di lavoro diverse combinazioni di dimensioni e metriche per vedere quali sono le opzioni disponibili.

Se accidentalmente trascinate un componente non valido nel progetto dell’area di lavoro o desiderate tornare indietro di un passo, premete Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. Potete anche iniziare con una lavagna pulita facendo clic su *[!UICONTROL Project]&gt;[!UICONTROL New]* in alto a sinistra.

Adobe ha fornito numerose funzionalità in Analysis Workspace nel menu di scelta rapida. Per un’analisi e un’interazione più dettagliate, è possibile fare clic con il pulsante destro del mouse sulla maggior parte delle visualizzazioni e dei componenti. È consigliabile fare clic con il pulsante destro del mouse sui componenti nell’area di lavoro per visualizzare le opzioni disponibili.

## Informazioni sulle dimensioni e metriche da utilizzare

Se ti senti a tuo agio con Analysis Workspace e desideri ricreare un rapporto specifico generalmente visualizzato in Google Analytics, individua il rapporto nella relativa pagina:

* [Rapporti in tempo reale](realtime-reports.md)
* [Rapporti sul pubblico](audience-reports.md)
* [Rapporti sull'acquisizione](acquisition-reports.md)
* [Rapporti sul comportamento](behavior-reports.md)
* [Rapporti sulle conversioni](conversions-reports.md)
