---
description: Le suite di rapporti virtuali possono essere utilizzate per sostituire i tag multisuite. Ad esempio, invece di inviare dati a due suite di rapporti separate, puoi inviare dati a uno e utilizzare suite di rapporti virtuali per limitare il numero di dati a cui hanno accesso gli utenti. Tuttavia, l'accesso ai dati è solo uno dei motivi per cui le suite di rapporti separate possono essere utili. Considerate attentamente i seguenti casi d'uso prima di apportare modifiche all'implementazione relativamente alle suite di rapporti virtuali.
keywords: Suite di rapporti virtuali
seo-description: Le suite di rapporti virtuali possono essere utilizzate per sostituire i tag multisuite. Ad esempio, invece di inviare dati a due suite di rapporti separate, puoi inviare dati a uno e utilizzare suite di rapporti virtuali per limitare il numero di dati a cui hanno accesso gli utenti. Tuttavia, l'accesso ai dati è solo uno dei motivi per cui le suite di rapporti separate possono essere utili. Considerate attentamente i seguenti casi d'uso prima di apportare modifiche all'implementazione relativamente alle suite di rapporti virtuali.
seo-title: VRS e considerazioni su tag globali/su più suite
solution: Analytics
title: VRS e considerazioni su tag globali/su più suite
topic: Reports & Analytics
uuid: f 17 d 3659-a 5 b 1-4807-a 01 d-a 1 b 422009 a 64
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# VRS e considerazioni su tag globali/su più suite

Le suite di rapporti virtuali (VRS) ti consentono di visualizzare i dati da una suite di rapporti che raccoglie dati dalle tue proprietà digitali, ma con un segmento applicato in modo permanente.

Because they function as report suites and can be assigned to user groups just like report suites, VRS can, in some cases, be used to replace multi-suite tagging and thus remove [secondary server calls](/help/admin/c-server-call-usage/overage-overview.md). (L'assegnazione di tag per più suite è definita come la capacità di inviare dati a più suite di rapporti utilizzando una sola richiesta di immagine). Ad esempio, invece di inviare dati per due marchi in due suite di rapporti secondarie separate, più una suite di rapporti «globale» in cui i dati tra i marchi vengono combinati, puoi inviare dati da entrambi i marchi solo alla suite di rapporti globale. Potrai quindi utilizzare la VRS per limitare l'accesso degli utenti ai dati (per marchio) replicando le suite di rapporti secondarie.

La sostituzione di tag con più suite con una suite di rapporti globale e una VRS consente di semplificare l'implementazione di Adobe Analytics e di ridurre il consumo di chiamate server, e viene generalmente consigliato come procedura ottimale. Tuttavia, esistono alcune limitazioni importanti di VRS da considerare per decidere se utilizzare i tag per più suite o una singola suite di rapporti globale più virtuale. Le seguenti linee guida possono aiutarti a stabilire se implementare suite di rapporti virtuali create su una suite di rapporti globale è l'approccio giusto per voi.

## Linee guida

>[!NOTE]
>
> Le considerazioni seguenti applicano solo ai casi seguenti:
>
>* Stai valutando la modifica della tua implementazione per rimuovere suite di rapporti secondarie e per fare affidamento unicamente su virtuale &gt; suite di rapporti per controllare le viste in dati per gli utenti finali, oppure
>* Gli utenti di Adobe Analytics nella tua azienda si affideranno alle suite di rapporti virtuali come la loro visualizzazione principale dei dati.


Se non sei sicuro se i casi di utilizzo descritti sono applicabili a te e alla tua organizzazione, consulta gli altri amministratori di Adobe Analytics o il team di account Adobe. Possono contribuire a valutare le esigenze aziendali e a effettuare una raccomandazione.

L'utilizzo di suite di rapporti virtuali per sostituire i tag con più suite è consigliato se:

## La pubblicazione di segmenti da Adobe Analytics al resto di Adobe Experience Cloud è necessaria solo a livello globale, e tutti gli utenti che pubblicano segmenti possono accedere alla suite di rapporti globale.

Riepilogo:

* La condivisione di segmenti ad Adobe Experience Cloud non è supportata per le suite di rapporti virtuali.
* Gli utenti che devono condividere un segmento in Experience Cloud devono avere accesso a una suite di rapporti (principale o figlio).

Attualmente, i segmenti non possono essere pubblicati su Adobe Experience Cloud da una suite di rapporti virtuale per la personalizzazione e il targeting. A questo scopo, tutti gli utenti che pubblicano segmenti devono accedere a una suite di rapporti vera e propria. Un approccio con tag per più suite crea suite di rapporti secondarie a marchio, proprietà, regione ecc. che consente agli utenti che non hanno accesso alla suite di rapporti globale di pubblicare i segmenti rispetto solo al set di dati resi disponibili nella suite di rapporti secondari.

Ad esempio, gli utenti possono avere accesso alle suite di rapporti virtuali solo per le loro aree geografiche, ma dovranno essere in grado di creare e condividere segmenti da Adobe Analytics ad Adobe Experience Cloud per il targeting in Adobe Target. In questo caso, questi utenti non saranno in grado di pubblicare segmenti e si consiglia di utilizzare i tag multisuite per garantire che gli utenti possano pubblicare segmenti.

## Non hai bisogno di rapporti in tempo reale (o dati correnti) a livello di report virtuale-suite.

Riepilogo:

* I report in tempo reale non sono supportati nelle suite di rapporti virtuali, perché i dati vengono segmentati.
* «Dati correnti» non è supportato nelle suite di rapporti virtuali, perché non supporta la segmentazione.

[I report in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md) e [i "Dati correnti"](../../technotes/latency.md) non sono disponibili nelle suite di rapporti virtuali. Queste funzioni di Reporting e analisi consentono di accedere a tipi limitati di dati in modo più veloce, entro pochi secondi o minuti. Una delle limitazioni di queste viste è che non supportano la segmentazione; in altre parole, i dati in tempo reale in Reporting e analisi non possono essere segmentati. Poiché una suite di rapporti virtuale viene creata utilizzando la segmentazione, non è compatibile con i report in tempo reale. Ciò interessa gli utenti che rispondono alle tendenze visualizzate in Adobe Analytics in pochi secondi o in pochi minuti di raccolta dati, come editor in una newsroom che stanno regolando stack di intestazione in base al consumo di contenuto in tempo reale. In questo caso, è necessario:

* Prendete in considerazione l'utilizzo dei tag per più suite per garantire che ogni utente visualizzi solo i dati in tempo reale che dovrebbero essere consentiti oppure
* Concedi a questi utenti l'accesso a una suite di rapporti (globale) se devono poter accedere al set di dati completo.

## Non superi i limiti di valori univoci per le dimensioni chiave nelle suite di rapporti globali o non ti interessano se gli utenti visualizzano «Traffico basso» nelle suite di rapporti virtuali.

Riepilogo:

* Le suite di rapporti virtuali non hanno limiti di valore univoci per le dimensioni e li ereditano dalla suite di rapporti principale.
* Se gli utenti di Adobe Analytics richiedono l'accesso a ogni valore di una dimensione che riceve spesso oltre 500,000 valori univoci al mese, prendete in considerazione l'ipotesi di passare al tag multisuite.

In casi elevati (numero elevato di valori univoci in una determinata dimensione, come SKU di prodotto o Pagine), i bucket di Adobe Analytics hanno raramente incontrato valori ogni mese in un elemento di linea «Low Traffic» aggregato all'interno di qualsiasi dimensione di una suite di rapporti. I valori inclusi nel bucket «Traffico basso» non possono essere segmentati. Ciò consente di tornare rapidamente alle query di Adobe Analytics, concentrandosi sui primi 500,000 elementi visualizzati più spesso per la dimensione delle proprietà digitali. Ad esempio, questi possono essere i primi 500,000 nomi di pagina. You can read more about unique value limits [here](../../technotes/low-traffic.md).

Le suite di rapporti virtuali non hanno un proprio insieme di 500,000 valori univoci per dimensione al mese. Se la suite di rapporti su cui è basata una VRS ha superato 500,000 valori univoci per una determinata dimensione e hai iniziato a combinare valori di frequenza inferiore nell'elemento della riga «Traffico basso» per quella dimensione, potresti vedere «Traffico basso» nella suite di rapporti virtuale.

**Esempio**: un cluster di supporti possiede 100 proprietà Web. Ogni proprietà pubblica ogni mese un paio di articoli di notizie, oltre all'hosting di tutti gli articoli dei mesi precedenti, e tutte le proprietà combinano in una suite di rapporti globale. Nella dimensione «Nome articolo» della suite di rapporti globale, presupponiamo che ogni mese vi siano 4 milioni di nomi di articolo univoci, dalle varie proprietà. I primi 500,000 valori che costituiscono la massa del traffico vengono visualizzati e possono essere segmentati, mentre i restanti 3.5 milioni di valori vengono caricati nell'elemento «Low Traffic».

In questo caso, potete creare 100 suite di rapporti virtuali per i team che lavorano sulle singole proprietà. Benché sia accettabile, tenete presente che nella dimensione «Nome articolo» in ciascuna suite di rapporti virtuali, i valori visualizzati come elementi distinti sono solo quelli provenienti dalle prime 500,000 nella suite di rapporti globale per la proprietà specificata. Le suite di rapporti virtuali non dispongono di un proprio allocazione di 500,000 valori univoci per dimensione. I valori che si estendono nell'elemento «Low Traffic» (Traffico basso) nella suite di rapporti globale non verranno visualizzati singolarmente nella VRS. Ciò può causare confusione tra gli utenti che si aspettano di visualizzare un intero set di valori dimensionali in una suite di rapporti virtuale e di vedere invece solo i valori di traffico elevati.

Se si è certi di superare regolarmente i limiti univoci dei valori nella suite di rapporti globale o nelle suite di rapporti secondarie esistenti, valutare se gli utenti devono accedere a tali valori in modo frequente prima di eseguire la migrazione alle suite di rapporti virtuali. Se gli utenti devono accedere a qualsiasi valore univoco in una dimensione che superi i limiti univoci di valori nella suite di rapporti globale, è consigliabile continuare a utilizzare i tag per più suite per fornire questo accesso.

Inoltre, l'Assistenza clienti Adobe può aumentare i limiti di valori univoci per una suite di rapporti globale su base limitata per un numero limitato di dimensioni, il che potrebbe evitare il problema. Consulta il team dell'account e l'Assistenza clienti per ulteriori informazioni.

## Puoi utilizzare la serie di dimensioni personalizzate (evar e prop) e metriche (eventi) nella suite di rapporti globale per tenere traccia di tutti i punti dati critici in tutte le proprietà.

Riepilogo:

* Le suite di rapporti virtuali non hanno un proprio insieme di dimensioni e metriche, li ereditano dalla suite di rapporti principale.
* Pertanto, la suite di rapporti principale deve essere in grado di acquisire tutte le dimensioni e metriche rilevanti per ogni proprietà che viene combinata all'interno utilizzando solo le dimensioni e le metriche personalizzate disponibili per la suite di rapporti globale (325 e 1000, rispettivamente).

Un vantaggio attuale per i tag con più suite è l'abilitazione di proprietà, marchi, aree geografiche ecc. diverse. per acquisire diversi tipi di dati. Ad esempio, un'unità aziendale potrebbe utilizzare evar 76 per acquisire «Parole chiave ricerca interna», mentre un'altra unità aziendale potrebbe utilizzare la stessa evar per acquisire «Nome video». I gruppi hanno la libertà di implementare Adobe Analytics in base alle esigenze univoche.

Con una suite di rapporti globale, tutte le proprietà devono passare gli stessi punti dati nelle stesse dimensioni e metriche. Nell'esempio precedente, questi due marchi dovranno allineare l'evar 76 in modo da poter essere usati come «Parole chiave interne ricerca» o «Nome video», quindi inserire l'altro punto dati in una dimensione diversa nelle rispettive implementazioni. Se non viene eseguita questa operazione, potrai danneggiarti a dimensioni e/o metriche nella suite di rapporti globale. Si tratta di un problema che si verifica nelle situazioni in cui diverse proprietà, marchi, aree geografiche ecc. che il tuo supporto (con suite di rapporti singole) usa il loro completo condizionale di dimensioni o metriche personalizzate. Di conseguenza, non saranno in grado di adattare alcune delle loro dimensioni o metriche alle esigenze di tracciamento di altre proprietà, marchi, aree geografiche ecc.

Il numero massimo di dimensioni personalizzate di Adobe Analytics per suite di rapporti è 325 e il numero massimo di eventi personalizzati per suite di rapporti è 1000. Lo spostamento a una suite di rapporti globale richiede pertanto che tutti i punti dati critici per tutte le proprietà digitali possano essere tracciati utilizzando le stesse 325 dimensioni personalizzate e 1000 eventi personalizzati.

Se ti trovi in questa situazione e stai pensando di passare a una suite di rapporti globale con VRS, controlla le diverse implementazioni di Adobe Analytics nella tua azienda per valutare l'entità di sovrapposizione/disonanza in queste implementazioni e per vedere quali dimensioni o metriche non sono decisive per il successo aziendale. Also consider using [classifications](/help/components/c-classifications2/c-classifications.md) in your global suite to report on values that may currently be using their own dimension. Le classificazioni sono disponibili automaticamente per qualsiasi VRS basato su quella suite globale. Ad esempio, invece di acquisire «Nome prodotto» in evar 5, crea una classificazione «Product Name» in base alla dimensione «Prodotto».

Se il consolidamento di tali dimensioni e eventi personalizzati non è praticabile, Adobe consiglia di continuare a utilizzare i tag per più suite.

>[!IMPORTANT]
>
>With the introduction of [virtual report suite curation](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), you can now change the name of a given dimension or &gt;metric on a per-VRS basis. Se segmentate la suite di rapporti virtuali, ora potete utilizzare la &gt; stessa evar, prop o evento per acquisire elementi diversi in suite di rapporti virtuali diverse. Tuttavia, passare due &gt; diversi tipi di dati nella stessa dimensione o metrica renderanno il punto dati praticamente inutilizzabile nella suite di rapporti globale. Potrebbe anche causare problemi con l'attribuzione, come in questo esempio: se un utente riceve due &gt; valori per evar 10, uno che è «Internal Campaign» sulla proprietà A e l'altro che è una proprietà «Page Name'on &gt; property B, questo significa che il successo è ora suddiviso in «Internal Campaign» e «Page Name», che dovrebbe essere attivato su livelli diversi. Di conseguenza, in genere Adobe consiglia di utilizzare la cura VRS come soluzione alternativa &gt; per questo particolare problema.

## I segmenti utilizzati con suite di rapporti virtuali non dividono i dati in modo da confondere i tuoi utenti.

Riepilogo:

* La segmentazione dei dati da una suite di rapporti globale nelle suite di rapporti virtuali può creare risultati sfumati che potrebbero confondere alcuni utenti.
* Valuta in che modo i segmenti nelle suite di rapporti virtuali possono influenzare dimensioni e capacità come pagina di entrata, dominio di provenienza, percorsi ecc.

Ricorda che una suite di rapporti virtuale è solo un segmento applicato a una suite di rapporti; tutte le sfumature nei dati segmentati sono applicabili alle suite di rapporti virtuali. I segmenti (e quindi le suite di rapporti virtuali) possono essere utilizzati per suddividere i dati in modi che sembrano non intuitivi ai tuoi utenti Adobe Analytics.

Ad esempio, si supponga di disporre di due marchi, A e B, le cui proprietà digitali inviano dati in una suite di rapporti globale. Alcuni utenti passeranno da un sito Web al sito Web B e viceversa, e questo passaggio da uno all'altro è visibile nel percorso nella suite di rapporti globale. Tuttavia, se create suite di rapporti virtuali per marchi A e B, gli utenti che accedono alla suite di rapporti virtuale B possono vedere risultati non intuitivi per determinate dimensioni e metriche. Una visita introduttiva al marchio A e terminata sul marchio B non mostrerà alcuna pagina di inclusione nella suite di rapporti virtuale B, dato che la pagina di immissione per la visita cross-site è iniziata sul marchio A, che viene segmentata da questa suite di rapporti virtuale.

Un esempio simile riguarda «Numero visita». Nella suite di rapporti virtuale per il marchio B, gli utenti possono vedere alcuni visitatori che hanno una seconda, terza e quarta visita, ma nessuna prima visita. Ciò si verifica quando la prima visita del cliente deve essere il marchio A, e tutte le visite successive saranno al marchio B. Poiché i dati del marchio A non sono inclusi nella suite di rapporti virtuali, tutte le informazioni sulla prima visita, incluso il fatto che sono avvenute, non sono incluse in questa suite di rapporti virtuale.

Adobe consiglia di utilizzare i tag multisuite in questi scenari o in altre situazioni in cui parte del percorso del cliente potrebbe verificarsi all'esterno di una suite di rapporti virtuale in modo che possa confondere i vostri utenti. I tag con più suite consentono di tenere traccia di un percorso a livello di proprietà multipla in una suite di rapporti globale, ma forniscono anche ai singoli team la visualizzazione completa del percorso a un singolo livello di proprietà.

## Voi e gli utenti non dovete essere in grado di visualizzare le transazioni in diverse valute nazionali.

Riepilogo:

* Le suite di rapporti virtuali non possono attualmente generare report su una valuta diversa rispetto alla suite di rapporti su cui sono basate.
* Adobe Analytics consente di convertire la valuta in caso di rapporti, ma il tasso di cambio è basato sul giorno corrente, anche per i dati storici.

Le suite di rapporti virtuali non possono attualmente generare report su una valuta diversa rispetto alla suite di rapporti su cui sono basate. Se la tua azienda e i tuoi utenti Adobe Analytics eseguono l'analisi su una sola valuta, non si verifica un problema. Tuttavia, se avete bisogno di un'attività aziendale significativa per i diversi team regionali che devono essere in grado di visualizzare entrate e metriche simili nella propria valuta locale (che viene convertita in base al tasso di scambio al momento della raccolta dati), dovrete utilizzare i tag per più suite.

Questo consente di inviare simultaneamente i dati in Adobe Analytics in diverse valute. Con i tag per più suite, una transazione che si verifica nella versione giapponese dell'app può essere registrata nella suite globale in USD. Può essere convertito da JPY al tasso di cambio del giorno specificato, ma continua a essere visualizzato nella suite di rapporti in Giappone in JPY.

>[!NOTE]
>
>Mentre le suite di rapporti virtuali non consentono di convertire i dati delle entrate in un'altra valuta a una frequenza storica, puoi comunque convertire la valuta in una suite di rapporti virtuale su base ad hoc. Per applicare il tasso di cambio del giorno corrente ai dati storici, passate a Componenti &gt; Impostazioni rapporto.

## Puoi usare un singolo feed dati per ricevere tutti i dati da una suite di rapporti globale.

Riepilogo:

* I feed dati possono essere creati solo in base a suite di rapporti vere e proprio, non a suite di rapporti virtuali.
* Tuttavia, potete ricevere un feed dati da una suite di rapporti globale e quindi suddividerlo in base al marchio, alla proprietà, alla regione e così via.

I feed di dati consentono di ricevere un'esportazione giornaliera o oraria di tutti i dati di Adobe Analytics a un livello «event» o «hit». Poiché i feed dati non possono essere previamente segmentati prima di inviarli, utilizzando una suite di rapporti globale con suite di rapporti virtuali, puoi ricevere un feed dati solo per la suite di rapporti globale. Non puoi configurare feed dati per suite di rapporti virtuali.

Tuttavia, puoi configurare tutti i feed dati basati su suite di rapporti vere e propri. Dopo aver ricevuto questi Feed di dati, puoi segmentarli e suddividerli in qualsiasi configurazione utile. Ad esempio, dopo aver ricevuto un feed dati per una suite di rapporti globale, puoi caricare la porzione di quel feed dati che riguarda il tuo sito Web in un data warehouse. Puoi caricare simultaneamente la porzione che riguarda la tua app mobile in un data warehouse diverso.

Tuttavia, è possibile che alcuni campi precalcolati nel feed dati debbano essere ricalcolati dopo la ricezione. Vedere l'elemento 5 (sopra) per esempi di campi che devono essere ricalcolati durante il filtraggio di un feed di dati in base ad alcuni criteri.

Se l'organizzazione ha una necessità forte di singoli feed dati a marchio, proprietà, regione ecc. , potrebbe essere utile utilizzare i tag per più suite.

## Non utilizzate l'integrazione di Exchange (connettori dati) che consente un solo account Partner per suite di rapporti e non disponete di più account partner da integrare.

Riepilogo:

* Alcune integrazioni partner Adobe in Adobe Analytics sono limitate a un account partner per suite di rapporti.
* Alcune organizzazioni potrebbero desiderare di utilizzare più account partner in Adobe Analytics, che richiedono l'utilizzo di tag per più suite.

Adobe Exchange consente di integrare altre soluzioni tecnologiche e di marketing con Adobe Analytics. Esempi di integrazioni disponibili includono advertising advertising, email, VOC e call center. A causa di varianza nel modo in cui i dati vengono raccolti, presentati e integrati, alcuni dei partner Adobe che puoi decidere di utilizzare con Adobe Exchange limitano un'istanza della loro integrazione per suite di rapporti. Ogni istanza viene mappata su un account con il partner.

Un esempio è Google DCM. Molte aziende dispongono di più account DCM, che consentono marchi, unità aziendali, aree geografiche ecc. diverse. per gestire gli annunci visualizzati separatamente l'uno dall'altro. Tuttavia, quando integrate DCM con Adobe Analytics, potete utilizzare solo un account DCM per suite di rapporti. Non puoi integrare ciascuno di questi account DCM nella stessa suite di rapporti. Non è inoltre possibile impostare un'integrazione direttamente in una suite di rapporti virtuale.

Di conseguenza, l'assegnazione di tag per più suite è l'approccio preferito se i diversi team dell'organizzazione devono avere i dati del proprio account in Adobe Analytics per un partner Adobe Exchange. Se utilizzi o meno integrazioni Adobe Exchange in cui diversi gruppi gestiscono account diversi, controlla con il partner Adobe se sono consentiti più account per suite di rapporti.

>[!NOTE]
>
>Il termine «account» può essere diverso da quello dei fornitori. Nel contesto della tecnologia di marketing, in genere non fa riferimento a un singolo account utente, ma a un insieme di servizi resi disponibili a un intero team o a un'intera organizzazione. Pertanto, se avete più nomi utente che accedono al servizio di un partner Adobe, tutti questi nomi utente potrebbero appartenere allo stesso account.

>[!NOTE]
>
>Tutte le metriche «pre-clic» (riepilogate/aggregate) importate da un partner Adobe Exchange non sono disponibili per la segmentazione e pertanto potrebbero non essere visibili in una suite di rapporti virtuale. Esempi di tali metriche &gt; includono e-mail inviate o visualizzate ad impression, entrambe che si verificano non in-site/off-app e vengono importate in Adobe &gt; Analytics in un modulo aggregato.

## L'Utente non si basa molto sulle Origini dati di riepilogo a una proprietà, a un marchio, a un'area geografica, ecc. livello.

Riepilogo:

* ' Riepilogo origini datì consente di importare metriche aggregate in Adobe Analytics a livello di suite di rapporti.
* Lo spostamento a una suite di rapporti globale con suite di rapporti virtuali richiederà che tutte le operazioni di caricamento delle Origini dati di riepilogo si verifichino nella suite di rapporti globale.

' Riepilogo origini datì consente di importare metriche preaggregate in una suite di rapporti vera e propria in Adobe Analytics. Esempi dì Origini dati riepilogò includono metriche qualì Entrate offline'o «Visualizzazioni di pagina» che si sono verificate in un'altra soluzione prima della tua implementazione di Adobe Analytics. Poiché i caricamenti di Origini dati riepilogo contengono metriche aggregate, non possono essere segmentate. Di conseguenza, non vengono segmentati nelle suite di rapporti virtuali.

I tag per più suite offrono alla vostra organizzazione la possibilità di importare metriche aggregate a livello di suite di rapporti. Se il marchio A desidera importare ricavi offline, può farlo separatamente dal marchio B e questi dati saranno visualizzati nella suite di rapporti di un marchio A. Il marchio B potrebbe fare lo stesso. Se l'organizzazione utilizza o pianifica di utilizzare le Origini dati Riepilogo in una proprietà, marchio, regione, ecc. può essere utile utilizzare i tag per più suite invece di suite di rapporti virtuali.

## Passaggi da seguire se decidete di utilizzare VRS

Dopo aver letto le considerazioni qui sopra e aver deciso di rimuovere le chiamate server secondarie e utilizzare suite di rapporti virtuali, ecco cosa devi fare:

**Innanzitutto**, crea suite di rapporti virtuali per far corrispondere i dati nelle suite di rapporti secondarie/secondari. Segmento su una dimensione personalizzata come «brand», «platform». »» Scegli una dimensione che semplifica la distinzione di una proprietà digitale da un'altra e applica questi segmenti a VRS.

* Se state eseguendo la migrazione da un'implementazione esistente di tag per più suite di Adobe Analytics, ricordate di confrontare i segmenti delle suite di rapporti virtuali con le suite di rapporti secondarie esistenti prima di migrare gli utenti. Vuoi accertarti che i segmenti utilizzati nelle suite di rapporti virtuali siano corretti.

* Se necessario, regola i segmenti su cui si basano le suite di rapporti virtuali.

* As a best practice, use [segment stacking](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) wherever possible so you can edit a segment in one location and have it apply to all virtual report suites that use that segment. Ad esempio, se desidero creare una VRS per «utenti mobili dall'Europa» e un'altra per «utenti mobili dall'Asia», creare un segmento per gli utenti mobili e quindi separare segmenti per gli utenti europei e asiatici. In questo modo, se desideri aggiornare la definizione del segmento "utenti mobili", puoi farlo in un unico segmento senza dover aggiornare singolarmente ogni segmento di suite di rapporti virtuale.

* Potresti essere in grado di cercare set di dati mutualmente esclusivi nelle suite di rapporti virtuali. Ad esempio, potresti voler vedere «Domain A» e «Domain B» come suite di rapporti separate, e non desideri il traffico di un dominio A nella suite di rapporti del dominio B. In questo caso, usa un contenitore «hit» per i segmenti.

**Secondo**: dopo aver confermato che le suite di rapporti virtuali che hai creato sono impostate correttamente e risponderanno alle esigenze del tuo team, rimuovi gli ID di suite di rapporti secondari dalla tua implementazione.

Per rimuovere suite di rapporti secondarie:

* In Adobe Experience Platform Launch, premi la "x" accanto a qualsiasi suite di rapporti che non desideri più utilizzare.
* In Gestione dinamica dei tag individua la proprietà e lo strumento Adobe Analytics in questione. Nei campi ID account di produzione e ID account Staging, rimuovi eventuali ID suite di rapporti che non desideri utilizzare.
* In legacy JavaScript implementations, locate the `s.account` variable and remove any report suites that you no longer wish to use.

Per raccogliere dati dai siti e dalle app, puoi lasciare gli ID di suite di rapporti globali o principali. Nell'interfaccia di Adobe Analytics, puoi nascondere le suite di rapporti precedenti dai tuoi utenti tramite Admin (Amministratore) &gt; Company Settings (Impostazioni società).

Se non riuscite a modificare l'implementazione, collaborate con il team di account Adobe. Possono esplorare le opzioni per evitare che le chiamate server secondarie vengano elaborate da Adobe Analytics.