---
description: Classifica l’attività di collegamento utilizzando le sovrapposizioni visive per monitorare il coinvolgimento del pubblico delle pagine web.
title: Panoramica di Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
TQID: https://experienceleague.adobe.com/1-o8wAr6cY8jSR2facQEvh--wvXByJf6R01r4RcVEhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 4%

---

# Panoramica di Activity Map

Adobe Analytics Activity Map è una funzione di Adobe Analytics che fornisce una rappresentazione visiva del coinvolgimento utenti su pagine web e app mobile. Consente agli esperti di marketing e agli analisti di monitorare e analizzare le interazioni degli utenti, ad esempio i clic e il comportamento di scorrimento. Activity Map genera mappe di calore e rapporti di sovrapposizione che mostrano gli elementi più popolari su una pagina web, per aiutarti a ottimizzare le tue esperienze digitali.

Activity Map as a concept è costituito da diversi componenti importanti:

* **Impostazione suite di rapporti**: per poter iniziare a utilizzare una suite di rapporti, è necessario che Activity Map sia abilitato. Consulta [Rapporti di Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) nelle impostazioni della suite di rapporti.
* **Implementazione**: la maggior parte dei rapporti di Activity Map è disponibile come standard. Tuttavia, alcuni siti web potrebbero richiedere un’implementazione aggiuntiva per ottenere il massimo dal tracciamento dei collegamenti. Sono disponibili le seguenti variabili di implementazione:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filtra i dati di clic in base al nome del collegamento.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filtra i dati di clic per nome di area.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): modificare l&#39;attributo che popola la dimensione Area geografica di Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): personalizzare la logica utilizzata da Activity Map per popolare la dimensione Collegamento Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): personalizzare la logica utilizzata da Activity Map per popolare la dimensione Area geografica di Activity Map.
* **Sovrapposizione**: estensione del browser che consente di visualizzare i dati dei clic sovrapposti sul sito Web. Per ulteriori informazioni, vedere [Interfaccia dell&#39;estensione Activity Map](overlay/overview.md). Questa funzione non è disponibile per le implementazioni Web SDK.
* **Dimensioni**: oltre all&#39;estensione di sovrapposizione, Activity Map fornisce diverse dimensioni che è possibile utilizzare in Analysis Workspace.
   * [Collegamento Activity Map](/help/components/dimensions/activity-map-link.md): nome del collegamento su cui è stato fatto clic.
   * [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md): il nome dell&#39;area su cui è stato fatto clic.
   * [Pagina Activity Map](/help/components/dimensions/activity-map-page.md): il nome della pagina al momento in cui è stato fatto clic sul collegamento.
   * [Collegamento Activity Map per area](/help/components/dimensions/activity-map-link-by-region.md): valore concatenato di Collegamento Activity Map e area geografica Activity Map.

## Caratteristiche e vantaggi

* **Visualizzazione del coinvolgimento degli utenti**: Activity Map offre una rappresentazione visiva dinamica del comportamento degli utenti, che consente di vedere esattamente dove gli utenti fanno clic. Questi dati visivi facilitano l’identificazione di pattern, tendenze e aree di interesse. Puoi quindi prendere decisioni informate sulla progettazione, il posizionamento dei contenuti e il flusso degli utenti.

* **Mappe di calore**: Activity Map genera mappe di calore che visualizzano le aree con il maggior numero di clic o di interazioni di una pagina Web. Le mappe di calore utilizzano la codifica a colori per rappresentare il livello di coinvolgimento, che consente di identificare i punti attivi e dare priorità all’attenzione per le aree ad alto impatto. Queste informazioni possono essere utili per ottimizzare pulsanti, collegamenti, moduli o qualsiasi altro elemento interattivo di call-to-action.

* **Rapporti di sovrapposizione**: i rapporti di sovrapposizione in Activity Map forniscono metriche di clic dettagliate per elementi specifici in una pagina Web. Comprendendo i tassi di click-through e i livelli di coinvolgimento dei singoli elementi, puoi perfezionare le strategie di progettazione e contenuto per migliorare le esperienze degli utenti. Questa funzione non è disponibile per le implementazioni Web SDK.

* **Analisi del segmento**: puoi analizzare il comportamento degli utenti in base a segmenti diversi, ad esempio origini di traffico, dati demografici o utenti tipo. Segmentando i dati, puoi scoprire informazioni preziose in gruppi di utenti specifici, consentendo esperienze personalizzate e strategie di marketing mirate.

## Applicazioni pratiche

* **Ottimizzazione del sito Web**: Activity Map consente di ottimizzare i siti Web identificando gli elementi con prestazioni insoddisfacenti, migliorando la navigazione e migliorando l&#39;esperienza utente complessiva. Analizzando le interazioni degli utenti, puoi prendere decisioni basate sui dati per semplificare i flussi di utenti, semplificare i moduli o regolare il posizionamento dei contenuti per il massimo impatto.

* **Ottimizzazione del tasso di conversione**: visualizzando il coinvolgimento degli utenti e analizzando i tassi di click-through, Activity Map svolge un ruolo cruciale nelle attività CRO. Puoi identificare gli ostacoli alla conversione e sperimentare diverse varianti di progettazione per ottimizzare i funnel di conversione, le pagine di destinazione e i processi di pagamento.

* **Test A/B**: Activity Map può essere combinato con test A/B per misurare l&#39;impatto delle modifiche alla progettazione o al contenuto. Confrontando le metriche di coinvolgimento tra versioni diverse di una pagina web, puoi determinare quali varianti portano a un coinvolgimento degli utenti, tassi di conversione o ricavi più elevati.

