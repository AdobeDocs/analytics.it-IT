---
description: nulle
seo-description: nulle
seo-title: Ottimizzare le prestazioni dell'area di lavoro
title: Ottimizzare le prestazioni dell'area di lavoro
uuid: de 51 d 03 d-d 555-4 f 0 e-b 19 c -4 a 8 f 140770 fc
translation-type: tm+mt
source-git-commit: 4c400faacdc0cc405f719cb849ed02d03b0cf972

---


# Ottimizzare le prestazioni dell'area di lavoro

Alcuni fattori possono influenzare le prestazioni di un progetto in Analysis Workspace. È importante sapere cosa sono questi contributi prima di iniziare a creare un progetto, in modo da essere in grado di pianificare e creare il progetto nel modo migliore. Di seguito è riportato un elenco di fattori che influiranno sulle prestazioni e sulle tecniche consigliate per l’ottimizzazione dei tuoi progetti. Le prestazioni di Analysis Workspace rappresentano una delle principali priorità di Adobe e un aspetto che continuiamo a migliorare giorno dopo giorno.

## Complessità della logica dei segmenti

Segmenti complessi possono avere un impatto significativo sulle prestazioni del progetto. Fattori che aggiungono complessità a un segmento (in ordine decrescente dell'impatto) includono:

* Operatori di “contiene”, “contiene”, “contiene qualsiasi di”, “corrisponde”, “inizia con” o “finisce con”
* La segmentazione sequenziale avviene specialmente quando si utilizzano restrizioni delle dimensioni (entro/dopo)
* Numero di elementi di dimensione unica, compresa nelle dimensioni utilizzate nel segmento, (ad es. Pagina = “A” quando la Pagina ha 10 elementi unici sarà più veloce della Pagina = “A” quando la Pagina ha 100.000 elementi unici)
* Numero di diverse dimensioni utilizzate (ad es. Pagina = “Home” e Pagina = “Risultati della ricerca” sarà più veloce di eVar 1 = “rosso” ed eVar 2 = “blu”).
* Molti operatori OR (invece di AND)
* Contenitori nidificati di vario ambito (ad es., Hit inside of Visit inside of Visitor)

### Best practice

Mentre alcuni dei fattori di complessità non possono essere evitati, pensa alle opportunità di ridurre la complessità dei tuoi segmenti. In generale, più si può essere specifici con i propri criteri di segmento, meglio è. Ad esempio:

* Con i contenitori, l'utilizzo di un singolo contenitore nella parte superiore del segmento sarà più veloce di una serie di contenitori nidificati.
* Con operatori, «uguale» sarà più veloce di «contiene» e «uguale a qualsiasi di» sarà più veloce di «contiene qualsiasi di».
* Con molti criteri, gli operatori AND saranno più veloci di una serie di operatori OR. Inoltre, cercare opportunità per ridurre molte istruzioni OR in una singola istruzione "è uguale a qualsiasi" istruzione.

Inoltre, l’uso delle [classificazioni](/help/components/c-classifications2/c-classifications.md) può aiutare a consolidare più valori in gruppi compatti, dai quali è possibile creare dei segmenti. La segmentazione dei gruppi di classificazione offre vantaggi in termini di prestazioni, in particolare per i segmenti che contengono numerose istruzioni OR o criteri “contiene”.

## Intervallo dei dati richiesti

L’intervallo dei dati richiesti nell’ambito di un progetto influenzerà le prestazioni di Analysis Workspace.

### Best practice

Dove possibile, non inserire più dati del necessario.

Ricorda che gli intervalli di date (componenti viola) ignorano l’intervallo date del pannello. Come risultato, se stai utilizzando diversi intervalli di date come colonne (ad es. colonne ultimo mese, ultima settimana e ieri), il pannello intervallo date non deve estendere tutti gli intervalli date delle colonne. Può essere impostato semplicemente su domani, in quanto gli intervalli di date utilizzati nella tabella a forma libera ignoreranno il pannello. Per ulteriori informazioni sulle attività con gli intervalli di date in Analysis Workspace, guarda [questo video](https://www.youtube.com/watch?v=ybmv6EBmhn0) .

Use [date comparison options](../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764) to pull in the specific time periods of data you want to compare. Ad esempio, se vuoi visualizzare i dati del mese scorso rispetto ai dati dello stesso mese dello scorso anno, invece di impostare il pannello sugli ultimi 13 mesi di dati, puoi semplicemente utilizzare l’opzione di confronto di periodi di tempo per mostrare le prestazioni anno-su-anno.

## Numero di visualizzazioni

Il numero di visualizzazioni di grafico contenute in un progetto influenzeranno la responsività complessiva di Analysis Workspace.

### Best practice

Diminuisci il numero di visualizzazioni nel tuo progetto. Analysis Workspace effettua un gran numero di elaborazioni in background per ogni visualizzazione che aggiungi; pertanto dai priorità alle visualizzazioni più importanti per l’utilizzatore del rapporto e, se necessario, suddividi le visualizzazioni di supporto in progetti separati e più dettagliati.

## Complessità delle visualizzazioni (segmenti, metriche, filtri)

Il tipo di visualizzazione (ad es. abbandono rispetto a una tabella a forma libera) aggiunta a un progetto di per sé non influenza molto le prestazioni del progetto. È la complessità della visualizzazione che influenzerà il tempo di elaborazione. Fattori che aggiungono complessità a una visualizzazione includono:

* Intervallo dei dati richiesti, così come riportato sopra
* Numero di segmenti applicati; ovvero segmenti utilizzati come righe di una tabella a forma libera
* Utilizzo di segmenti complessi
* Righe o colonne statiche di elementi in tabelle a forma libera
* Filtri applicati a righe in tabelle a forma libera
* Numero di metriche incluse, in particolare metriche calcolate che utilizzano segmenti

### Best practice

Se noti che i tuoi progetti non si caricano rapidamente tanto quanto vorresti, prova a sostituire alcuni segmenti con eVar e filtri, ove possibile.

Se utilizzi costantemente segmenti e metriche calcolate per punti dati importanti per la tua azienda, puoi prendere in considerazione il miglioramento della tua implementazione per acquisire questi punti dati in modo più diretto. L'utilizzo di un gestore tag come Adobe Experience Platform Launch e le regole di elaborazione di Adobe può rendere le modifiche di implementazione veloci e facili da implementare. Per capire meglio come semplificare i segmenti più complessi, vedi “Complessità della logica dei segmenti” sopra.

## Numero di pannelli

Un pannello può contenere diverse visualizzazioni e, come risultato, il numero di pannelli può influire anche sulla responsività globale di Analysis Workspace.

### Best practice

Non cercare di aggiungere tutti gli elementi a un progetto; piuttosto crea progetti diversi per uno scopo preciso o per un determinato gruppo di soggetti interessati. Utilizza i tag per organizzare i progetti in temi chiave e condividi i progetti correlati con i soggetti interessati.

Se desideri progetti più organizzati, ricorda che il [collegamento diretto](https://www.youtube.com/watch?v=6IOEewflG2U) al tuo prodotto potrebbe rappresentare una possibilità. Crea un indice interno di progetti in modo che i soggetti interessati possano trovare più facilmente ciò di cui hanno bisogno. Inoltre, Adobe sta lavorando per integrare ulteriori opzioni per l’organizzazione in Analysis Workspace.

Se sono necessari più pannelli in Workspace, comprimili prima di salvare e condividere. Al caricamento di un progetto, Analysis Workspace caricherà solo i contenuti dei pannelli espansi. I pannelli compressi vengono caricati solo se l’utente li espande. Questo approccio è utile in due modi:

* I pannelli compressi consentono di ridurre il tempo di caricamento complessivo di un progetto
* I pannelli compressi sono molto utili per organizzare i progetti in modo logico per l’utente del rapporto

## Dimensione della suite di rapporti

La dimensione della suite di rapporti può sembrare un fattore fondamentale, ma in realtà riveste un’importanza limitata per via del modo in cui Adobe gestisce l’elaborazione dati

## Diverse persone accedono simultaneamente ad Analysis Workspace

Il numero di persone che accede contemporaneamente ad Analysis Workspace o a progetti specifici non ha un effetto notevole sulle prestazioni di Analysis Workspace.