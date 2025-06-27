---
description: Scopri come utilizzare i modelli in Analysis Workspace.
title: Utilizzare i modelli
feature: Analysis Workspace
role: User, Admin
exl-id: 9e5d1b35-e2b3-4fa5-af12-67bb913675bc
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '18642'
ht-degree: 91%

---

# Utilizzare i modelli

I modelli (o i modelli aziendali) in Analysis Workspace forniscono informazioni rapide sugli scenari di reporting più comuni. Di seguito sono riportati alcuni esempi di domande a cui puoi rispondere con i modelli:

* quante persone visitano il sito
* quanti di questi visitatori sono visitatori univoci (conteggiati una sola volta)
* come sono arrivati al sito (ad esempio, se hanno seguito un collegamento o ci sono arrivati direttamente)
* quali parole chiave hanno utilizzato i visitatori per cercare il contenuto del sito
* per quanto tempo i visitatori sono rimasti su una determinata pagina o sull’intero sito
* su quali collegamenti i visitatori hanno fatto clic e quando hanno lasciato il sito
* quali canali di marketing sono più efficaci nel generare ricavi o eventi di conversione
* quanto tempo hanno trascorso a guardare un video
* quali browser e dispositivi hanno utilizzato per visitare il sito

Le informazioni seguenti descrivono come accedere e utilizzare i modelli della scheda [!UICONTROL Templates] in Analysis Workspace.

## Accedere ed eseguire un modello

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**].

   <!--update screenshot -->

   ![Scheda Rapporti](assets/view-prebuilt-templates-full.png)

1. Nella sezione [!UICONTROL **Modelli**] seleziona una delle schede seguenti:

   * **[!UICONTROL Adobe templates]**: mostra tutti i modelli forniti da Adobe.

   * **[!UICONTROL _modelli login_company_name _]**: mostra tutti i modelli aziendali creati per la tua organizzazione.

     Solo gli amministratori possono creare modelli aziendali. Per ulteriori informazioni sulla creazione di un modello aziendale, vedere [Creare e gestire modelli](/help/analyze/analysis-workspace/templates/create-templates.md).

1. Per modificare la modalità di visualizzazione dei modelli disponibili, utilizza una delle opzioni seguenti:

   * Scegli se visualizzare i modelli in una vista a colonne o in una vista a schede selezionando l’icona della vista a colonne ![ViewColumn](/help/assets/icons/ViewColumn.svg) o della vista a schede ![Card](/help/assets/icons/Card.svg).

   * Quando utilizzi la vista a schede ![Card](/help/assets/icons/Card.svg), scegli uno dei seguenti criteri di ordinamento: **[!UICONTROL Most recently used]**, **[!UICONTROL Most popular]**, **[!UICONTROL Alphabetical]**, **[!UICONTROL Categorical]**.

1. Nel campo di ricerca, iniziare a digitare il nome del modello che si desidera trovare, quindi selezionarlo dall&#39;elenco dei modelli. Puoi anche effettuare ricerche nell’elenco dei modelli per prop, eVar e numero evento. <!-- still true? -->

   Oppure

   Seleziona la categoria di modelli che desideri visualizzare, quindi seleziona il modello dall’elenco dei modelli.

   >[!TIP]
   >
   >Per spostarti nel menu utilizzando i tasti freccia, premi il tasto Barra obliqua (/), quindi premi il tasto Freccia giù. Premi Invio per caricare il modello selezionato.

   Per un elenco di modelli disponibili, consulta la sezione [Modelli disponibili](#available-reports) di seguito.

## Creare un progetto basato su un modello {#use-reports}

Un modello potrebbe non soddisfare esattamente le tue esigenze, ma può avvicinarvisi. In questi casi, puoi utilizzare il modello come punto di partenza e personalizzarlo in base alle tue esigenze.

Se esci da un modello dopo aver effettuato modifiche, ti viene richiesto di salvare o eliminare le modifiche. Quando si salvano le modifiche a un modello, questo viene salvato come un nuovo progetto.

Per personalizzare un modello e salvarlo come progetto:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Workspace**].

1. Seleziona la scheda [!UICONTROL **Modelli**] 

1. Seleziona il modello che desideri visualizzare. Ad esempio, in [!UICONTROL **Più popolari**], seleziona il modello [!UICONTROL **Pagine**].

   ![Rapporto Pagine](assets/pages-report.png)

1. Come mostrato in Analysis Workspace, il modello Pagine mostra due [visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Grafico a barre](/help/analyze/analysis-workspace/visualizations/bar.md) e [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) e una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). La metrica utilizzata è Occorrenze.
1. Esegui una delle operazioni seguenti:

   * Visualizza il modello.
   * Puoi trascinare uno o più segmenti nella zona di rilascio Segmento, nella parte superiore. Ad esempio, trascina il segmento [!UICONTROL **Clienti mobile**] e visualizza i risultati.
   * Modifica l’intervallo di date andando sul calendario in alto a destra.
   * Aggiungi raggruppamenti di dimensioni, trascina altre metriche e personalizza il modello a livello generale in base alle tue esigenze.

1. (Facoltativo) Salva il modello come progetto selezionando [!UICONTROL **Progetto**] > [!UICONTROL **Salva**].

   Il rapporto viene salvato come nuovo progetto e non viene modificato il rapporto esistente. Per ulteriori informazioni sul salvataggio dei progetti, consulta [Salvare i progetti](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Modelli disponibili

Per accedere a tutti i modelli predfiniti disponibili:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Area di lavoro**], quindi scegli la scheda [!UICONTROL **Modelli**].

   I modelli predefiniti sono organizzati per categoria.

   <!--add screenshot-->

1. Seleziona una categoria per visualizzare i modelli al suo interno.

   Le sezioni seguenti corrispondono alle categorie disponibili e forniscono informazioni su ciascun modello.

   * **[[!UICONTROL Most popular]](#most-popular)**

   * **[[!UICONTROL Engagement]](#engagement)**

### Most popular (Più popolari) {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come le vendite delle unità aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche acquistano il maggior numero di unità e quale sia la tendenza delle rispettive vendite nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando le vendite di unità prima e dopo l’avvio della campagna. Oppure è possibile confrontare le vendite di unità durante le festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Unità."

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Modello per le esercitazioni"
>abstract="Scopri la terminologia e i passaggi più comuni di Analysis Workspace per creare la tua prima analisi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identifica le pagine più popolari e quelle meno popolari."
>abstract="**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui è più interessato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare i metadati della pagina per aumentare la visibilità delle pagine meno visualizzate oppure dedicare del tempo al miglioramento dei contenuti delle pagine più visualizzate.<br/>Questo modello utilizza la dimensione Pagina e la metrica Visualizzazioni pagina."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Visualizza il numero totale di visualizzazioni di pagina. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visualizzazioni pagina."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Visualizza il numero totale di visite. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. "
>abstract="**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentano o diminuiscono nel tempo o rispetto a un periodo precedente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se una campagna di marketing avviata di recente è riuscita ad attirare nuove persone sul sito confrontando i visitatori univoci prima e dopo l’avvio della campagna. Oppure è possibile confrontare il numero di persone che visitano il sito durante le festività rispetto all’anno precedente.<br/>Questo modello utilizza la dimensione Giorno e la metrica Visitatori univoci. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Visualizza un rapporto che mostra fianco a fianco le metriche relative a visualizzazioni pagina, visite e visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che visitano il sito, del numero di volte che le pagine sono state visitate e del numero di sessioni.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell’anno o prima e dopo l’esecuzione di campagne di marketing. <br/>Questo modello utilizza la dimensione Giorno e le metriche di Visualizzazioni pagina, Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Visualizza le sezioni del sito più popolari o con le prestazioni migliori."
>abstract="**Questo può aiutarti** a comprendere meglio quali sezioni del tuo sito sono più visitate.<br>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali tra i prodotti o i servizi che fornisci generano maggiore interesse.<br/>Questo modello utilizza la dimensione Sezione sito e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Visualizza i luoghi più comuni in cui le persone vanno immediatamente dopo aver visitato una determinata pagina."
>abstract="**Questo può aiutarti** a comprendere meglio il comportamento degli utenti dopo aver visitato una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione.<br/>Questo modello utilizza la dimensione Pagina e la metrica Eventi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="Visualizza i luoghi più comuni in cui le persone vanno immediatamente prima di visitare una determinata pagina."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine indirizzano il traffico maggiore verso una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le pagine che non sono visualizzate come le pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Visualizza i collegamenti che sono stati più efficaci nel generare traffico verso il tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali codici di tracciamento (e i collegamenti associati a essi) sono stati più utilizzati per accedere al tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare la strategia su dove aggiungere i collegamenti al tuo sito.<br/>Questo modello utilizza la dimensione Codice di tracciamento e la metrica Visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un periodo di tempo."
>abstract="**Questo può aiutarti** a comprendere quali sono i prodotti con la domanda più alta o più bassa.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le strategie di marketing per promuovere prodotti con prestazioni elevate oppure per migliorare o interrompere prodotti con prestazioni insufficienti. Puoi anche modificare l’inventario dei prodotti in base all’analisi dei dati.<br/>Questo modello utilizza la dimensione Prodotto e la metrica Ordini."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Visualizza i canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno generato delle conversioni.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.<br/>Questo modello utilizza la dimensione Canale di ultimo contatto e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito generando conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.<br/>Questo modello utilizza la dimensione Dettaglio canale di ultimo contatto e la metrica Visitatori univoci. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Visualizza l’importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere il modo in cui i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi della dimensione hanno contribuito ai ricavi.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano maggiori ricavi.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ricavi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio come aumenta o diminuisce nel tempo l’interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche stanno effettuando il maggior numero di ordini e quale sia la tendenza di tali ordini nel tempo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo l’avvio della campagna. Oppure potresti confrontare gli ordini relativi alle festività anno per anno.<br/>Questo modello utilizza la dimensione Giorno e la metrica Ordini."

<!-- markdownlint-enable MD034 -->

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial di formazione**] | Scopri la terminologia e i passaggi più comuni di Analysis Workspace per creare la tua prima analisi. |
| [!UICONTROL **Pagine**] | <!--duplicated in Engagement section--> Identifica le pagine più popolari e quelle meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui è più interessato.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.</p><p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visualizzazioni di pagina. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Page Views](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visite**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visite. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visits](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitatori**] | <!--duplicated in Engagement section--> Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentano o diminuiscono nel tempo o rispetto a un periodo precedente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se una campagna di marketing avviata di recente è riuscita ad attirare nuove persone sul sito confrontando i visitatori univoci prima e dopo l’avvio della campagna. Oppure è possibile confrontare il numero di persone che visitano il sito durante le festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Engagement section--> Visualizza un rapporto che mostra fianco a fianco le metriche relative a visualizzazioni pagina, visite e visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che visitano il sito, del numero di volte che le pagine sono state visitate e del numero di sessioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell’anno o prima e dopo l’esecuzione di campagne di marketing. </p><p>Questo modello utilizza la [dimensione Giorno](/help/components/dimensions/day.md), [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), [metrica Visite](/help/components/metrics/visits.md) e [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Sezioni del sito**] | Visualizza le sezioni del sito più popolari o con le prestazioni migliori. <p>**Questo può aiutarti** a comprendere meglio quali sezioni del tuo sito sono più visitate.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali tra i prodotti o i servizi che fornisci generano maggiore interesse.</p> <p>Questo modello utilizza la [dimensione Sezione sito](/help/components/dimensions/site-section.md) e la [metrica Visite](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Codice di tracking**] | Visualizza i collegamenti che sono stati più efficaci nel generare traffico verso il tuo sito. <p>**Questo può aiutarti** a comprendere meglio quali codici di tracciamento (e i collegamenti associati a essi) sono stati più utilizzati per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare la strategia su dove aggiungere i collegamenti al tuo sito.</p><p>Questo modello utilizza la dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md) e la metrica [Visite](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Pagina successiva**] | Visualizza i luoghi più comuni in cui le persone vanno immediatamente dopo aver visitato una determinata pagina. <p>**Questo può aiutarti** a comprendere meglio il comportamento degli utenti dopo aver visitato una determinata pagina.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione.</p> <p>Questo modello utilizza la dimensione Pagina e la metrica Eventi.</p> |
| [!UICONTROL **Pagina precedente**] | Visualizza i luoghi più comuni in cui le persone vanno immediatamente prima di visitare una determinata pagina. <p>**Questo può aiutarti** a comprendere meglio quali pagine indirizzano il traffico maggiore verso una determinata pagina.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le pagine che non sono visualizzate come le pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente.</p><p>Questo modello utilizza la dimensione Pagina e la metrica Eventi.</p> |
| [!UICONTROL **Prodotti**] | Visualizza il numero di ordini per prodotto. I dati vengono visualizzati in un periodo di tempo. <p>**Questo può aiutarti** a comprendere quali sono i prodotti con la domanda più alta o più bassa.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio modificare le strategie di marketing per promuovere prodotti con prestazioni elevate oppure per migliorare o interrompere prodotti con prestazioni insufficienti. Puoi anche modificare l’inventario dei prodotti in base all’analisi dei dati.</p><p>Questo modello utilizza la [dimensione prodotto](/help/components/dimensions/product.md) e la [metrica ordini](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Canale di ultimo contatto**] | Visualizza i canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito e che hanno generato delle conversioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.</p><p>Questo modello utilizza la [dimensione Canale di ultimo contatto](/help/components/dimensions/last-touch-channel.md) e la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Dettaglio del canale di ultimo contatto**] | Visualizza i dettagli sui canali di marketing più recenti con cui i visitatori corrispondono durante il periodo di coinvolgimento (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere non solo quali canali di marketing sono stati più efficaci nel portare le persone sul tuo sito generando conversioni, ma anche i dettagli su tali canali di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio assegnare più risorse ai canali con prestazioni elevate o meno risorse ai canali con prestazioni insufficienti.</p><p>Questo modello utilizza la dimensione [Dettaglio canale di ultimo contatto](/help/components/dimensions/last-touch-detail.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Ricavi**] | Visualizza l’importo monetario dei prodotti acquistati in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti.<p>**Questo può aiutarti** a comprendere il modo in cui i ricavi aumentano o diminuiscono nel tempo. Puoi combinare questa metrica con qualsiasi dimensione per scoprire quali elementi della dimensione hanno contribuito ai ricavi.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio proiettare i ricavi futuri in base alle tendenze precedenti. Puoi anche aggiungere un’altra dimensione, come la dimensione Codice di tracciamento, per scoprire quali campagne generano maggiori ricavi.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Revenue](/help/components/metrics/revenue.md).</p> |
| [!UICONTROL **Ordini**] | Visualizza il numero totale di eventi di acquisto. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come aumenta o diminuisce nel tempo l’interesse per i tuoi prodotti e servizi. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche stanno effettuando il maggior numero di ordini e quale sia la tendenza di tali ordini nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando gli ordini prima e dopo l’avvio della campagna. Oppure potresti confrontare gli ordini relativi alle festività anno per anno.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Orders](/help/components/metrics/orders.md).</p> |
| [!UICONTROL **Unità**] | Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come le vendite delle unità aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche acquistano il maggior numero di unità e quale sia la tendenza delle rispettive vendite nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando le vendite di unità prima e dopo l’avvio della campagna. Oppure è possibile confrontare le vendite di unità durante le festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Units](/help/components/metrics/units.md).</p> |

### Coinvolgimento {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="Visualizza le dimensioni e le metriche attualmente raccolte sul tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio le tendenze sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio rispondere a e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing correnti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visualizza il tempo medio trascorso dagli utenti prima di un evento di successo."
>abstract="**Questo può aiutarti** a comprendere meglio quanto tempo impiegano i visitatori per eseguire un’azione desiderata, ad esempio per effettuare un acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori possono raggiungere più rapidamente un evento di successo.<br/>Questo modello utilizza la dimensione Tempo prima dell’evento e la metrica Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visualizza il punto in cui le persone abbandonano o proseguono attraverso una sequenza di pagine predefinita."
>abstract="**Questo può aiutarti** a comprendere meglio dove le persone abbandonano il percorso dell’utente.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come analizzare i tassi di conversione per processi specifici (come un processo di acquisto o di registrazione) oppure analizzare le correlazioni tra gli eventi. Ad esempio, la percentuale di persone che ha visualizzato l’informativa sulla privacy e ha poi acquistato un prodotto. Puoi anche utilizzare questo modello per eseguire confronti paralleli di due segmenti diversi dello stesso rapporto.<br/>Questo modello utilizza la visualizzazione Fallout."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Visualizza quali dispositivi le persone hanno utilizzato in tutti i punti del percorso."
>abstract="**Questo può aiutarti** a comprendere meglio quante persone interagiscono col tuo brand, i tipi di dispositivi che utilizzano e come l’utilizzo di più dispositivi influisce sulla loro esperienza. Ad esempio, con quale frequenza le persone iniziano un’attività da un dispositivo mobile e successivamente passano a un PC desktop per completare tale attività? Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo? E così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare determinate parti del percorso dell’utente per un’esperienza mobile.<br/>Questo modello utilizza le visualizzazioni Flusso e Fallout, l’analisi Coorte, e le metriche Persone e Dispositivi univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Visualizza chi sono gli utenti più fedeli e cosa fanno sul sito."
>abstract="**Questo può aiutarti** a comprendere quante volte una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e quanti giorni passano tra visite successive.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti più efficaci nel riportare le persone sul sito.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Visualizza le tendenze e le metriche principali relative al consumo di audio su tutti i dispositivi digitali."
>abstract="**Questo può aiutarti** a comprendere meglio come i visitatori consumano contenuti audio sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti maggiormente consultati.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Visualizza le tendenze e le metriche principali relative al consumo di contenuti multimediali su tutti i dispositivi digitali."
>abstract="**Questo può aiutarti** a comprendere meglio quante volte una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e quanti giorni passano tra visite successive.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti più efficaci nel riportare le persone sul sito.<br/>Questo modello utilizza le metriche Visite e Visitatori univoci."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visualizza quante volte un elemento dimensione è stato presente durante un ricaricamento. In genere un ricaricamento si verifica quando un visitatore aggiorna la finestra del browser."
>abstract="**Questo può aiutarti** a individuare quando su una determinata pagina potrebbero verificarsi problemi che inducono il visitatore a ricaricarla.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali pagine presentano problemi da risolvere.<br/>Questo modello utilizza la metrica Ricaricamenti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Visualizza le pagine principali a cui le persone accedono alla prima visita del tuo sito durante il ciclo di vita di un visitatore."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o quali sono le prime impressioni dei visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visualizza il numero di visite in cui è stata visitata una singola pagina univoca."
>abstract="**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.<br/>Questo modello utilizza la dimensione Visite a pagina singola."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Visualizza i dati sulle prestazioni per il sito Adobe Experience Manager."
>abstract="**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare le impostazioni di Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="Visualizza i dati sulle prestazioni per Adobe Experience Manager Forms."
>abstract="**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare le impostazioni di Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visualizza e analizza gli effetti della Prevenzione intelligente del tracciamento (ITP) sulla raccolta dei dati e sul reporting."
>abstract="**Questo può aiutarti** a comprendere meglio la potenziale perdita di dati dovuta alle restrizioni sui cookie imposte dall’ITP.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio adattare la configurazione dell’analisi per ridurre al minimo l’impatto dell’ITP."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita, nonché il tempo medio trascorso dagli utenti prima di un evento di successo. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio i livelli di coinvolgimento dei visitatori e quanto tempo impiegano per eseguire un’azione desiderata, ad esempio per effettuare un acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se le modifiche al tuo sito migliorano la possibilità dei visitatori di raggiungere rapidamente un evento di successo.<br/>Questo modello utilizza la dimensione Giorno e la metrica Tempo trascorso per visita (secondi)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Visualizza quali sono i contenuti web maggiormente consumati e che coinvolgono gli utenti."
>abstract="**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.<br/>Questo modello utilizza la dimensione Pagina e le metriche Visualizzazioni pagina, Visite, Visitatori univoci, Percentuale di entrata, Percentuale di mancati recapiti, Percentuale di uscita e Velocità operazioni. Inoltre utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Visualizza quali sono i contenuti multimediali maggiormente utilizzati e che coinvolgono gli utenti."
>abstract="**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.<br/>Questo modello utilizza la dimensione Pagina e le metriche Visualizzazioni pagina, Visite, Visitatori univoci, Percentuale di entrata, Percentuale di mancati recapitati, Percentuale di uscita e Velocità operazioni. Inoltre utilizza le visualizzazioni Flusso per le sezioni di entrata, uscita e principali; una visualizzazione con grafico a dispersione che mostra le visualizzazioni di pagina per le pagine più comuni; una visualizzazione a barre che mostra le visualizzazioni di pagina per blocchi di tempo e una visualizzazione a linee che mostra una visualizzazione con le tendenze del tempo medio trascorso sul sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="Visualizza i luoghi più comuni in cui le persone vanno immediatamente dopo aver visitato o prima di visitare un determinato luogo."
>abstract="**Questo può aiutarti** a comprendere come il traffico si sposta da una determinata pagina ad altre parti del sito e i percorsi seguiti dalle persone per arrivare a una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se la progettazione o il layout della pagina può essere ottimizzato per indirizzare gli utenti verso le pagine più desiderate, ad esempio una pagina dove effettuare un acquisto o lasciare una recensione. Oppure valuta se le informazioni presenti nella pagina corrente sono in grado di fornire la direzione o le azioni che le persone cercano quando arrivano dalle pagine precedenti. Oppure puoi valutare se le pagine che non sono visualizzate come pagine precedenti necessitano di collegamenti più evidenti alla pagina corrente.<br/>Questo modello utilizza il pannello Elemento successivo o precedente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Visualizza informazioni chiave su qualsiasi pagina delle tue proprietà. Mostra le visualizzazioni di pagina, una linea di tendenza, una visualizzazione di flusso e altro ancora."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone interagiscono con una determinata pagina.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come analizzare le prestazioni della pagina rispetto a un periodo di tempo o comprendere meglio cosa favorisce il traffico verso la pagina.<br/>Questo modello utilizza la metrica Visualizzazioni pagina. Utilizza anche le visualizzazioni a linee e flusso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Visualizza le pagine principali a cui gli utenti accedono quando visitano il tuo sito per la prima volta."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o le prime impressioni che i visitatori hanno rispetto ad esso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Visualizza le pagine principali a cui le persone accedono immediatamente prima di lasciare il sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali pagine allontanano le persone dal sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l’esperienza che le persone hanno del sito prima di lasciarlo, oppure includere contenuti o collegamenti per incoraggiarle a rimanere sullo stesso.<br/>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera."

<!-- markdownlint-enable MD034 -->

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Metriche chiave**] | <!--duplicated in Most popular section--> Visualizza un rapporto che mostra fianco a fianco le metriche relative a visualizzazioni pagina, visite e visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a confrontare queste metriche importanti per ottenere un quadro più completo del numero di persone univoche che visitano il sito, del numero di volte che le pagine sono state visitate e del numero di sessioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare il numero medio di pagine visualizzate da ogni persona durante la visita al sito in una determinata settimana o mese e come è cambiato durante determinati periodi dell’anno o prima e dopo l’esecuzione di campagne di marketing. </p><p>Questo modello utilizza la [dimensione Giorno](/help/components/dimensions/day.md), [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), [metrica Visite](/help/components/metrics/visits.md) e [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Visualizzazioni pagina**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visualizzazioni di pagina. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Page Views](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Pagine**] | <!--duplicated in Most popular section-->Identifica le pagine più popolari e quelle meno popolari. <p>**Questo può aiutarti** a comprendere meglio il tuo pubblico e il tipo di informazioni a cui è più interessato.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, come regolare i metadati della pagina per aumentare la visibilità sulle pagine visualizzate meno o passare del tempo a migliorare il contenuto delle pagine più visualizzate.</p><p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md).</p> |
| [!UICONTROL **Visite**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visite. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come il traffico sul tuo sito potrebbe aumentare o diminuire nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando il traffico del sito prima e dopo l’avvio della campagna. Oppure è possibile confrontare il traffico nel periodo delle festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visits](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Visitatori**] | <!--duplicated in Most popular section-->Visualizza il numero totale di visitatori univoci. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come la portata e la dimensione del pubblico del tuo sito aumentano o diminuiscono nel tempo o rispetto a un periodo precedente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se una campagna di marketing avviata di recente è riuscita ad attirare nuove persone sul sito confrontando i visitatori univoci prima e dopo l’avvio della campagna. Oppure è possibile confrontare il numero di persone che visitano il sito durante le festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Tempo trascorso per visita**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.</p><p>Questo modello utilizza la dimensione [Giorno](/help/components/dimensions/day.md) e la metrica [Tempo trascorso per visita (secondi)](/help/components/metrics/time-spent-per-visit.md).</p> |
| [!UICONTROL **Tempo precedente all’evento**] | Visualizza il tempo medio trascorso dagli utenti prima di un evento di successo. <p>**Questo può aiutarti** a comprendere meglio quanto tempo impiegano i visitatori per eseguire un’azione desiderata, ad esempio per effettuare un acquisto.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori possono raggiungere più rapidamente un evento di successo.</p><p>Questo modello utilizza la dimensione [Tempo precedente all&#39;evento](/help/components/dimensions/time-prior-to-event.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Sezioni del sito**] | <!--duplicated in Most popular section-->Visualizza le sezioni del sito più popolari o con le prestazioni migliori. <p>**Questo può aiutarti** a comprendere meglio quali sezioni del tuo sito sono più visitate.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali tra i prodotti o i servizi che fornisci generano maggiore interesse.</p> <p>Questo modello utilizza la [dimensione Sezione sito](/help/components/dimensions/site-section.md) e la [metrica Visite](/help/components/metrics/visits.md).</p> |
| [!UICONTROL **Tempo reale**] | Visualizza le dimensioni e le metriche attualmente raccolte sul tuo sito. <p>**Questo può aiutarti** a comprendere meglio le tendenze sul tuo sito.</p><p>**In base a ciò che hai appreso, potresti** rispondere e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing correnti.</p> <p>Questo modello utilizza il [rapporto in tempo reale](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> |
| [!UICONTROL **Consumo di contenuti web**] | Visualizza quali sono i contenuti web maggiormente consumati e che coinvolgono gli utenti.<p>**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.</p> <p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), la [metrica Visite](/help/components/metrics/visits.md), la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md), la [metrica Tasso di ingresso](/help/components/metrics/entries.md), la [metrica Tasso di mancato recapito](/help/components/metrics/bounce-rate.md), la [metrica Tasso di uscita](/help/components/metrics/exits.md) e la [metrica Velocità contenuto](/help/components/metrics/content-velocity.md). Utilizza anche [Visualizzazioni di flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per le sezioni di entrata, uscita e superiori.</p> |
| [!UICONTROL **Consumo di contenuti multimediali**] | Visualizza quali sono i contenuti multimediali maggiormente utilizzati e che coinvolgono gli utenti.<p>**Questo può aiutarti** a comprendere meglio dove vanno le persone che accedono per la prima volta al sito, quali sezioni visitano di più e quali pagine hanno più probabilità di allontanarle dallo stesso.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.</p> <p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), la [metrica Visite](/help/components/metrics/visits.md), la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md), la [metrica Tasso di ingresso](/help/components/metrics/entries.md), la [metrica Tasso di mancato recapito](/help/components/metrics/bounce-rate.md), la [metrica Tasso di uscita](/help/components/metrics/exits.md) e la [metrica Velocità contenuto](/help/components/metrics/content-velocity.md). Vengono inoltre utilizzate [Visualizzazioni di flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per le sezioni di entrata, uscita e superiori; una [Visualizzazione grafico a dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) che mostra le visualizzazioni di pagina per le pagine più comuni; una [Visualizzazione a barre](/help/analyze/analysis-workspace/visualizations/bar.md) che mostra le visualizzazioni di pagina per periodo fisso; e una [Visualizzazione a linee](/help/analyze/analysis-workspace/visualizations/line.md) che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito.</p> |
| [!UICONTROL **Flusso pagina successivo e precedente**] | Visualizza i luoghi più comuni in cui le persone vanno prima o dopo aver visitato un determinato luogo.<p>**Questo può aiutarti** a capire meglio dove vanno le persone al primo accesso al sito, quali sezioni del sito sono più visitate e quali pagine hanno più probabilità di essere visitate prima di lasciare il sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali percorsi del sito conducono le persone verso le pagine più importanti e quali pagine hanno maggiori probabilità di allontanarle dallo stesso.</p> <p>Questo modello utilizza la [dimensione Pagina](/help/components/dimensions/page.md) e la [metrica Visualizzazioni pagina](/help/components/metrics/page-views.md), la [metrica Visite](/help/components/metrics/visits.md), la [metrica Visitatori univoci](/help/components/metrics/unique-visitors.md), la [metrica Tasso di ingresso](/help/components/metrics/entries.md), la [metrica Tasso di mancato recapito](/help/components/metrics/bounce-rate.md), la [metrica Tasso di uscita](/help/components/metrics/exits.md) e la [metrica Velocità contenuto](/help/components/metrics/content-velocity.md). Vengono inoltre utilizzate [visualizzazioni Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per le sezioni di entrata, uscita e principali; una [visualizzazione Grafico a dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) che mostra le visualizzazioni di pagina per le pagine più comuni; una [visualizzazione a barre](/help/analyze/analysis-workspace/visualizations/bar.md) che mostra le visualizzazioni di pagina per periodo fisso; e una [visualizzazione a linee](/help/analyze/analysis-workspace/visualizations/line.md) che mostra una visualizzazione con tendenze del tempo medio trascorso sul sito.</p> |
| [!UICONTROL **Fallout**] | Visualizza il punto in cui le persone abbandonano o proseguono attraverso una sequenza di pagine predefinita.<p>**Questo può aiutarti** a comprendere meglio dove le persone abbandonano il percorso dell’utente.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come analizzare i tassi di conversione per processi specifici (come un processo di acquisto o di registrazione) oppure analizzare le correlazioni tra gli eventi. Ad esempio, la percentuale di persone che ha visualizzato l’informativa sulla privacy e ha poi acquistato un prodotto. Puoi anche utilizzare questo modello per eseguire confronti paralleli di due segmenti diversi dello stesso rapporto.</p> <p>Questo modello utilizza la [Visualizzazione di fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> |
| [!UICONTROL **Analisi cross-device**] | Visualizza quali dispositivi le persone hanno utilizzato in tutti i punti del percorso.<p>**Questo può aiutarti** a comprendere meglio quante persone interagiscono col tuo brand, i tipi di dispositivi che utilizzano e come l’utilizzo di più dispositivi influisce sulla loro esperienza. Ad esempio, con quale frequenza le persone iniziano un’attività da un dispositivo mobile e successivamente passano a un PC desktop per completare tale attività? Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo? E così via.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare determinate parti del percorso dell’utente per un’esperienza mobile.</p> <p>Questo modello utilizza la [visualizzazione Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), la [visualizzazione Abbandono](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), la [analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), la [metrica Persone](/help/components/metrics/people.md) e la [metrica Dispositivi univoci](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Conservazione Web**] | Visualizza chi sono gli utenti più fedeli e cosa fanno sul sito.<p>**Questo può aiutarti** a comprendere quante volte una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e quanti giorni passano tra visite successive.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti più efficaci nel riportare le persone sul sito.<p>Questo modello utilizza la metrica [Visite](/help/components/metrics/visits.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Consumo di contenuti multimediali in streaming**] | Visualizza le tendenze e le metriche principali relative al consumo di audio su tutti i dispositivi digitali.<p>**Questo può aiutarti** a comprendere meglio come i visitatori consumano contenuti audio sul tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti maggiormente consultati.<p>Questo modello utilizza la metrica [Visite](/help/components/metrics/visits.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| [!UICONTROL **Recency, frequenza, fedeltà contenuti multimediali**] | Visualizza le tendenze e le metriche principali relative al consumo di contenuti multimediali su tutti i dispositivi digitali.<p>**Questo può aiutarti** a comprendere meglio quante volte una persona visita il tuo sito in media, la frequenza con cui le persone ritornano al sito e quanti giorni passano tra visite successive.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio analizzare quali sono i contenuti più efficaci nel riportare le persone sul sito.<p>Questo modello utilizza la metrica [Visite](/help/components/metrics/visits.md) e la metrica [Visitatori univoci](/help/components/metrics/unique-visitors.md).</p> |
| **[!UICONTROL Page analysis]** > [!UICONTROL **Riepilogo pagina**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.</p><p>Questo modello utilizza la dimensione [Giorno](/help/components/dimensions/day.md) e la metrica [Tempo trascorso per visita (secondi)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Page analysis]** > [!UICONTROL **Ricarica**] | Visualizza quante volte un elemento dimensione è stato presente durante un ricaricamento. In genere un ricaricamento si verifica quando un visitatore aggiorna la finestra del browser. <p>**Questo può aiutarti** a individuare quando su una determinata pagina potrebbero verificarsi problemi che inducono il visitatore a ricaricarla.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare quali pagine presentano problemi da risolvere.</p><p>Questo modello utilizza la metrica [Ricarica](https://experienceleague.adobe.com/it/docs/analytics/components/metrics/reloads).</p> |
| **[!UICONTROL Page analysis]** > [!UICONTROL **Tempo trascorso sulla pagina**] | Visualizza il tempo medio che i visitatori trascorrono sul sito durante ogni visita. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.</p><p>Questo modello utilizza la dimensione [Giorno](/help/components/dimensions/day.md) e la metrica [Tempo trascorso per visita (secondi)](/help/components/metrics/time-spent-per-visit.md).</p> |
| **[!UICONTROL Entries & exits]** > [!UICONTROL **Pagine di ingresso**] | Visualizza le pagine principali a cui gli utenti accedono quando visitano per la prima volta il tuo sito per una determinata sessione. <p>**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o quali sono le prime impressioni dei visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera.</p> |
| **[!UICONTROL Entries & exits]** > [!UICONTROL **Pagine di ingresso originali**] | Visualizza le pagine principali a cui le persone accedono alla prima visita del tuo sito durante il ciclo di vita di un visitatore. <p>**Questo può aiutarti** a comprendere meglio quali pagine generano maggior traffico verso il tuo sito o quali sono le prime impressioni dei visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare l’esperienza iniziale o assicurarsi che le pagine visualizzate per prima, all’accesso, siano accoglienti e forniscano i collegamenti necessari verso altre aree del sito.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera.</p> |
| **[!UICONTROL Entries & exits]** > [!UICONTROL **Visite a pagina singola**] | Visualizza il numero di visite in cui è stata visitata una singola pagina univoca. <p>**Questo può aiutarti** a comprendere meglio il livello di coinvolgimento dei visitatori e quanto tempo trascorrono sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare se, in seguito a modifiche apportate al sito, i visitatori trascorrono più tempo sul sito.</p><p>Questo modello utilizza la dimensione [Visite a pagina singola](https://experienceleague.adobe.com/it/docs/analytics/components/dimensions/single-page-visits).</p> |
| **[!UICONTROL Entries & exits]** > [!UICONTROL **Pagine di uscita**] | Visualizza le pagine principali a cui le persone accedono immediatamente prima di lasciare il sito.<p>**Questo può aiutarti** a capire meglio quali pagine allontanano le persone dal sito. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare le pagine di uscita comuni per ottimizzare l’esperienza che le persone hanno del sito prima di lasciarlo, oppure includere contenuti o collegamenti per incoraggiarle a rimanere sullo stesso.</p><p>Questo modello utilizza la metrica Sessioni. Utilizza anche le visualizzazioni a barre e tabella a forma libera.</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **Panoramica delle prestazioni del sito**] > [!UICONTROL **Prestazioni del sito AEM**] | Visualizza i dati sulle prestazioni per il sito Adobe Experience Manager.  <p>**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare le impostazioni di Experience Manager.</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **Panoramica delle prestazioni dei moduli**] > [!UICONTROL **Prestazioni dei moduli AEM**] | Visualizza i dati sulle prestazioni per Adobe Experience Manager Forms.  <p>**Questo può aiutarti** a comprendere meglio la realizzazione del valore da Adobe Experience Manager.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare le impostazioni di Experience Manager.</p> |
| [!UICONTROL **Impatto ITP**] | Visualizza e analizza gli effetti della Prevenzione intelligente del tracciamento (ITP) sulla raccolta dei dati e sul reporting. <p>**Questo può aiutarti** a comprendere meglio la potenziale perdita di dati dovuta alle restrizioni sui cookie imposte dall’ITP.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio adattare la configurazione dell’analisi per ridurre al minimo l’impatto dell’ITP.</p> |

### Conversione {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="Visualizza il numero di visite associate a ciascuna categoria di prodotto sul sito. Questa funzione è utile per le implementazioni che utilizzano la variabile prodotti e desiderano visualizzare metriche sulla categoria di prodotto. La dimensione che popola questo modello può essere intenzionalmente vuota se non hai prodotti sul sito."
>abstract="**Questo può aiutarti** a capire meglio i prodotti più venduti o più visualizzati. &lt;/br/>**In base a quanto appreso, potresti** fare diverse cose, ad esempio misurare l’efficacia di una campagna di marketing per un determinato prodotto.<br/>Questo modello utilizza la dimensione Categoria e la metrica Visite. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Visualizza insight predefiniti per rivenditori sulle attività commerciali, per aiutare a migliorare le vendite. Questo è destinato agli utenti di Adobe Commerce, ma può essere utilizzato da qualsiasi rivenditore online."
>abstract="**Questo può aiutarti** a comprendere meglio come le tue attività commerciali contribuiscono ai numeri di vendita.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come regolare i budget per le attività che ottengono il maggior ROI."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Visualizza la conversione del prodotto in una visualizzazione funnel che mostra carrelli, pagamenti e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Visualizza quali sono i prodotti più performanti."
>abstract="**Questo può aiutarti** a comprendere meglio quali sono i prodotti di maggior successo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come aumentare i finanziamenti per i prodotti di successo e diminuirli per i prodotti di minore successo.<br/>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte carrello, Ordini, Ricavi e Unità. Utilizza anche la dimensione Prodotto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Visualizza il numero di volte in cui le persone hanno eseguito eventi chiave di pagamento, ad esempio l’aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e il pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio quali parti del funnel del processo di pagamento portano alla conversione e quali sono più soggette all’abbandono del carrello.<br/>**Sulla base di quanto appreso potresti** fare diverse cose, ad esempio ridurre l’attrito in determinati passaggi del processo di pagamento.<br/>Questo modello utilizza"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="Visualizza il numero di persone che hanno aggiunto un prodotto al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti aggiunti a un carrello.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio misurare l’efficacia delle pagine relative ai tuoi prodotti.<br/>Questo modello utilizza la metrica Carrelli."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno visualizzato il carrello."
>abstract="**Questo può aiutarti** a comprendere meglio l’esperienza di pagamento nel tentativo di ridurre le percentuali di abbandono del carrello o ad analizzare il tempo che intercorre tra le aggiunte al carrello e i pagamenti tra i diversi prodotti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come offrire promozioni per i prodotti che rimangono più a lungo nei carrelli e che sono a maggior rischio di abbandono.<br/>Questo modello utilizza la metrica Visualizzazioni carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l’interesse della clientela per un prodotto è abbastanza alto da spingerla ad aggiungerlo al carrello.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i consigli sui prodotti per tutta la clientela. Questo può essere fatto analizzando quali prodotti vengono aggiunti frequentemente agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già presenti nel carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello."
>abstract="**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui la clientela non è più interessata a un prodotto, oppure può aiutarti a capire dove potrebbero esserci problemi nel processo di pagamento.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio rimuovere eventuali barriere esistenti nel processo di pagamento, ad esempio un’esperienza utente complicata.<br/>Questo modello utilizza la metrica Rimozioni carrello."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Visualizza la conversione dell’acquisto in una visualizzazione funnel che mostra sessioni, carrelli e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido."

<!-- markdownlint-enable MD034 -->

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Funnel conversione del prodotto**] | Visualizza la conversione del prodotto in una visualizzazione funnel che mostra carrelli, pagamenti e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini.<p>**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido.</p> |
| **Prodotti** | Visualizza quali prodotti sono più determinanti per le metriche chiave, ad esempio i più venduti o i più visualizzati. <p>**Questo può aiutarti** a comprendere meglio quali sono i prodotti di maggior successo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come aumentare i finanziamenti per i prodotti di successo e diminuirli per i prodotti di minore successo.</p><p>Questo modello utilizza la metrica Ordini e la dimensione Prodotto. |
| **Prestazioni prodotto** | Visualizza quali sono i prodotti più performanti.<p>**Questo può aiutarti** a comprendere meglio quali sono i prodotti di maggior successo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come aumentare i finanziamenti per i prodotti di successo e diminuirli per i prodotti di minore successo.</p><p>Questo modello utilizza le metriche Visualizzazioni prodotto, Aggiunte al carrello, Ordini, Ricavi e Unità. Utilizza anche la dimensione Prodotto. |
| **Categorie** | Visualizza il numero di visite associate a ciascuna categoria di prodotto sul sito. Questa funzione è utile per le implementazioni che utilizzano la variabile prodotti e desiderano visualizzare metriche sulla categoria di prodotto. La dimensione che popola questo modello può essere intenzionalmente vuota se non hai prodotti sul sito.<p>**Questo ti aiuta** a comprendere meglio i prodotti più venduti o più visualizzati. </p><p>**In base a ciò che hai appreso, potresti** eseguire un numero qualsiasi di operazioni, ad esempio misurare l&#39;efficacia di una campagna di marketing per un determinato prodotto.</p><p>Questo modello utilizza la dimensione Categoria e la metrica Visite. |
| **Funnel di conversione carrello** | Visualizza il numero di volte in cui le persone hanno eseguito eventi chiave di pagamento, ad esempio l’aggiunta di articoli al carrello, la visualizzazione del carrello, la rimozione di articoli dal carrello e il pagamento. <p>**Questo può aiutarti** a comprendere meglio quali parti del funnel del processo di pagamento portano alla conversione e quali sono più soggette all’abbandono del carrello.</p><p>**Sulla base di quanto appreso potresti** fare diverse cose, ad esempio ridurre l’attrito in determinati passaggi del processo di pagamento.</p><p>Questo modello utilizza |
| **Carrelli** | Visualizza il numero di persone che hanno aggiunto un prodotto al carrello.<p>**Questo può aiutarti** a comprendere meglio il numero di persone che aggiungono un prodotto al carrello, rispetto al numero complessivo di prodotti aggiunti a un carrello.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio misurare l’efficacia delle pagine relative ai tuoi prodotti.</p><p>Questo modello utilizza la metrica Carrelli. |
| **Visualizzazioni carrello** | Visualizza il numero di volte in cui le persone hanno visualizzato il carrello. <p>**Questo può aiutarti** a comprendere meglio l’esperienza di pagamento nel tentativo di ridurre le percentuali di abbandono del carrello o ad analizzare il tempo che intercorre tra le aggiunte al carrello e i pagamenti tra i diversi prodotti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come offrire promozioni per i prodotti che rimangono più a lungo nei carrelli e che sono a maggior rischio di abbandono.</p><p>Questo modello utilizza la metrica Visualizzazioni carrello. |
| **Aggiunte carrello** | Visualizza il numero di volte in cui le persone hanno aggiunto qualcosa al carrello. <p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui l’interesse della clientela per un prodotto è abbastanza alto da spingerla ad aggiungerlo al carrello.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i consigli sui prodotti per tutta la clientela. Questo può essere fatto analizzando quali prodotti vengono aggiunti frequentemente agli stessi carrelli e suggerendo prodotti correlati in base agli articoli già presenti nel carrello. |
| **Rimozioni carrello** | Visualizza il numero di volte in cui le persone hanno rimosso qualcosa dal carrello.<p>**Questo può aiutarti** a comprendere meglio la parte del funnel di conversione in cui la clientela non è più interessata a un prodotto, oppure può aiutarti a capire dove potrebbero esserci problemi nel processo di pagamento.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio rimuovere eventuali barriere esistenti nel processo di pagamento, ad esempio un’esperienza utente complicata.</p><p>Questo modello utilizza la metrica Rimozioni carrello. |
| **Funnel conversione dell’acquisto** | Visualizza la conversione dell’acquisto in una visualizzazione funnel che mostra sessioni, carrelli e ordini. È inoltre possibile visualizzare le percentuali di conversione e le medie dei ricavi, delle unità e degli ordini.<p>**Questo può aiutarti** a comprendere meglio come le persone procedono e abbandonano durante il processo di conversione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il tuo sito web per facilitare un processo di pagamento più fluido.</p> |
| **Ricavi** | <!--duplicated in Most popular section-->Visualizza l’importo monetario dei prodotti acquistati in tutti gli ordini.<p>**Questo può aiutarti** a comprendere meglio quali elementi dimensionali hanno contribuito ai ricavi, combinando la metrica Ricavi con qualsiasi dimensione. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito ai ricavi. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le campagne che non soddisfano gli obiettivi di ricavo previsti.</p><p>Questo modello utilizza la metrica Entrate. |
| **Ordini** | <!--duplicated in Most popular section-->Visualizza il numero totale di eventi di acquisto effettuati sul sito. <p>**Questo può aiutarti** a capire meglio quali elementi dimensionali hanno contribuito a un ordine, combinando la metrica Ordini con qualsiasi dimensione. Ad esempio, puoi vedere le campagne principali (utilizzando la dimensione Codice di tracciamento) che hanno contribuito agli acquisti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le campagne che non soddisfano i target di acquisto previsti. </p><p>Questo modello utilizza la metrica Ordini. |
| [!UICONTROL **Unità**] | Visualizza il numero totale di unità acquistate in tutti gli ordini. I dati vengono visualizzati rispetto a un periodo di tempo e confrontati con periodi precedenti. <p>**Questo può aiutarti** a comprendere meglio come le vendite delle unità aumentano o diminuiscono nel tempo. Puoi applicare un segmento per scoprire quale clientela o quali aree geografiche acquistano il maggior numero di unità e quale sia la tendenza delle rispettive vendite nel tempo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare l’efficacia di una campagna di marketing avviata di recente confrontando le vendite di unità prima e dopo l’avvio della campagna. Oppure è possibile confrontare le vendite di unità durante le festività rispetto all’anno precedente.</p><p>Questo modello utilizza la dimensione [Day](/help/components/dimensions/day.md) e la metrica [Units](/help/components/metrics/units.md).</p> |
| [!UICONTROL **Magento: marketing e commerce**] | Visualizza insight predefiniti per rivenditori sulle attività commerciali, per aiutare a migliorare le vendite. Questo è destinato agli utenti di Adobe Commerce, ma può essere utilizzato da qualsiasi rivenditore online. <p>**Questo può aiutarti** a comprendere meglio come le tue attività commerciali contribuiscono ai numeri di vendita.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come regolare i budget per le attività che ottengono il maggior ROI.</p> |

### Pubblico {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--people"
>title="Visualizza il numero di persone che interagiscono con il tuo brand."
>abstract="**Questo può aiutarti** a comprendere meglio le tendenze di utilizzo sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come misurare l’efficacia delle recenti attività di marketing nel generare nuovi visitatori per il tuo sito."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--bots"
>title="Visualizza le visualizzazioni di pagina e le tendenze relative al traffico da bot sul sito."
>abstract="**Questo può aiutarti** a comprendere meglio la quantità di traffico da bot filtrato dai tuoi rapporti, in base alle regole bot che hai configurato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio continuare a monitorare l’attività dei bot per identificare nuovi pattern."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="Visualizza un confronto tra visitatori nuovi e visitatori ripetuti."
>abstract="**Questo può aiutarti** a comprendere meglio l’efficacia del tuo sito nel mantenere la fedeltà della clientela oppure la velocità con cui ne acquisisci di nuova.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio offrire ai nuovi visitatori degli incentivi per acquisti futuri, così da invogliarli a ritornare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--personid"
>title="Visualizza il comportamento di singoli utenti su vari canali."
>abstract="**Questo può aiutarti** a comprendere meglio il percorso cliente completo e le interazioni tra più punti di contatto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come personalizzare le attività di marketing per indirizzare meglio le preferenze degli utenti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Visualizza i fusi orari principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio in quali fusi orari vivono i tuoi visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare la manutenzione del sito in orari che interessino il minor numero di persone."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="Visualizza una panoramica della posizione del visitatore in una visualizzazione della mappa."
>abstract="**Questo può aiutarti** a comprendere meglio dove si trovano i visitatori che visitano il tuo sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le risorse di marketing nelle posizioni in cui visualizzi maggiore interesse e opportunità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Visualizza i domini principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio da quali organizzazioni provengono i tuoi visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio indirizzare i contenuti verso la clientela maggiore."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Visualizza i domini principali dei visitatori che accedono al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio da quali organizzazioni provengono i tuoi visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio indirizzare i contenuti verso la clientela maggiore."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Visualizza le dimensioni della larghezza dei browser principali che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni di larghezza dei browser più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.<br/>Questo modello utilizza la dimensione Browser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Visualizza le dimensioni dell’altezza dei browser principali che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni di altezza dei browser più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.<br/>Questo modello utilizza la dimensione Browser. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Visualizza il nome e la versione dei sistemi operativi che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio le versioni e i sistemi operativi più comuni utilizzati dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni tramite i principali sistemi operativi e relative versioni. In questo modo è possibile massimizzare le attività di controllo qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Visualizza il nome dei sistemi operativi utilizzati dalle persone per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio i sistemi operativi più comuni utilizzati dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con principali sistemi operativi. In questo modo è possibile massimizzare le attività di controllo qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore di telefonia mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore di telefonia mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Visualizza quante volte un visitatore ha visitato il sito."
>abstract="**Questo può aiutarti** a comprendere meglio quanto sono coinvolti i visitatori quando ritornano sul tuo sito. Questo viene applicato al ciclo di vita del visitatore, indipendentemente dall’intervallo di date del progetto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le attività di marketing per i visitatori frequenti.<br/>Questo modello utilizza la dimensione Numero di visite."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Visualizza il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti."
>abstract="**Questo può aiutarti** a comprendere meglio in che modo il tuo sito influisce sul comportamento d’acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrarti sui visitatori che tornano per fare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.<br/>Questo modello utilizza la dimensione Fedeltà della clientela."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Visualizza il numero di giorni che trascorrono tra la prima volta che un visitatore raggiunge il sito e il momento in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento della dimensione 1 giorno."
>abstract="**Questo può aiutarti** a capire meglio quanto tempo impiegano i visitatori per effettuare un acquisto.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare il tuo sito per incoraggiare un acquisto più veloce.<br/>Questo modello utilizza la dimensione Giorni prima del primo acquisto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Visualizza il tempo trascorso tra l’hit corrente del visitatore e il suo acquisto più recente in quel momento."
>abstract="**Questo può aiutarti** a comprendere meglio il comportamento del visitatore dopo che ha acquistato qualcosa sul tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare il tuo sito per incoraggiare gli acquisti successivi.<br/>Questo modello utilizza la dimensione Giorni dall’ultimo acquisto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Visualizza le dimensioni principali dello schermo dei dispositivi mobili che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare le attività di controllo qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Visualizza le dimensioni dell’altezza dello schermo dei dispositivi mobili principali che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le altezze dello schermo dei dispositivi mobili più comuni. In questo modo è possibile massimizzare le attività di controllo qualità."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Visualizzare le dimensioni della larghezza dello schermo dei dispositivi mobili principali che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le larghezze dello schermo dei dispositivi mobili più comuni. In questo modo è possibile massimizzare le attività di controllo qualità."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Visualizzare il Paese da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a capire meglio quali sono i Paesi più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Paesi, oppure assicurarti che l’esperienza sul tuo sito sia ottimale in Paesi con lingue principali diverse.<br/>Questo modello utilizza la dimensione Paesi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Visualizza lo stato (negli Stati Uniti) da cui provengono le persone che visitano il sito. È simile al modello Aree geografiche, ma è specifico per gli Stati Uniti."
>abstract="**Questo può aiutarti** a comprendere meglio quali sono gli Stati Uniti più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Stati.<br/>Questo modello utilizza la dimensione Stati Uniti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Visualizza l’area geografica da cui provengono le persone che visitano il sito. Un’area è un’area geografica più piccola di un Paese ma più grande di una città. In alcuni Paesi, un’area geografica è uno stato, una provincia o una prefettura. In altre aree, è un Paese costituente, un dipartimento o un’area metropolitana. "
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste aree geografiche, oppure assicurarti che l’esperienza del tuo sito sia ottimale nelle aree geografiche con lingue principali diverse. <br/>Questo modello utilizza le dimensioni ID(variables/geocountry) e Aree geografiche. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Visualizza la città da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori del tu sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. <br/>Questo modello utilizza la dimensione Città"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Visualizza le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui provengono le persone che visitano il sito."
>abstract="**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree geografiche di maggior successo. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto."
>abstract="**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.<br/>Questo modello utilizza la dimensione Lingua."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Visualizza informazioni relative alla tecnologia che utilizzano le persone per accedere al tuo sito, ad esempio sistemi operativi, browser e dispositivi."
>abstract="**Questo può aiutarti** a comprendere meglio quali tecnologie vengono utilizzate più di frequente per accedere al tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per le tecnologie in uso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Visualizza il nome e la versione dei principali browser che le persone utilizzano per accedere al tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando delle nuove versioni con i principali browser. In questo modo è possibile massimizzare le attività di controllo qualità.<br/>Questo modello utilizza la dimensione Browser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Visualizza i nomi delle organizzazioni che hanno realizzato i principali browser utilizzati dalle persone per accedere al tuo sito. Questo si differenzia dal modello Browser in quanto non elenca le diverse versioni dello stesso browser come elementi della dimensione separati."
>abstract="**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con l’utilizzo dei principali browser. In questo modo è possibile massimizzare le attività di controllo qualità. <br/>Questo modello utilizza la dimensione Tipo di browser. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="Visualizza il numero di eventi, sessioni e persone associati a ciascuna schermata nell’app mobile."
>abstract="**Questo può aiutarti** a comprendere meglio quali schermate del tuo sito sono più popolari.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare i contenuti delle schermate più popolari."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="Visualizza le azioni che le persone eseguono sull’app mobile."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone utilizzano la tua app e il valore che ne traggono.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come sviluppare funzioni che completino o perfezionino quelle più popolari."

<!-- markdownlint-enable MD034 -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Visualizza il numero di utenti, avvii e primi avvii sull’app, nonché la durata media di una sessione."
>abstract="**Questo può aiutarti** a comprendere meglio quanto viene utilizzata l’applicazione. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le prestazioni dell’app in modo che possa essere adattata alla quantità di utilizzo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Visualizza i pattern di utilizzo in primo piano per l’app mobile."
>abstract="**Questo può aiutarti** a comprendere meglio il modo in cui le persone utilizzano la tua app. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il modo in cui le persone passano da una schermata all’altra per identificare i flussi di lavoro più comuni."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Visualizza alcune delle metriche più comuni per le app mobili."
>abstract="**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare lo stato e le prestazioni complessive dell’app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Visualizza i dati sulle prestazioni per la messaggistica in-app e push dell’applicazione."
>abstract="**Questo può aiutarti** a comprendere meglio come le persone utilizzano le funzionalità di messaggistica in-app e l’efficacia delle notifiche push nell’indirizzare più traffico verso la tua app.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare l’esperienza di notifica push in-app."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Visualizza le prestazioni dell’app e i punti in cui gli utenti riscontrano problemi."
>abstract="**Questo può aiutarti** a comprendere meglio se chi utilizza la tua app riscontra rallentamenti o prestazioni ridotte. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come risolvere i problemi esistenti o migliorare le prestazioni dell’app prima che si verifichino."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Visualizza quali utenti sono i più fedeli all’app e cosa fanno all’interno dell’app."
>abstract="**Questo può aiutarti** a comprendere meglio come i tuoi utenti più fedeli utilizzano la tua applicazione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le attività di marketing per le funzioni utilizzate dagli utenti più fedeli."

<!-- markdownlint-enable MD034 -->

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Metrica persone**] | Visualizza il numero di persone che interagiscono con il tuo brand. <p>**Questo può aiutarti** a comprendere meglio le tendenze di utilizzo sul tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come misurare l’efficacia delle recenti attività di marketing nel generare nuovi visitatori per il tuo sito.</p> |
| **Profilo visitatore** > **Panoramica sulla posizione** | Visualizza una panoramica della posizione del visitatore in una visualizzazione della mappa.<p>**Questo può aiutarti** a capire meglio dove si trovano i visitatori che stanno visitando il tuo sito. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le risorse di marketing nelle posizioni in cui visualizzi maggiore interesse e opportunità.</p><!-- This template uses the --> |
| **Profilo visitatore** > **Segmentazione geografica** > **Paesi geografici** | Visualizzare il Paese da cui provengono le persone che visitano il sito.<p>**Questo può aiutarti** a capire meglio quali sono i Paesi più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Paesi, oppure assicurarti che l’esperienza sul tuo sito sia ottimale in Paesi con lingue principali diverse.</p><p>Questo modello utilizza la dimensione Paesi. </p> |
| **Profilo visitatore** > **Segmentazione geografica** > **Stati Geo US** | Visualizza lo stato (negli Stati Uniti) da cui provengono le persone che visitano il sito. È simile al modello Aree geografiche, ma è specifico per gli Stati Uniti.<p>**Questo può aiutarti** a comprendere meglio quali sono gli Stati Uniti più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in questi Stati.</p><p>Questo modello utilizza la dimensione Stati Uniti. </p> |
| **Profilo visitatore** > **Segmentazione geografica** > **Aree geografiche** | Visualizza l’area geografica da cui provengono le persone che visitano il sito. Un’area è un’area geografica più piccola di un Paese ma più grande di una città. In alcuni Paesi, un’area geografica è uno stato, una provincia o una prefettura. In altre aree, è un Paese costituente, un dipartimento o un’area metropolitana. <p>**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività relative al marketing in queste aree geografiche oppure assicurarti che l’esperienza del tuo sito sia ottimale nelle aree geografiche con lingue principali diverse. </p><p>Questo modello utilizza le dimensioni ID(variabili/paese geografico) e Aree geografiche. </p> |
| **Profilo visitatore** > **Segmentazione geografica** > **Città geografiche** | Visualizza la città da cui provengono le persone che visitano il sito. <p>**Questo può aiutarti** a comprendere meglio le città più popolari da cui provengono i visitatori del tu sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing in queste città. </p><p>Questo modello utilizza la dimensione Città. </p> |
| **Profilo visitatore** > **Segmentazione geografica** > **DMA Geo US** | Visualizza le aree di marketing designate (DMA) all’interno degli Stati Uniti da cui provengono le persone che visitano il sito.<p>**Questo può aiutarti** a comprendere meglio le aree geografiche più popolari da cui provengono i visitatori del tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio utilizzare i dati per concentrarti sulle attività di marketing nelle aree geografiche di maggior successo. </p><!-- This template uses the --> |
| **Profilo visitatore** > **Lingue** | Visualizza le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. <p>**Questo può aiutarti** a comprendere meglio le lingue preferite più frequentemente dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come concentrare le attività di localizzazione o di marketing per le lingue più popolari.</p><p>Questo modello utilizza la dimensione Lingua.</p> |
| **Profilo visitatore** > **Fusi orari** | Visualizza i fusi orari principali dei visitatori che accedono al tuo sito. <p>**Questo può aiutarti** a comprendere meglio in quali fusi orari vivono i tuoi visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare la manutenzione del sito in orari che interessino il minor numero di persone.</p> |
| **Profilo visitatore** > **Domini** | Visualizza i domini principali dei visitatori che accedono al tuo sito. <p>**Questo può aiutarti** a comprendere meglio da quali organizzazioni provengono i tuoi visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio indirizzare i contenuti verso la clientela maggiore.</p> |
| **Profilo visitatore** > **Domini di primo livello** | Visualizza i domini di primo livello dei visitatori che accedono al tuo sito. <p>**Questo può aiutarti** a comprendere meglio da quali organizzazioni provengono i tuoi visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio indirizzare i contenuti verso la clientela maggiore.</p> |
| **Profilo visitatore** > **Tecnologia** > **Panoramica tecnologia** | Visualizza informazioni relative alla tecnologia che le persone utilizzano per accedere al tuo sito, ad esempio sistemi operativi, browser e dispositivi. <p>**Questo può aiutarti** a comprendere meglio quali tecnologie vengono utilizzate più di frequente per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per le tecnologie in uso.</p> |
| **Profilo visitatore** > **Tecnologia** > **Browser** | Visualizza il nome e la versione dei principali browser che le persone utilizzano per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio i browser più comuni utilizzati dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando delle nuove versioni con i principali browser. In questo modo è possibile massimizzare le attività di controllo qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Tipi di browser** | Visualizza i nomi delle organizzazioni che hanno realizzato i principali browser utilizzati dalle persone per accedere al tuo sito. Questo si differenzia dal modello Browser in quanto non elenca le diverse versioni dello stesso browser come elementi della dimensione separati.<p>**Questo può aiutarti** a capire meglio i browser più comuni utilizzati dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando delle nuove versioni con i principali browser. In questo modo è possibile massimizzare le attività di controllo qualità. </p><p>Questo modello utilizza la dimensione Tipo di browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Larghezza browser** | Visualizza le dimensioni della larghezza dei browser principali che le persone utilizzano per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni di larghezza dei browser più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Altezza browser** | Visualizza le altezze principali del browser utilizzate dagli utenti per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni di altezza dei browser più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.</p><p>Questo modello utilizza la dimensione Browser. </p> |
| **Profilo visitatore** > **Tecnologia** > **Sistema operativo** | Visualizza il nome e la versione dei sistemi operativi che le persone utilizzano per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio le versioni e i sistemi operativi più comuni utilizzati dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni tramite i principali sistemi operativi e relative versioni. In questo modo è possibile massimizzare le attività di controllo qualità.</p> |
| **Profilo visitatore** > **Tecnologia** > **Tipi di sistemi operativi** | Visualizza il nome dei sistemi operativi utilizzati dalle persone per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio i sistemi operativi più comuni utilizzati dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con principali sistemi operativi. In questo modo è possibile massimizzare le attività di controllo qualità.</p> |
| **Profilo visitatore** > **Tecnologia** > [!UICONTROL **Operatore mobile**] | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Gestore di telefonia mobile.</p> |
| **Fidelizzazione visitatori** > **Frequenza di ritorno** | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Gestore di telefonia mobile.</p> |
| **Fidelizzazione visitatori** > **Visite di ritorno** | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Gestore di telefonia mobile.</p> |
| **Fidelizzazione visitatori** > **Numero visite** | Visualizza quante volte un visitatore ha visitato il sito.<p>**Questo può aiutarti** a comprendere meglio quanto sono coinvolti i visitatori quando ritornano sul tuo sito. Questo viene applicato al ciclo di vita del visitatore, indipendentemente dall’intervallo di date del progetto.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio regolare le attività di marketing per i visitatori frequenti.</p><p>Questo modello utilizza la dimensione Numero di visite.</p> |
| **Fidelizzazione visitatori** > **Ciclo di vendita** > **Fedeltà clienti** | Visualizza il numero di visitatori del sito che hanno effettuato 0 acquisti precedenti, 1 acquisto precedente, 2 acquisti precedenti o 3+ acquisti precedenti. <p>**Questo può aiutarti** a comprendere meglio in che modo il tuo sito influisce sul comportamento d’acquisto.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrarti sui visitatori che tornano per fare un acquisto, in modo da poter incoraggiare un comportamento simile per i nuovi visitatori.</p><p>Questo modello utilizza la dimensione Fedeltà del cliente.</p> |
| **Fidelizzazione visitatori** > **Ciclo di vendita** > **Giorni prima del primo acquisto** | Visualizza il numero di giorni che trascorrono tra la prima volta che un visitatore raggiunge il sito e il momento in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento dimensione &quot;1 giorno&quot;.<p>**Questo può aiutarti** a capire meglio quanto tempo impiegano i visitatori per effettuare un acquisto.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare il tuo sito per incoraggiare un acquisto più veloce.</p><p>Questo modello utilizza la dimensione Giorni prima del primo acquisto.</p> |
| **Fidelizzazione visitatori** > **Ciclo di vendita** > **Giorni dall&#39;ultimo acquisto** | Visualizza il tempo trascorso tra l’hit corrente del visitatore e il suo acquisto più recente in quel momento.<p>**Questo può aiutarti** a comprendere meglio il comportamento del visitatore dopo che ha acquistato qualcosa sul tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio aggiornare il tuo sito per incoraggiare gli acquisti successivi.</p><p>Questo modello utilizza la dimensione Giorni dall’ultimo acquisto.</p> |
| **Dispositivi mobili** > **Dispositivi** | Visualizza la marca e il modello dei dispositivi mobili utilizzati dalle persone per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali siano i dispositivi mobili più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.</p><p>Questo modello utilizza la dimensione Nome dispositivo mobile.</p> |
| **Mobile** > **Tipo di dispositivo** | Visualizza i tipi di dispositivi mobili utilizzati dalle persone per accedere al sito, ad esempio telefoni e tablet.<p>**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.</p><p>Questo modello utilizza la dimensione Tipo di dispositivo mobile.</p> |
| **Mobile** > **Produttore** | Visualizza i produttori dei dispositivi mobili utilizzati per accedere al sito, ad esempio Apple e Samsung.<p>**Questo può aiutarti** a comprendere meglio quali produttori sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle capacità dei diversi produttori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Produttore dispositivi mobili.</p> |
| **Mobile** > **Dimensioni schermo** | Visualizza le dimensioni principali dello schermo dei dispositivi mobili che le persone utilizzano per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le dimensioni più comuni dello schermo dei dispositivi mobili. In questo modo è possibile massimizzare le attività di controllo qualità.</p> |
| **Dispositivi mobili** > **Altezza schermo** | Visualizza le dimensioni dell’altezza dello schermo dei dispositivi mobili principali che le persone utilizzano per accedere al tuo sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le altezze dello schermo dei dispositivi mobili più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.</p> |
| **Dispositivi mobili** > **Larghezza schermo** | Visualizzare le dimensioni della larghezza dello schermo dei dispositivi mobili principali che le persone utilizzano per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio come il contenuto viene visualizzato dai visitatori.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la qualità del sito testando nuove versioni con le larghezze dello schermo dei dispositivi mobili più comuni. In questo modo è possibile massimizzare le attività di controllo qualità.</p> |
| **Mobile** > **Utilizzo app mobile** | Visualizza il numero di utenti, avvii e primi avvii sull’app, nonché la durata media di una sessione.<p>**Questo può aiutarti** a comprendere meglio quanto viene utilizzata l’app. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le prestazioni dell’app in modo che possa essere adattata alla quantità di utilizzo.</p><!-- This template uses the --> |
| **Dispositivi mobili** > **percorsi di app mobili** | Visualizza i pattern di utilizzo in primo piano per l’app mobile. <p>**Questo può aiutarti** a comprendere meglio il modo in cui le persone utilizzano la tua app. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare il modo in cui le persone passano da una schermata all’altra per i flussi di lavoro più comuni. </p><!-- This template uses the --> |
| **Dispositivi mobili** > **Metriche app dispositivi mobili** | Visualizza alcune delle metriche più comuni per le app mobili. <p>**Questo può aiutarti** a comprendere meglio le prestazioni di base della tua app mobile.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio valutare lo stato e le prestazioni complessive dell’app.</p><!-- This template uses the --> |
| **Mobile** > **Messaggistica app mobile** | Visualizza i dati sulle prestazioni per la messaggistica in-app e push dell’applicazione.<p>**Questo può aiutarti** a comprendere meglio come le persone utilizzano le funzionalità di messaggistica in-app e l’efficacia delle notifiche push nell’indirizzare più traffico verso la tua app.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare l’esperienza di notifica push in-app.</p><!-- This template uses the --> |
| **Mobile** > **Prestazioni app mobile** | Visualizza le prestazioni dell’app e i punti in cui gli utenti riscontrano problemi. <p>**Questo può aiutarti** a comprendere meglio se chi utilizza la tua app riscontra rallentamenti o prestazioni ridotte. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come risolvere dei problemi esistenti o migliorare le prestazioni dell’app prima che si verifichino dei problemi.</p><!-- This template uses the --> |
| **Mobile** > **Conservazione app mobile** | Visualizza quali utenti sono i più fedeli all’app e cosa fanno all’interno dell’app. <p>**Questo può aiutarti** a comprendere meglio come i tuoi utenti più fedeli utilizzano la tua applicazione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare le attività di marketing per le funzioni utilizzate dagli utenti più fedeli.</p><!-- This template uses the --> |
| **Bot** | Visualizza le visualizzazioni di pagina e le tendenze relative al traffico da bot sul sito. <p>**Questo può aiutarti** a comprendere meglio la quantità di traffico da bot filtrato dai tuoi rapporti, in base alle regole bot che hai configurato.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, ad esempio continuare a monitorare l&#39;attività dei bot per identificare nuovi pattern.</p><!-- This template uses the --> |

### Acquisizione {#web-acquisition}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Visualizza in che modo il sito web ottiene visitatori sui dispositivi mobili."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancato recapito. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visualizza tutti i dati di ricerca a pagamento di Google Ads e di Microsoft Advertising affiancati."
>abstract="**Questo può aiutarti** a comprendere meglio la quantità di traffico che arriva al tuo sito e se la clientela si sta convertendo.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio stimare in termini di costi l’efficacia di una campagna pubblicitaria."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Visualizza quale pagina dei risultati di ricerca su cui un visitatore ha fatto clic per arrivare sul sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento della dimensione per questa variabile è Pagina di ricerca 2."
>abstract="**Questo può aiutarti** a comprendere meglio il posizionamento delle pagine nei risultati di ricerca.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio migliorare la strategia SEO per garantire che i tuoi contenuti vengano visualizzati nella prima pagina dei risultati di ricerca."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="Quando viene utilizzata l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali dei tuoi canali di marketing sono i più efficaci.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio investire maggiormente su canali di marketing efficaci e disinvestire da quelli meno influenti.<br/>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Visualizza il primo canale di marketing a cui un visitatore corrisponde durante il relativo periodo di coinvolgimento (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere meglio quali canali di marketing favoriscono il traffico iniziale verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Canale di primo contatto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Visualizza i dettagli sul primo canale di marketing a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita)."
>abstract="**Questo può aiutarti** a comprendere meglio cosa ha contribuito all’hit corrispondente a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.<br/>Questo modello utilizza la dimensione Dettaglio canale di primo contatto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Visualizza il numero di click-through e di pagamenti per le campagne."
>abstract="**Questo può aiutarti** a comprendere meglio il modo in cui le campagne di marketing promuovono una conversione.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio individuare quali campagne di marketing generano il maggior ROI."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Visualizza i dettagli sulle prestazioni delle campagne di marketing."
>abstract="**Questo può aiutarti** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggiori ricavi. <br/>Questo modello utilizza le metriche Ricavi, Visualizzazioni prodotto, Aggiunte carrello, Ordini e Unità. Utilizza inoltre le dimensioni Codice di tracciamento e Dominio di riferimento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Visualizza come il tuo sito web ottiene visitatori."
>abstract="**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.<br/>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancato recapito. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito. <br/>Questo modello utilizza la dimensione Parola chiave di ricerca - A pagamento. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che favoriscono il traffico del sito.<br/>Questo modello utilizza la dimensione Parola chiave di ricerca - Naturale. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito. <br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.<br/>Questo modello utilizza la dimensione Motore di ricerca. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito. <br/>Questo modello utilizza la dimensione Motore di ricerca - A pagamento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento."
>abstract="**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.<br/>Questo modello utilizza la dimensione Motore di ricerca - Naturale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Visualizza i domini su cui le persone fanno clic per raggiungere il tuo sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali siti di terze parti favoriscono maggiore traffico verso il tuo sito. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sul sito esterno e un visitatore deve fare clic su di esso.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo maggiormente agli interessi dei visitatori provenienti dai principali domini di riferimento. <br/>Questo modello utilizza la dimensione Dominio di riferimento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Visualizza il primo dominio di riferimento su cui le persone hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intero ciclo di vita dell’ID visitatore."
>abstract="**Questo può aiutarti** a comprendere meglio quali siti di terze parti inizialmente favoriscono il traffico verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali domini di riferimento. <br/>Questo modello utilizza la dimensione Dominio di riferimento originale."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Visualizza su quali URL si trovano i visitatori quando fanno clic per raggiungere il sito. Affinché l’elemento della dimensione venga visualizzato, deve esistere un collegamento sull’URL esterno e un visitatore deve fare clic su di esso."
>abstract="**Questo può aiutarti** a comprendere meglio quali URL specifici favoriscono maggiore traffico verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti dai principali URL. <br/>Questo modello utilizza la dimensione Dominio di riferimento.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Visualizza i canali generici su cui i visitatori hanno fatto clic per arrivare al tuo sito. Adobe gestisce le regole per ciascun canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail."
>abstract="**Questo può aiutarti** a comprendere meglio quale tipo di referrer favorisce maggior traffico verso il tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come creare o adattare il contenuto per allinearlo meglio agli interessi dei visitatori provenienti da un determinato canale.<br/>Questo modello utilizza la dimensione Tipo referrer."

<!-- markdownlint-enable MD034 -->

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Rapporto panoramica canale**] | Quando viene utilizzata l’attribuzione personalizzata, questo modello mostra il modo in cui i visitatori arrivano sul tuo sito.<p>**Questo può aiutarti** a comprendere meglio quali dei tuoi canali di marketing sono i più efficaci.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio investire maggiormente su canali di marketing efficaci e disinvestire da quelli meno influenti.</p><p>Questo modello utilizza la dimensione ID(variables/marketingchannel) e la metrica Ricavi.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Canale primo contatto**] | Visualizza il primo canale di marketing a cui un visitatore corrisponde durante il relativo periodo di coinvolgimento (30 giorni per impostazione predefinita). <p>**Questo può aiutarti** a comprendere meglio quali canali di marketing favoriscono il traffico iniziale verso il tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di primo contatto.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Dettagli canale di primo contatto**] | Visualizza i dettagli sul primo canale di marketing a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere meglio cosa ha contribuito all’hit corrispondente a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Dettaglio canale di primo contatto.</p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Canale ultimo contatto**] | Visualizza il canale di marketing più recente a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere meglio quali canali di marketing favoriscono il traffico iniziale verso il tuo sito che si traduce in conversioni.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci.</p><p>Questo modello utilizza la dimensione Canale di ultimo contatto.  </p> |
| [!UICONTROL **Canali marketing**] > [!UICONTROL **Dettaglio canale ultimo contatto**] | Visualizza i dettagli sul canale di marketing più recente a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).<p>**Questo può aiutarti** a comprendere meglio cosa ha contribuito all’hit corrispondente a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing nelle aree più efficaci. </p><p>Questo modello utilizza la dimensione Dettaglio del canale di primo contatto. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Funnel di conversione campagna**] | Visualizza il numero di click-through e di pagamenti per le campagne. <p>**Questo può aiutarti** a comprendere meglio il modo in cui le campagne di marketing promuovono una conversione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio individuare quali campagne di marketing generano il maggior ROI.</p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Prestazioni campagna**] | Visualizza i dettagli sulle prestazioni delle campagne di marketing.<p>**Questo può aiutarti** a comprendere meglio i vari indicatori di successo associati alle campagne, come ricavi, visualizzazioni prodotti, ordini e così via.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggiori entrate. </p><p>Questo modello utilizza le metriche Entrate, Visualizzazioni prodotto, Aggiunte al carrello, Ordini e Unità. Utilizza inoltre le dimensioni Codice di tracciamento e Dominio di riferimento. </p> |
| [!UICONTROL **Campagne**] > [!UICONTROL **Codice di tracciamento**] | Visualizza i nomi dei codici di tracciamento sul tuo sito. Puoi inserire collegamenti con valori di parametri delle stringhe di query diversi in posizioni diverse su Internet.<p>**Questo ti aiuta** a capire meglio quali collegamenti sono stati più efficaci nel portare traffico sul tuo sito. L’aggiunta di stringhe di query del codice di tracciamento è comune nelle e-mail, negli annunci pubblicitari, nei post sui social media e in altre attività di marketing utilizzate dalla tua organizzazione.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sulle campagne che generano maggiori entrate.</p><p>Questo modello utilizza la dimensione Codice di tracciamento. </p> |
| **Acquisizione web** | Visualizza come il tuo sito web ottiene visitatori.<p>**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.</p><p>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancati recapiti. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer.  </p> |
| **Acquisizione mobile** | Visualizza in che modo il tuo sito ottiene visitatori su dispositivi mobili.<p>**Questo può aiutarti** a comprendere meglio i vari fattori che portano all’acquisizione, come le parole chiave di ricerca, il dominio di riferimento e così via.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività di marketing sui canali più efficaci.</p><p>Questo modello utilizza le metriche Percentuale di mancati recapiti e Mancati recapiti. Vengono inoltre utilizzate le dimensioni Motore di ricerca, Parola chiave di ricerca, Pagina di ingresso, Dominio di riferimento, Codice di tracciamento e Referrer.  </p> |
| **Advertising Analytics: ricerca a pagamento** | Visualizza tutti i dati di ricerca a pagamento di Google Ads e di Microsoft Advertising affiancati. <p>**Questo può aiutarti** a comprendere meglio la quantità di traffico che arriva al tuo sito e se la clientela si sta convertendo.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio stimare in termini di costi l’efficacia di una campagna pubblicitaria.</p> |
| **Parole chiave di ricerca: tutte** | Visualizza le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali. <p>**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito. </p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che determinano il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca. </p> |
| **Parole chiave di ricerca: a pagamento** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che determinano il traffico del sito. </p><p>Questo modello utilizza la dimensione Parola chiave di ricerca: a pagamento. </p> |
| **Parole chiave di ricerca: naturale** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio le parole chiave che le persone utilizzano nelle ricerche che generano traffico sul sito.</p><p>**In base a ciò che hai appreso, potresti** fare un certo numero di cose, come identificare e colmare i gap SEO tra le parole chiave utilizzate e quelle che determinano il traffico del sito.</p><p>Questo modello utilizza la dimensione Parola chiave di ricerca: naturale. </p> |
| **Motori di ricerca: tutti** | Visualizza i motori di ricerca utilizzati dai visitatori per raggiungere il sito, indipendentemente dal fatto che siano a pagamento o naturali. <p>**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito. </p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca. </p> |
| **Motori di ricerca: a pagamento** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il sito e che corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito. </p><p>Questo modello utilizza la dimensione Motore di ricerca: a pagamento. </p> |
| **Motori di ricerca: naturale** | Visualizza le parole chiave di ricerca che i visitatori utilizzano per raggiungere il tuo sito e che non corrispondono al rilevamento della ricerca a pagamento.<p>**Questo può aiutarti** a comprendere meglio i motori di ricerca che le persone utilizzano e che generano traffico sul sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio concentrare le attività SEO sui motori di ricerca che favoriscono maggiore traffico verso il tuo sito.</p><p>Questo modello utilizza la dimensione Motore di ricerca: naturale. </p> |
| **Classificazione di tutte le pagine di ricerca** | Visualizza quale pagina dei risultati di ricerca su cui un visitatore ha fatto clic per arrivare sul sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensionale per questa variabile è &quot;Pagina di ricerca 2&quot;.<p>**Questo può aiutarti** a comprendere meglio il posizionamento delle pagine nei risultati di ricerca.</p><p>**In base a ciò che hai appreso, potresti** fare qualsiasi cosa, ad esempio migliorare la tua strategia SEO per garantire che il contenuto venga visualizzato nella prima pagina dei risultati di ricerca. </p> |
| **Domini di riferimento** | Visualizza i domini su cui le persone fanno clic per raggiungere il tuo sito.<p>**Questo può aiutarti** a comprendere meglio quali siti di terze parti favoriscono maggiore traffico verso il tuo sito. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sul sito esterno e un visitatore deve fare clic su di esso.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo più strettamente agli interessi dei visitatori provenienti dai principali domini di riferimento. </p><p>Questo modello utilizza la dimensione Dominio di riferimento. </p> |
| **Domini di riferimento originali** | Visualizza il primo dominio di riferimento su cui le persone hanno fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intero ciclo di vita dell’ID visitatore.<p>**Questo può aiutarti** a comprendere meglio quali siti di terze parti inizialmente favoriscono il traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo più strettamente agli interessi dei visitatori provenienti dai principali domini di riferimento originali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento originale. </p> |
| **Riferimenti** | Visualizza su quali URL si trovano i visitatori quando fanno clic per raggiungere il sito. Affinché l’elemento della dimensione venga visualizzato, deve esistere un collegamento sull’URL esterno e un visitatore deve fare clic su di esso.  <p>**Questo può aiutarti** a comprendere meglio quali URL specifici favoriscono maggiore traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare qualsiasi cosa, come creare o regolare il contenuto per allinearlo più strettamente agli interessi dei visitatori provenienti dagli URL principali. </p><p>Questo modello utilizza la dimensione Dominio di riferimento. </p><p>Questo modello utilizza la dimensione Referrer. </p> |
| **Tipi di referrer** | Visualizza i canali generici su cui i visitatori hanno fatto clic per arrivare al tuo sito. Adobe gestisce le regole per ciascun canale. I canali possibili includono motori di ricerca, social network, altri siti web, disco rigido o e-mail.<p>**Questo può aiutarti** a comprendere meglio quale tipo di referrer favorisce maggior traffico verso il tuo sito.</p><p>**In base a ciò che apprendi, potresti** fare un certo numero di cose, come creare o regolare il contenuto per allinearlo più strettamente agli interessi dei visitatori provenienti da un determinato canale.</p><p>Questo modello utilizza la dimensione Tipo di referrer.</p> |

### Mobile {#mobile-not-ready-for-use}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Operatore di telefonia mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Visualizza la marca e il modello dei dispositivi mobili utilizzati dalle persone per accedere al sito."
>abstract="**Questo può aiutarti** a comprendere meglio quali siano i dispositivi mobili più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.<br/>Questo modello utilizza la dimensione Nome dispositivo mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Visualizza i tipi di dispositivi mobili utilizzati dalle persone per accedere al sito, ad esempio telefoni e tablet."
>abstract="**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.<br/>Questo modello utilizza la dimensione Tipo di dispositivo mobile."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Visualizza i produttori dei dispositivi mobili utilizzati per accedere al sito, ad esempio Apple e Samsung."
>abstract="**Questo può aiutarti** a comprendere meglio quali produttori sono più popolari nella tua base di utenti.<br/>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle capacità dei diversi produttori, in modo da garantire un’esperienza utente fluida.<br/>Questo modello utilizza la dimensione Produttore dispositivi mobili."

<!-- markdownlint-enable MD034 -->

 Sono disponibili i modelli seguenti:

| Nome modello | Perché utilizzare questo modello <!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Gestore di telefonia mobile**] | Visualizza la società di telecomunicazioni che fornisce la connettività di rete cellulare ai dispositivi mobili che le persone utilizzano per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali operatori di telefonia mobile sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle funzionalità di rete dei diversi operatori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Gestore di telefonia mobile.</p> |
| **Dispositivi** | Visualizza la marca e il modello dei dispositivi mobili utilizzati dalle persone per accedere al sito.<p>**Questo può aiutarti** a comprendere meglio quali siano i dispositivi mobili più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio ottimizzare il rendering del sito per i dispositivi mobili più comuni.</p><p>Questo modello utilizza la dimensione Nome dispositivo mobile.</p> |
| **Tipo di dispositivo** | Visualizza i tipi di dispositivi mobili utilizzati dalle persone per accedere al sito, ad esempio telefoni e tablet.<p>**Questo può aiutarti** a comprendere meglio i vari tipi di dispositivi mobili che vengono utilizzati per accedere al tuo sito.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, come ottimizzare il tuo sito per i tipi di dispositivi mobili più utilizzati.</p><p>Questo modello utilizza la dimensione Tipo di dispositivo mobile.</p> |
| **Produttore** | Visualizza i produttori dei dispositivi mobili utilizzati per accedere al sito, ad esempio Apple e Samsung.<p>**Questo può aiutarti** a comprendere meglio quali produttori sono più popolari nella tua base di utenti.</p><p>**Sulla base di quanto appreso, potresti** fare diverse cose, ad esempio personalizzare la consegna dei contenuti in base alle capacità dei diversi produttori, in modo da garantire un’esperienza utente fluida.</p><p>Questo modello utilizza la dimensione Produttore dispositivi mobili.</p> |


