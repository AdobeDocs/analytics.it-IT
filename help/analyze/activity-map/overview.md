---
description: Classifica l’attività di collegamento utilizzando le sovrapposizioni visive per monitorare il coinvolgimento del pubblico delle pagine web.
title: Panoramica di Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# Panoramica di Activity Map

Adobe Analytics Activity Map è una funzione di Adobe Analytics che fornisce una rappresentazione visiva del coinvolgimento utenti su pagine web e app mobile. Consente agli esperti di marketing e agli analisti di monitorare e analizzare le interazioni degli utenti, ad esempio i clic e il comportamento di scorrimento. Activity Map genera mappe di calore e rapporti di sovrapposizione che mostrano gli elementi più popolari su una pagina web, per aiutarti a ottimizzare le tue esperienze digitali.

Questa sezione della documentazione si concentra sulla sovrapposizione di Activity Map. Tuttavia, l’utilizzo di Activity Map prevede anche altre parti importanti:

* **Impostazione suite di rapporti**: per una suite di rapporti deve essere abilitato Activity Map. Consulta [Rapporti di Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) nelle impostazioni della suite di rapporti.
* **Implementazione**: la maggior parte dei rapporti di Activity Map è disponibile come standard. Tuttavia, alcuni siti web potrebbero richiedere un’implementazione aggiuntiva per ottenere il massimo dal tracciamento dei collegamenti. Sono disponibili le seguenti variabili di implementazione:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filtra i dati di clic in base al nome del collegamento.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filtra i dati di clic per nome di area.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): modificare l&#39;attributo che popola la dimensione Area geografica di Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): personalizzare la logica utilizzata da Activity Map per popolare la dimensione Collegamento Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): personalizzare la logica utilizzata da Activity Map per popolare la dimensione Area geografica di Activity Map.
* **Dimensioni**: oltre all&#39;estensione di sovrapposizione, Activity Map fornisce diverse dimensioni che è possibile utilizzare in Analysis Workspace.
   * [Collegamento Activity Map](/help/components/dimensions/activity-map-link.md): nome del collegamento su cui è stato fatto clic.
   * [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md): il nome dell&#39;area su cui è stato fatto clic.
   * [Pagina Activity Map](/help/components/dimensions/activity-map-page.md): il nome della pagina al momento in cui è stato fatto clic sul collegamento.
   * [Collegamento Activity Map per area](/help/components/dimensions/activity-map-link-by-region.md): valore concatenato di Collegamento Activity Map e area geografica Activity Map.

## Caratteristiche e vantaggi

* **Visualizzazione del coinvolgimento degli utenti**: Activity Map offre una rappresentazione visiva dinamica del comportamento degli utenti, che consente di vedere esattamente dove gli utenti fanno clic. Questi dati visivi facilitano l’identificazione di pattern, tendenze e aree di interesse. Puoi quindi prendere decisioni informate sulla progettazione, il posizionamento dei contenuti e il flusso degli utenti.

* **Mappe di calore**: Activity Map genera mappe di calore che visualizzano le aree con il maggior numero di clic o di interazioni di una pagina Web. Le mappe di calore utilizzano la codifica a colori per rappresentare il livello di coinvolgimento, che consente di identificare i punti attivi e dare priorità all’attenzione per le aree ad alto impatto. Queste informazioni possono essere utili per ottimizzare pulsanti, collegamenti, moduli o qualsiasi altro elemento interattivo di call-to-action.

* **Rapporti di sovrapposizione**: i rapporti di sovrapposizione in Activity Map forniscono metriche di clic dettagliate per elementi specifici in una pagina Web. Comprendendo i tassi di click-through e i livelli di coinvolgimento dei singoli elementi, puoi perfezionare le strategie di progettazione e contenuto per migliorare le esperienze degli utenti.

* **Analisi del segmento**: puoi analizzare il comportamento degli utenti in base a segmenti diversi, ad esempio origini di traffico, dati demografici o utenti tipo. Segmentando i dati, puoi scoprire informazioni preziose in gruppi di utenti specifici, consentendo esperienze personalizzate e strategie di marketing mirate.

## Applicazioni pratiche

* **Ottimizzazione del sito Web**: Activity Map consente di ottimizzare i siti Web identificando gli elementi con prestazioni insoddisfacenti, migliorando la navigazione e migliorando l&#39;esperienza utente complessiva. Analizzando le interazioni degli utenti, puoi prendere decisioni basate sui dati per semplificare i flussi di utenti, semplificare i moduli o regolare il posizionamento dei contenuti per il massimo impatto.

* **Ottimizzazione del tasso di conversione**: visualizzando il coinvolgimento degli utenti e analizzando i tassi di click-through, Activity Map svolge un ruolo cruciale nelle attività CRO. Puoi identificare gli ostacoli alla conversione e sperimentare diverse varianti di progettazione per ottimizzare i funnel di conversione, le pagine di destinazione e i processi di pagamento.

* **Test A/B**: Activity Map può essere combinato con test A/B per misurare l&#39;impatto delle modifiche alla progettazione o al contenuto. Confrontando le metriche di coinvolgimento tra versioni diverse di una pagina web, puoi determinare quali varianti portano a un coinvolgimento degli utenti, tassi di conversione o ricavi più elevati.

