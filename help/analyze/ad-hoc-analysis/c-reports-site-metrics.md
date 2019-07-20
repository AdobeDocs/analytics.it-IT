---
description: Visualizza informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati e dati quantificati simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri report basati sugli elementi.
seo-description: Visualizza informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati e dati quantificati simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri report basati sugli elementi.
seo-title: Rapporti sulle metriche del sito
solution: Analytics
title: Rapporti sulle metriche del sito
topic: Analisi ad hoc
uuid: 0730747 a -216 f -4 a 58-b 62 b-a 9812968 cde 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporti sulle metriche del sito

Visualizza informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati e dati quantificati simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri report basati sugli elementi.

## Site Metrics reports {#concept_0639CA16551749A693F49ADED4842CCE}

Visualizza informazioni quantitative sul sito Web, ad esempio quante volte i visitatori hanno guardato determinate pagine, numero di acquisti complessivi effettuati da pagine specifiche, quando sono arrivati e dati quantificati simili. Ciascuno di questi rapporti è una metrica che puoi inserire in altri report basati sugli elementi.

I report delle metriche vengono tendenze nel tempo. Potete applicare una granularità di tempo e giorni a tali rapporti. In alternativa, puoi analizzare il tempo trascorso sul sito, acquisti, ricavi e metriche simili.

The following Site Metrics reports are available in the [!UICONTROL Site Metrics] menu.

## Page Views Report {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

Rapporto con tendenze che mostra quante volte sono state visualizzate le pagine del sito Web per il periodo di tempo selezionato (ora, giorno, settimana, mese, trimestre o anno). A [!UICONTROL Page View] is a request for a full page document, rather than an element of a page, such as an image or video. Ad esempio, se durante una visita un singolo visitatore visualizzerà 15 pagine, vengono conteggiate 15 visualizzazioni di pagina. Se durante una visita un visitatore visualizza la stessa pagina tre volte, vengono conteggiate tre visualizzazioni di pagina. Questo rapporto consente di tenere traccia delle visualizzazioni di pagina per ogni pagina sul sito e di un'aggregazione di visualizzazioni di pagina per l'intero sito.

## Visits Report {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Visualizza il numero di visite effettuate all'intero sito Web nel corso di un periodo di tempo specificato. A *visit* is a sequence of page views. Una visita inizia quando un visitatore carica una pagina e la visita termina dopo 30 minuti di inattività. Una visita può durare diverse ore, purché il visitatore carichi almeno una pagina prima del timeout. Una visita non corrisponde necessariamente a una sessione del browser. Ad esempio, se un visitatore chiude il browser, riapre il browser e accede al sito cinque minuti dopo, viene riconosciuto come continuazione della stessa visita. Ciò significa anche che se un visitatore si sofferma su una pagina per 35 minuti, la visita sarà chiusa ed elaborata e verrà avviata una nuova visita se fa clic su un'altra pagina. Le visite vengono tracciate dai cookie. Una visita viene terminata dopo 12 ore di attività continua.

<!-- 

c_reports_visits.xml

 -->

In marketing reports and analytics, you can run a [!UICONTROL Visits Report] on a selected page. In analisi ad hoc, puoi segmentare i dati per visualizzare pagine specifiche.

## Unique Visitors Report {#concept_39097C54E46C496CBAD537329DB3C84A}

Report con tendenze che mostra il numero di visitatori unici che hanno eseguito l'accesso al sito. Ogni visitatore viene conteggiato una volta a prescindere da quante volte la persona visita il sito Web. Adobe utilizza una tecnologia di tipo cookie-handshake in sospeso per distinguere un visitatore univoco da un visitatore di ritorno. L'handshake dei cookie non presenta limiti nella tecnologia dei cookie del browser Internet.

<!-- 

c_reports_unique_visitors.xml

 -->

Puoi utilizzare questo rapporto per:

* Vedi il numero di persone che hanno visualizzato il tuo sito Web in un determinato periodo di tempo.
* Visualizza i pattern di traffico recenti e scopri in che modo le promozioni portano visitatori unici sul tuo sito.
* Confronta il numero di visitatori univoci con il numero di visualizzazioni di pagina.

## Visitors Report {#concept_7371DAB5DA474D03A2D1448F151E011B}

Mostra il numero di visitatori unici al tuo sito per un'ora, giorno, settimana, mese, trimestre o anno selezionato. Un visitatore univoco viene conteggiato solo una volta per l'intervallo di tempo selezionato. I visitatori che ritornano al sito non vengono considerati nuovamente come utenti unici fino alla trascorsa del periodo di tempo.

<!-- 

c_reports_visitors.xml

 -->

Il valore totale visualizzato in fondo alla tabella è la somma di tutte le visite per il periodo di tempo specificato e non corrisponde sempre al numero di visitatori unici. For example, if you run a [!UICONTROL Daily Unique Visitors Report] with a time frame of several days, the total can include repeat visitors, because the same visitor might return on the next day and be counted again. However, if you run a [!UICONTROL Monthly Unique Visitors Report], the value in the Totals column accurately reflects how many unique visitors came during the month.

## Time Spent per Visit Report {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Mostra il tempo impiegato dai visitatori per visualizzare il sito durante ogni visita. Dispone inoltre di una statistica Media dedicata al sito che mostra il tempo medio impiegato dai visitatori per la visualizzazione del sito.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Utilizzate questo rapporto per:

* Identificare il tempo di permanenza dei visitatori sul sito.
* Identificazione del contenuto del sito e delle promozioni che attivano l'interesse dei visitatori.
* Scopri perché il traffico è elevato, ma i visitatori escono immediatamente.

## Purchases Report {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Visualizza i dati di riepilogo per Revenue (Entrate), Orders (Ordini) e Units (Unità). You can also view the [!DNL Purchase Conversion Funnel] report.

<!-- 

c_reports_purchases.xml

 -->

* **Entrate**: Consente di visualizzare i profitti lordi per periodi di tempo selezionati. Gli esempi possono includere entrate nel mese di marzo, acquisti effettuati la settimana scorsa o entrate per oggi.
* **Ordini**: Mostra il numero di ordini effettuati sul tuo sito Web nel periodo di tempo specificato. Gli ordini possono avere più prodotti.
* **Unità**: Mostra le unità totali ordinate per il periodo di tempo specificato.
* ** Purchase Conversion Funnel**: Ideale per visualizzare eventi di conversione sul sito se si verificano in un ordine specifico, ad esempio in un'impostazione per la vendita al dettaglio. Un rapporto funnel mostra le metriche di conversione per ogni passaggio del processo di conversione, nonché Ordini, Revue e Unità.

## Shopping Cart Report {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Visualizza il numero di carrelli della spesa che vengono aperti durante il periodo di tempo specificato. Puoi eseguire rapporti per analizzare visualizzazioni del carrello, aggiunte, rimozioni e pagamenti. Un carrello acquisti viene generalmente aperto quando un cliente seleziona un elemento per l'acquisto, ma può verificarsi anche senza un elemento.

<!-- 

c_reports_shopping_cart.xml

 -->

You can use the [!UICONTROL Carts Report] to:

* Consente di determinare pattern, alti o vertici nel numero di carrelli aperti sul sito.
* Esaminate specifici periodi di tempo per ulteriori informazioni sulle metriche che hanno contribuito in modo specifico all'apertura del carrello.

## Custom Events Report {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

Le azioni di conversione sul sito che desiderate vengano completate dai visitatori. Queste azioni possono essere registrazioni, iscrizione, completamento del modulo lead, avvio chat, acquisto, prenotazione o sondaggio finito.

<!-- 

c_reports_custom_events.xml

 -->

Poiché ogni suite di rapporti di analisi è diversa, questo set di report viene utilizzato diversamente per ogni client. [!UICONTROL Custom Event] Un rapporto può essere usato come contatore che mostra quante volte si verifica un evento. For example, if **[!UICONTROL event1]** is set to count the number of times a document is downloaded, then the [!UICONTROL Custom Event] report for Event 1 shows the total number of times the event (or download) occurs. Potete avere più rapporti sull'evento personalizzato.

## Conversion Reports {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Mostra i ricavi generati da diversi aspetti del sito Web. Potete visualizzare rapporti che mostrano entrate derivanti da campagne pubblicitarie, entrate da clienti fedeli rispetto alle entrate dei nuovi clienti, una suddivisione delle entrate per prodotto e molti altri rapporti sulle entrate. I rapporti di conversione possono anche mostrare altri eventi di successo quali clic pubblicitario, download o altri eventi.

<!-- 

c_reports_conversion.xml

 -->

La conversione di conversione include statistiche in tempo reale su tutte le attività importanti del cliente, tra cui:

* Pattern di acquisto dei clienti
* Metriche del carrello, compresa l'abbandono
* Tassi di conversione dei clienti
* Efficacia della pubblicità e dei partner di canale
* Prestazioni delle campagne di marketing online e offline
* Metriche sulla fedeltà dei clienti
* Approfondimenti sui cicli di vendita

## Marketing Channel Reports {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

I rapporti sul canale di marketing mostrano la prima allocazione del canale di tocco, con metriche standard come entrate, ordini e costi, consentendo di sapere quante entrate vengono generate da ogni canale. You configure channel definition rules in the [!DNL Admin Console], and APIs specific for the channel reports are available.

<!-- 

c_reports_marketing_channel.xml

 -->

** [!UICONTROL First or Last Touch Channel Report] **: Displays metrics showing data about a specific first-touch or last-touch channel. In questi rapporti, puoi suddividere un canale e mostrare i dettagli di ogni canale. Se adlens è abilitato, visualizzerai classificazioni nei rapporti di marketing e nei rapporti sui canali di analisi.

** [!UICONTROL First or Last Touch Channel Detail Reports] **: Displays details such as page names and referrers, which is taken from the channel values you set up in the [!UICONTROL Set the channel's value to] option when configuring rules. I rapporti sui dettagli dei canali ti permettono di esaminare attentamente i valori dei dettagli del canale dal rapporto Panoramica.

For more in-depth information about configuring the Marketing Channel in marketing reports and analytics, see the [Marketing Channel Help](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html) system.
