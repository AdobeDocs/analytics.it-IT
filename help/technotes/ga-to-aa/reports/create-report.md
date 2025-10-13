---
title: Creare un rapporto di base in Analysis Workspace
description: Scopri come creare un rapporto di base in Analysis Workspace in un formato rivolto agli utenti che hanno familiarità con strumenti di terze parti come Google Analytics.
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 18%

---

# Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics

Analysis Workspace (una delle funzioni principali di Adobe Analytics) fornisce un’area solida per consentire agli utenti di ottenere qualsiasi insight sui dati raccolti. Il reporting è molto diverso tra Google Analytics e Adobe Analytics:

* La struttura di reporting in Google Analytics consente di selezionare un particolare tipo di dati, ad esempio geolocalizzazione o traffico di riferimento. La piattaforma utilizza una visualizzazione di reporting prefabbricata basata sul modo migliore per visualizzare tali dati.
* La struttura di reporting in Analysis Workspace fornisce un’area di lavoro vuota, fornendo maggiore flessibilità nel soddisfare le esigenze di reporting esatte.

Poiché Analysis Workspace funziona più come un’area di lavoro che come rapporti prefabbricati, ricreare rapporti da Google Analytics consiste semplicemente nell’utilizzare le visualizzazioni e i componenti giusti.

## Termini chiave utilizzati in Workspace

* **I pannelli** sono i blocchi predefiniti principali dell&#39;area di lavoro. In quasi tutti gli scenari viene utilizzato un pannello a forma libera.
* **Le visualizzazioni** costituiscono tutti i pannelli a forma libera. Il loro scopo è quello di rappresentare i dati in diversi formati. Nella maggior parte dei casi il formato è una tabella, ma altre volte può essere simile a un grafico ad anello o a linee. In Google Analytics molti rapporti equivalgono a due visualizzazioni: un grafico a linee e una tabella a forma libera.
* **I componenti** sono inseriti in una visualizzazione per restituire dati. I componenti possono essere combinati in molti modi diversi per soddisfare le esigenze di reporting.
   * **Le dimensioni** sono valori di variabile e in genere contengono testo. Alcuni esempi includono il nome della pagina, il referrer o il paese geografico. Nella maggior parte dei casi sono elencate come righe in una tabella.
   * **Le metriche** in genere indicano un evento o una conversione di qualche tipo. Alcuni esempi includono eventi comuni come la visualizzazione di una pagina o altri eventi più significativi come un acquisto o una registrazione. Nella maggior parte dei casi sono visualizzate come colonne nelle tabelle per mostrare il numero di volte in cui si è verificato un evento per dimensione.
   * **I segmenti** sono un sottoinsieme dei tuoi dati e si comportano in modo simile ai segmenti in Google Analytics. Consentono di creare filtri personalizzati, che consentono di concentrarsi su una parte specifica dei dati.
   * **Intervalli di date** consente di organizzare i dati in base a quando si è verificato un evento. Sono la spina dorsale delle tendenze di visualizzazione nel tempo e sono in genere associati a una metrica.

## Creare un rapporto di base in Workspace

Crea un rapporto Tutte le pagine (simile a quello di Google Analytics) trascinando i componenti giusti nell’area di lavoro.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Nella barra di navigazione superiore, fai clic su Workspace.
1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Nella finestra a comparsa modale, assicurati che sia selezionato “Progetto vuoto”, quindi fai clic su Crea.
1. A sinistra viene visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Pages (Pagine) (di colore arancione) e trascinala sull’area di lavoro con l’etichetta &quot;Drop a Dimension Here&quot; (Rilascia qui un).
1. È possibile visualizzare un report che mostra le pagine principali di questo mese. Analysis Workspace compila automaticamente il report con la metrica [Occorrenze](/help/components/metrics/occurrences.md).
1. Una tabella in Google Analytics contiene in genere 7-8 metriche. Individua la metrica Percentuale non recapitate (di colore verde) e trascinala accanto all’intestazione della metrica Occorrenze. Se trascini la metrica Percentuale non recapitate accanto a Occorrenze, entrambe le metriche vengono visualizzate una accanto all’altra.
1. Molte metriche possono essere posizionate una accanto all’altra trascinando le metriche accanto alle intestazioni di metrica esistenti. Per informazioni su come ottenere le metriche normalmente utilizzate in Google Analytics, consulta [metriche di uso comune](common-metrics.md).

   ![Nuova metrica](/help/technotes/ga-to-aa/assets/new_metric.png)

## Iniziare con un modello di rapporto predefinito in Workspace

Crea il modello per consumo di contenuti (simile al rapporto Tutte le pagine in Google Analytics) accedendo a un modello di progetto.

1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Individua e fai doppio clic sull&#39;icona &quot;Consumo di contenuti (Web)&quot; elencata in Tutti i modelli.
1. Sfoglia ciascuna delle visualizzazioni predefinite: Flusso pagina di ingresso, Tabella pagine principali, Flusso pagina di uscita, Flusso sezione sito di ingresso e Tabella sezioni sito principale.

   ![Selezione modello](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Esercitarsi con lo strumento

Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili.

Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl + Z (Windows) o Comando + Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su *[!UICONTROL Project] > [!UICONTROL New]* nel menu in alto a sinistra.

Adobe ha inserito molte funzionalità in Analysis Workspace nel menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse. Puoi fare clic con il pulsante destro del mouse sulla maggior parte delle visualizzazioni e dei componenti per eseguire analisi e interazioni più dettagliate. Per visualizzare le opzioni disponibili, fai clic con il pulsante destro del mouse sui componenti nell’area di lavoro.

## Dimensioni e metriche da utilizzare

Se hai familiarità con Analysis Workspace e desideri ricreare un rapporto specifico generalmente visualizzato in Google Analytics, individua il rapporto nella rispettiva pagina:

* [Rapporti in tempo reale](realtime-reports.md)
* [Rapporti sul pubblico](audience-reports.md)
* [Rapporti di acquisizione](acquisition-reports.md)
* [Rapporti sul comportamento](behavior-reports.md)
* [Rapporti sulle conversioni](conversions-reports.md)
