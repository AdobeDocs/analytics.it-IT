---
description: Le suite di rapporti virtuali e l’assegnazione di tag a più suite presentano vantaggi diversi. Scopri qual è il migliore per la tua organizzazione.
keywords: Suite di rapporti virtuali
title: Considerazioni sulle suite di rapporti virtuali e sull’assegnazione di tag a più suite
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1650'
ht-degree: 0%

---

# Considerazioni sulle suite di rapporti virtuali e sull’assegnazione di tag a più suite

Le suite di rapporti virtuali ti consentono di visualizzare i dati di una suite di rapporti che raccoglie dati dalle proprietà digitali, ma con un segmento applicato in modo permanente.

In molti casi, puoi utilizzare suite di rapporti virtuali per sostituire l’assegnazione di tag a più suite. Il passaggio alle suite di rapporti virtuali può eliminare efficacemente la necessità di [chiamate server secondarie](/help/admin/admin/c-server-call-usage/overage-overview.md). Ad esempio, la tua organizzazione dispone di 6 siti web diversi, ciascuno dei quali invia dati alla propria suite di rapporti e a una suite di rapporti globale combinata. Ogni sito riceve una chiamata al server secondaria, una alla singola suite di rapporti sul brand e una seconda alla suite di rapporti globale. Al contrario, puoi inviare dati da tutti i siti solo alla suite di rapporti globale, quindi utilizzare più suite di rapporti virtuali per separare ogni marchio.

La sostituzione dell’assegnazione tag per più suite con una suite di rapporti globale e una suite di rapporti virtuale consente di semplificare l’implementazione di Adobe Analytics e ridurre il consumo di chiamate al server; questa procedura è consigliata come best practice. Tuttavia, le suite di rapporti virtuali presentano alcune limitazioni importanti da considerare. Le linee guida seguenti sono utili per decidere se implementare suite di rapporti virtuali basate su una suite di rapporti globale sia l’approccio giusto.

## Linee guida

Se non sei sicuro se i casi d’uso descritti si applicano a te e alla tua organizzazione, consulta gli altri amministratori di Adobe Analytics o il tuo account team di Adobi. Possono essere utili per valutare le esigenze aziendali e formulare raccomandazioni.

Per determinare se utilizzare l’assegnazione di tag multisuite o le suite di rapporti virtuali, tieni presenti le seguenti considerazioni:

### Pubblicazione di segmenti in Adobe Experience Cloud

La condivisione di segmenti su Adobe Experience Cloud non è supportata per le suite di rapporti virtuali. Gli utenti che desiderano condividere un segmento con l’Experience Cloud devono avere accesso alla suite di rapporti di origine.

Non è ancora possibile pubblicare segmenti in Adobe Experience Cloud da una suite di rapporti virtuale per la personalizzazione e il targeting. A questo scopo, tutti gli utenti che pubblicano segmenti devono accedere alla suite di rapporti di origine. Ad esempio, se desideri che gli utenti abbiano accesso solo ai dati per le loro aree geografiche, vuoi che possano creare e condividere segmenti da Adobe Analytics a Adobe Experience Cloud per il targeting in Adobe Target. In questo caso, l’Adobe consiglia di utilizzare l’assegnazione tag per più suite. Se non ti dispiace se gli utenti hanno accesso alla suite di rapporti globale o se non devi pubblicare segmenti da utilizzare in altre soluzioni, puoi utilizzare le suite di rapporti virtuali.

### Limiti univoci

Se disponi di una suite di rapporti globale che combina un numero elevato di siti, è possibile che si verifichi l’errore [traffico ridotto](/help/technotes/low-traffic.md) riga frequentemente. Se utilizzi l’assegnazione tag per più suite, si tratta solo di un problema per la suite di rapporti globale (le singole suite di rapporti avrebbero meno probabilità di vedere un traffico ridotto). Se utilizzi suite di rapporti virtuali, vengono condivisi limiti univoci, causando la visualizzazione di traffico ridotto anche nelle singole suite di rapporti. Per evitare di inserire dati in blocchi a traffico ridotto, utilizza l’assegnazione di tag per più suite.

Ad esempio, una grande organizzazione di media possiede 100 proprietà web. Ogni proprietà pubblica qualche migliaio di articoli di notizie mensili, oltre a ospitare tutti gli articoli dei mesi precedenti. Questa organizzazione utilizza una suite di rapporti globale in cui eVar1 è &quot;Nome articolo&quot;. In questo rapporto, ci sono circa 4 milioni di nomi di articolo univoci ogni mese dalle varie proprietà combinate. Se utilizzi una suite di rapporti virtuale, i primi 500.000 valori che costituiscono la maggior parte del traffico sono inclusi nelle suite di rapporti virtuali; i rimanenti 3,5 milioni sono inclusi nella categoria traffico ridotto. Se utilizzi l’assegnazione tag per più suite, ogni singola suite di rapporti può visualizzare i propri valori superiori di 500.000. I limiti univoci della suite di rapporti globale sono gli stessi tra l’utilizzo di tag multisuite e le suite di rapporti virtuali.

L’Assistenza clienti di Adobe può aumentare i limiti di valore univoci per un numero limitato di dimensioni, eliminando completamente questo problema. Per ulteriori informazioni, consulta il team del tuo account e l’Assistenza clienti.

### Variabili condivise tra suite di rapporti

Le suite di rapporti virtuali non hanno set propri di dimensioni e metriche, ma li ereditano dalla suite di rapporti di origine. La suite di rapporti globale deve acquisire tutte le dimensioni e le metriche per tutti i siti web. Le suite di rapporti hanno attualmente un massimo di 250 eVar e 1000 eventi personalizzati.

Diversi siti hanno esigenze di implementazione diverse. Alcune dimensioni e alcuni eventi possono essere condivisi tra due siti. Ad esempio, una registrazione e-mail può utilizzare lo stesso evento su più siti web, attivando lo stesso evento personalizzato. Altre dimensioni possono essere specifiche di un sito. Ad esempio, solo uno dei siti consente all’utente di modificare l’immagine del profilo. Questo evento personalizzato verrebbe implementato solo sul sito Web che lo supporta.

Assicurati che il numero di dimensioni e metriche univoche possa rientrare in una singola suite di rapporti globale. Se riscontri che sono presenti troppe dimensioni o metriche univoche, esamina ogni dimensione all’interno di ogni implementazione. È probabile che vi siano sovrapposizioni e dimensioni che non sono fondamentali per il successo aziendale. Valuta l’utilizzo di [classificazioni](/help/components/classifications/c-classifications.md) anche. Ad esempio, invece di acquisire &quot;Nome prodotto&quot; in eVar5, crea una classificazione &quot;Nome prodotto&quot; basata sulla dimensione &quot;Prodotto&quot;. Le classificazioni in una suite di rapporti di origine sono automaticamente disponibili per tutte le suite di rapporti virtuali dipendenti.

>[!TIP]
>
>Con l&#39;introduzione di [cura](/help/analyze/analysis-workspace/curate-share/curate.md), puoi modificare il nome di una dimensione o metrica specifica in base alla suite di rapporti virtuale.

### Sfumature di segmentazione

Una suite di rapporti virtuale a un livello fondamentale è semplicemente un segmento applicato a una suite di rapporti. Le dimensioni basate su visite e visitatori possono fornire risultati di reporting non intuitivi.

Ad esempio, disponi di due siti web, A e B, che inviano entrambi i dati a una suite di rapporti globale. Alcuni visitatori passano inevitabilmente dal sito A al sito B e questo spostamento dall’uno all’altro è visibile nei percorsi nella suite di rapporti globale. Se si creano suite di rapporti virtuali per i siti A e B, una visita iniziata sul sito A e terminata sul sito B non mostrerebbe una pagina di ingresso nella suite di rapporti virtuale B. La pagina di ingresso per questa visita è iniziata sul sito A, che è segmentato dalla suite di rapporti virtuali.

### Conversione valuta

Le suite di rapporti virtuali non generano rapporti con una valuta diversa da quella della suite di rapporti su cui si basano. Adobe Analytics consente di convertire la valuta durante l’esecuzione dei rapporti, ma il tasso di cambio si basa sul giorno corrente (anche per i dati storici).

Se la tua organizzazione esegue l’analisi in un’unica valuta, non si verifica alcun problema. Tuttavia, se hai una necessità aziendale significativa per diversi team regionali che devono visualizzare le entrate nella propria valuta locale, puoi utilizzare l’assegnazione tag per più suite.

### Feed di dati

I feed di dati non possono utilizzare suite di rapporti virtuali. Tuttavia, puoi ricevere un feed di dati da una suite di rapporti globale e quindi separarlo.

I feed di dati ti consentono di ricevere un’esportazione giornaliera o oraria di tutti i dati di Adobe Analytics a livello di singolo hit. I feed di dati non possono essere pre-segmentati prima di essere inviati all’utente, pertanto puoi ricevere solo un feed di dati per la suite di rapporti globale. Se la tua organizzazione ha una forte necessità di feed di dati individuali a livello di marchio, proprietà, area geografica o altro livello granulare, puoi utilizzare l’assegnazione tag per più suite.

### Connettori dati con account partner

Alcune integrazioni di Adobi partner in Adobe Analytics sono limitate a un account partner per suite di rapporti. Alcune organizzazioni potrebbero richiedere più account partner per la stessa integrazione.

Ad esempio, è consentito un solo DCM Google per suite di rapporti. Molte aziende hanno più account DCM, il che consente a diversi marchi, business unit e aree geografiche di gestire i propri annunci display separatamente l&#39;uno dall&#39;altro. Non è possibile configurare le integrazioni nelle suite di rapporti virtuali. Se disponi di connettori dati dipendenti con più account, puoi utilizzare l’assegnazione tag per più suite.

### Origini dati di riepilogo

Le origini dati di riepilogo consentono di importare metriche aggregate in Adobe Analytics a livello di suite di rapporti. Perché i caricamenti dell’origine dati di riepilogo contengono metriche aggregate *senza un ID visitatore*, non possono essere segmentati in [!UICONTROL Visit] e [!UICONTROL Visitor] contenitori. Poiché la suite di rapporti virtuali funziona utilizzando la segmentazione, i dati importati utilizzando origini dati di riepilogo non saranno disponibili nelle suite di rapporti virtuali se il segmento viene creato utilizzando un contenitore Visita o Visitatore.

Le origini dati di riepilogo vengono visualizzate nella suite di rapporti virtuali se viene utilizzato un contenitore Hit e se tale contenitore dispone di regole condizionate per includere le informazioni sull’origine dati.

>[!TIP]
>
>Le origini dati a elaborazione completa supportano la segmentazione e possono essere utilizzate nelle suite di rapporti virtuali.

## Passaggi da seguire se hai deciso di utilizzare una suite di rapporti virtuale

Se scegli di rimuovere le chiamate al server secondarie a favore delle suite di rapporti virtuali:

1. Crea suite di rapporti virtuali per far corrispondere i dati nelle suite di rapporti figlio. Segmento su una dimensione personalizzata che distingue i siti tra loro.
   * Se esegui la migrazione da un’implementazione con tag multisuite esistente, confronta i segmenti della suite di rapporti virtuale con le suite di rapporti figlio esistenti. Assicurati che i dati siano comparabili prima di spostare gli utenti alla suite di rapporti virtuale.
   * Come best practice, considera l’utilizzo di [stacking dei segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) in modo da poter modificare un segmento in un’unica posizione e applicarlo a tutte le suite di rapporti virtuali dipendenti.
   * Utilizza i contenitori Hit per mantenere le suite di rapporti virtuali più esclusive tra loro.
2. Dopo aver confermato che le suite di rapporti virtuali sono configurate correttamente, rimuovi gli ID suite di rapporti secondari dall’implementazione. Per rimuovere le suite di rapporti secondarie:
   * Nell’estensione Adobe Analytics di Adobe Experience Platform Data Collection, fai clic sulla &quot;x&quot; accanto alle suite di rapporti che non desideri più utilizzare.
   * Nelle implementazioni JavaScript legacy, individua `s.account` e rimuovi eventuali ID suite di rapporti che non desideri più utilizzare.
   * In tutti i casi, lascia solo l’ID suite di rapporti globale/principale per raccogliere i dati per i siti e le app.
   * Passa a Amministrazione > Suite di rapporti e nascondi le eventuali suite di rapporti secondarie non più utilizzate.
