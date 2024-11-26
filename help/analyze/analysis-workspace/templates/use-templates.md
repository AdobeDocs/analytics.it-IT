---
description: Panoramica sull’utilizzo dei modelli in Analysis Workspace.
title: Utilizzare i modelli
feature: Analysis Workspace
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: e98458a96e9950ffab40876b80a9e799a9182e6a
workflow-type: tm+mt
source-wordcount: '18028'
ht-degree: 7%

---

# Utilizzare i modelli

I modelli (o modelli aziendali) in Analysis Workspace forniscono informazioni rapide sugli scenari di reporting più comuni. Di seguito sono riportati alcuni esempi di domande a cui è possibile rispondere con i modelli:

* quante persone visitano il sito
* quanti di questi visitatori sono visitatori univoci (conteggiati una sola volta)
* come sono arrivati al sito (ad esempio, se hanno seguito un collegamento o ci sono arrivati direttamente)
* quali parole chiave hanno utilizzato i visitatori per cercare il contenuto del sito
* per quanto tempo i visitatori sono rimasti su una determinata pagina o sull’intero sito
* su quali collegamenti i visitatori hanno fatto clic e quando hanno lasciato il sito
* quali canali di marketing sono più efficaci nel generare ricavi o eventi di conversione
* quanto tempo hanno trascorso a guardare un video
* quali browser e dispositivi hanno utilizzato per visitare il sito

Le informazioni seguenti descrivono come accedere e utilizzare i modelli dalla scheda [!UICONTROL Templates] in Analysis Workspace.

## Accedere ed eseguire un modello

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**].

   <!--update screenshot -->

   ![Scheda Rapporti](assets/view-prebuilt-reports.png)

1. Nella sezione [!UICONTROL **Modelli**] selezionare una delle schede seguenti:

   * **[!UICONTROL Adobe templates]**: mostra tutti i modelli forniti da Adobe.

   * **[!UICONTROL _login_company_name _modelli]**: mostra tutti i modelli aziendali creati per nell&#39;organizzazione.

     I modelli aziendali possono essere creati solo da un amministratore. Per ulteriori informazioni sulla creazione di un modello aziendale, vedere [Creare e gestire modelli](/help/analyze/analysis-workspace/reports/create-company-reports.md).

1. Scegli se visualizzare i modelli in una vista a colonne o in una vista a schede selezionando l&#39;icona della vista a colonne ![icona della vista a colonne](assets/column-view-icon.png) o l&#39;icona della vista a schede ![icona della vista a schede](assets/card-view-icon.png).

1. Nel campo di ricerca, iniziare a digitare il nome del modello che si desidera trovare, quindi selezionarlo dall&#39;elenco dei modelli. Puoi anche effettuare ricerche nell’elenco dei modelli per proprietà, eVar e numero evento. <!-- still true? -->

   Oppure

   Selezionare la categoria di modello che si desidera visualizzare, quindi selezionare il modello dall&#39;elenco dei modelli.

   >[!TIP]
   >
   >Per spostarti nel menu utilizzando i tasti freccia, premi il tasto Barra obliqua (/), quindi premi il tasto Freccia giù. Premi Invio per caricare il modello selezionato.

   Per un elenco dei modelli disponibili, vedere la sezione [Modelli disponibili](#available-reports) di seguito.

1. (Facoltativo) Visualizza e utilizza modelli che contengono componenti non disponibili nella suite di rapporti. Per impostazione predefinita, gli unici modelli visualizzati sono quelli che utilizzano componenti disponibili nella suite di rapporti. <!--does this apply to AA? -->

## Creare un progetto basato su un modello {#use-reports}

Un modello potrebbe non soddisfare esattamente le tue esigenze, ma può avvicinarti. In questi casi, puoi utilizzare il modello come punto di partenza e personalizzarlo in base alle tue esigenze.

Se si esce da un modello dopo aver apportato modifiche, viene richiesto di salvare o eliminare le modifiche. Quando si salvano le modifiche apportate a un modello, questo viene salvato come nuovo progetto.

Per personalizzare un modello e salvarlo come progetto:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Workspace**].

1. Selezionare la scheda [!UICONTROL **Modelli**].

1. Seleziona il modello da visualizzare. Ad esempio, in [!UICONTROL **Più popolari**], seleziona il modello [!UICONTROL **Pagine**].

   ![Rapporto Pagine](assets/pages-report.png)

1. Il modello Pagine, visualizzato in Analysis Workspace, mostra due [visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Grafico a barre](/help/analyze/analysis-workspace/visualizations/bar.md) e [Numero riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) e una [Tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). La metrica utilizzata è Occorrenze.
1. Esegui una delle operazioni seguenti:

   * Visualizza il modello.
   * Puoi trascinare uno o più segmenti nella zona di rilascio Segmento, nella parte superiore. Ad esempio, trascina il segmento [!UICONTROL **Clienti mobile**] e visualizza i risultati.
   * Modifica l’intervallo di date andando sul calendario in alto a destra.
   * Aggiungi suddivisioni dimensionali, trascina altre metriche e in genere personalizza il modello in base alle tue esigenze.

1. (Facoltativo) Salva il modello come progetto selezionando [!UICONTROL **Progetto**] > [!UICONTROL **Salva**].

   Il modello viene salvato come nuovo progetto e non modifica il modello esistente. Per ulteriori informazioni sul salvataggio dei progetti, vedere [Salva progetti](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Modelli disponibili

Per accedere a tutti i modelli predefiniti disponibili:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Workspace**], quindi la scheda [!UICONTROL **Modelli**].

   I modelli predefiniti sono organizzati per categoria.

   <!--add screenshot-->

1. Selezionare una categoria per visualizzare i modelli al suo interno.

   Le sezioni seguenti corrispondono alle categorie disponibili e forniscono informazioni su ciascun modello.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

### Most popular (Più popolari) {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--training"
>title="Modello per le esercitazioni"
>abstract="Scopri la terminologia e i passaggi comuni di Analysis Workspace per creare la tua prima analisi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--pagesRankedReport"
>title="Identifica le pagine più popolari e meno popolari."
>abstract="**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui sono più interessati.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--pageViewsOvertimeReport"
>title="Visualizzare il numero totale di visualizzazioni di pagina. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitsOvertimeReport"
>title="Visualizza il numero totale di visite. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitorsOvertimeReport"
>title="Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentino o diminuiscano nel tempo o rispetto a un periodo precedente.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare se una campagna di marketing lanciata di recente è riuscita ad attirare nuove persone sul sito confrontando visitatori univoci prima e dopo il lancio della campagna. Oppure puoi confrontare il numero di persone che visitano il sito durante le festività anno su anno.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--keyMetricsReport"
>title="Visualizza un rapporto che mostra affiancate le metriche di visualizzazioni di pagina, visite e visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che che visitano il sito, del numero di volte in cui sono state visitate le pagine e del numero di sessioni.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell&#39;anno o prima e dopo l&#39;esecuzione di campagne di marketing. <br/>Questo modello utilizza la dimensione Giorno, la metrica Visualizzazioni pagina, la metrica Visite e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--siteSectionRankedReport"
>title="Visualizza le sezioni più popolari o con le prestazioni più elevate del sito."
>abstract="**Questo può aiutarti** a capire meglio quali sezioni del tuo sito sono più visitate.<br>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali prodotti o servizi fornisci generano il maggior interesse.<br/>Questo modello utilizza la dimensione Sezione sito e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--next-page-report"
>title="Visualizzare i luoghi più comuni in cui le persone vanno immediatamente dopo la visita o immediatamente prima di visitare un determinato luogo."
>abstract="**Questo ti aiuta** a capire come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se la progettazione o il layout della pagina possa essere ottimizzato per indirizzare gli utenti a pagine più desiderate, ad esempio una pagina per effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni sulla pagina corrente possano fornire la direzione o le azioni che le persone stanno cercando quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti richiedono collegamenti più prominenti alla pagina corrente.<br/>Questo modello utilizza il pannello Elemento successivo o precedente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--campaignRankedReport"
>title="Visualizza i collegamenti più efficaci per indirizzare il traffico verso il tuo sito."
>abstract="**Questo può aiutarti** a capire meglio quali codici di tracciamento (e i collegamenti a essi associati) sono stati più utilizzati per accedere al tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare la tua strategia per la posizione in cui aggiungi collegamenti al tuo sito.<br/>Questo modello utilizza la dimensione Codice di tracciamento e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--productsRankedReport"
>title="Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un arco di tempo."
>abstract="**Questo ti aiuta** a capire quali prodotti sono più richiesti o meno.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio modificare le tue strategie di marketing per promuovere prodotti dalle prestazioni elevate o per migliorare o interrompere prodotti dalle prestazioni insoddisfacenti. Puoi anche regolare l’inventario dei prodotti in base all’analisi dei dati.<br/>Questo modello utilizza la dimensione Prodotto e la metrica Ordini."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--lastTouchChannelRankedReport"
>title="Visualizza i canali di marketing più recenti con cui i visitatori fanno riferimento durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a capire quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno causato conversioni.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.<br/>Questo modello utilizza la dimensione Canale di ultimo contatto e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--lastTouchChannelDetailRankedReport"
>title="Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a capire non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito che hanno generato conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.<br/>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto e la metrica Visitatori univoci. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--revenueOvertimeReport"
>title="Visualizza l&#39;importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a capire come i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi dimensionali hanno contribuito ai ricavi.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano più ricavi.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ricavi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--ordersOvertimeReport"
>title="Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo ti aiuta** a comprendere meglio come aumenta o diminuisce nel tempo l&#39;interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quali clienti o aree geografiche stanno effettuando il maggior numero di ordini e come questi ultimi tendono nel tempo.<br/>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo il lancio della campagna. Oppure puoi confrontare gli ordini relativi alle festività su base annua.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ordini."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--unitsOvertimeReport"
>title="Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo ti aiuta** a capire meglio come le vendite unitarie aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quali clienti o aree geografiche acquistano più unità e come queste vendite unitarie tendono nel tempo.<br/>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando le vendite unitarie prima e dopo l&#39;avvio della campagna. In alternativa, è possibile confrontare le vendite unitarie annuali durante le festività.<br/>Questo modello utilizza la dimensione Giorno e la metrica Unità."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Esercitazione**] | Scopri la terminologia e i passaggi comuni di Analysis Workspace per creare la tua prima analisi |
| [!UICONTROL **Pagine**] | <!--duplicated in Engagement section--> Identifica le pagine più popolari e meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui sono più interessati.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.</p><p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Engagement section--> Visualizzare il numero totale di visualizzazioni di pagina. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Page Views](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visite**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visite. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visits](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitatori**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentino o diminuiscano nel tempo o rispetto a un periodo precedente.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare se una campagna di marketing lanciata di recente è riuscita ad attirare nuove persone sul sito confrontando visitatori univoci prima e dopo il lancio della campagna. Oppure puoi confrontare il numero di persone che visitano il sito durante le festività anno su anno.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Engagement section--> Visualizza un rapporto che mostra affiancate le metriche di visualizzazioni di pagina, visite e visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che che visitano il sito, del numero di volte in cui sono state visitate le pagine e del numero di sessioni.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell&#39;anno o prima e dopo l&#39;esecuzione di campagne di marketing. </p><p>Questo modello utilizza la [dimensione Giorno](/help/components/dimensions/day.md), [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), [metrica Visite](/help/components/metrics/visits.md) e [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Sezioni del sito**] | Visualizza le sezioni più popolari o con le prestazioni più elevate del sito. <p>**Questo può aiutarti** a capire meglio quali sezioni del tuo sito sono più visitate.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali prodotti o servizi fornisci generano il maggior interesse.</p> <p>Questo modello utilizza la [dimensione Sezione sito](/help/components/dimensions/site-section.md) e la [metrica Visite](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Pagina successiva e precedente**] | Visualizzare i luoghi più comuni in cui le persone vanno immediatamente dopo la visita o immediatamente prima di visitare un determinato luogo. <p>**Questo ti aiuta** a capire come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se la progettazione o il layout della pagina possa essere ottimizzato per indirizzare gli utenti a pagine più desiderate, ad esempio una pagina per effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni sulla pagina corrente possano fornire la direzione o le azioni che le persone stanno cercando quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti richiedono collegamenti più prominenti alla pagina corrente.</p><p>Questo modello utilizza il [pannello elemento successivo o precedente](/help/analyze/analysis-workspace/c-panels/next-previous.md).</p> |
| [!UICONTROL **Campagne (codice di tracciamento)**] | Visualizza i collegamenti più efficaci per indirizzare il traffico verso il tuo sito. <p>**Questo può aiutarti** a capire meglio quali codici di tracciamento (e i collegamenti a essi associati) sono stati più utilizzati per accedere al tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio modificare la tua strategia per la posizione in cui aggiungi collegamenti al tuo sito.</p><p>Questo modello utilizza la dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md) e la metrica [Visite](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Prodotti**] | Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un arco di tempo. <p>**Questo ti aiuta** a capire quali prodotti sono più richiesti o meno.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio modificare le tue strategie di marketing per promuovere prodotti dalle prestazioni elevate o per migliorare o interrompere prodotti dalle prestazioni insoddisfacenti. Puoi anche regolare l’inventario dei prodotti in base all’analisi dei dati.</p><p>Questo modello utilizza la [dimensione prodotto](/help/components/dimensions/product.md) e la [metrica ordini](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Canale di ultimo contatto**] | Visualizza i canali di marketing più recenti con cui i visitatori fanno riferimento durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a capire quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno causato conversioni.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.</p><p>Questo modello utilizza la [dimensione Canale di ultimo contatto](/help/components/dimensions/last-touch-channel.md) e la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Dettaglio del canale di ultimo contatto**] | Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a capire non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito che hanno generato conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio allocare più risorse ai canali con prestazioni elevate o allocare meno risorse ai canali con prestazioni insoddisfacenti.</p><p>Questo modello utilizza la dimensione [Dettaglio canale di ultimo contatto](/help/components/dimensions/last-touch-detail.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Ricavi**] | Visualizza l&#39;importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti.<p>**Questo può aiutarti** a capire come i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi dimensionali hanno contribuito ai ricavi.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano più ricavi.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Revenue](/help/components/metrics/revenue.md).</p> |
| [!UICONTROL **Ordini**] | Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo ti aiuta** a comprendere meglio come aumenta o diminuisce nel tempo l&#39;interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quali clienti o aree geografiche stanno effettuando il maggior numero di ordini e come questi ultimi tendono nel tempo.</p><p>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo il lancio della campagna. Oppure puoi confrontare gli ordini relativi alle festività su base annua.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Orders](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Unità**] | Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo ti aiuta** a capire meglio come le vendite unitarie aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quali clienti o aree geografiche acquistano più unità e come queste vendite unitarie tendono nel tempo.</p><p>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando le vendite unitarie prima e dopo l&#39;avvio della campagna. In alternativa, è possibile confrontare le vendite unitarie annuali durante le festività.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Units](/help/components/metrics/units.md).</p> |

### Coinvolgimento {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visualizzare il tempo medio trascorso dagli utenti prima di un evento di successo."
>abstract="**Questo può aiutarti** a comprendere meglio quanto tempo impiegano i visitatori per eseguire un&#39;azione desiderata, ad esempio per effettuare un acquisto.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio valutare se le modifiche al tuo sito migliorano la capacità dei visitatori di raggiungere rapidamente un evento di successo.<br/>Questo modello utilizza la dimensione Tempo precedente all&#39;evento e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-content-consumption"
>title="Visualizzare i contenuti web più utilizzati e coinvolge maggiormente gli utenti."
>abstract="**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali sono le pagine che più probabilmente allontanano le persone dal sito.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Vengono inoltre utilizzate le visualizzazioni Flusso per le sezioni di entrata, uscita e superiori."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-content-consumption"
>title="Visualizzare i contenuti multimediali più utilizzati e coinvolge maggiormente gli utenti."
>abstract="**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali sono le pagine che più probabilmente allontanano le persone dal sito.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina, la metrica Visite, la metrica Visitatori univoci, la metrica Tasso di ingresso, la metrica Tasso di rimbalzo, la metrica Tasso di uscita e la metrica Velocità contenuto. Inoltre, utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali; una visualizzazione grafico a dispersione che mostra le visualizzazioni di pagina per le pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per periodo fisso; e una visualizzazione a linee che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visualizza il punto in cui le persone escono o continuano attraverso una sequenza di pagine predefinita."
>abstract="**Questo può aiutarti** a capire meglio dove le persone stanno abbandonando il percorso di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come analizzare i tassi di conversione attraverso processi specifici sul tuo sito (ad esempio un processo di acquisto o registrazione), o analizzare le correlazioni tra gli eventi sul tuo sito. Ad esempio, la percentuale di persone che hanno guardato l&#39;informativa sulla privacy ha continuato ad acquistare un prodotto. Puoi anche utilizzare questo modello per eseguire confronti affiancati di due segmenti diversi nello stesso rapporto.<br/>Questo modello utilizza la visualizzazione Abbandono."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Visualizzare i dispositivi utilizzati da tutti i punti del percorso."
>abstract="**Questo ti aiuta** a capire meglio quante persone interagiscono con il tuo marchio, i tipi di dispositivi che utilizzano e come il loro utilizzo di più dispositivi influisce sulla loro esperienza. Ad esempio, con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un desktop per completare un’attività? Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo? E così via.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio ottimizzare alcune parti del percorso di utenti per un&#39;esperienza mobile.<br/>Questo modello utilizza le metriche Flusso, Abbandono, Analisi per coorte, Persone e Dispositivi univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Visualizza chi sono i tuoi utenti più fedeli e cosa stanno facendo sul tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio il numero di volte in cui una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e il numero di giorni tra le visite di ritorno.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio analizzare quale contenuto è più efficace per riportare le persone sul sito.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Visualizza le tendenze e le metriche principali del consumo audio multimediale su tutti i dispositivi digitali."
>abstract="**Questo può aiutarti** a comprendere meglio come i visitatori consumano contenuti audio sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio analizzare quale contenuto viene maggiormente utilizzato.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Visualizza le tendenze e le metriche principali del consumo di contenuti multimediali su tutti i dispositivi digitali."
>abstract="**Questo può aiutarti** a comprendere meglio il numero di volte in cui una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e il numero di giorni tra le visite di ritorno.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio analizzare quale contenuto è più efficace per riportare le persone sul sito.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--page-summary-report"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visualizza il numero di volte in cui un elemento dimensione era presente durante un ricaricamento. Un visitatore che aggiorna il browser è il modo più comune per attivare un ricaricamento."
>abstract="**Questo può aiutarti** a identificare quando potrebbero verificarsi problemi in una determinata pagina che richiederebbero a un visitatore di ricaricare la pagina.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali pagine presentano problemi da risolvere.<br/>Questo modello utilizza la metrica Ricarica."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta."
>abstract="**Questo ti aiuta** a capire meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni dei visitatori sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare l&#39;esperienza iniziale che le persone trovano sul sito o assicurarti che le pagine che le persone vedono per la prima volta quando accedono al tuo sito siano accoglienti e forniscano i collegamenti necessari ad altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta nel corso della vita del visitatore."
>abstract="**Questo ti aiuta** a capire meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni dei visitatori sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare l&#39;esperienza iniziale che le persone trovano sul sito o assicurarti che le pagine che le persone vedono per la prima volta quando accedono al tuo sito siano accoglienti e forniscano i collegamenti necessari ad altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visualizzare il numero di visite costituito da una singola pagina univoca."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.<br/>Questo modello utilizza la dimensione Visite a pagina singola."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--exitPageRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono immediatamente prima di lasciare il sito."
>abstract="**Questo ti aiuta** a capire meglio quali pagine allontanano le persone dal sito. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l&#39;esperienza che le persone ottengono prima di partire, oppure includere contenuti o collegamenti per incoraggiare le persone a rimanere sul tuo sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Visualizzare i dati sulle prestazioni per il sito Adobe Experience Manager."
>abstract="**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare le impostazioni di Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visualizzare e analizzare gli effetti di Intelligent Tracking Prevention (ITP) sulla raccolta dei dati e sul reporting."
>abstract="**Questo può aiutarti** a comprendere meglio la potenziale perdita di dati dovuta alle restrizioni sui cookie imposte da ITP.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio adattare la configurazione di Analytics per ridurre al minimo l&#39;impatto di ITP."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Most popular section--> Visualizza un rapporto che mostra affiancate le metriche di visualizzazioni di pagina, visite e visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che che visitano il sito, del numero di volte in cui sono state visitate le pagine e del numero di sessioni.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell&#39;anno o prima e dopo l&#39;esecuzione di campagne di marketing. </p><p>Questo modello utilizza la [dimensione Giorno](/help/components/dimensions/day.md), [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), [metrica Visite](/help/components/metrics/visits.md) e [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Most popular section-->Visualizzare il numero totale di visualizzazioni di pagina. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Page Views](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Pagine**] | <!--duplicated in Most popular section-->Identifica le pagine più popolari e meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui sono più interessati.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.</p><p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visite**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visite. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**In base a ciò che apprendi, potresti** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l&#39;avvio della campagna. Oppure puoi confrontare il traffico delle vacanze su base annua.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visits](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitatori**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentino o diminuiscano nel tempo o rispetto a un periodo precedente.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare se una campagna di marketing lanciata di recente è riuscita ad attirare nuove persone sul sito confrontando visitatori univoci prima e dopo il lancio della campagna. Oppure puoi confrontare il numero di persone che visitano il sito durante le festività anno su anno.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Tempo trascorso per visita**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.</p><p>Questo modello utilizza la dimensione [Giorno](/help/components/dimensions/day.md) e la metrica [Tempo trascorso per visita (secondi)](/help/components/metrics/time-spent-per-visit.md).</p> |
| [!UICONTROL **Tempo precedente all’evento**] | Visualizzare il tempo medio trascorso dagli utenti prima di un evento di successo. <p>**Questo può aiutarti** a comprendere meglio quanto tempo impiegano i visitatori per eseguire un&#39;azione desiderata, ad esempio per effettuare un acquisto.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio valutare se le modifiche al tuo sito migliorano la capacità dei visitatori di raggiungere rapidamente un evento di successo.</p><p>Questo modello utilizza la dimensione [Tempo precedente all&#39;evento](/help/components/dimensions/time-prior-to-event.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Sezioni del sito**] | <!--duplicated in Most popular section-->Visualizza le sezioni più popolari o con le prestazioni più elevate del sito. <p>**Questo può aiutarti** a capire meglio quali sezioni del tuo sito sono più visitate.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali prodotti o servizi fornisci generano il maggior interesse.</p> <p>Questo modello utilizza la [dimensione Sezione sito](/help/components/dimensions/site-section.md) e la [metrica Visite](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Tempo reale**] | Visualizza le dimensioni e le metriche attualmente raccolte sul tuo sito. <p>**Questo può aiutarti** a comprendere meglio le tendenze sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** rispondere e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing correnti.</p> <p>Questo modello utilizza il [rapporto in tempo reale](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> |
| [!UICONTROL **Consumo di contenuti Web**] | Visualizzare i contenuti web più utilizzati e coinvolge maggiormente gli utenti.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.</p><p>**In base a quanto appreso, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali pagine hanno più probabilità di allontanarle dal sito <!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), la [metrica Visite](/help/components/metrics/visits.md), la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md), la [metrica Tasso di ingresso](/help/components/metrics/entries.md), la [metrica Tasso di mancato recapito](/help/components/metrics/bounce-rate.md), la [metrica Tasso di uscita](/help/components/metrics/exits.md) e la [metrica Velocità contenuto](/help/components/metrics/content-velocity.md). Utilizza anche [Visualizzazioni di flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per le sezioni di entrata, uscita e superiori.</p> |
| [!UICONTROL **Consumo di contenuti multimediali**] | Visualizzare i contenuti multimediali più utilizzati e coinvolge maggiormente gli utenti.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di allontanare le persone dal sito.</p><p>**In base a quanto appreso, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali pagine hanno più probabilità di allontanarle dal sito <!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), la [metrica Visite](/help/components/metrics/visits.md), la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md), la [metrica Tasso di ingresso](/help/components/metrics/entries.md), la [metrica Tasso di mancato recapito](/help/components/metrics/bounce-rate.md), la [metrica Tasso di uscita](/help/components/metrics/exits.md) e la [metrica Velocità contenuto](/help/components/metrics/content-velocity.md). Vengono inoltre utilizzate [Visualizzazioni di flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per le sezioni di entrata, uscita e superiori; una [Visualizzazione grafico a dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) che mostra le visualizzazioni di pagina per le pagine più comuni; una [Visualizzazione a barre](/help/analyze/analysis-workspace/visualizations/bar.md) che mostra le visualizzazioni di pagina per periodo fisso; e una [Visualizzazione a linee](/help/analyze/analysis-workspace/visualizations/line.md) che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito.</p> |
| [!UICONTROL **Flusso pagina successivo e precedente**] | Visualizza i luoghi più comuni in cui le persone vanno prima o dopo aver visitato un determinato luogo.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di essere visitate prima di lasciare il sito.</p><p>**In base a quanto appreso, è possibile** eseguire un&#39;operazione qualsiasi, ad esempio valutare quali percorsi sul sito indirizzano le persone alle pagine più importanti e quali pagine hanno più probabilità di allontanarle dal sito <!-- not sure about these takeaways... -->.</p> <p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), la [metrica Visite](/help/components/metrics/visits.md), la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md), la [metrica Tasso di ingresso](/help/components/metrics/entries.md), la [metrica Tasso di mancato recapito](/help/components/metrics/bounce-rate.md), la [metrica Tasso di uscita](/help/components/metrics/exits.md) e la [metrica Velocità contenuto](/help/components/metrics/content-velocity.md). Vengono inoltre utilizzate [visualizzazioni Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per le sezioni di entrata, uscita e principali; una [visualizzazione Grafico a dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) che mostra le visualizzazioni di pagina per le pagine più comuni; una [visualizzazione a barre](/help/analyze/analysis-workspace/visualizations/bar.md) che mostra le visualizzazioni di pagina per periodo fisso; e una [visualizzazione a linee](/help/analyze/analysis-workspace/visualizations/line.md) che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito.</p> |
| [!UICONTROL **Fallout**] | Visualizza il punto in cui le persone escono o continuano attraverso una sequenza di pagine predefinita.<p>**Questo può aiutarti** a capire meglio dove le persone stanno abbandonando il percorso di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come analizzare i tassi di conversione attraverso processi specifici sul tuo sito (ad esempio un processo di acquisto o registrazione), o analizzare le correlazioni tra gli eventi sul tuo sito. Ad esempio, la percentuale di persone che hanno guardato l&#39;informativa sulla privacy ha continuato ad acquistare un prodotto. Puoi anche utilizzare questo modello per eseguire confronti affiancati di due segmenti diversi nello stesso rapporto.</p> <p>Questo modello utilizza la [Visualizzazione di fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> |
| [!UICONTROL **Analisi cross-device**] | Visualizzare i dispositivi utilizzati da tutti i punti del percorso.<p>**Questo ti aiuta** a capire meglio quante persone interagiscono con il tuo marchio, i tipi di dispositivi che utilizzano e come il loro utilizzo di più dispositivi influisce sulla loro esperienza. Ad esempio, con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un desktop per completare un’attività? Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo? E così via.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio ottimizzare alcune parti del percorso di utenti per un&#39;esperienza mobile.</p> <p>Questo modello utilizza la [visualizzazione Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), la [visualizzazione Abbandono](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), la [analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), la [metrica Persone](/help/components/metrics/people.md) e la [metrica Dispositivi univoci](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Conservazione Web**] | Visualizza chi sono i tuoi utenti più fedeli e cosa stanno facendo sul tuo sito.<p>**Questo può aiutarti** a comprendere meglio il numero di volte in cui una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e il numero di giorni tra le visite di ritorno.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio analizzare quale contenuto è più efficace per riportare le persone sul sito.<p>Questo modello utilizza la metrica [Visite](/help/components/metrics/visits.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Consumo audio di contenuti multimediali**] | Visualizza le tendenze e le metriche principali del consumo audio multimediale su tutti i dispositivi digitali.<p>**Questo può aiutarti** a comprendere meglio come i visitatori consumano contenuti audio sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio analizzare quale contenuto viene maggiormente utilizzato.<p>Questo modello utilizza la metrica [Visite](/help/components/metrics/visits.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Attualità contenuti multimediali, Frequenza, Fedeltà**] | Visualizza le tendenze e le metriche principali del consumo di contenuti multimediali su tutti i dispositivi digitali.<p>**Questo può aiutarti** a comprendere meglio il numero di volte in cui una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e il numero di giorni tra le visite di ritorno.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio analizzare quale contenuto è più efficace per riportare le persone sul sito.<p>Questo modello utilizza la metrica [Visite](/help/components/metrics/visits.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| **[!UICONTROL Page Analysis]** > [!UICONTROL **Riepilogo pagina**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.</p><p>Questo modello utilizza la dimensione [Giorno](/help/components/dimensions/day.md) e la metrica [Tempo trascorso per visita (secondi)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Page Analysis]** > [!UICONTROL **Ricarica**] | Visualizza il numero di volte in cui un elemento dimensione era presente durante un ricaricamento. Un visitatore che aggiorna il browser è il modo più comune per attivare un ricaricamento. <p>**Questo può aiutarti** a identificare quando potrebbero verificarsi problemi in una determinata pagina che richiederebbero a un visitatore di ricaricare la pagina.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio valutare quali pagine presentano problemi da risolvere.</p><p>Questo modello utilizza la metrica [Ricarica](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/reloads).</p> |
| **[!UICONTROL Page Analysis]** > [!UICONTROL **Tempo trascorso sulla pagina**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.</p><p>Questo modello utilizza la dimensione [Giorno](/help/components/dimensions/day.md) e la metrica [Tempo trascorso per visita (secondi)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Pagine di ingresso**] | Visualizza le pagine principali a cui gli utenti accedono quando visitano per la prima volta il tuo sito per una determinata sessione. <p>**Questo ti aiuta** a capire meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni dei visitatori sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare l&#39;esperienza iniziale che le persone trovano sul sito o assicurarti che le pagine che le persone vedono per la prima volta quando accedono al tuo sito siano accoglienti e forniscano i collegamenti necessari ad altre aree del sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella.</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Pagine di ingresso originali**] | Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta nel corso della vita del visitatore. <p>**Questo ti aiuta** a capire meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni dei visitatori sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare l&#39;esperienza iniziale che le persone trovano sul sito o assicurarti che le pagine che le persone vedono per la prima volta quando accedono al tuo sito siano accoglienti e forniscano i collegamenti necessari ad altre aree del sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella.</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Visite a pagina singola**] | Visualizzare il numero di visite costituito da una singola pagina univoca. <p>**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo i visitatori passano sul sito.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio valutare se le modifiche al sito determinano una maggiore quantità di tempo da parte dei visitatori.</p><p>Questo modello utilizza la dimensione [Visite a pagina singola](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/single-page-visits).</p> |
| **[!UICONTROL Entries & Exits]** > [!UICONTROL **Pagine di uscita**] | Visualizza le pagine principali a cui gli utenti accedono immediatamente prima di lasciare il sito.<p>**Questo ti aiuta** a capire meglio quali pagine allontanano le persone dal sito. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l&#39;esperienza che le persone ottengono prima di partire, oppure includere contenuti o collegamenti per incoraggiare le persone a rimanere sul tuo sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche la visualizzazione a barre e la visualizzazione a forma libera della tabella.</p> |
| [!UICONTROL **AEM**] > [!UICONTROL **Prestazioni sito**] > [!UICONTROL **Prestazioni sito AEM**] | Visualizzare i dati sulle prestazioni per il sito Adobe Experience Manager.  <p>**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare le impostazioni di Experience Manager.</p> |
| [!UICONTROL **Impatto ITP**] | Visualizzare e analizzare gli effetti di Intelligent Tracking Prevention (ITP) sulla raccolta dei dati e sul reporting. <p>**Questo può aiutarti** a comprendere meglio la potenziale perdita di dati dovuta alle restrizioni sui cookie imposte da ITP.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio adattare la configurazione di Analytics per ridurre al minimo l&#39;impatto di ITP.</p> |




Ignora sotto

| Opzione di menu | Rapporti sotto questa voce di menu |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Tutorial di formazione (modello Workspace preesistente)</li><li>Pagine (quali sono le pagine principali?)</li><li>Visualizzazioni pagina (quante visualizzazioni di pagina vengono generate?)</li><li>Visite (quante visite ricevo?)</li><li>Visitatori (quanti visitatori ricevo?)</li><li>Metriche chiave (come sono le prestazioni delle metriche più importanti?)</li><li>Sezioni del sito (quali sezioni del sito hanno generato il maggior numero di visualizzazioni della pagina?)</li><li>In tempo reale (quali sono le tendenze sul sito e perché?)</li><li>Pagina successiva (quali sono le pagine successive visitate dagli utenti?)</li><li>Pagina precedente (quali sono le pagine precedenti visitate dagli utenti?)</li><li>Campagne (quali campagne sono più determinanti per le metriche chiave?)</li><li>Prodotti (quali prodotti sono più determinanti per le metriche chiave?)</li><li>Canale ultimo contatto (quale canale di ultimo contatto offre le prestazioni migliori?)</li><li>Dettaglio canale ultimo contatto (quale canale di ultimo contatto specifico ha prestazioni migliori degli altri?)</li><li>Ricavi (come stanno andando i ricavi?)</li><li>Ordini (come vanno gli ordini?)</li><li>Unità (quante unità vengono vendute?)</li></ul> |
| **[!UICONTROL Engagement]** | <ul><li>Metriche chiave (come sono le prestazioni delle metriche più importanti?)</li><li>Visualizzazioni pagina (quante visualizzazioni di pagina vengono generate?)</li><li>Pagine (quali sono le pagine principali?)</li><li>Visite (quante visite ricevo?)</li><li>Visitatori (quanti visitatori ricevo?)</li><li>Tempo trascorso per visita (quanto tempo trascorrono gli utenti per visita?)</li><li>Tempo precedente all’evento (quanto tempo trascorrono gli utenti prima di un evento di successo?)</li><li>Sezioni del sito (quali sezioni del sito hanno generato il maggior numero di visualizzazioni di pagina?)</li><li>Consumo di contenuti web (quali contenuti vengono maggiormente consumati e coinvolgono maggiormente gli utenti?)</li><li>Consumo di contenuti multimediali (quali contenuti vengono maggiormente consumati e coinvolgono maggiormente gli utenti?)</li><li>Flusso pagine successive e precedenti (quali sono o sono stati i percorsi successivi/precedenti seguiti dai visitatori?)</li><li>Abbandono (dove si verifica l’abbandono nelle proprietà digitali?)</li><li>Analisi tra dispositivi (tramite analisi tra dispositivi in Analysis Workspace)</li><li>Fidelizzazione web (chi sono gli utenti più fedeli e cosa fanno?)</li><li>Consumo audio multimediale (quali sono le tendenze e le metriche migliori in merito al consumo audio?)</li><li>Recency, frequenza, fedeltà per contenuti multimediali (chi sono i lettori più fedeli?)</li><li>Analisi pagina > Ricaricamenti (quali pagine vengono ricaricate maggiormente?)</li><li>Analisi pagina > Tempo trascorso su pagina (quanto tempo passano gli utenti sulle pagine?)</li><li>Entrate e uscite > Pagine di ingresso (quali sono le pagine di ingresso principali?)</li><li>Entrate e uscite > Pagine di entrata originali (da quale pagina è entrato originariamente il visitatore?)</li><li>Entrate e uscite > Visite pagina singola (quali pagine hanno generato più visite a una singola pagina?)</li><li>Entrate e uscite > Pagine di uscita (quali sono le pagine di uscita principali?)</li><li>Analisi pagina > Riepilogo pagina</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Prodotti > Prodotti (quali prodotti sono più determinanti per le metriche chiave?)</li><li>Prodotti > Prestazioni prodotto (quali prodotti hanno prestazioni migliori?)</li><li>Prodotti > Categorie (quali sono le categorie di prodotti con le migliori prestazioni?)</li><li>Carrello acquisti > Carrelli (quanti utenti hanno aggiunto un prodotto al carrello?)</li><li>Carrello acquisti > Visualizzazioni carrello (quante volte i visitatori hanno visualizzato il carrello?)</li><li>Carrello acquisti > Aggiunte al carrello (con quale frequenza gli utenti aggiungono un prodotto al carrello?)</li><li>Carrello acquisti > Rimozioni dal carrello (con quale frequenza gli utenti rimuovono un prodotto dal carrello?)</li><li>Acquisti > Ricavi (come stanno andando i ricavi?)</li><li>Acquisti > Ordini (come vanno gli ordini?)</li><li>Acquisti > Unità (quante unità sto vendendo?)</li><li>[Magento: marketing e commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#commerce)</li></ul> |
| **[!UICONTROL Audience]** | <ul><li>Metrica persone (quante persone interagiscono con il marchio?)</li><li>Profilo visitatore > Panoramica posizioni (quali posizioni generano maggior utilizzo tra gli utenti?)</li><li>Profilo visitatore > Geosegmentazione > Geo Counties, Geo Stati Uniti, Geo Region, Geo Cities, Geo US DMA (da quali aree geografiche provengono i visitatori?)</li><li>Profilo visitatore > Lingue (quali lingue preferiscono gli utenti?)</li><li>Profilo visitatore > Fusi orari (da quali fusi orari provengono gli utenti?)</li><li>Profilo visitatore > Domini (quali ISP utilizzano i visitatori per accedere al sito?)</li><li>Profilo visitatore > Domini di primo livello (quali domini sono più determinanti per il traffico verso il sito?)</li><li>Profilo visitatore > Tecnologia > Panoramica tecnologia (quali tecnologie vengono utilizzate dalle persone per accedere al sito?)</li><li>Profilo visitatore > Tecnologia > Browser, Tipo di browser, Larghezza browser, Altezza browser (quale browser, versione del browser e relative dimensioni vengono utilizzati per accedere al sito?)</li><li>Profilo visitatore > Tecnologia > Sistema operativo, Tipi di sistema operativo (quale sistema operativo e quale versione utilizzano i visitatori?)</li><li>Profilo visitatore > Tecnologia > Operatore mobile (quali operatori mobili utilizzano i visitatori per accedere al sito?)</li><li>Fidelizzazione visitatori > Frequenza di ritorno (quanto tempo trascorre tra la visita corrente dell’utente e le visite precedenti?)</li><li>Fidelizzazione visitatori > Visite di ritorno (quante visite sono riconducibili a utenti di ritorno?)</li><li>Fidelizzazione visitatori > Numero di visite (quale numero di visite determina la maggior parte delle metriche chiave?)</li><li>Fidelizzazione visitatori > Ciclo di vendita > Fedeltà cliente (a quale segmento di fedeltà appartengono gli utenti?)</li><li>Fidelizzazione visitatori > Ciclo di vendita > Giorni prima del primo acquisto (quanti giorni sono trascorsi tra la prima visita e il primo acquisto?)</li><li>Fidelizzazione visitatori > Ciclo di vendita > Giorni dall’ultimo acquisto (quanti giorni sono passati tra la visita corrente e l’ultimo acquisto?) )</li><li>Fidelizzazione visitatori > Dispositivi mobili > Dispositivi e tipi di dispositivi (quali dispositivi e tipi di dispositivi utilizzano i visitatori?)</li><li>Fidelizzazione visitatori > Dispositivi mobili > Produttore (quale produttore di dispositivi mobili usano i visitatori?)</li><li>Fidelizzazione visitatori > Dispositivi mobili > Dimensioni schermo, Altezza schermo, Larghezza schermo (quali sono le dimensioni/altezza/larghezza dello schermo dei dispositivi mobili usati dai visitatori?)</li><li>Fidelizzazione visitatori > Dispositivi mobili > [Utilizzo app mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li><li>Fidelizzazione visitatori > Dispositivi mobili > [Percorsi in app mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li><li>Fidelizzazione visitatori > Dispositivi mobili > [Metriche app mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li><li>Fidelizzazione visitatori > Dispositivi mobili > [Messaggistica app mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li><li>Fidelizzazione visitatori > Dispositivi mobili > [Prestazioni app mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li><li>Fidelizzazione visitatori > Dispositivi mobili > [Fidelizzazione app mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** | <ul><li>Canali marketing > Canale primo contatto, Dettaglio canale primo contatto (quale canale di primo contatto e quale canale di primo contatto specifico offre le prestazioni migliori?)</li><li>Canali marketing > Primo ultimo canale, Dettaglio primo ultimo canale (quale canale di ultimo contatto e quale canale di ultimo contatto specifico ha prestazioni migliori?)</li><li>Campagne > Campagne (quali campagne sono più determinanti per le metriche chiave?)</li><li>Campagne > Prestazione campagna (quali campagne generano maggior fatturato?)</li><li>Campagne > Codice di tracciamento (quali codici di tracciamento delle campagne hanno le migliori prestazioni?)</li><li>[Acquisizione web](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#web)</li><li>[Acquisizione mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#mobile)</li><li>[Advertising Analytics: ricerca a pagamento](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#advertising)</li><li>Parole chiave di ricerca - tutto, a pagamento, naturale (quali parole chiave di ricerca e parole chiave di ricerca a pagamento/naturale sono più determinanti per le metriche chiave?)</li><li>Motori di ricerca - tutti, a pagamento, naturali (quali motori di ricerca e motori di ricerca a pagamento/naturali sono più determinanti per le metriche chiave?)</li><li>Classificazione di tutte le pagine di ricerca (da quale pagina di ricerca arrivano gli utenti?)</li><li>Domini di riferimento (quali domini indirizzano il traffico al sito?)</li><li>Domini di riferimento originali (qual era il primo dominio in cui si trovavano gli utenti prima di visitare il sito?)</li><li>Riferimenti (su quali URL si trovavano gli utenti prima di fare clic e arrivare al mio sito?)</li><li>Tipi di riferimento (a quale categoria appartengono gli URL di riferimento?)</li></ul> |

### Conversione   {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--productConversionReport"
>title="Modello Funnel di conversione prodotto"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--retail-products-template"
>title="Visualizzare i prodotti con le prestazioni più elevate."
>abstract="**Questo ti aiuta** a capire meglio quali prodotti hanno più successo.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come aumentare i finanziamenti per i prodotti di successo e diminuire i finanziamenti per i prodotti di minor successo.<br/>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte carrello, Ordini, Entrate e Unità. Utilizza anche la dimensione Prodotto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="."
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartConversionReport"
>title="Visualizzare il numero di volte in cui le persone hanno eseguito eventi di pagamento chiave, ad esempio l&#39;aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e l&#39;estrazione."
>abstract="**Questo può aiutarti** a capire meglio quali parti del funnel del processo di pagamento che portano alla conversione e quali sono più soggette all&#39;abbandono del carrello.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio ridurre l&#39;attrito in determinati passaggi del processo di pagamento.<br/>Questo modello utilizza"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartsOvertimeReport"
>title="Visualizza il numero di persone che hanno aggiunto un prodotto al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti che vengono aggiunti a un carrello.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio misurare l&#39;efficacia delle pagine dei tuoi prodotti.<br/>Questo modello utilizza la metrica Carrelli."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartViewsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno visualizzato il carrello."
>abstract="**Questo può aiutarti** a comprendere meglio l&#39;esperienza di pagamento nel tentativo di ridurre i tassi di abbandono del carrello o di analizzare il tempo tra le aggiunte al carrello e le estrazioni tra i diversi prodotti.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come offrire promozioni per prodotti che rimangono nei carrelli più a lungo e sono a maggior rischio di abbandono.<br/>Questo modello utilizza la metrica Visualizzazioni carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartAdditionsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l&#39;interesse del cliente per un prodotto è sufficientemente elevato da consentirne l&#39;aggiunta al carrello.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i consigli di prodotto per tutti i clienti. Questo può essere fatto analizzando quali prodotti vengono spesso aggiunti agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già nel carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cartRemovalsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui i clienti non sono più interessati a un prodotto, oppure può aiutarti a capire dove possono esistere problemi nel processo di pagamento.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio rimuovere eventuali barriere che potrebbero esistere nel processo di pagamento, ad esempio un&#39;esperienza utente complicata.<br/>Questo modello utilizza la metrica Rimozioni carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--purchaseConversionReport"
>title="Modello funnel di conversione acquisto"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Visualizza informazioni predefinite per i rivenditori sulle attività di e-commerce per migliorare le vendite. Questo è destinato agli utenti del Magento, ma può essere utilizzato da qualsiasi rivenditore online."
>abstract="**Questo ti aiuta** a capire meglio in che modo le attività di e-commerce contribuiscono ai numeri di vendita.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i budget per le attività che ottengono il maggior ROI."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funnel di conversione prodotto**] | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza |
| **Prodotti** | Scopri quali prodotti sono più determinanti per le metriche chiave, ad esempio i più venduti o i più visualizzati. <p>**Questo ti aiuta** a capire meglio quali prodotti hanno più successo.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come aumentare i finanziamenti per i prodotti di successo e diminuire i finanziamenti per i prodotti di minor successo.</p><p>Questo modello utilizza la metrica Ordini e la dimensione Prodotto. |
| **Prestazioni prodotto** | Visualizzare i prodotti con le prestazioni più elevate.<p>**Questo ti aiuta** a capire meglio quali prodotti hanno più successo.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come aumentare i finanziamenti per i prodotti di successo e diminuire i finanziamenti per i prodotti di minor successo.</p><p>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte carrello, Ordini, Ricavi e Unità. Utilizza anche la dimensione Prodotto. |
| **Categorie** |  |
| **Funnel di conversione carrello** | Visualizzare il numero di volte in cui le persone hanno eseguito eventi di pagamento chiave, ad esempio l&#39;aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e l&#39;estrazione. <p>**Questo può aiutarti** a capire meglio quali parti del funnel del processo di pagamento che portano alla conversione e quali sono più soggette all&#39;abbandono del carrello.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio ridurre l&#39;attrito in determinati passaggi del processo di pagamento.</p><p>Questo modello utilizza |
| **Carrelli** | Visualizza il numero di persone che hanno aggiunto un prodotto al carrello.<p>**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti che vengono aggiunti a un carrello.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio misurare l&#39;efficacia delle pagine dei tuoi prodotti.</p><p>Questo modello utilizza la metrica Carrelli. |
| **Visualizzazioni carrello** | Visualizza il numero di volte in cui le persone hanno visualizzato il carrello. <p>**Questo può aiutarti** a comprendere meglio l&#39;esperienza di pagamento nel tentativo di ridurre i tassi di abbandono del carrello o di analizzare il tempo tra le aggiunte al carrello e le estrazioni tra i diversi prodotti.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come offrire promozioni per prodotti che rimangono nei carrelli più a lungo e sono a maggior rischio di abbandono.</p><p>Questo modello utilizza la metrica Visualizzazioni carrello. |
| **Aggiunte carrello** | Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello. <p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l&#39;interesse del cliente per un prodotto è sufficientemente elevato da consentirne l&#39;aggiunta al carrello.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare i consigli di prodotto per tutti i clienti. Questo può essere fatto analizzando quali prodotti vengono spesso aggiunti agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già nel carrello. |
| **Rimozioni carrello** | Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello.<p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui i clienti non sono più interessati a un prodotto, oppure può aiutarti a capire dove possono esistere problemi nel processo di pagamento.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio rimuovere eventuali barriere che potrebbero esistere nel processo di pagamento, ad esempio un&#39;esperienza utente complicata.</p><p>Questo modello utilizza la metrica Rimozioni carrello. |
| **Funnel di conversione acquisti** | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza |
| **Ricavi** | <!--duplicated in Most popular section-->Visualizza l&#39;importo monetario dei prodotti acquistati in tutti gli ordini.<p>**Questo può aiutarti** a capire meglio quali elementi dimensionali hanno contribuito ai ricavi, combinando la metrica Ricavi con qualsiasi dimensione. Ad esempio, puoi vedere le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito ai ricavi. </p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio regolare le campagne che non soddisfano gli obiettivi di ricavo previsti.</p><p>Questo modello utilizza la metrica Ricavi. |
| **Ordini** | <!--duplicated in Most popular section-->Visualizza il numero totale di eventi di acquisto effettuati sul sito. <p>**Questo può aiutarti** a capire meglio quali elementi dimensionali hanno contribuito a un ordine, combinando la metrica Ordini con qualsiasi dimensione. Ad esempio, puoi vedere le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito agli acquisti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare le campagne che non soddisfano i target di acquisto previsti. </p><p>Questo modello utilizza la metrica Ordini. |
| [!UICONTROL **Unità**] | Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati in un periodo di tempo e confrontati con i periodi precedenti. <p>**Questo ti aiuta** a capire meglio come le vendite unitarie aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quali clienti o aree geografiche acquistano più unità e come queste vendite unitarie tendono nel tempo.</p><p>**In base a quanto appreso, è possibile** eseguire una serie di operazioni, ad esempio valutare l&#39;efficacia di una campagna di marketing avviata di recente confrontando le vendite unitarie prima e dopo l&#39;avvio della campagna. In alternativa, è possibile confrontare le vendite unitarie annuali durante le festività.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Units](/help/components/metrics/units.md).</p> |
| [!UICONTROL **Magento: marketing e Commerce**] | Visualizza informazioni predefinite per i rivenditori sulle attività di e-commerce per migliorare le vendite. Questo è destinato agli utenti del Magento, ma può essere utilizzato da qualsiasi rivenditore online. <p>**Questo ti aiuta** a capire meglio in che modo le attività di e-commerce contribuiscono ai numeri di vendita.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio regolare i budget per le attività che ottengono il maggior ROI.</p> |

### Pubblico {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Visualizzare il paese da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a capire meglio da cosa provengono i visitatori dei paesi più popolari che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come utilizzare i dati per concentrarti sulle attività di marketing in questi paesi, o assicurarti che la tua esperienza sul sito sia ottimale in paesi che hanno diverse lingue primarie.<br/>Questo modello utilizza la dimensione Paesi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Visualizza lo stato (negli Stati Uniti) da cui hanno avuto origine le persone che visitano il sito. È simile al modello Geo Regions, con la differenza che è specifico per gli Stati Uniti."
>abstract="**Questo può aiutarti** a comprendere meglio gli stati americani più popolari da cui provengono i visitatori che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come utilizzare i dati per concentrarsi sulle attività di marketing in questi stati.<br/>Questo modello utilizza la dimensione Stati Uniti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Visualizzare l&#39;area geografica da cui hanno avuto origine le persone che visitano il sito. Una regione è un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni paesi, una regione è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. "
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste aree geografiche, oppure assicurarti che l&#39;esperienza del tuo sito sia ottimale nelle aree geografiche che hanno diverse lingue primarie. <br/>Questo modello utilizza le dimensioni ID(variabili/geocountry) e Region. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Visualizza la città da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. <br/>Questo modello utilizza la dimensione Città"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Visualizzare le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui hanno avuto origine le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree di maggior successo. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto."
>abstract="**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.<br/>Questo modello utilizza la dimensione Lingua."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Visualizza i fusi orari principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a capire meglio in quali fusi orari vivono i tuoi visitatori.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come regolare la manutenzione del sito in momenti che influenzeranno il minor numero di persone."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Visualizza i domini principali dei visitatori che accedono al tuo sito."
>abstract="**Questo ti aiuta** a capire meglio da quali organizzazioni provengono i tuoi visitatori.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio indirizzare i contenuti ai tuoi clienti più grandi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Visualizza i domini principali dei visitatori che accedono al tuo sito."
>abstract="**Questo ti aiuta** a capire meglio da quali organizzazioni provengono i tuoi visitatori.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio indirizzare i contenuti ai tuoi clienti più grandi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Panoramica sulla tecnologia"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Visualizza il nome e la versione dei principali browser utilizzati dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.<br/>Questo modello utilizza la dimensione Browser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Visualizza i nomi delle organizzazioni che hanno creato i browser principali utilizzati dagli utenti per accedere al sito. Questo è diverso dal modello Browser in quanto non elenca diverse versioni dello stesso browser come elementi dimensionali separati."
>abstract="**Questo ti aiuta** a comprendere meglio i browser più comuni utilizzati dai visitatori <br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità. <br/>Questo modello utilizza la dimensione Tipo di browser. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Visualizzare le larghezze superiori del browser utilizzate per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le larghezze più comuni del browser. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.<br/>Questo modello utilizza la dimensione Browser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Visualizza le altezze principali del browser utilizzate dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le altezze più comuni del browser. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.<br/>Questo modello utilizza la dimensione Browser. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Visualizzare il nome dei sistemi operativi e la versione utilizzati per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio i sistemi operativi e le versioni più comuni utilizzati dai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i sistemi operativi e le versioni principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Visualizzare il nome dei sistemi operativi utilizzati dagli utenti per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio i sistemi operativi più comuni utilizzati dai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i sistemi operativi principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileCarrierRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito."
>abstract="**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito."
>abstract="**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito."
>abstract="**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Visualizza quante volte un visitatore ha visitato il sito."
>abstract="**Questo può aiutarti** a comprendere meglio quanto sono coinvolti i visitatori quando ritornano al tuo sito. Questo vale per la durata del visitatore, indipendentemente dall’intervallo di date del progetto.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio regolare le attività di marketing per i visitatori frequenti.<br/>Questo modello utilizza la dimensione Numero visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Visualizza il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti."
>abstract="**Questo ti aiuta** a capire meglio in che modo il tuo sito influisce sul comportamento d&#39;acquisto. .<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio concentrarsi sui visitatori che tornano per fare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.<br/>Questo modello utilizza la dimensione Fedeltà del cliente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Visualizza il numero di giorni che trascorrono tra la prima volta che un visitatore raggiunge il sito e il momento in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento dimensione 1 giorno."
>abstract="**Questo può aiutarti** a capire meglio quanto tempo impiegano i visitatori per effettuare un acquisto.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio aggiornare il tuo sito per incoraggiare un&#39;acquisizione più veloce.<br/>Questo modello utilizza la dimensione Giorni prima del primo acquisto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Visualizza il tempo trascorso tra l’hit corrente del visitatore e il suo acquisto più recente in quel momento."
>abstract="**Questo può aiutarti** a comprendere meglio il comportamento dei visitatori dopo l&#39;acquisto di qualcosa sul tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio aggiornare il tuo sito per incoraggiare gli acquisti successivi.<br/>Questo modello utilizza la dimensione Giorni dall&#39;ultimo acquisto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileDeviceNameRankedReport"
>title="Visualizza la marca e il modello dei dispositivi mobili utilizzati dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a capire meglio quali dispositivi mobili sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.<br/>Questo modello utilizza la dimensione Nome dispositivo mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileDeviceTypeRankedReport"
>title="Visualizza i tipi di dispositivi mobili utilizzati dagli utenti per accedere al sito, ad esempio telefoni e tablet."
>abstract="**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.<br/>Questo modello utilizza la dimensione Tipo di dispositivo mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileManufacturerRankedReport"
>title="Visualizza quali produttori producono i dispositivi mobili utilizzati dagli utenti per accedere al tuo sito, ad esempio Apple e Samsung."
>abstract="**Questo può aiutarti** a capire meglio quali produttori sono più popolari nella tua base di utenti.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle capacità di diversi produttori per garantire un&#39;esperienza utente fluida.<br/>Questo modello utilizza la dimensione Produttore di dispositivi mobili."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Visualizza le dimensioni principali dello schermo dei dispositivi mobili utilizzate dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le dimensioni più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare gli sforzi di controllo della qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Visualizza le altezze superiori dello schermo del cellulare utilizzate dagli utenti per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le altezze dello schermo più comuni per dispositivi mobili. In questo modo è possibile massimizzare gli sforzi di controllo della qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Visualizzare le larghezze superiori dello schermo dei dispositivi mobili utilizzate dagli utenti per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le larghezze più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare gli sforzi di controllo della qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualizza il numero di utenti, avvii e primi avvii nell&#39;app, nonché la durata media della sessione."
>abstract="**Questo ti aiuta** a capire meglio quanto viene utilizzata l&#39;app. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare le prestazioni dell&#39;app in modo che possano essere scalate in base alla quantità di utilizzo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-journeys"
>title="Visualizza i pattern di utilizzo principali per la tua app mobile."
>abstract="**Questo ti aiuta** a capire meglio come le persone usano la tua app. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare il modo in cui le persone possono passare da una schermata all&#39;altra per eseguire il targeting dei flussi di lavoro più comuni."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-key-metrics"
>title="Visualizza alcune delle metriche più comuni per le app mobili."
>abstract="**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.<br/>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare lo stato e le prestazioni complessive dell&#39;app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-messaging"
>title="Visualizza i dati sulle prestazioni per i messaggi in-app e push per la tua app."
>abstract="**Questo ti aiuta** a capire meglio come le persone utilizzano le funzionalità di messaggistica in-app e come le notifiche push indirizzino efficacemente il traffico verso la tua app.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare l&#39;esperienza di notifica push della messaggistica in-app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-performance-template"
>title="Visualizza le prestazioni dell’app e dove gli utenti riscontrano problemi."
>abstract="**Questo può aiutarti** a capire meglio se gli utenti che usano la tua app riscontrano rallentamento o prestazioni ridotte. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come risolvere problemi esistenti o migliorare le prestazioni dell&#39;app prima che si verifichino dei problemi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-retention"
>title="Puoi vedere quali utenti sono i più fedeli all’app e cosa fanno all’interno dell’app."
>abstract="**Questo può aiutarti** a capire meglio come i tuoi utenti più fedeli stanno utilizzando la tua app.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio migliorare le tue attività di marketing per le funzionalità utilizzate dai tuoi utenti più fedeli."

<!-- markdownlint-enable MD034 -->


Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Metrica Persone**] | Visualizza il numero di persone che interagiscono con il tuo marchio. <p>**Questo può aiutarti** a comprendere meglio le tendenze di utilizzo sul tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come misurare l&#39;efficacia delle recenti attività di marketing nella generazione di nuovi visitatori del tuo sito.</p> |
| **Profilo visitatore** > **Panoramica sulla posizione** | Visualizza una panoramica della posizione del visitatore in una visualizzazione mappa.<p>**Questo può aiutarti** a capire meglio dove si trovano i visitatori che stanno visitando il tuo sito. </p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come concentrare le risorse di marketing nelle posizioni in cui visualizzi più interesse e opportunità.</p><!-- This template uses the --> |
| **Profilo visitatore** > **Paesi geografici** | Visualizzare il paese da cui provengono le persone che visitano il sito.<p>**Questo può aiutarti** a capire meglio da cosa provengono i visitatori dei paesi più popolari che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come utilizzare i dati per concentrarti sulle attività di marketing in questi paesi, o assicurarti che la tua esperienza sul sito sia ottimale in paesi che hanno diverse lingue primarie.</p><p>Questo modello utilizza la dimensione Paesi. </p> |
| **Profilo visitatore** > **Stati Geo USA** | Visualizza lo stato (negli Stati Uniti) da cui hanno avuto origine le persone che visitano il sito. È simile al modello Geo Regions, con la differenza che è specifico per gli Stati Uniti.<p>**Questo può aiutarti** a comprendere meglio gli stati americani più popolari da cui provengono i visitatori che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come utilizzare i dati per concentrarsi sulle attività di marketing in questi stati.</p><p>Questo modello utilizza la dimensione Stati Uniti. </p> |
| **Profilo visitatore** > **Aree geografiche** | Visualizzare l&#39;area geografica da cui hanno avuto origine le persone che visitano il sito. Una regione è un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni paesi, una regione è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. <p>**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste aree geografiche, oppure assicurarti che l&#39;esperienza del tuo sito sia ottimale nelle aree geografiche che hanno diverse lingue primarie. </p><p>Questo modello utilizza le dimensioni ID(variabili/geocountry) e Aree geografiche. </p> |
| **Profilo visitatore** > **Città geografiche** | Visualizza la città da cui provengono le persone che visitano il sito. <p>**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. </p><p>Questo modello utilizza la dimensione Città. </p> |
| **Profilo visitatore** > **Geo US DMA** | Visualizzare le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui hanno avuto origine le persone che visitano il sito.<p>**Questo può aiutarti** a comprendere meglio le aree geografiche da cui provengono i visitatori più popolari che visitano il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree di maggior successo. </p><!-- This template uses the --> |
| **Profilo visitatore** > **Lingue** | Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. <p>**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.</p><p>Questo modello utilizza la dimensione Lingua.</p> |
| **Profilo visitatore** > **Fusi orari** | Visualizza i fusi orari principali dei visitatori che accedono al tuo sito. <p>**Questo può aiutarti** a capire meglio in quali fusi orari vivono i tuoi visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come regolare la manutenzione del sito in momenti che influenzeranno il minor numero di persone.</p> |
| **Profilo visitatore** > **Domini** | Visualizza i domini principali dei visitatori che accedono al tuo sito. <p>**Questo ti aiuta** a capire meglio da quali organizzazioni provengono i tuoi visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio indirizzare i contenuti ai tuoi clienti più grandi.</p> |
| **Profilo visitatore** > **Domini di primo livello** | Visualizza i domini di primo livello dei visitatori che accedono al tuo sito. <p>**Questo ti aiuta** a capire meglio da quali organizzazioni provengono i tuoi visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio indirizzare i contenuti ai tuoi clienti più grandi.</p> |
| **Profilo visitatore** > **Tecnologia** > **Panoramica tecnologia** | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza </p> |
| **Profilo visitatore** > **Tecnologia** > **Browser** | Visualizza il nome e la versione dei principali browser utilizzati dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Tipi di browser** | Visualizza i nomi delle organizzazioni che hanno creato i browser principali utilizzati dagli utenti per accedere al sito. Questo è diverso dal modello Browser in quanto non elenca diverse versioni dello stesso browser come elementi dimensionali separati.<p>**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i browser principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità. </p><p>Questo modello utilizza la dimensione Tipo di browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Larghezza browser** | Visualizzare le larghezze superiori del browser utilizzate per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le larghezze più comuni del browser. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Altezza browser** | Visualizza le altezze principali del browser utilizzate dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le altezze più comuni del browser. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Sistema operativo** | Visualizzare il nome dei sistemi operativi e la versione utilizzati per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio i sistemi operativi e le versioni più comuni utilizzati dai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i sistemi operativi e le versioni principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p> |
| **Profilo visitatore** > **Tecnologia** > **Tipi di sistema operativo** | Visualizzare il nome dei sistemi operativi utilizzati dagli utenti per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio i sistemi operativi più comuni utilizzati dai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando i sistemi operativi principali. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p> |
| **Profilo visitatore** > **Tecnologia** > [!UICONTROL **Operatore mobile**] | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito.<p>**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Operatore mobile.</p> |
| **Conservazione dei visitatori** > **Frequenza di ritorno** | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito.<p>**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Operatore mobile.</p> |
| **Conservazione dei visitatori** > **Visite di ritorno** | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili.utilizzati dagli utenti per accedere al sito.<p>**Questo può aiutarti** a capire meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle funzionalità di rete di diversi gestori per garantire un&#39;esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Operatore mobile.</p> |
| **Conservazione visitatori** > **Numero visite** | Visualizza quante volte un visitatore ha visitato il sito.<p>**Questo può aiutarti** a comprendere meglio quanto sono coinvolti i visitatori quando ritornano al tuo sito. Questo vale per la durata del visitatore, indipendentemente dall’intervallo di date del progetto.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio regolare le attività di marketing per i visitatori frequenti.</p><p>Questo modello utilizza la dimensione Numero di visite.</p> |
| **Conservazione dei visitatori** > **Ciclo di vendita** > **Fedeltà cliente** | Visualizza il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti. <p>**Questo ti aiuta** a capire meglio in che modo il tuo sito influisce sul comportamento d&#39;acquisto. .</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio concentrarsi sui visitatori che tornano per fare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.</p><p>Questo modello utilizza la dimensione Fedeltà del cliente.</p> |
| **Conservazione dei visitatori** > **Ciclo di vendita** > **Giorni prima del primo acquisto** | Visualizza il numero di giorni che trascorrono tra la prima volta che un visitatore raggiunge il sito e il momento in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento dimensione &quot;1 giorno&quot;.<p>**Questo può aiutarti** a capire meglio quanto tempo impiegano i visitatori per effettuare un acquisto.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio aggiornare il tuo sito per incoraggiare un&#39;acquisizione più veloce.</p><p>Questo modello utilizza la dimensione Giorni prima del primo acquisto.</p> |
| **Conservazione dei visitatori** > **Ciclo di vendita** > **Giorni dall&#39;ultimo acquisto** | Visualizza il tempo trascorso tra l’hit corrente del visitatore e il suo acquisto più recente in quel momento.<p>**Questo può aiutarti** a comprendere meglio il comportamento dei visitatori dopo l&#39;acquisto di qualcosa sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio aggiornare il tuo sito per incoraggiare gli acquisti successivi.</p><p>Questo modello utilizza la dimensione Giorni dall’ultimo acquisto.</p> |
| **Dispositivi mobili** > **Dispositivi mobili** | Visualizza la marca e il modello dei dispositivi mobili utilizzati dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a capire meglio quali dispositivi mobili sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** eseguire una serie di operazioni, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.</p><p>Questo modello utilizza la dimensione Nome dispositivo mobile.</p> |
| **Mobile** > **Tipo di dispositivo mobile** | Visualizza i tipi di dispositivi mobili utilizzati dagli utenti per accedere al sito, ad esempio telefoni e tablet.<p>**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.</p><p>Questo modello utilizza la dimensione Tipo di dispositivo mobile.</p> |
| **Mobile** > **Produttore** | Visualizza quali produttori producono i dispositivi mobili utilizzati dagli utenti per accedere al tuo sito, ad esempio Apple e Samsung.<p>**Questo può aiutarti** a capire meglio quali produttori sono più popolari nella tua base di utenti.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio personalizzare la distribuzione dei contenuti in base alle capacità di diversi produttori per garantire un&#39;esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Produttore di dispositivi mobili.</p> |
| **Mobile** > **Dimensioni schermo** | Visualizza le dimensioni principali dello schermo dei dispositivi mobili utilizzate dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le dimensioni più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p> |
| **Mobile** > **Altezza schermo** | Visualizza le altezze superiori dello schermo del cellulare utilizzate dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le altezze dello schermo più comuni per dispositivi mobili. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p> |
| **Mobile** > **Larghezza schermo** | Visualizzare le larghezze superiori dello schermo dei dispositivi mobili utilizzate dagli utenti per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato ai visitatori.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la qualità del sito testando nuove versioni del sito utilizzando le larghezze più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare gli sforzi di controllo della qualità.</p> |
| **Mobile** > **Utilizzo app mobile** | Visualizza il numero di utenti, avvii e primi avvii nell&#39;app, nonché la durata media della sessione.<p>**Questo ti aiuta** a capire meglio quanto viene utilizzata l&#39;app. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare le prestazioni dell&#39;app in modo che possano essere scalate in base alla quantità di utilizzo.</p><!-- This template uses the --> |
| **Dispositivi mobili** > **Percorsi di app mobili** | Visualizza i pattern di utilizzo principali per la tua app mobile. <p>**Questo ti aiuta** a capire meglio come le persone usano la tua app. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare il modo in cui le persone possono passare da una schermata all&#39;altra per eseguire il targeting dei flussi di lavoro più comuni. </p><!-- This template uses the --> |
| **Mobile** > **Metriche app mobile** | Visualizza alcune delle metriche più comuni per le app mobili. <p>**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.</p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio valutare lo stato e le prestazioni complessive dell&#39;app.</p><!-- This template uses the --> |
| **Dispositivi mobili** > **Messaggistica app mobili** | Visualizza i dati sulle prestazioni per i messaggi in-app e push per la tua app.<p>**Questo ti aiuta** a capire meglio come le persone utilizzano le funzionalità di messaggistica in-app e come le notifiche push indirizzino efficacemente il traffico verso la tua app.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare l&#39;esperienza di notifica push della messaggistica in-app.</p><!-- This template uses the --> |
| **Mobile** > **Prestazioni app mobile** | Visualizza le prestazioni dell’app e dove gli utenti riscontrano problemi. <p>**Questo può aiutarti** a capire meglio se gli utenti che usano la tua app riscontrano rallentamento o prestazioni ridotte. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come risolvere problemi esistenti o migliorare le prestazioni dell&#39;app prima che si verifichino dei problemi.</p><!-- This template uses the --> |
| **Mobile** > **Conservazione app mobile** | Puoi vedere quali utenti sono i più fedeli all’app e cosa fanno all’interno dell’app. <p>**Questo può aiutarti** a capire meglio come i tuoi utenti più fedeli stanno utilizzando la tua app.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio migliorare le tue attività di marketing per le funzionalità utilizzate dai tuoi utenti più fedeli.</p><!-- This template uses the --> |

### Acquisizione {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="Quando si utilizza l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul sito."
>abstract="**Questo ti aiuta** a capire meglio quali dei tuoi canali di marketing sono più efficaci.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio investire di più in canali di marketing efficaci e disinvestire da canali di marketing meno influenti.<br/>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Visualizza il primo canale di marketing con cui un visitatore trova una corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)."
>abstract="**Questo ti aiuta** a capire meglio quali canali di marketing indirizzano il traffico iniziale verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Canale di primo contatto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Visualizza i dettagli sul primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)."
>abstract="**Questo ti può aiutare** a capire meglio cosa ha contribuito all&#39;hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Dettaglio canale di primo contatto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Funnel di conversione campagna"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Visualizza i dettagli sulle prestazioni delle campagne di marketing."
>abstract="**Questo ti aiuta** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggior fatturato. <br/>Questo modello utilizza la metrica Ricavi, la metrica Visualizzazioni prodotto, la metrica Aggiunte carrello, la metrica Ordini e la metrica Unità. Vengono inoltre utilizzate le dimensioni Codice di tracciamento e Dominio di riferimento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Visualizza in che modo il tuo sito web ottiene visitatori su dispositivi mobili."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all&#39;acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza la metrica Percentuale non recapitate e la metrica Rimbalzi. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-acquisition-template"
>title="Visualizza come il tuo sito web ottiene i visitatori."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all&#39;acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza la metrica Percentuale non recapitate e la metrica Rimbalzi. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visualizza affiancati i dati di Google e di Bing Paid Search."
>abstract="**Questo può aiutarti** a comprendere meglio la quantità di traffico che viene inviato al tuo sito e se i clienti si stanno convertendo.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio stimare l&#39;efficacia in termini di costi di una campagna pubblicitaria."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito. <br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito e corrispondenti al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito. <br/>Questo modello utilizza la dimensione Parola chiave di ricerca - Pagato. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca - Naturale. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, indipendentemente dal fatto che sia a pagamento o naturale."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito. <br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.<br/>Questo modello utilizza la dimensione Motore di ricerca. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, che corrispondono al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito. <br/>Questo modello utilizza la dimensione Motore di ricerca - Pagato."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.<br/>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.<br/>Questo modello utilizza la dimensione Motore di ricerca - Naturale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Puoi vedere quale pagina dei risultati di ricerca un visitatore ha fatto clic sul tuo sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensionale per questa variabile è Pagina di ricerca 2."
>abstract="**Questo ti aiuta** a comprendere meglio il livello di classifica delle pagine nei risultati di ricerca.<br/>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, migliorare la tua strategia SEO per garantire che il contenuto venga visualizzato nella prima pagina dei risultati di ricerca."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Visualizza i domini su cui gli utenti fanno clic per raggiungere il tuo sito."
>abstract="**Questo ti aiuta** a capire meglio quali siti di terze parti indirizzano più traffico verso il tuo. Affinché l’elemento dimensione venga visualizzato, è necessario che nel sito esterno esista un collegamento e che un visitatore faccia clic su di esso.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. <br/>Questo modello utilizza la dimensione Dominio di riferimento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Visualizza il primo dominio di riferimento tramite il quale gli utenti hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore."
>abstract="**Questo può aiutarti** a capire meglio quali siti di terze parti originariamente indirizzano il traffico verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento originali. <br/>Questo modello utilizza la dimensione Dominio di riferimento originale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Puoi vedere su quali URL si trovavano i visitatori quando facevano clic per raggiungere il tuo sito. Affinché l’elemento della dimensione venga visualizzato, è necessario che sull’URL esterno esista un collegamento e che un visitatore faccia clic su di esso."
>abstract="**Questo può aiutarti** a capire meglio quali URL specifici indirizzano il maggior traffico verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dagli URL principali. <br/>Questo modello utilizza la dimensione Dominio di riferimento.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Visualizza i canali generici attraverso i quali i visitatori hanno fatto clic per arrivare al sito. Adobe mantiene le regole per ogni canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail."
>abstract="**Questo può aiutarti** a capire meglio quale tipo di referrer gestisce più traffico verso il tuo sito.<br/>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.<br/>Questo modello utilizza la dimensione Tipo referrer."

<!-- markdownlint-enable MD034 -->

Sono disponibili i seguenti modelli:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Rapporto panoramica canale marketing**] | Quando si utilizza l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul sito.<p>**Questo ti aiuta** a capire meglio quali dei tuoi canali di marketing sono più efficaci.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio investire di più in canali di marketing efficaci e disinvestire da canali di marketing meno influenti.</p><p>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Canale marketing primo contatto**] | Visualizza il primo canale di marketing con cui un visitatore trova una corrispondenza durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). <p>**Questo ti aiuta** a capire meglio quali canali di marketing indirizzano il traffico iniziale verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di primo contatto.</p> |
| [!UICONTROL **Canali Marketing**] > [!UICONTROL **Dettagli Canale Marketing Di Primo Contatto**] | Visualizza i dettagli sul primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo ti può aiutare** a capire meglio cosa ha contribuito all&#39;hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Dettaglio canale di primo contatto.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Canale marketing ultimo contatto**] | Visualizza il canale di marketing con cui un visitatore trova corrispondenza più recente durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo ti può aiutare** a capire meglio quali canali di marketing indirizzano il traffico verso il tuo sito che dà luogo a conversioni.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di ultimo contatto.  </p> |
| [!UICONTROL **Canali Marketing**] > [!UICONTROL **Dettagli Canale Marketing Ultimo Contatto**] | Visualizza dettagli sul canale di marketing più recente con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)<p>**Questo ti può aiutare** a capire meglio cosa ha contribuito all&#39;hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing nelle aree più efficaci. </p><p>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Campagne (codice di tracciamento)**] | Visualizza i nomi dei codici di tracciamento sul tuo sito. Puoi inserire collegamenti con valori di parametri di stringhe di query diversi in posizioni diverse su Internet.<p>**Questo ti aiuta** a capire meglio quali collegamenti sono stati più efficaci nel traffico verso il tuo sito. L’aggiunta di stringhe di query del codice di tracciamento è comune nelle e-mail, negli annunci pubblicitari, nei post sui social media e in altre attività di marketing utilizzate dalla tua organizzazione</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggior fatturato.</p><p>Questo modello utilizza la dimensione Codice di tracciamento. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Funnel di conversione campagna**] | <p>**Questo ti può aiutare** a comprendere meglio</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come </p><p>Questo modello utilizza  </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Prestazioni campagna**] | Visualizza i dettagli sulle prestazioni delle campagne di marketing.<p>**Questo ti aiuta** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggior fatturato. </p><p>Questo modello utilizza la metrica Ricavi, la metrica Visualizzazioni prodotto, la metrica Aggiunte carrello, la metrica Ordini e la metrica Unità. Vengono inoltre utilizzate le dimensioni Codice di tracciamento e Dominio di riferimento. </p> |
| **Acquisizione mobile** | Visualizza in che modo il tuo sito ottiene visitatori su dispositivi mobili.<p>**Questo può aiutarti** a comprendere meglio i vari fattori che portano all&#39;acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali più efficaci.</p><p>Questo modello utilizza le metriche Percentuale non recapitate e Percentuale non recapitate. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer.  </p> |
| **Acquisizione Web** | Visualizza come il tuo sito web ottiene i visitatori.<p>**Questo può aiutarti** a comprendere meglio i vari fattori che portano all&#39;acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, ad esempio concentrare le attività di marketing sui canali più efficaci.</p><p>Questo modello utilizza le metriche Percentuale non recapitate e Percentuale non recapitate. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer.  </p> |
| **Advertising Analytics: ricerca a pagamento** | Visualizza affiancati i dati di Google e di Bing Paid Search. <p>**Questo può aiutarti** a comprendere meglio la quantità di traffico che viene inviato al tuo sito e se i clienti si stanno convertendo.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio stimare l&#39;efficacia in termini di costi di una campagna pubblicitaria.</p> |
| **Parole chiave di ricerca - Tutto** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale. <p>**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito. </p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca. </p> |
| **Parole chiave di ricerca - pagate** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito e corrispondenti al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito. </p><p>Questo modello utilizza la dimensione Parola chiave di ricerca - A pagamento. </p> |
| **Parole chiave di ricerca - Naturale** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che gli utenti usano nelle ricerche che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che stanno guidando il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca - Naturale. </p> |
| **Motori di ricerca - Tutti** | Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, indipendentemente dal fatto che sia a pagamento o naturale. <p>**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito. </p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca. </p> |
| **Motori di ricerca - Pagati** | Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il tuo sito, che corrispondono al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito. </p><p>Questo modello utilizza la dimensione Motore di ricerca - Pagato. </p> |
| **Motori di ricerca - Naturale** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il tuo sito che non corrispondono al rilevamento di ricerche a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca utilizzati dagli utenti che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come concentrare le tue attività SEO sui motori di ricerca che generano più traffico verso il sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca - Naturale. </p> |
| **Classificazione di tutte le pagine di ricerca** | Puoi vedere quale pagina dei risultati di ricerca un visitatore ha fatto clic sul tuo sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensionale per questa variabile è &quot;Pagina di ricerca 2&quot;.<p>**Questo ti aiuta** a comprendere meglio il livello di classifica delle pagine nei risultati di ricerca.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, migliorare la tua strategia SEO per garantire che il contenuto venga visualizzato nella prima pagina dei risultati di ricerca. </p> |
| **Domini di riferimento** | Visualizza i domini su cui gli utenti fanno clic per raggiungere il tuo sito.<p>**Questo ti aiuta** a capire meglio quali siti di terze parti indirizzano più traffico verso il tuo. Affinché l’elemento dimensione venga visualizzato, è necessario che nel sito esterno esista un collegamento e che un visitatore faccia clic su di esso.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. </p><p>Questo modello utilizza la dimensione Dominio di riferimento. </p> |
| **Domini di riferimento originali** | Visualizza il primo dominio di riferimento tramite il quale gli utenti hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore.<p>**Questo può aiutarti** a capire meglio quali siti di terze parti originariamente indirizzano il traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento originali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento originale. </p> |
| **Riferimenti** | Puoi vedere su quali URL si trovavano i visitatori quando facevano clic per raggiungere il tuo sito. Affinché l’elemento della dimensione venga visualizzato, è necessario che sull’URL esterno esista un collegamento e che un visitatore faccia clic su di esso.  <p>**Questo può aiutarti** a capire meglio quali URL specifici indirizzano il maggior traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dagli URL principali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento </p><p>Questo modello utilizza la dimensione Referrer. </p> |
| **Tipi di riferimento** | Visualizza i canali generici attraverso i quali i visitatori hanno fatto clic per arrivare al sito. Adobe mantiene le regole per ogni canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail.<p>**Questo può aiutarti** a capire meglio quale tipo di referrer gestisce più traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o modificare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.</p><p>Questo modello utilizza la dimensione Tipo referrer.</p> |