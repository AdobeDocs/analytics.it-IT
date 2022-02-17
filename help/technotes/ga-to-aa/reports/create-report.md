---
title: Creare un rapporto di base in Analysis Workspace
description: Scopri come creare un rapporto di base in Analysis Workspace in un formato rivolto agli utenti che conoscono strumenti di terze parti come Google Analytics.
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 18%

---

# Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics

Analysis Workspace (una delle funzionalità principali di Adobe Analytics) fornisce un’area solida per consentire all’utente di ottenere informazioni sui dati raccolti. Il reporting è molto diverso tra Google Analytics e Adobe Analytics:

* La struttura di reporting in Google Analytics consente di selezionare un particolare tipo di dati, ad esempio la posizione geografica o il traffico di riferimento. La piattaforma utilizza una visualizzazione di reporting prefabbricata basata sul modo migliore previsto per visualizzare tali dati.
* La struttura di reporting in Analysis Workspace fornisce un’area di lavoro vuota, offrendo maggiore flessibilità per soddisfare esigenze di reporting esatte.

Poiché Analysis Workspace funziona più come un’area di lavoro che come un rapporto prefabbricato, ricreare i rapporti dalle Google Analytics è semplicemente questione di utilizzare le visualizzazioni e i componenti giusti.

## Termini chiave utilizzati in Workspace

* **Pannelli** sono gli elementi costitutivi principali di workspace. In quasi tutti gli scenari, viene utilizzato un pannello a forma libera.
* **Visualizzazioni** crea tutti i pannelli a forma libera. Lo scopo è quello di rappresentare i dati in formati diversi. La maggior parte del tempo quel formato è una tabella, ma altre volte può essere come un diagramma ad anello o a linee. Molti rapporti nelle Google Analytics sono composti dall’equivalente di due visualizzazioni: un grafico a linee e una tabella a forma libera.
* **Componenti** vengono inseriti in una visualizzazione per restituire i dati. I componenti possono essere combinati in diversi modi per soddisfare le esigenze di reporting.
   * **Dimension** sono valori variabili e in genere contengono testo. Gli esempi includono il nome della pagina, il referente o il paese geografico. Sono più comunemente elencate come righe in una tabella.
   * **Metriche** in genere indica un evento o una conversione di un qualche tipo. Gli esempi includono eventi comuni come la visualizzazione di una pagina o qualcosa di più significativo come un acquisto o una registrazione. Vengono generalmente visualizzate come colonne nelle tabelle per mostrare il numero di volte in cui si è verificato l’evento per dimensione.
   * **Segmenti** sono un sottoinsieme di dati e si comportano in modo simile ai segmenti nelle Google Analytics. Consentono di creare filtri personalizzati, che consentono di concentrarsi su una parte specifica dei dati.
   * **Intervalli di date** consente di organizzare i dati in base al momento in cui si è verificato un evento. Sono la spina dorsale della visualizzazione delle tendenze nel tempo e sono tipicamente abbinati a una metrica.

## Creare un rapporto di base in Workspace

Crea un rapporto Tutte le pagine (simile a quello in Google Analytics) trascinando i componenti giusti nell’area di lavoro.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Nella barra di navigazione superiore, fai clic su Workspace.
1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Nella finestra a comparsa modale, assicurati che sia selezionato “Progetto vuoto”, quindi fai clic su Crea.
1. A sinistra viene visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Pagine (di colore arancione) e trascinala nell’area di lavoro denominata &quot;Rilascia qui un Dimension&quot;.
1. È possibile visualizzare un rapporto che mostra le pagine principali per questo mese. Analysis Workspace compila automaticamente il rapporto con [Occorrenze](/help/components/metrics/occurrences.md) metrica.
1. In genere, una tabella in Google Analytics contiene 7-8 metriche. Individua la metrica Frequenza di rimbalzo (di colore verde) e trascinala accanto all’intestazione della metrica Occorrenze. Se trascini la metrica Frequenza di rimbalzo accanto a Occorrenze, entrambe le metriche vengono visualizzate una accanto all’altra.
1. Puoi posizionare molte metriche una accanto all’altra trascinando le metriche accanto alle intestazioni di metrica esistenti. Vedi [metriche comunemente utilizzate](common-metrics.md) per informazioni su come ottenere le metriche generalmente utilizzate in Google Analytics.

   ![Nuova metrica](/help/technotes/ga-to-aa/assets/new_metric.png)

## Inizia con un modello di rapporto predefinito in Workspace

Crea il modello Consumo di contenuto (simile al rapporto Tutte le pagine nelle Google Analytics) accedendo a un modello di progetto.

1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Individua e fai doppio clic sull’icona &quot;Consumo di contenuto (Web)&quot; elencata in Tutti i modelli.
1. Sfoglia ciascuna delle visualizzazioni predefinite: Flusso della pagina di ingresso, tabella delle pagine principali, flusso della pagina di uscita, flusso della sezione del sito di ingresso e tabella delle sezioni principali del sito.

   ![Selezione di modelli](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Esercitarsi con lo strumento

Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili.

Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl + Z (Windows) o Comando + Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su *[!UICONTROL Project] > [!UICONTROL New]* nel menu in alto a sinistra.

Adobe ha implementato numerose funzionalità in Analysis Workspace nel menu di scelta rapida. Per eseguire analisi e interazioni più dettagliate, fai clic con il pulsante destro del mouse sulla maggior parte delle visualizzazioni e dei componenti. Per visualizzare le opzioni disponibili, prendi in considerazione la possibilità di fare clic con il pulsante destro del mouse sui componenti nell’area di lavoro.

## Comprendere le dimensioni e le metriche da utilizzare

Se hai familiarità con Analysis Workspace e desideri ricreare un rapporto specifico generalmente visualizzato in Google Analytics, individua il rapporto nella relativa pagina:

* [Rapporti in tempo reale](realtime-reports.md)
* [Rapporti sul pubblico](audience-reports.md)
* [Rapporti di acquisizione](acquisition-reports.md)
* [Rapporti sul comportamento](behavior-reports.md)
* [Rapporti sulle conversioni](conversions-reports.md)
