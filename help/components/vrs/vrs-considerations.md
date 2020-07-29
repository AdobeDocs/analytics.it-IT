---
description: Le suite di rapporti virtuali e i tag con più suite presentano vantaggi diversi. Scoprite quale è la soluzione migliore per la vostra organizzazione.
keywords: Virtual Report Suite,VRS
title: Suite di rapporti virtuali e considerazioni sui tag con più suite
topic: Adobe Analytics
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '1735'
ht-degree: 0%

---


# Suite di rapporti virtuali e considerazioni sui tag con più suite

Suite di rapporti virtuali (VRS) consente di visualizzare i dati di una suite di rapporti che raccoglie dati dalle proprietà digitali, ma con un segmento applicato in modo permanente.

In molti casi, potete utilizzare suite di rapporti virtuali per sostituire i tag per più suite. Il passaggio alle suite di rapporti virtuali consente di eliminare efficacemente la necessità di effettuare chiamate [server](/help/admin/c-server-call-usage/overage-overview.md)secondarie. Ad esempio, la tua organizzazione dispone di 6 siti Web diversi, ciascuno dei quali invia dati alla propria suite di rapporti, nonché di una suite di rapporti globale combinata. Ogni sito esegue una chiamata server secondaria; una nella suite di rapporti per il singolo marchio e una seconda nella suite di rapporti globale. Puoi invece inviare dati da tutti i siti esclusivamente alla suite di rapporti globale, quindi utilizzare più suite di rapporti virtuali per separare ciascun marchio.

La sostituzione dei tag con più suite con una suite di rapporti globale e una VRS consente di semplificare l&#39;implementazione Adobe Analytics  e di ridurre il consumo delle chiamate server, ed è consigliato come procedura ottimale. Tuttavia, esistono alcune importanti limitazioni della VRS da considerare. Le seguenti linee guida possono aiutarti a decidere se implementare le suite di rapporti virtuali basate su una suite di rapporti globale sia l&#39;approccio giusto per te.

## Linee guida

Se non siete sicuri se i casi di utilizzo descritti si applicano a voi e alla vostra organizzazione, rivolgetevi agli altri amministratori  Adobe Analytics o al vostro account manager  Adobe. Possono aiutare a valutare le esigenze aziendali e a formulare una raccomandazione.

Quando decidi se devi usare tag per più suite o suite di rapporti virtuali, tieni presente le considerazioni seguenti:

### Pubblicazione di segmenti sull’Adobe Experience Cloud

La condivisione di segmenti su Adobe Experience Cloud non è supportata per le suite di rapporti virtuali. Gli utenti che desiderano condividere un segmento con il Experience Cloud  devono avere accesso alla suite di rapporti di origine.

I segmenti non possono ancora essere pubblicati su Adobe Experience Cloud da una suite di rapporti virtuale per la personalizzazione e il targeting. A tal fine, tutti gli utenti che pubblicano segmenti devono poter accedere alla suite di rapporti di origine. Ad esempio, vuoi che gli utenti abbiano accesso solo ai dati per le loro aree geografiche, ma vuoi che siano in grado di creare e condividere segmenti da  Adobe Analytics ad Adobe Experience Cloud per il targeting in  Adobe Target. In questo caso,  Adobe consiglia di utilizzare i tag per più suite. Se non ti dispiace se gli utenti hanno accesso alla suite di rapporti globale o se non hai bisogno di pubblicare segmenti da utilizzare in altre soluzioni, puoi utilizzare suite di rapporti virtuali.

### Dati in tempo reale e correnti

I rapporti in tempo reale non sono supportati nelle suite di rapporti virtuali, perché i dati sono segmentati. I dati correnti non sono supportati anche nelle suite di rapporti virtuali, in quanto non supportano la segmentazione. Entrambe queste funzioni sono specifiche di Reporting e  Analytics.

[I rapporti](/help/admin/admin/realtime/t-realtime-admin.md) in tempo reale e i dati [](/help/technotes/latency.md) correnti non sono disponibili nelle suite di rapporti virtuali. Questo interessa gli utenti che rispondono alle tendenze visualizzate in Reporting e  Analytics in pochi secondi o pochi minuti di raccolta dei dati. Ad esempio, questo può includere editori in una newsroom che regolano i titoli in base al consumo di contenuti in tempo reale. Considera l’utilizzo di tag con più suite se hai importanti esigenze di dati in tempo reale specifiche per le singole suite di rapporti. I dati in tempo reale e quelli correnti possono essere utilizzati nella suite di rapporti globale.

### Limiti univoci

Se disponete di una suite di rapporti globale che combina un numero elevato di siti, è possibile che vi troviate spesso nell&#39;elemento di linea a [basso traffico](/help/technotes/low-traffic.md) . Se utilizzate i tag per più suite, questo è solo un problema per la suite di rapporti globale (le singole suite di rapporti avranno meno probabilità di vedere traffico basso). Se utilizzate suite di rapporti virtuali, vengono condivisi limiti univoci, causando la visualizzazione di singole suite di rapporti anche a traffico limitato. Considerate l&#39;utilizzo di tag con più suite se desiderate evitare il bucketing dei dati con traffico limitato.

Ad esempio, un&#39;organizzazione di grandi dimensioni possiede 100 proprietà Web. Ogni proprietà pubblica qualche migliaio di articoli al mese, oltre a ospitare tutti gli articoli dei mesi precedenti. Questa organizzazione utilizza una suite di rapporti globale in cui  eVar 1 è &#39;Nome articolo&#39;. In questo rapporto, ci sono circa 4 milioni di nomi di articolo unici ogni mese dalle varie proprietà combinate. Se si utilizza una suite di rapporti virtuale, i primi 500.000 valori che costituiscono la maggior parte del traffico sono inclusi nelle suite di rapporti virtuali; gli altri 3,5 milioni sono inclusi nel traffico limitato. Se si utilizza l’assegnazione di tag a più suite, ogni singola suite di rapporti può visualizzare i propri primi 500 k valori. I limiti univoci della suite di rapporti globali sono gli stessi tra l&#39;utilizzo di tag con più suite e le suite di rapporti virtuali.

&#39;Assistenza clienti di Adobe può aumentare i limiti di valore univoci per un numero limitato di dimensioni, il che può eliminare completamente questo problema. Per ulteriori informazioni, consulta il team di assistenza clienti e l’assistenza clienti.

### Variabili condivise tra le suite di rapporti

Le suite di rapporti virtuali non dispongono di un proprio set di dimensioni e metriche; ereditano questi dalla suite di rapporti di origine. La suite di rapporti globale deve acquisire tutte le dimensioni e le metriche per tutti i siti Web. Le suite di rapporti dispongono attualmente di un massimo di 250 eVar e 1000 eventi personalizzati.

Diversi siti presentano diverse esigenze di implementazione. Alcune dimensioni ed eventi possono essere condivisi tra due siti. Ad esempio, una registrazione tramite e-mail può utilizzare lo stesso evento su più siti Web, attivando lo stesso evento personalizzato. Altre dimensioni possono essere specifiche per un sito. Ad esempio, solo uno dei vostri siti può modificare la propria immagine del profilo. Questo evento personalizzato verrebbe implementato solo sul sito Web che lo supporta.

Assicurati che il numero di dimensioni e metriche univoche possa essere incluso in una singola suite di rapporti globale. Se riscontri che sono presenti troppe dimensioni o metriche univoche, controlla ogni dimensione all’interno di ogni implementazione. È probabile che vi siano sovrapposizioni e dimensioni che non sono fondamentali per il successo aziendale. Valutare anche l&#39;utilizzo [delle classificazioni](/help/components/classifications/c-classifications.md) . Ad esempio, invece di acquisire &#39;Product Name&#39; in  eVar 5, create una classificazione &#39;Product Name&#39; basata sulla dimensione &#39;Product&#39;. Le classificazioni in una suite di rapporti sorgente sono automaticamente disponibili per qualsiasi suite di rapporti virtuale dipendente.

>[!TIP]
>
>Con l&#39;introduzione della [cura](/help/analyze/analysis-workspace/curate-share/curate.md), puoi cambiare il nome di una determinata dimensione o metrica in base a ogni VRS.

### Sfumature di segmentazione

Una suite di rapporti virtuale a livello fondamentale è semplicemente un segmento applicato a una suite di rapporti. Le dimensioni basate su visite e visitatori possono fornire risultati di reporting non intuitivi.

Ad esempio, avete due siti Web, A e B, entrambi che inviano dati a una suite di rapporti globale. Alcuni visitatori passano inevitabilmente dal sito A al sito B, e questo movimento dall&#39;uno all&#39;altro è visibile nei percorsi nella suite di rapporti globale. Se si creano suite di rapporti virtuali per i siti A e B, una visita iniziata sul sito A e terminata sul sito B non mostrerebbe una pagina di voci nella VRS B. La pagina iniziale di questa visita è iniziata nel sito A, segmentato fuori dalla suite di rapporti virtuali.

### Conversione valuta

Le suite di rapporti virtuali non eseguono il report in una valuta diversa rispetto alla suite di rapporti su cui si basano.  Adobe Analytics consente di convertire la valuta durante l&#39;esecuzione dei report, ma il tasso di cambio è basato sul giorno corrente (anche per i dati storici).

Se l&#39;organizzazione esegue la propria analisi in una moneta unica, ciò non crea problemi. Tuttavia, se si ha un&#39;esigenza aziendale significativa per diversi team regionali che devono visualizzare le entrate nella propria valuta locale, è consigliabile utilizzare i tag per più suite.

### Feed di dati

I feed di dati non possono utilizzare suite di rapporti virtuali. Tuttavia, puoi ricevere un feed di dati da una suite di rapporti globale e quindi separarlo.

I feed di dati consentono di ricevere un’esportazione giornaliera o oraria di tutti i dati Adobe Analytics  a un singolo livello hit. I feed di dati non possono essere pre-segmentati prima che vengano inviati all&#39;utente, pertanto puoi ricevere solo un feed di dati per la suite di rapporti globale. Se l’organizzazione ha una forte necessità di feed di dati singoli a un marchio, una proprietà, un’area o un altro livello granulare, è consigliabile utilizzare i tag per più suite.

### Connettori dati con account partner

Alcune integrazioni  partner di Adobe in  Adobe Analytics sono limitate a un account partner per suite di rapporti. Alcune organizzazioni potrebbero richiedere più account partner per la stessa integrazione.

Ad esempio, è consentito un solo Google DCM per suite di rapporti. Molte aziende dispongono di account DCM multipli, che consentono a marchi, unità aziendali e aree geografiche differenti di gestire i loro annunci display separatamente l&#39;uno dall&#39;altro. Le integrazioni non possono essere configurate nelle suite di rapporti virtuali. Se disponete di connettori dati dipendenti con più account, provate a utilizzare i tag per più suite.

### Riepilogo origini dati

Le origini dati di riepilogo consentono di importare metriche aggregate in  Adobe Analytics a livello di suite per report. Poiché i caricamenti delle origini dati di riepilogo contengono metriche aggregate, non possono essere segmentati. Poiché la VRS funziona utilizzando la segmentazione, tutti i dati importati utilizzando origini dati di riepilogo non sono disponibili nelle suite di rapporti virtuali. Le origini dati di riepilogo sono visibili solo nella suite di rapporti di origine.

>[!TIP]
>
>Le origini dati di elaborazione completa supportano la segmentazione e possono essere utilizzate nelle suite di rapporti virtuali.

## Passaggi da seguire se si decide di utilizzare la VRS

Se si sceglie di rimuovere le chiamate server secondarie a favore delle suite di rapporti virtuali:

1. Crea suite di rapporti virtuali per far corrispondere i dati nelle suite di rapporti figlio. Segmento su una dimensione personalizzata che distingue i siti tra loro.
   * Se effettui la migrazione da un&#39;implementazione con tag multi-suite esistente, confronta i segmenti della suite di rapporti virtuale con le suite di rapporti figlio esistenti. Prima di spostare gli utenti nella suite di rapporti virtuali, è necessario assicurarsi che i dati siano confrontabili.
   * Come procedura ottimale, prendete in considerazione l&#39;utilizzo dell&#39;impilamento [dei](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) segmenti in modo da poter modificare un segmento in un&#39;unica posizione e applicarlo a tutte le suite di rapporti virtuali dipendenti.
   * Utilizzate i contenitori hit per mantenere le suite di rapporti virtuali più esclusive tra loro.
2. Dopo aver confermato che le suite di rapporti virtuali sono configurate correttamente, rimuovi gli ID suite di rapporti secondari dall&#39;implementazione. Per rimuovere delle suite di rapporti secondarie:
   * In  Adobe Experience Platform Launch, fai clic sulla &quot;x&quot; accanto alle suite di rapporti che non vuoi più utilizzare.
   * In Gestione dinamica dei tag, individua la proprietà e  strumento Analytics. Nei campi ID account produzione e ID account di gestione temporanea, rimuovete gli ID suite di rapporti che non desiderate più utilizzare.
   * Nelle implementazioni JavaScript precedenti, individua la `s.account` variabile e rimuovi gli ID suite di rapporti che non desideri più utilizzare.
   * In tutti i casi, lasciare solo l&#39;ID suite di rapporti globale/principale per raccogliere i dati per i siti e le app.
   * Passa ad Admin (Amministratore) > Report Suites (Suite di rapporti) e nascondi eventuali suite di rapporti secondarie non più utilizzate.
