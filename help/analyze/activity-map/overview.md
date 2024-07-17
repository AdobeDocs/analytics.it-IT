---
description: Classifica l’attività di collegamento utilizzando le sovrapposizioni visive per monitorare il coinvolgimento del pubblico delle pagine web.
title: Panoramica di Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 4%

---

# Panoramica di Activity Map

Adobe Analytics Activity Map è una funzione di Adobe Analytics che fornisce una rappresentazione visiva del coinvolgimento utenti su pagine web e app mobile. Consente agli esperti di marketing e agli analisti di monitorare e analizzare le interazioni degli utenti, ad esempio i clic e il comportamento di scorrimento. Activity Map genera mappe di calore e rapporti di sovrapposizione che mostrano gli elementi più popolari su una pagina web, aiutandoti a ottimizzare le tue esperienze digitali.

Questa sezione della documentazione si concentra sulla sovrapposizione Activity Map. Tuttavia, l’utilizzo dell’Activity Map è soggetto ad altre parti importanti:

* **Impostazione suite di rapporti**: per una suite di rapporti deve essere abilitato l&#39;Activity Map. Consulta [Rapporti Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) nelle impostazioni della suite di rapporti.
* **Implementazione**: la maggior parte dei rapporti Activity Map è disponibile come standard. Tuttavia, alcuni siti web potrebbero richiedere un’implementazione aggiuntiva per ottenere il massimo dal tracciamento dei collegamenti. Sono disponibili le seguenti variabili di implementazione:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filtra i dati di clic in base al nome del collegamento.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filtra i dati di clic per nome di area.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): modificare l&#39;attributo che popola la dimensione Regione Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): personalizzare la logica utilizzata da Activity Map per popolare la dimensione Collegamento Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): personalizzare la logica utilizzata da Activity Map per popolare la dimensione Regione Activity Map.
* **Dimension**: oltre all&#39;estensione di sovrapposizione, Activity Map fornisce diverse dimensioni che è possibile utilizzare in Analysis Workspace.
   * [Collegamento Activity Map](/help/components/dimensions/activity-map-link.md): nome del collegamento su cui è stato fatto clic.
   * [Regione Activity Map](/help/components/dimensions/activity-map-region.md): il nome dell&#39;area su cui è stato fatto clic.
   * [Pagina Activity Map](/help/components/dimensions/activity-map-page.md): il nome della pagina al momento in cui è stato fatto clic sul collegamento.
   * [Collegamento Activity Map per area](/help/components/dimensions/activity-map-link-by-region.md): valore concatenato di Collegamento Activity Map e area Activity Map.

## Caratteristiche e vantaggi

* **Visualizzazione del coinvolgimento dell&#39;utente**: Activity Map offre una rappresentazione visiva dinamica del comportamento dell&#39;utente, che consente di vedere esattamente dove gli utenti fanno clic. Questi dati visivi facilitano l’identificazione di pattern, tendenze e aree di interesse. Puoi quindi prendere decisioni informate sulla progettazione, il posizionamento dei contenuti e il flusso degli utenti.

* **Mappe di calore**: Activity Map genera mappe di calore che visualizzano le aree con il maggior numero di clic o di interazioni di una pagina Web. Le mappe di calore utilizzano la codifica a colori per rappresentare il livello di coinvolgimento, che consente di identificare i punti attivi e dare priorità all’attenzione per le aree ad alto impatto. Queste informazioni possono essere utili per ottimizzare pulsanti di invito all’azione, collegamenti, moduli o qualsiasi altro elemento interattivo.

* **Rapporti di sovrapposizione**: i rapporti di sovrapposizione in Activity Map forniscono metriche di clic dettagliate per elementi specifici in una pagina Web. Comprendendo i tassi di click-through e i livelli di coinvolgimento dei singoli elementi, puoi perfezionare le strategie di progettazione e contenuto per migliorare le esperienze degli utenti.

* **Analisi del segmento**: puoi analizzare il comportamento degli utenti in base a segmenti diversi, ad esempio origini di traffico, dati demografici o utenti tipo. Segmentando i dati, puoi scoprire informazioni preziose in gruppi di utenti specifici, consentendo esperienze personalizzate e strategie di marketing mirate.

## Applicazioni pratiche

* **Ottimizzazione del sito Web**: Activity Map consente di ottimizzare i siti Web identificando gli elementi con prestazioni insoddisfacenti, migliorando la navigazione e migliorando l&#39;esperienza utente complessiva. Analizzando le interazioni degli utenti, puoi prendere decisioni basate sui dati per semplificare i flussi di utenti, semplificare i moduli o regolare il posizionamento dei contenuti per il massimo impatto.

* **Ottimizzazione del tasso di conversione**: visualizzando il coinvolgimento degli utenti e analizzando i tassi di click-through, l&#39;Activity Map svolge un ruolo cruciale nelle attività CRO. Puoi identificare gli ostacoli alla conversione e sperimentare diverse varianti di progettazione per ottimizzare i funnel di conversione, le pagine di destinazione e i processi di pagamento.

* **Test A/B**: l&#39;Activity Map può essere combinato con test A/B per misurare l&#39;impatto delle modifiche alla progettazione o al contenuto. Confrontando le metriche di coinvolgimento tra versioni diverse di una pagina web, puoi determinare quali varianti portano a un coinvolgimento degli utenti, tassi di conversione o ricavi più elevati.

* **Ottimizzazione delle app per dispositivi mobili**: Activity Map non è limitato ai siti Web, ma estende le sue funzionalità anche alle applicazioni per dispositivi mobili. Puoi ottenere informazioni approfondite sulle interazioni degli utenti all’interno delle app, consentendogli di migliorare l’usabilità, migliorare la navigazione e perfezionare le funzioni per un’esperienza mobile fluida.
