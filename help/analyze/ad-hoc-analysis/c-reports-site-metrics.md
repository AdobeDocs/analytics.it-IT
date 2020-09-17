---
description: Consente di visualizzare informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, il numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati, e dati quantitativi simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri rapporti basati sugli elementi.
title: Rapporti sulle metriche del sito
topic: Ad hoc analysis
uuid: 0730747a-216f-4a58-b62b-a9812968cde5
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '1373'
ht-degree: 1%

---


# Rapporti sulle metriche del sito

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

Consente di visualizzare informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, il numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati, e dati quantitativi simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri rapporti basati sugli elementi.

## Rapporti sulle metriche del sito {#concept_0639CA16551749A693F49ADED4842CCE}

Consente di visualizzare informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, il numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati, e dati quantitativi simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri rapporti basati sugli elementi.

I report delle metriche hanno una tendenza nel tempo. A questi rapporti potete applicare la granularità di ora e giorno della settimana. In alternativa, puoi analizzare il tempo trascorso sul tuo sito, acquisti, ricavi e metriche simili.

I seguenti rapporti Metriche del sito sono disponibili nel [!UICONTROL Site Metrics] menu.

## Rapporto Visualizzazioni pagina {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

Un rapporto con tendenze che mostra il numero di volte in cui le pagine del sito Web sono state visualizzate per il periodo di tempo selezionato (ora, giorno, settimana, mese, trimestre o anno). Una [!UICONTROL Page View] è una richiesta per un documento a pagina intera, anziché per un elemento di una pagina, ad esempio un&#39;immagine o un video. Ad esempio, se un singolo visitatore visualizza 15 pagine durante una visita, vengono conteggiate 15 visualizzazioni di pagina. Se un visitatore visualizza la stessa pagina tre volte durante una visita, vengono conteggiate tre visualizzazioni di pagina. Questo rapporto consente di tenere traccia delle visualizzazioni di pagina per ogni pagina del sito, nonché di un insieme di visualizzazioni di pagina per l’intero sito.

## Rapporto sulle visite {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Visualizza il numero di visite effettuate all’intero sito Web durante un periodo di tempo specificato. Una *visita* è una sequenza di visualizzazioni di pagina. Una visita inizia quando un visitatore carica una pagina e termina dopo 30 minuti di inattività. Una visita può durare diverse ore, purché il visitatore carichi almeno una pagina prima del timeout. Una visita non coincide necessariamente con una sessione del browser. Ad esempio, se un visitatore chiude il browser, riapre il browser e accede al sito cinque minuti dopo, viene riconosciuto come continuazione della stessa visita. Questo significa anche che se un visitatore fissa una pagina per 35 minuti, la visita sarà chiusa ed elaborata e una nuova visita inizierà se fa clic fino a un&#39;altra pagina. Le visite sono tracciate dai cookie. Una visita viene terminata dopo 12 ore di attività continua.

<!-- 

c_reports_visits.xml

 -->

In marketing reports and analytics, è possibile eseguire una [!UICONTROL Visits Report] pagina selezionata. Nell&#39;analisi ad hoc puoi segmentare i dati per visualizzare pagine specifiche.

## Rapporto Visitatori unici {#concept_39097C54E46C496CBAD537329DB3C84A}

Un rapporto con tendenze che mostra il numero di visitatori univoci che hanno eseguito l&#39;accesso al sito. Ogni visitatore viene conteggiato una volta, a prescindere dal numero di visite che la persona visita il sito Web.  Adobe utilizza una tecnologia di cookie-handshake in attesa di brevetto per distinguere un visitatore univoco da un visitatore di ritorno. Il cookie handshake supera i limiti nella tecnologia dei cookie del browser Internet.

<!-- 

c_reports_unique_visitors.xml

 -->

Puoi utilizzare questo rapporto per:

* Visualizzate il numero di persone diverse che hanno visualizzato il vostro sito Web in un determinato periodo di tempo.
* Visualizza i modelli di traffico recenti e scopri come le promozioni stanno portando visitatori unici sul tuo sito.
* Confronta il numero di visitatori univoci con il numero di visualizzazioni di pagina.

## Rapporto sui visitatori {#concept_7371DAB5DA474D03A2D1448F151E011B}

Mostra il numero di visitatori unici del sito per un&#39;ora, un giorno, una settimana, un mese, un trimestre o un anno selezionati. Un visitatore univoco viene conteggiato una sola volta per l&#39;intervallo di tempo selezionato. I visitatori che tornano al sito non vengono più conteggiati come utenti univoci finché l’intervallo di tempo non è scaduto.

<!-- 

c_reports_visitors.xml

 -->

Il valore totale visualizzato nella parte inferiore della tabella è la somma di tutte le visite per il periodo di tempo specificato e non riflette sempre il numero di visitatori univoci. Ad esempio, se eseguite un [!UICONTROL Daily Unique Visitors Report] periodo di tempo di diversi giorni, il totale può includere visitatori ripetuti, perché lo stesso visitatore potrebbe tornare il giorno successivo e essere conteggiato di nuovo. Tuttavia, se eseguite un [!UICONTROL Monthly Unique Visitors Report]oggetto, il valore nella colonna Totali riflette accuratamente il numero di visitatori univoci che sono arrivati durante il mese.

## Time Spent per Visit Report {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Mostra il tempo impiegato dai visitatori per visualizzare il sito durante ogni visita. Dispone inoltre di una statistica del tempo medio trascorso sul sito che mostra il tempo medio trascorso dalla visualizzazione del sito.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Utilizzate questo rapporto per:

* Identificare il periodo di permanenza dei visitatori sul sito.
* Identificazione del contenuto del sito e delle promozioni che suscitano interesse per i visitatori.
* Scopri perché hai un traffico elevato ma i visitatori se ne vanno immediatamente.

## Rapporto acquisti {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Visualizza i dati di riepilogo per Ricavi, Ordini e Unità. You can also view the [!DNL Purchase Conversion Funnel] report.

<!-- 

c_reports_purchases.xml

 -->

* **Entrate**: Consente di visualizzare i profitti lordi per i periodi di tempo selezionati. Gli esempi possono includere entrate nel mese di marzo, acquisti effettuati la settimana scorsa o entrate per oggi.
* **Ordini**: Mostra il numero di ordini effettuati sul sito Web durante il periodo di tempo specificato. Gli ordini possono contenere più prodotti.
* **Unità**: Mostra le unità totali ordinate per il periodo di tempo specificato.
* **Funnel** di conversione acquisto: Ideale per mostrare gli eventi di conversione sul sito se si verificano in un ordine specifico, ad esempio in un&#39;impostazione di vendita al dettaglio. Un rapporto funnel mostra le metriche di conversione per ogni fase del processo di conversione, nonché Ordini, Entrate e Unità.

## Rapporto Carrello acquisti {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Visualizza il numero di carrelli commerciali aperti durante il periodo di tempo specificato. Puoi eseguire rapporti per analizzare viste del carrello, aggiunte, rimozioni e pagamenti. Un carrello viene generalmente aperto quando un cliente seleziona un articolo per l&#39;acquisto, ma può verificarsi anche senza un articolo.

<!-- 

c_reports_shopping_cart.xml

 -->

È possibile utilizzare [!UICONTROL Carts Report] per:

* Determinare pattern, livelli alti o bassi nel numero di carrelli aperti sul sito.
* Esaminare specifici periodi di tempo apprendere ulteriori informazioni sulle metriche che hanno contribuito specificamente all&#39;apertura del carrello.

## Report eventi personalizzati {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

Le azioni di conversione sul sito che desiderate vengano completate dai visitatori. Queste azioni possono essere una registrazione, un abbonamento, un completamento del modulo lead, un avvio chat, un acquisto, una prenotazione o un sondaggio finito.

<!-- 

c_reports_custom_events.xml

 -->

Poiché ogni suite di rapporti di analisi è diversa, questo set di rapporti viene utilizzato in modo diverso per ciascun client. Un [!UICONTROL Custom Event] report può essere utilizzato come contatore che mostra il numero di volte in cui si verifica un evento. Ad esempio, se **[!UICONTROL event1]** è impostato per calcolare il numero di volte che un documento viene scaricato, il [!UICONTROL Custom Event] rapporto per l&#39;evento 1 mostra il numero totale di volte in cui si verifica l&#39;evento (o il download). Potete avere più rapporti sull&#39;evento personalizzati.

## Report di conversione {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Mostra i ricavi ottenuti da diversi aspetti del sito Web. Potete visualizzare rapporti che mostrano le entrate derivanti da campagne pubblicitarie, le entrate provenienti da clienti fedeli rispetto alle entrate provenienti dai nuovi clienti, una suddivisione delle entrate per prodotto e molti altri rapporti sulle entrate. I rapporti di conversione possono anche mostrare altri eventi di successo come clic di annunci pubblicitari, download o altri eventi.

<!-- 

c_reports_conversion.xml

 -->

I rapporti sulla conversione includono statistiche in tempo reale su tutte le attività importanti dei clienti, tra cui:

* Modelli di acquisto cliente
* Metriche del carrello acquisti, incluso abbandono
* Tassi di conversione cliente
* Pubblicità ed efficacia dei partner di canale
* Prestazioni delle campagne di marketing online e offline
* Metriche sulla fedeltà dei clienti
* Informazioni sui cicli di vendita

## Report canale di marketing {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

I rapporti sul canale di marketing mostrano l&#39;allocazione dei canali di primo e ultimo contatto, con metriche standard fondamentali come entrate, ordini e costi, che consentono di sapere quanto fatturato genera ogni canale. Puoi configurare le regole di definizione del canale in [!DNL Admin Console]e sono disponibili le API specifiche per i rapporti sul canale.

<!-- 

c_reports_marketing_channel.xml

 -->

**[!UICONTROL First or Last Touch Channel Report]**: Visualizza le metriche che mostrano i dati su un canale di primo o ultimo contatto specifico. In questi rapporti, puoi suddividere un canale e mostrare i dettagli di ciascun canale. Se  AdLens sono abilitati, nei rapporti sui canali marketing reports and analytics verranno visualizzate le classificazioni.

**[!UICONTROL First or Last Touch Channel Detail Reports]**: Visualizza dettagli quali i nomi delle pagine e i riferimenti, che vengono ricavati dai valori dei canali impostati nell&#39; [!UICONTROL Set the channel's value to] opzione al momento della configurazione delle regole. I rapporti sui dettagli dei canali consentono di esaminare attentamente i valori dei dettagli dei canali dal rapporto sulla panoramica.

Per ulteriori informazioni sulla configurazione del canale di marketing in marketing reports and analytics, consultate la Guida [di](/help/components/c-marketing-channels/analyze-mc.md) Marketing Channel.
