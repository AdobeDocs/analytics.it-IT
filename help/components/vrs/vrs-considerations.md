---
description: Le suite di rapporti virtuali e l’assegnazione di tag a più suite hanno vantaggi diversi. Scopri quale è meglio per la tua organizzazione.
keywords: Suite di rapporti virtuale,VRS
title: Suite di rapporti virtuali e considerazioni sull’assegnazione di tag a più suite
feature: Impostazioni di Suite di rapporti
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: 1cd14244b81fbf8d1e4c6f0642f181fd4b60705d
workflow-type: tm+mt
source-wordcount: '1750'
ht-degree: 0%

---

# Suite di rapporti virtuali e considerazioni sull’assegnazione di tag a più suite

Le suite di rapporti virtuali (VRS, Virtual Report Suite) consentono di visualizzare i dati di una suite di rapporti che raccoglie dati dalle proprietà digitali, ma con un segmento applicato in modo permanente.

In molti casi, puoi utilizzare suite di rapporti virtuali per sostituire l’assegnazione tag a più suite. Il passaggio alle suite di rapporti virtuali può rimuovere efficacemente la necessità di [chiamate server secondarie](/help/admin/c-server-call-usage/overage-overview.md). Ad esempio, la tua organizzazione dispone di 6 siti web diversi, ognuno dei quali invia dati alla propria suite di rapporti e a una suite di rapporti globale combinata. Ogni sito effettua una chiamata server secondaria; una alla singola suite di rapporti del marchio e una seconda alla suite di rapporti globale. Puoi invece inviare dati da tutti i siti esclusivamente alla suite di rapporti globale, quindi utilizzare più suite di rapporti virtuali per separare ogni marchio.

La sostituzione dell’assegnazione tag a più suite con una suite di rapporti globale e una VRS consente di semplificare l’implementazione di Adobe Analytics e di ridurre il consumo di chiamate al server, ed è consigliata come best practice. Tuttavia, esistono alcune limitazioni importanti della VRS da considerare. Le seguenti linee guida possono aiutarti a decidere se implementare suite di rapporti virtuali create su una suite di rapporti globale è l’approccio giusto per te.

## Linee guida

Se non sei sicuro se i casi d’uso descritti sono applicabili a te e alla tua organizzazione, consulta gli altri amministratori di Adobe Analytics o il tuo account manager di Adobe. Possono aiutare a valutare le tue esigenze aziendali e a formulare un consiglio.

Quando stabilisci se devi utilizzare tag per più suite o suite di rapporti virtuali, prendi in considerazione le seguenti considerazioni:

### Pubblicazione di segmenti in Adobe Experience Cloud

La condivisione di segmenti in Adobe Experience Cloud non è supportata per le suite di rapporti virtuali. Gli utenti che desiderano condividere un segmento nell’Experience Cloud devono avere accesso alla suite di rapporti sorgente.

I segmenti non possono ancora essere pubblicati in Adobe Experience Cloud da una suite di rapporti virtuale per la personalizzazione e il targeting. A tal fine, tutti gli utenti che pubblicano segmenti devono avere accesso alla suite di rapporti sorgente. Ad esempio, vuoi che gli utenti abbiano accesso solo ai dati per le loro aree geografiche, ma vuoi che siano in grado di creare e condividere segmenti da Adobe Analytics a Adobe Experience Cloud per il targeting in Adobe Target. In questo caso, Adobe consiglia di utilizzare l’assegnazione tag a più suite. Se non ti dispiace se gli utenti hanno accesso alla suite di rapporti globale o se non hai bisogno di pubblicare segmenti da utilizzare in altre soluzioni, puoi utilizzare le suite di rapporti virtuali.

### Dati in tempo reale e correnti

I rapporti in tempo reale non sono supportati nelle suite di rapporti virtuali, perché i dati sono segmentati. I dati correnti non sono supportati anche nelle suite di rapporti virtuali, in quanto non supportano la segmentazione. Entrambe queste funzioni sono specifiche di Reports &amp; Analytics.

[I ](/help/admin/admin/realtime/t-realtime-admin.md) rapporti in tempo reale e i  [dati ](/help/technotes/latency.md) correnti non sono disponibili nelle suite di rapporti virtuali. Questo influisce sugli utenti che rispondono alle tendenze osservate in Reports &amp; Analytics in pochi secondi o minuti dalla raccolta dei dati. Ad esempio, potrebbe includere gli editori in una newsroom che modificano i titoli in base al consumo di contenuti in tempo reale. Prendi in considerazione l’utilizzo di tag per più suite se hai esigenze di dati in tempo reale significative e specifiche per le singole suite di rapporti. I dati in tempo reale e correnti possono ancora essere utilizzati nella suite di rapporti globale.

### Limiti univoci

Se disponi di una suite di rapporti globale che combina un numero elevato di siti, è possibile che venga eseguito frequentemente nell&#39;elemento di riga [traffico ridotto](/help/technotes/low-traffic.md). Se utilizzi l’assegnazione tag a più suite, si tratta solo di un problema per la suite di rapporti globale (le singole suite di rapporti potrebbero avere meno probabilità di visualizzare traffico ridotto). Se utilizzi suite di rapporti virtuali, vengono condivisi limiti univoci, causando la visualizzazione di traffico limitato anche nelle singole suite di rapporti. Prendi in considerazione l’utilizzo di tag per più suite se desideri evitare il bucketing dei dati in traffico ridotto.

Ad esempio, una grande organizzazione multimediale possiede 100 proprietà web. Ogni proprietà pubblica qualche migliaio di articoli al mese, oltre ad ospitare tutti gli articoli dei mesi precedenti. Questa organizzazione utilizza una suite di rapporti globale in cui eVar1 è &quot;Nome articolo&quot;. In questo rapporto, ci sono circa 4 milioni di nomi di articolo unici ogni mese dalle varie proprietà combinate. Se utilizzi una suite di rapporti virtuale, i primi 500.000 valori che costituiscono la maggior parte del traffico sono inclusi nelle suite di rapporti virtuali; i restanti 3,5 milioni sono inclusi nella categoria traffico limitato. Se utilizzi l’assegnazione tag a più suite, ogni singola suite di rapporti può visualizzare i propri valori principali di 500.000. I limiti univoci della suite di rapporti globali sono gli stessi tra l’utilizzo di tag con più suite e le suite di rapporti virtuali.

L’Assistenza clienti Adobe può aumentare i limiti di valore univoci per un numero limitato di dimensioni, il che può eliminare completamente questo problema. Per ulteriori informazioni, consulta il team del tuo account e l’Assistenza clienti .

### Variabili condivise tra le suite di rapporti

Le suite di rapporti virtuali non dispongono di un proprio set di dimensioni e metriche; ereditano dalla suite di rapporti sorgente. La suite di rapporti globale deve acquisire tutte le dimensioni e metriche per tutti i siti web. Le suite di rapporti dispongono attualmente di un massimo di 250 eVar e 1000 eventi personalizzati.

Un sito diverso ha esigenze di implementazione diverse. Alcune dimensioni ed eventi possono essere condivisi tra due siti. Ad esempio, una registrazione e-mail può utilizzare lo stesso evento su più siti web, attivando lo stesso evento personalizzato. Altre dimensioni possono essere specifiche per un sito. Ad esempio, solo uno dei tuoi siti può modificare la propria immagine del profilo. Questo evento personalizzato verrebbe implementato solo sul sito web che lo supporta.

Assicurati che il numero di dimensioni e metriche univoche possa essere incluso in una singola suite di rapporti globale. Se trovi troppe dimensioni o metriche univoche, controlla ogni dimensione all’interno di ogni implementazione. È probabile che vi siano sovrapposizioni e dimensioni che non sono fondamentali per il successo aziendale. Considera anche l&#39;utilizzo di [classificazioni](/help/components/classifications/c-classifications.md). Ad esempio, invece di acquisire &quot;Product Name&quot; in eVar5, crea una classificazione &quot;Product Name&quot; basata sulla dimensione &quot;Product&quot;. Le classificazioni in una suite di rapporti sorgente sono automaticamente disponibili per tutte le suite di rapporti virtuali dipendenti.

>[!TIP]
>
>Con l’introduzione di [curation](/help/analyze/analysis-workspace/curate-share/curate.md), puoi modificare il nome di una data dimensione o metrica in base a VRS.

### Sfumature di segmentazione

Una suite di rapporti virtuale a un livello fondamentale è semplicemente un segmento applicato a una suite di rapporti. Le dimensioni basate su visite e visitatori possono fornire risultati di reporting non intuitivi.

Ad esempio, hai due siti web, A e B, che inviano entrambi dati a una suite di rapporti globale. Alcuni visitatori inevitabilmente passano dal sito A al sito B, e questo movimento dall’uno all’altro è visibile nei percorsi nella suite di rapporti globale. Se si creano suite di rapporti virtuali per i siti A e B, una visita avviata sul sito A e terminata sul sito B non mostrerebbe una pagina di ingresso nella VRS B. La pagina di ingresso per questa visita è iniziata sul sito A, che è segmentato fuori dalla suite di rapporti virtuali.

### Conversione in valuta

Le suite di rapporti virtuali non eseguono rapporti in una valuta diversa dalla suite di rapporti su cui si basano. Adobe Analytics consente di convertire la valuta durante l’esecuzione dei rapporti, ma il tasso di cambio è basato sul giorno corrente (anche per i dati storici).

Se la tua organizzazione effettua la propria analisi in una moneta unica, questo non crea problemi. Tuttavia, se hai un&#39;esigenza aziendale significativa per diversi team regionali che devono visualizzare i ricavi nella propria valuta locale, puoi utilizzare l&#39;assegnazione tag a più suite.

### Feed di dati

I feed di dati non possono utilizzare suite di rapporti virtuali. Tuttavia, puoi ricevere un feed di dati da una suite di rapporti globale e quindi separarlo.

I feed di dati consentono di ricevere un’esportazione giornaliera o oraria di tutti i dati di Adobe Analytics a livello di singolo hit. I feed di dati non possono essere pre-segmentati prima che vengano consegnati all’utente, pertanto puoi ricevere solo un feed di dati per la suite di rapporti globale. Se l’organizzazione ha una forte necessità di feed di dati singoli a un marchio, una proprietà, un’area geografica o un altro livello granulare, è consigliabile utilizzare l’assegnazione tag a più suite.

### Connettori dati con account partner

Alcune integrazioni dei partner di Adobe in Adobe Analytics sono limitate a un account partner per suite di rapporti. Alcune organizzazioni potrebbero richiedere più account partner per la stessa integrazione.

Ad esempio, è consentito un solo Google DCM per suite di rapporti. Molte aziende dispongono di più account DCM, che consentono a marchi, business unit e aree geografiche diversi di gestire i propri annunci display separatamente l&#39;uno dall&#39;altro. Impossibile configurare le integrazioni nelle suite di rapporti virtuali. Se disponi di connettori dati dipendenti con più account, puoi utilizzare l’assegnazione tag a più suite.

### Riepilogo origini dati

Le origini dati di riepilogo consentono di importare metriche aggregate in Adobe Analytics a livello di suite di rapporti. Poiché i caricamenti di origine dati di riepilogo contengono metriche aggregate *senza un ID visitatore*, non possono essere segmentati nei contenitori [!UICONTROL Visit] e [!UICONTROL Visitor]. Poiché le VRS funzionano utilizzando la segmentazione, i dati importati utilizzando origini dati di riepilogo non saranno disponibili nelle suite di rapporti virtuali se il segmento viene generato utilizzando un contenitore Visita o Visitatore.

Le origini dati di riepilogo vengono visualizzate nella suite di rapporti virtuali se viene utilizzato un contenitore Hit e se tale contenitore Hit dispone di regole condizionate per includere le informazioni sull’origine dati.

>[!TIP]
>
>Le origini dati a elaborazione completa supportano la segmentazione e possono essere utilizzate nelle suite di rapporti virtuali.

## Passaggi da seguire se hai deciso di utilizzare VRS

Se si sceglie di rimuovere le chiamate al server secondario a favore delle suite di rapporti virtuali:

1. Crea suite di rapporti virtuali per farli corrispondere ai dati presenti nelle suite di rapporti figlio. Segmento su una dimensione personalizzata che distingue i siti tra loro.
   * Se esegui la migrazione da un’implementazione con tag multi-suite esistente, confronta i segmenti della suite di rapporti virtuali con le suite di rapporti figlio esistenti. È necessario assicurarsi che i dati siano confrontabili prima di spostare gli utenti nella suite di rapporti virtuali.
   * Come best practice, considera l’utilizzo di [stack di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) in modo da poter modificare un segmento in un’unica posizione e applicarlo a tutte le suite di rapporti virtuali dipendenti.
   * Utilizza i contenitori hit per mantenere le suite di rapporti virtuali più esclusive tra loro.
2. Dopo aver confermato che le suite di rapporti virtuali sono configurate correttamente, rimuovi gli ID della suite di rapporti secondari dall’implementazione. Per rimuovere le suite di rapporti secondarie:
   * In Adobe Experience Platform Launch, fai clic sulla x accanto a qualsiasi suite di rapporti che non desideri più utilizzare.
   * Nelle implementazioni JavaScript legacy, individua la variabile `s.account` e rimuovi gli ID suite di rapporti che non desideri più utilizzare.
   * In tutti i casi, lascia solo l’ID suite di rapporti globale/principale per raccogliere i dati per i tuoi siti e le tue app.
   * Passa a Amministratore > Suite di rapporti e nasconde eventuali suite di rapporti secondarie non più utilizzate.
