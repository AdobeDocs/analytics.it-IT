---
description: Visualizza le informazioni relative all'ordine in cui viene effettuato l'accesso alle pagine del tuo sito Web. Potete raccogliere informazioni su dove un visitatore va prima e dopo qualsiasi pagina visitata sul sito.
seo-description: Visualizza le informazioni relative all'ordine in cui viene effettuato l'accesso alle pagine del tuo sito Web. Potete raccogliere informazioni su dove un visitatore va prima e dopo qualsiasi pagina visitata sul sito.
seo-title: Rapporti sui percorsi
solution: Analytics
title: Rapporti sui percorsi
topic: Analisi ad hoc
uuid: 5881 cb 1 c -6 d 66-49 fe-ac 84-70 b 82662 acd 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporti sui percorsi

Visualizza le informazioni relative all'ordine in cui viene effettuato l'accesso alle pagine del tuo sito Web. Potete raccogliere informazioni su dove un visitatore va prima e dopo qualsiasi pagina visitata sul sito.

## Paths reports {#concept_CB32E270FB9E4D929C91FDFE428CB224}

Visualizza le informazioni relative all'ordine in cui viene effettuato l'accesso alle pagine del tuo sito Web. Potete raccogliere informazioni su dove un visitatore va prima e dopo qualsiasi pagina visitata sul sito.

I rapporti sui percorsi includono rapporti di analisi avanzati standard e facoltativi che mostrano il click-stream delle pagine visualizzate. Potete individuare percorsi completi, tracciati più lunghi e percorsi più popolari; spiegare il flusso di pagina, il abbandono e l'effetto grafico, visualizzare pattern nuovi e cambiati nel tempo; e analizzare i percorsi di entrata e uscita.

** [!UICONTROL Next Page Flow] ** or ** [!UICONTROL Next Site Flow]**: Displays a two-level-deep branching graphic of a selected page (or section, department, and so on), that your visitors view after moving away from the selected page. Utilizzate questo rapporto per analizzare e identificare i passaggi seguiti dai visitatori più spesso dopo la visualizzazione di una pagina selezionata. Puoi:

* Scopri i passaggi che vengono eseguiti più frequentemente dopo la visualizzazione di una pagina selezionata.
* Ottimizzate la progettazione del percorso del sito per un funnel del traffico verso una pagina obiettivo desiderata.
* Identificare dove vanno i visitatori rispetto alle pagine obiettivo desiderate.

** [!UICONTROL Next Page] ** (or next categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed after seeing a selected page. Ad esempio, quando selezioni e reattivi l'intero sito, il rapporto mostra le dieci pagine di destinazione più importanti, con le cinque pagine più popolari elencate sotto ciascuna pagina di destinazione. Questi dati possono aiutarti a capire quali contenuti, funzionalità e altri dati spingono i visitatori a spostarsi nel tuo sito.

** [!UICONTROL Previous Page Flow] ** (or other previous categories flow): Displays two levels of the most popular pages that your visitors view before the selected page. Il rapporto evidenzia anche quando i visitatori accedono al sito.

** [!UICONTROL Previous Page] ** (or other previous categories): Provides detailed site path analysis by showing you the pages on your site that visitors viewed before seeing a selected page on your site.

** [!UICONTROL Fallout] **: Displays the visit attrition and conversion rates between each checkpoint you define. I passaggi sono organizzati dall'alto verso il basso, con numeri e percentuali grezzi mostrati a sinistra, nonché percentuali di conversione e abbandono a destra.

See [Fallout Report](../../analyze/ad-hoc-analysis/c-reports-paths.md#concept_0ED452F3B1D04A19A59DD04D76D20347) for more information.

** [!UICONTROL Path Length] **: Shows how deep visitors browse into your site (both by percentage and by total count). In altre parole, il rapporto indica il numero di pagine che il visitatore medio visualizza prima di uscire.

** [!UICONTROL Page Analysis] **: Contains a subset of reports that let you analyze the following:

* ** [!UICONTROL Page Summary / Site Category Summary] **: Tells you everything you need to know about the page report. Raccoglie e organizza informazioni specifiche sulla pagina su una singola pagina e la visualizza in un unico rapporto.
* ** [!UICONTROL Reloads] **: Shows the number of times individual pages were reloaded by visitors.
* ** [!UICONTROL Time Spent on Page / Site Category] **: Displays the length of time that visitors browse individual pages in your site. Il tempo trascorso è diviso in dieci categorie: meno di 15 secondi, 15-30 secondi, 30-60 secondi, 1-3 minuti, 3-5 minuti, 5-10 minuti, 10-15 minuti, 15-20 minuti, 20-30 minuti e superiori a 30 minuti.
* ** [!UICONTROL Clicks to Page] **: Identifies the number of clicks visitors used to access each page in your site. La profondità per una pagina viene misurata contando il numero di pagine visualizzate prima.

** [!UICONTROL Entries & Exits] **: The [!UICONTROL Entry Page] report shows you, by percentage and by total visits, which pages on your site are the first ones seen by new visitors. Potete visualizzare:

* ** [!UICONTROL Entry Pages] ** (or sections): Displays, by percentage and by total visits, which pages on your site are the first pages seen by a new visitor. Potete usare questo rapporto per identificare quali delle pagine Web sono i punti di ingresso più frequenti, ottimizzare i punti di ingresso principali sul sito e indirizzare il traffico verso i messaggi chiave.
* ** [!UICONTROL Original Entry Pages] **: Shows the first page viewed for first-time visitors to your site. Ogni utente viene conteggiato solo una volta, a meno che non eliminino i cookie o non venga tracciato con i cookie.
* ** [!UICONTROL Single Page Visits] **: Shows pages that are most often both the entry and exit pages for visitor browsing sessions.
* ** [!UICONTROL Exit Pages] **: Displays, by percentage and by total visits, the pages on your site that were the last pages visitors viewed before leaving your site.

## Fallout Report {#concept_0ED452F3B1D04A19A59DD04D76D20347}

The [!UICONTROL Fallout Report] shows where visitors leave (fallout) and continue through (fallthrough) a pre-specified sequence of pages. Vengono visualizzati i tassi di conversione e abbandono tra ogni passaggio. Ad esempio, puoi tenere traccia dei punti di abbandono di un visitatore durante un processo di acquisto. È possibile selezionare un punto iniziale e un punto finale e aggiungere punti intermedi per creare un percorso di navigazione nel sito Web.

<!-- 

c_reports_fallout.xml

 -->

Puoi analizzare i dati di abbandono a livello di Visita o Visitatore. Puoi anche vedere un tracciato con tendenze che mostra un grafico dell'abbandono in un periodo specifico. Puoi impostare singoli o gruppi di pagine come punti di controllo del rapporto oppure aggiungere qualsiasi dimensione o metrica in qualsiasi combinazione o sequenza. Puoi anche utilizzare le categorie configurate in reporting e analisi di marketing come punti di controllo in questo rapporto.

Questo rapporto è utile per analizzare:

* I tassi di conversione tramite specifici processi sul sito (ad esempio, acquisto o registrazione).
* Flussi di traffico generali di ambito più ampio: per le persone che hanno visto la pagina Home, questo flusso mostra quanti hanno poi fatto una ricerca e quanti sono quindi passati a uno specifico articolo.
* Correlazioni tra eventi attivati sul sito. Le correlazioni mostrano la percentuale di persone che, dopo aver letto l’informativa sulla privacy, proseguono con l’acquisto di un prodotto.

## Run a Fallout Report {#task_3594E8BE55964C1C8B0BEC8DEABF82D3}

Steps to run a [!UICONTROL Fallout Report].

<!-- 

t_fallout.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL New Report]** &gt; **[!UICONTROL Fallout.]**

   Other Fallout reports are found in **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]**.

1. (Optional) Drag a segment to the [!UICONTROL Drop Segment Here] field, if you want to filter the data by a specific segment.
1. Drag any dimension item to the [!UICONTROL Drop Event or Dimension Items Here] field.
1. Click **[!UICONTROL Show Fallout At]**Visit or Visitor level, depending on whether you want to view fallout at the visit level, or across visitor sessions.
1. Aggiungi al rapporto elementi dimensionali, ad esempio pagine.

## Assign Pages to a Fallout Report {#task_B386289703494FA7B5A40FF9F97CB537}

Passaggi per assegnare le pagine a un rapporto di abbandono.

<!-- 

t_fallout_assign_pages.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Fallout]**.
1. From the [!UICONTROL Dimensions] pane, locate the pages to add, then drag them to the [!UICONTROL Drop Event or Dimension Here] field.

## Fallout Report - Field Descriptions {#reference_74255CC8D6134F349FEBFEC72934C866}

Field descriptions for the [!UICONTROL Fallout] report.

<!-- 

r_dsc_fallout.xml

 -->

| Campo | Descrizione |
|--- |--- |
| Mostra abbandono a visita o a livello visitatore | Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello di visitatore, tra le visite. I rapporti Analisi sito, Flusso e Abbandono sono abilitati per i percorsi dei visitatori. Modificando questa impostazione si ripristina il rapporto, vincolando i dati alla selezione. |
| Totale successo | Un indicatore totale del successo. Questo valore riflette il valore nell'ultimo punto di controllo del percorso. |
| Totale successo % | Totale totale della percentuale di visitatori provenienti da ogni punto di controllo. |
| Punto di controllo % | Percentuale di successo tra i punti di controllo. (Non cumulativo). |
| Includi tutte le visite | Aggiunge tutte le visite come punto di controllo iniziale. |
| Abbandono | Consente di visualizzare le pagine visualizzate dopo che il visitatore è uscito dal percorso del punto di controllo specificato. |
| Abbandono | Consente di visualizzare le pagine visualizzate nel passaggio successivo del percorso del punto di controllo specificato. |
