---
description: Le suite di rapporti virtuali possono essere utilizzate per sostituire i tag per più suite. Ad esempio, invece di inviare dati a due suite di rapporti separate, puoi inviare dati a una e utilizzare suite di rapporti virtuali per limitare il numero di dati a cui gli utenti hanno accesso. Tuttavia, l'accesso ai dati è solo uno dei motivi per cui suite di rapporti separate possono essere vantaggiose. Considera attentamente i seguenti casi di utilizzo prima di apportare modifiche all’implementazione per quanto riguarda le suite di rapporti virtuali.
keywords: Suite di rapporti virtuali
seo-description: Le suite di rapporti virtuali possono essere utilizzate per sostituire i tag per più suite. Ad esempio, invece di inviare dati a due suite di rapporti separate, puoi inviare dati a una e utilizzare suite di rapporti virtuali per limitare il numero di dati a cui gli utenti hanno accesso. Tuttavia, l'accesso ai dati è solo uno dei motivi per cui suite di rapporti separate possono essere vantaggiose. Considera attentamente i seguenti casi di utilizzo prima di apportare modifiche all’implementazione per quanto riguarda le suite di rapporti virtuali.
seo-title: VRS e considerazioni su tag globali/su più suite
solution: Analytics
title: VRS e considerazioni su tag globali/su più suite
topic: Reports and Analytics
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# VRS e considerazioni su tag globali/su più suite

Suite di rapporti virtuali (VRS) consente di visualizzare i dati di una suite di rapporti che raccoglie dati dalle proprietà digitali, ma con un segmento applicato in modo permanente.

Poiché funzionano come suite di rapporti e possono essere assegnate a gruppi di utenti esattamente come le suite di rapporti, in alcuni casi VRS può essere utilizzata per sostituire i tag con più suite e quindi rimuovere le chiamate [al server](/help/admin/c-server-call-usage/overage-overview.md)secondario. Per tag con più suite si intende la capacità di inviare dati a più suite di rapporti utilizzando una singola richiesta di immagine. Ad esempio, invece di inviare dati per due marchi in due suite di rapporti "figlio" separate più una suite di rapporti "globale" in cui i dati tra marchi vengono uniti, puoi inviare dati da entrambi i marchi solo alla suite di rapporti globale. A questo punto, utilizzerete la VRS per limitare l'accesso degli utenti ai dati (per marchio) replicando le suite di rapporti figlio.

La sostituzione dei tag con più suite con una suite di rapporti globale e una VRS consente di semplificare l'implementazione di Adobe Analytics e di ridurre il consumo di chiamate server, ed è generalmente consigliata come procedura ottimale. Tuttavia, è necessario considerare alcune limitazioni importanti della VRS per decidere se utilizzare i tag per più suite o una singola suite di rapporti globale più VRS. Le seguenti linee guida possono aiutarti a decidere se implementare le suite di rapporti virtuali basate su una suite di rapporti globale sia l'approccio giusto per te.

## Linee guida

> [!NOTE]  SOLO per questi casi valgono le seguenti considerazioni:
>
>* Stai pensando di modificare la tua implementazione per rimuovere le suite di rapporti figlio e di affidarti esclusivamente a suite di rapporti virtuali per controllare le viste nei dati per gli utenti finali, oppure
>* Gli utenti di Adobe Analytics della tua azienda si affideranno alle suite di rapporti virtuali come vista principale dei dati.


Se non sei sicuro se i casi di utilizzo descritti si applicano a te e alla tua organizzazione, consulta gli altri amministratori Adobe Analytics o il team di account Adobe. Possono aiutare a valutare le esigenze aziendali e a formulare una raccomandazione.

L’utilizzo di suite di rapporti virtuali per sostituire i tag con più suite è consigliato se:

## La pubblicazione dei segmenti da Adobe Analytics al resto di Adobe Experience Cloud è necessaria solo a livello di suite per report globale, e tutti gli utenti che pubblicano segmenti hanno accesso alla suite per report globale.

Riepilogo:

* La condivisione di segmenti in Adobe Experience Cloud non è supportata per le suite di rapporti virtuali.
* Gli utenti che devono essere in grado di condividere un segmento in Experience Cloud devono avere accesso a una suite di rapporti vera (principale o figlia).

Attualmente, i segmenti non possono essere pubblicati in Adobe Experience Cloud da una suite di rapporti virtuale per la personalizzazione e il targeting. A tal fine, tutti gli utenti che pubblicano segmenti devono poter accedere a una suite di rapporti vera e propria. Un approccio per tag con più suite crea suite per report figlio in base a marchio, proprietà, regione, ecc. livello che consente agli utenti che non hanno accesso alla suite di rapporti globale di pubblicare i segmenti in base solo al set di dati a loro disposizione nella suite di rapporti figlio.

Ad esempio, i tuoi utenti possono avere accesso alle suite di rapporti virtuali solo per le loro aree geografiche, ma vuoi che siano in grado di creare e condividere segmenti da Adobe Analytics ad Adobe Experience Cloud per il targeting in Adobe Target. In questo caso, questi utenti non sarebbero in grado di pubblicare i segmenti e dovreste considerare l’utilizzo di tag per più suite per garantire che gli utenti possano pubblicare i segmenti.

## Non è necessario generare report in tempo reale (o "Dati correnti") a livello di suite per report virtuale.

Riepilogo:

* I rapporti in tempo reale non sono supportati nelle suite di rapporti virtuali, perché i dati sono segmentati.
* "Dati correnti" non è supportato nelle suite di rapporti virtuali, perché non supporta la segmentazione.

[I report](/help/admin/admin/realtime/t-realtime-admin.md) in tempo reale e ["Dati correnti"](/help/technotes/latency.md) non sono disponibili nelle suite di rapporti virtuali. Queste funzioni di Reporting e analisi forniscono l'accesso a tipi limitati di dati in modo accelerato, in secondi o minuti. Una delle limitazioni di tali viste è che non supportano la segmentazione; in altre parole, non è possibile segmentare i dati in tempo reale in Reporting e analisi. Poiché una suite di rapporti virtuali è creata utilizzando la segmentazione, è incompatibile con i rapporti in tempo reale. Questo interessa gli utenti che rispondono alle tendenze rilevate in Adobe Analytics in pochi secondi o pochi minuti di raccolta dei dati, come gli editor in una newsroom che stanno regolando gli stack di titoli in base al consumo di contenuti in tempo reale. In questo caso, devi:

* Considerate l'utilizzo di tag con più suite per garantire che ogni utente visualizzi solo i dati in tempo reale che dovrebbero essere visualizzati, oppure
* Consentite a questi utenti di accedere a una suite di rapporti vera e propria (globale) se devono poter accedere al set di dati completo.

## Non superate i limiti di valori univoci per le dimensioni chiave nelle suite di rapporti globali, o non vi interessa se gli utenti vedono "Basso traffico" nelle loro suite di rapporti virtuali.

Riepilogo:

* Le suite di rapporti virtuali non hanno limiti di valore univoci per le dimensioni e le ereditano dalla suite di rapporti principale.
* Se gli utenti di Adobe Analytics devono poter accedere a ogni valore di una dimensione che riceve frequentemente più di 500.000 valori unici al mese, puoi continuare a utilizzare il tag per più suite.

In caso di elevata cardinalità (un elevato numero di valori univoci in una data dimensione, come SKU di prodotto o Pagine), i bucket Adobe Analytics raramente hanno incontrato valori ogni mese in un elemento di riga "Basso traffico" aggregato all'interno di una qualsiasi dimensione in una suite di rapporti. I valori inclusi nel bucket "Basso traffico" non possono essere segmentati. Questo consente alle query di Adobe Analytics di tornare rapidamente, concentrandosi sui primi 500.000 elementi riga visualizzati più spesso per la dimensione sulle proprietà digitali. Ad esempio, potrebbe trattarsi dei primi 500.000 nomi di pagina. Per ulteriori informazioni sui limiti dei valori univoci, [consultate](/help/technotes/low-traffic.md).

Le suite di rapporti virtuali non dispongono di un set di 500.000 valori univoci per dimensione al mese. Se la suite di rapporti su cui si basa una VRS ha superato i 500.000 valori univoci per una determinata dimensione e ha iniziato a combinare valori di frequenza inferiore nell'elemento di linea "Basso traffico" per quella dimensione, potresti vedere anche "Basso traffico" nella suite di rapporti virtuali.

**Esempio**: un conglomerato multimediale possiede 100 proprietà Web. Ogni proprietà pubblica alcune migliaia di articoli di notizie al mese, oltre ad ospitare tutti gli articoli dei mesi precedenti, e tutte le proprietà si combinano in una suite di rapporti globale. Nella dimensione 'Nome articolo' della suite di rapporti globale, supponiamo che ogni mese ci siano 4 milioni di nomi di articolo univoci, dalle varie proprietà. I primi 500.000 valori che comprendono la maggior parte del traffico vengono visualizzati e possono essere segmentati, ma i restanti 3,5 milioni di valori sono raggruppati nell'elemento di riga "Basso traffico".

In questo caso, potete creare 100 suite di rapporti virtuali per i team che lavorano sulle singole proprietà. Anche se ciò è accettabile, tenere presente che nella dimensione 'Nome articolo' in ciascuna suite di rapporti virtuali, i valori visualizzati come voci distinte sono solo quelli dei primi 500.000 nella suite di rapporti globale per la proprietà specificata. Le suite di rapporti virtuali non ricevono la propria allocazione di 500.000 valori univoci per dimensione. I valori aggregati all'elemento "Basso traffico" nella suite di rapporti globale non verranno visualizzati singolarmente nella VRS. Ciò può creare confusione tra gli utenti che si aspettano di vedere un intero set di valori di dimensione in una suite di rapporti virtuale e che finiscono per visualizzare solo i valori di traffico elevato.

Se sai di superare regolarmente limiti di valori univoci nella suite di rapporti globale o nelle suite di rapporti figlio esistenti, verifica se gli utenti devono accedere a tali valori appena visualizzati prima di eseguire la migrazione alle suite di rapporti virtuali. Se gli utenti hanno bisogno di accedere a ogni valore univoco di una dimensione che supera attualmente i limiti di valore univoci nella suite di rapporti globale, considera di continuare a utilizzare i tag per più suite per fornire questo accesso.

Inoltre, l'Assistenza clienti Adobe può aumentare i limiti di valore univoci per una suite di rapporti globale su base limitata per un numero limitato di dimensioni, il che potrebbe eliminare completamente il problema. Per ulteriori informazioni, consulta il team di assistenza clienti e l’assistenza clienti.

## Puoi usare il set di dimensioni personalizzate (eVar e proprietà) e metriche (eventi) disponibili nella suite di rapporti globale per tenere traccia di tutti i punti dati critici tra tutte le proprietà.

Riepilogo:

* Le suite di rapporti virtuali non dispongono di un proprio set di dimensioni e metriche; ereditano questi dalla suite di rapporti principale.
* Pertanto, la suite di rapporti principale deve essere in grado di acquisire tutte le dimensioni e le metriche rilevanti per ciascuna proprietà combinata al suo interno utilizzando solo le dimensioni e le metriche personalizzate disponibili per la suite di rapporti globale (rispettivamente 325 e 1000).

Un vantaggio attuale dei tag per più suite consiste nel consentire proprietà, marchi, aree geografiche e così via. per acquisire diversi tipi di dati. Ad esempio, un'unità aziendale potrebbe utilizzare eVar76 per acquisire "Parole chiave di ricerca interna", mentre un'altra unità aziendale potrebbe utilizzare la stessa eVar per acquisire "Nome video". I gruppi possono implementare Adobe Analytics in base alle proprie esigenze specifiche.

Con una suite di rapporti globale, tutte le proprietà devono passare gli stessi punti dati nella stessa dimensione e nelle stesse metriche. Nell'esempio precedente, questi due marchi dovrebbero allinearsi sull'eVar76 utilizzato per le parole chiave di ricerca interna o per il nome del video, quindi posizionare l'altro punto dati in una dimensione diversa nelle rispettive implementazioni. In caso contrario, le dimensioni e/o le metriche nella suite di rapporti globali risulteranno danneggiate. Questo tende a essere un problema in situazioni in cui diverse proprietà, marche, regioni, ecc. che puoi supportare (con singole suite di rapporti) utilizza tutte le loro possibilità di dimensioni o metriche personalizzate disponibili. Di conseguenza, non sarebbero in grado di riservare alcune delle loro dimensioni o metriche per le esigenze di monitoraggio di altre proprietà, marchi, regioni, ecc.

Il numero massimo di dimensioni personalizzate di Adobe Analytics per suite di rapporti è 325 e il numero massimo di eventi personalizzati per suite di rapporti è 1000. Per passare a una suite di rapporti globale, è pertanto necessario che tutti i punti dati critici in tutte le proprietà digitali possano essere tracciati utilizzando le stesse 325 dimensioni personalizzate e 1000 eventi personalizzati.

Se ti trovi in questa situazione e stai pensando di passare a una suite di rapporti globale con VRS, consulta le varie implementazioni di Adobe Analytics della tua azienda per valutare la quantità di sovrapposizione/dissonanza in queste implementazioni e per vedere quali dimensioni o metriche non sono fondamentali per il successo aziendale. Considera anche l'utilizzo di [classificazioni](/help/components/c-classifications2/c-classifications.md) nella suite globale per generare report sui valori che al momento potrebbero utilizzare la propria dimensione. Le classificazioni sono automaticamente disponibili per qualsiasi VRS basato su tale suite globale. Ad esempio, invece di acquisire 'Product Name' in eVar5, create una classificazione 'Product Name' basata sulla dimensione 'Product'.

Se il consolidamento di tali dimensioni ed eventi personalizzati non è fattibile, Adobe consiglia di continuare a utilizzare i tag per più suite.

>[!IMPORTANT]
>
>Con l'introduzione della cura [della suite di rapporti](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md)virtuale, ora puoi cambiare il nome di una determinata dimensione o &gt;metrica in base a ogni VRS. Se segmentate correttamente la suite di rapporti virtuali, questo significa che ora potete utilizzare eVar, prop o evento &gt; lo stesso per acquisire elementi diversi in suite di rapporti virtuali diverse. Tuttavia, il passaggio di due tipi diversi di dati nella stessa dimensione o metrica renderà tale punto dati praticamente inutilizzabile nella suite di rapporti &gt;globale. Potrebbe anche causare problemi di attribuzione, come in questo esempio: se un utente riceve due &gt;valori per eVar10, uno che è una 'campagna interna' sulla proprietà A e l'altro che è un 'Nome pagina' su &gt;proprietà B, significa che il successo ora viene suddiviso tra 'Campagna interna' e 'Nome pagina', che dovrebbe &gt;funzionare su livelli diversi. Di conseguenza, Adobe in genere non consiglia di utilizzare la cura VRS come soluzione alternativa a questo particolare problema.

## I segmenti utilizzati con le suite di rapporti virtuali non dividono i dati in modi che possono confondere gli utenti.

Riepilogo:

* La segmentazione dei dati da una suite di rapporti globale a suite di rapporti virtuali può creare risultati sfumati che possono confondere alcuni utenti.
* Considera in che modo i tuoi segmenti nelle suite di rapporti virtuali possono avere un impatto su dimensioni e funzionalità quali la pagina iniziale, il dominio di riferimento, il percorso, ecc.

Ricorda che una suite di rapporti virtuale è solo un segmento applicato a una suite di rapporti; tutte le sfumature nei dati segmentati si applicano alle suite di rapporti virtuali. I segmenti (e quindi le suite di rapporti virtuali) possono essere utilizzati per suddividere i dati in modi che sembrano non intuitivi per gli utenti di Adobe Analytics.

Ad esempio, supponiamo di avere due marchi, A e B, le cui proprietà digitali inviano dati in una suite di rapporti globale. Alcuni utenti passeranno dal sito Web A al sito Web B e viceversa, e questo movimento dall'uno all'altro è visibile nel percorso nella suite di rapporti globale. Tuttavia, se si creano suite di rapporti virtuali per i marchi A e B, gli utenti che accedono alla suite di rapporti virtuale B potrebbero visualizzare risultati non intuitivi per determinate dimensioni e metriche. Una visita iniziata con il marchio A e terminata con il marchio B non mostrerà alcuna pagina iniziale nella suite di rapporti virtuale B, dal momento che la pagina iniziale della visita intersito è iniziata con il marchio A, che è segmentato fuori da questa suite di rapporti virtuali.

Un esempio simile riguarda 'Visit Number'. Nella suite di rapporti virtuali per il marchio B, gli utenti possono vedere alcuni visitatori che sembrano avere una seconda, una terza e una quarta visita, ma nessuna prima visita. Ciò si verifica quando la prima visita del cliente è il marchio A, e tutte le visite successive sono al marchio B. Poiché i dati del marchio A non sono inclusi nella suite di rapporti virtuali, tutte le informazioni sulla prima visita, incluso il fatto che sia avvenuta affatto, non sono incluse in questa suite di rapporti virtuali.

Adobe consiglia di utilizzare i tag per più suite in questi scenari o in altre situazioni in cui parte del percorso di un cliente può verificarsi al di fuori di una suite di rapporti virtuale in modo da confondere gli utenti. L’assegnazione di tag a più suite consente di monitorare un viaggio a livello di proprietà incrociata in una suite di rapporti globale, ma offre anche ai singoli team una visione completa del percorso a livello di singola proprietà.

## Voi e i vostri utenti non dovete essere in grado di visualizzare le transazioni in diverse valute nazionali.

Riepilogo:

* Le suite di rapporti virtuali non possono al momento generare rapporti in una valuta diversa rispetto alla suite di rapporti su cui si basano.
* Adobe Analytics consente di convertire la valuta durante l'esecuzione dei report, ma il tasso di cambio è basato sul giorno corrente, anche per i dati storici.

Le suite di rapporti virtuali non possono al momento generare rapporti in una valuta diversa rispetto alla suite di rapporti su cui si basano. Se la tua azienda e i tuoi utenti di Adobe Analytics eseguono le loro analisi in una sola valuta, questo non creerà problemi. Tuttavia, se hai un'esigenza aziendale significativa per diversi team regionali che devono essere in grado di visualizzare le entrate e metriche simili nella propria valuta locale (convertita in base al tasso di cambio al momento della raccolta dei dati), devi utilizzare i tag per più suite.

Questo consente di inviare contemporaneamente dati in Adobe Analytics in valute diverse. Con i tag per più suite, una transazione che si verifica nella versione giapponese dell'app potrebbe essere registrata nella suite globale in USD. Può essere convertito da JPY al tasso di cambio del giorno specificato, ma continua a essere visualizzato nella suite di rapporti Giappone in JPY.

> [!NOTE] Sebbene le suite di rapporti virtuali non consentano di convertire i dati sulle entrate in un'altra valuta a un tasso storico, è comunque possibile convertire la valuta in una suite di rapporti virtuale su base ad hoc. Puoi applicare il tasso di cambio del giorno corrente ai dati storici scegliendo Componenti &gt; Impostazioni rapporto.

## Puoi utilizzare un singolo Feed dati per ricevere tutti i tuoi dati da una suite di rapporti globale.

Riepilogo:

* I feed di dati possono essere creati solo in base a suite di rapporti vere, non a suite di rapporti virtuali.
* Tuttavia, puoi ricevere un Feed dati da una suite di rapporti globale e suddividerlo per marchio, proprietà, regione, ecc.

I feed di dati consentono di ricevere un'esportazione giornaliera o oraria di tutti i dati Adobe Analytics a livello di "evento" o "hit". Poiché i feed di dati non possono essere pre-segmentati prima che vengano inviati all'utente, l'utilizzo di una suite di rapporti globale con suite di rapporti virtuali consente di ricevere solo un feed di dati per la suite di rapporti globale. Non potete impostare feed di dati per le suite di rapporti virtuali.

Tuttavia, puoi impostare tutti i feed di dati in base alle suite di rapporti effettive desiderate. Dopo aver ricevuto questi feed di dati, potete segmentarli e suddividerli in qualsiasi configurazione utile. Ad esempio, dopo aver ricevuto un Feed dati per una suite di rapporti globale, puoi caricare la porzione di tale Feed dati relativa al tuo sito Web in un data warehouse. È possibile caricare simultaneamente la porzione relativa all'app mobile in un data warehouse diverso.

Tuttavia, alcuni campi precalcolati nel Feed dati potrebbero dover essere ricalcolati dopo la ricezione. Per esempi di campi che potrebbero dover essere ricalcolati durante il filtraggio di un feed di dati in base ad alcuni criteri, vedi il punto 5 (sopra).

Se la tua organizzazione ha una forte necessità di feed di dati singoli per un marchio, una proprietà, un'area geografica e così via. potete scegliere di utilizzare i tag per più suite.

## Non si utilizza un'integrazione di Exchange (connettori dati) che consente un solo account partner per suite di rapporti e non si dispone di più account partner da integrare.

Riepilogo:

* Alcune integrazioni di partner Adobe in Adobe Analytics sono limitate a un account per suite di rapporti.
* Alcune organizzazioni potrebbero voler utilizzare più account partner in Adobe Analytics, che richiede l'assegnazione di tag a più suite.

Adobe Exchange consente di integrare altre soluzioni di marketing e tecnologie pubblicitarie con Adobe Analytics. Esempi di integrazioni disponibili includono display pubblicitari, e-mail, VOC e call center. A causa delle variazioni nelle modalità di raccolta, presentazione e integrazione dei dati, alcuni partner Adobe che puoi scegliere di utilizzare con Adobe Exchange dispongono di un limite di un'istanza della loro integrazione per ogni suite di rapporti. Ogni istanza viene mappata su un account con il partner.

Un esempio è Google DCM. Molte aziende dispongono di account DCM multipli, che consentono l'utilizzo di marchi, unità aziendali, aree geografiche e così via. per gestire gli annunci visualizzati separatamente l'uno dall'altro. Tuttavia, quando integri DCM con Adobe Analytics, puoi utilizzare un solo account DCM per suite di rapporti. Non puoi integrare ciascuno dei tuoi diversi account DCM nella stessa suite di rapporti. Non è inoltre possibile impostare un'integrazione direttamente in una suite di rapporti virtuale.

Di conseguenza, l'assegnazione di tag a più suite è l'approccio preferito se i diversi team dell'organizzazione devono disporre dei dati del proprio account in Adobe Analytics per un partner Adobe Exchange. Se utilizzi o utilizzerai integrazioni Adobe Exchange in cui diversi gruppi gestiscono account diversi, verifica con il partner Adobe se sono consentiti più account per suite di rapporti.

> [!NOTE] Il termine "account" può significare cose diverse per diversi fornitori. Nel contesto della tecnologia di marketing, in genere non si riferisce a un singolo account utente, ma piuttosto a un insieme di servizi resi disponibili a un &gt;intero team o organizzazione. Pertanto, anche se potreste avere più nomi utente che effettuano l'accesso al servizio di un partner Adobe, &gt;tutti questi nomi utente potrebbero appartenere allo stesso account.

> [!NOTE] Eventuali metriche "pre-clic" (riepilogate/aggregate) importate da un partner Adobe Exchange non sono &gt; disponibili per la segmentazione e pertanto potrebbero non essere visibili in una suite di rapporti virtuale. Esempi di tali metriche &gt; includono le e-mail inviate o visualizzate le impressioni degli annunci, che si verificano sia all'esterno che all'esterno dell'app e vengono importate in Adobe &gt;Analytics in un modulo aggregato.

## Non fai molta affidamento su Origini dati di riepilogo a una proprietà, marchio, regione, ecc. level.

Riepilogo:

* 'Origini dati di riepilogo' consente di importare metriche aggregate in Adobe Analytics a livello di suite di rapporti.
* Per passare a una suite di rapporti globale con suite di rapporti virtuali è necessario che tutti i caricamenti di 'Origini dati di riepilogo' siano effettuati nella suite di rapporti globale.

'Origini dati di riepilogo' consente di importare metriche pre-aggregate in una suite di rapporti vera in Adobe Analytics. Esempi di 'Origini dati di riepilogo' includono metriche quali 'Ricavi offline' o 'Visualizzazioni di pagina' che si sono verificate in un'altra soluzione prima dell'implementazione di Adobe Analytics. Poiché i caricamenti di Origini dati di riepilogo contengono metriche aggregate, non possono essere segmentati. Di conseguenza, non appaiono segmentati nelle suite di rapporti virtuali.

L’assegnazione di tag a più suite consente all’organizzazione di importare metriche aggregate a livello di singola suite di rapporti. Se il marchio A vuole importare ricavi offline, può farlo separatamente dal marchio B, e questi dati saranno visualizzati nella suite di rapporti del marchio A. Il marchio B potrebbe fare lo stesso. Se la tua organizzazione utilizza o pianifica di utilizzare Origini dati di riepilogo in una proprietà, marchio, regione ecc. potete prendere in considerazione l'utilizzo di tag con più suite invece delle suite di rapporti virtuali.

## Passaggi da seguire se si decide di utilizzare VRS

Dopo aver letto le considerazioni di cui sopra e aver deciso di rimuovere le chiamate al server secondario e utilizzare invece suite di rapporti virtuali, è necessario effettuare le seguenti operazioni:

**Innanzitutto**, create suite di rapporti virtuali che corrispondano ai dati delle suite di rapporti secondarie. Segmento su una dimensione personalizzata come "brand", "platform", "domain". Scegli una dimensione che semplifica la distinzione tra una proprietà digitale e l'applicazione di questi segmenti alla VRS.

* Se effettui la migrazione da un’implementazione di tag per più suite Adobe Analytics, prima di eseguire la migrazione degli utenti ricorda di confrontare i segmenti delle suite di rapporti virtuali con le suite di rapporti figlio esistenti. Desiderate essere certi che i segmenti utilizzati nelle suite di rapporti virtuali siano corretti.

* Se necessario, regola i segmenti su cui si basano le suite di rapporti virtuali.

* Come procedura ottimale, utilizzate l'impilamento [dei](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) segmenti laddove possibile, in modo da poter modificare un segmento in una posizione e applicarlo a tutte le suite di rapporti virtuali che utilizzano tale segmento. Ad esempio, se si desidera creare una VRS per "utenti di telefonia mobile dall'Europa" e un'altra per "utenti di telefonia mobile dall'Asia", creare un segmento per gli utenti di telefonia mobile e quindi segmenti separati per gli utenti europei e asiatici. In questo modo, se vuoi aggiornare la definizione del segmento "utenti mobili", puoi farlo in un singolo segmento senza dover aggiornare singolarmente ogni segmento della suite di rapporti virtuale.

* Potresti cercare set di dati che si escludono a vicenda nelle suite di rapporti virtuali. Ad esempio, potresti voler vedere "Dominio A" e "Dominio B" come suite di rapporti separate e non vuoi traffico del dominio A nella suite di rapporti del dominio B. In questo caso, usa un contenitore "hit" per i tuoi segmenti.

**In secondo luogo**, dopo aver confermato che le suite di rapporti virtuali create sono configurate correttamente e soddisferanno le esigenze del team, rimuovete gli ID suite di rapporti secondari dall'implementazione.

Per rimuovere delle suite di rapporti secondarie:

* In Adobe Experience Platform Launch, fai clic sulla "x" accanto alle suite di rapporti che non desideri più utilizzare.
* In Gestione dinamica dei tag, individua la proprietà e lo strumento Adobe Analytics in questione. Nei campi ID account produzione e ID account di gestione temporanea, rimuovete gli ID suite di rapporti che non desiderate più utilizzare.
* Nelle implementazioni JavaScript precedenti, individua la `s.account` variabile e rimuovi le suite di rapporti che non desideri più utilizzare.

Lasciate solo gli ID suite di rapporti globali/padre per raccogliere i dati dai siti e dalle app. Nell'interfaccia di Adobe Analytics puoi nascondere agli utenti le suite di rapporti legacy andando in Admin (Amministratore) &gt; Company Settings (Impostazioni società).

Se non riesci a modificare l’implementazione, collabora con il team di account Adobe. Possono esplorare le opzioni per impedire che le chiamate al server secondario vengano elaborate da Adobe Analytics.
