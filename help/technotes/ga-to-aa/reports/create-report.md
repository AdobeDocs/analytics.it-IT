---
title: Creare un rapporto di base in Analysis Workspace
description: Scopri come creare un rapporto di base in Analysis Workspace in un formato adatto agli utenti che hanno familiarità con strumenti di terze parti come Google Analytics.
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 18%

---


# Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics

Analysis Workspace (una delle funzioni principali di Adobe Analytics) offre a un utente un’area solida per acquisire qualsiasi approfondimento sui dati raccolti. Reporting è molto diverso tra Google Analytics e Adobe Analytics:

* La struttura di reporting in Google Analytics consente di selezionare un particolare tipo di dati, ad esempio geolocalità o traffico di riferimento. La piattaforma utilizza una visualizzazione di reporting prefabbricata basata sul modo migliore previsto per visualizzare tali dati.
* La struttura di reporting in Analysis Workspace fornisce un quadro vuoto, fornendo maggiore flessibilità nel soddisfare esigenze di reporting esatte.

Poiché Analysis Workspace funziona più come un quadro che come rapporti prefabbricati, ricreare rapporti da Google Analytics è semplicemente una questione di utilizzare le visualizzazioni e i componenti giusti.

## Termini chiave utilizzati in Workspace

* **I pannelli** sono gli elementi costitutivi principali dell’area di lavoro. In quasi tutti gli scenari, viene utilizzato un pannello a forma libera.
* **Le visualizzazioni** compongono tutti i pannelli a forma libera. Lo scopo è quello di rappresentare i dati in diversi formati. La maggior parte del tempo quel formato è una tabella, ma altre volte può essere come una ciambella o un grafico a linee. Molti report in Google Analytics sono fatti dell&#39;equivalente di due visualizzazioni: un grafico a linee e una tabella a forma libera.
* **I componenti** vengono inseriti in una visualizzazione per restituire i dati. I componenti possono essere combinati in molti modi diversi per soddisfare le esigenze di reporting.
   * **Le dimensioni** sono valori variabili e in genere contengono testo. Alcuni esempi includono il nome della pagina, il referente o il paese geografico. Sono in genere elencate come righe in una tabella.
   * **Le metriche** in genere indicano un evento o una conversione di un certo tipo. Alcuni esempi includono eventi comuni come una visualizzazione di pagina o qualcosa di più significativo come un acquisto o una registrazione. Sono generalmente viste come colonne nelle tabelle per mostrare il numero di volte in cui si è verificato l’evento per dimensione.
   * **I segmenti** sono un sottoinsieme dei dati e si comportano in modo simile ai segmenti in Google Analytics. Consentono di creare filtri personalizzati, che consentono di concentrarsi su una parte specifica dei dati.
   * **Gli intervalli** di date consentono di organizzare i dati in base al momento in cui si è verificato un evento. Sono la spina dorsale della visualizzazione delle tendenze nel tempo e sono generalmente abbinati a una metrica.

## Creare un rapporto di base in Workspace

Per creare un rapporto Tutte le pagine (simile a quello di Google Analytics), trascinate i componenti giusti su un’area di lavoro.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Nella barra di navigazione superiore, fai clic su Workspace.
1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Nella finestra a comparsa modale, assicurati che sia selezionato “Progetto vuoto”, quindi fai clic su Crea.
1. A sinistra viene visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individuate la dimensione Pagine (arancione colorata) e trascinatela nell’area di lavoro con l’etichetta &quot;Rilascia qui una dimensione&quot;.
1. È possibile visualizzare un rapporto che mostra le pagine principali per questo mese. Analysis Workspace automatically populates the report with the [Occurrences](/help/components/metrics/occurrences.md) metric.
1. Una tabella in Google Analytics in genere contiene 7-8 metriche. Individuate la metrica Frequenza rimbalzi (verde colorato) e trascinatela accanto all’intestazione della metrica Occorrenze. Se trascinate la metrica Frequenza rimbalzi accanto a Occorrenze, entrambe le metriche vengono visualizzate affiancate.
1. Molte metriche possono essere affiancate trascinando le metriche accanto alle intestazioni delle metriche esistenti. Per informazioni su come ottenere le metriche tipicamente utilizzate in Google Analytics, consultate [le metriche](common-metrics.md) più utilizzate.

   ![Nuova metrica](/help/technotes/ga-to-aa/assets/new_metric.png)

## Iniziare con un modello di rapporto predefinito in Workspace

Create il modello Consumo di contenuto (simile al rapporto Tutte le pagine in Google Analytics) accedendo a un modello di progetto.

1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Individuate e fate doppio clic sull&#39;icona &quot;Consumo di contenuto (Web)&quot; elencata in Tutti i modelli.
1. Scorri tutte le visualizzazioni già create: Flusso pagina di immissione, Tabella pagine principali, Flusso pagina di uscita, Flusso sezione sito di entrata e Tabella sezioni sito principali.

   ![Selezione di modelli](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Esercitarsi con lo strumento

Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili.

Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su *[!UICONTROL Project] > [!UICONTROL New]*nel menu in alto a sinistra.

Adobe ha fornito numerose funzionalità in Analysis Workspace nel menu di scelta rapida. Per un’analisi e un’interazione più dettagliate, è possibile fare clic con il pulsante destro del mouse sulla maggior parte delle visualizzazioni e dei componenti. È consigliabile fare clic con il pulsante destro del mouse sui componenti nell’area di lavoro per visualizzare le opzioni disponibili.

## Scopri le dimensioni e le metriche da utilizzare

Se ti senti a tuo agio con Analysis Workspace e desideri ricreare un rapporto specifico generalmente visualizzato in Google Analytics, individua il rapporto nella relativa pagina:

* [Rapporti in tempo reale](realtime-reports.md)
* [Rapporti sul pubblico](audience-reports.md)
* [Rapporti sull&#39;acquisizione](acquisition-reports.md)
* [Rapporti sul comportamento](behavior-reports.md)
* [Rapporti sulle conversioni](conversions-reports.md)
