---
description: I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni sul sito Web. I segmenti sono progettati come approfondimenti per l'audience codificati che puoi generare per esigenze specifiche, quindi verifica, modifica e condividi con altri membri del team o usi in altri prodotti Adobe e funzionalità Analytics.
seo-description: I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni sul sito Web. I segmenti sono progettati come approfondimenti per l'audience codificati che puoi generare per esigenze specifiche, quindi verifica, modifica e condividi con altri membri del team o usi in altri prodotti Adobe e funzionalità Analytics.
seo-title: Informazioni su segmenti e contenitori
solution: Analytics
title: Informazioni su segmenti e contenitori
topic: Segmenti
uuid: e 8 b 1 edd 1-5 d 6 c -4213-994 b-fed 789 ad 30 a 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informazioni su segmenti e contenitori

I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni sul sito Web. I segmenti sono progettati come approfondimenti per l'audience codificati che puoi generare per esigenze specifiche, quindi verifica, modifica e condividi con altri membri del team o usi in altri prodotti Adobe e funzionalità Analytics.

## About segments and containers {#concept_82653C7E29FE49F5A4B5E5E93B0A6399}

I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni sul sito Web. I segmenti sono progettati come approfondimenti per l'audience codificati che puoi generare per esigenze specifiche, quindi verifica, modifica e condividi con altri membri del team o usi in altri prodotti Adobe e funzionalità Analytics.

<!-- 

seg_overview.xml

 -->

Segments are based on a [!UICONTROL Visitor], [!UICONTROL Visit] and [!UICONTROL Hit] level hierarchy using a nested container model. I contenitori nidificati consentono di definire attributi visitatore e azioni in base alle regole tra e all'interno dei contenitori. Analytics segments can be built, approved, shared, saved, and run across multiple products and capabilities in the [!DNL Adobe Experience Cloud]. I segmenti possono essere generati da un rapporto, integrato in un report dashboard o segnalibri per un accesso rapido.

You can build and save segments in the Segment Builder, or generate segments from a Fallout report (in [!DNL ad hoc analysis]). Puoi anche utilizzare ed estendere segmenti predefiniti basati su regole specifiche tra contenitori nidificati, per filtrare i risultati e applicare i rapporti. In addition, segments can be used together as [stacked segments](../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_40C299B60B354E10B344702EA3138B34).

I segmenti consentono di identificare i visitatori in base alle caratteristiche e alla sequenza di visualizzazioni di pagina.

## Segmenti {#section_CC4EBA2A6CCB4F8BBB8437052A880657}

I segmenti identificano chi sono i visitatori (paese, sesso, caffetteria), i dispositivi e i servizi utilizzati (browser, motore di ricerca, dispositivo mobile), da dove hanno navigato (motore di ricerca, pagina di uscita precedente, ricerca naturale) e molto altro ancora.

![](assets/seg.png)

I segmenti possono essere basati nei seguenti valori:

* Visitatori basati su attributi: tipo di browser, dispositivo, numero di visite, Paese, genere.
* Visitatori basati su interazioni: campagne, ricerca parola chiave, motore di ricerca.
* Visitatori in base a uscite e voci: visitatori di Facebook, una pagina di destinazione definita e un dominio di provenienza.
* Visitatori basati su variabili personalizzate: campo modulo, categorie definite, ID cliente.

When building audience segments in the Segment Builder, you define conditions using the [!UICONTROL AND] and [!UICONTROL OR]operators between containers.

![](assets/standard_segment_containers.png)

This type of segment filters data sets based on characteristics joined using the [!UICONTROL AND] and [!UICONTROL OR] operators.

## Sequential Segments {#section_EE5B14287FC44E0B96E77679A2438948}

I segmenti sequenziali consentono di identificare i visitatori in base alla navigazione e alla visualizzazione della pagina nel sito, fornendo un segmento di azioni e interazioni definite. I segmenti sequenziali consentono di identificare le caratteristiche di un visitatore e ciò che un visitatore evita. When building sequential segments, the [!UICONTROL THEN] operator is used to define and order visitor navigation.

![](assets/sequential_seg.png)

| Visita una | Visita due | Visita tre |
|---|---|---|
| Nella prima visita, il visitatore passava alla pagina di destinazione principale (A), escludeva la pagina della campagna (B) e quindi visualizzava la pagina Prodotto (C). | Nella seconda visita, il visitatore accedeva nuovamente alla pagina di destinazione principale (A), escludeva la pagina della campagna (B) e passava nuovamente alla pagina Product (C) e quindi a una nuova pagina (D). | Nella terza visita, il visitatore ha immesso e seguito lo stesso percorso della prima e della seconda visita, quindi la pagina F per passare direttamente a una pagina di prodotto di destinazione (G). |

I segmenti sequenziali possono essere basati sui seguenti valori hit:

* Visitatori basati su sequenze di hit di pagina: visualizzazioni di pagina in una singola visita, visualizzazioni di pagina in visite separate, visite che escludono le visualizzazioni di pagina.
* Visitatori basati sul tempo tra e dopo le visualizzazioni di pagina, dopo un limite di tempo, tra gli hit, dopo un evento.

![](assets/sequential_segmentation_containers_view.png)

A sequential segment filters data sets based on user actions using the [!UICONTROL THEN] operator.

## About Segment Containers {#concept_A38E7000056547399E346559D85E2551}

Un segmento imposta le condizioni per filtrare un visitatore in base ai suoi attributi o interazioni con il sito. Per impostare le condizioni in un segmento, impostate le regole per filtrare i visitatori in base alle caratteristiche dei visitatori e/o alle caratteristiche di navigazione. Per suddividere ulteriormente i dati dei visitatori, puoi filtrare in base a visite specifiche e/o a hit di pagina per ogni visitatore. Il Generatore di segmenti fornisce una semplice architettura per creare sottoinsiemi e applicare regole come nidificati, Visitor Visitor (Visitatore gerarchico) &gt; Visita &gt; Hit.

<!-- 

seg_container_overview.xml

 -->

## How-To Video {#section_89D6184890AF4086A8056BFBB0B68C29}

Questo video YouTube fornisce una breve panoramica sui contenitori dei segmenti e su come utilizzarli.

| Nome video | Collegamento video |
|---|---|
| Contenitori segmenti | [Segmentazione dei contenitori in Adobe Analytics](https://www.youtube.com/watch?v=A513j-ej0oc&index=2&list=PL2tCx83mn7GtHqZicFTa--aE6d02BvvTd) |

## About Containers {#section_AF2A28BE92474DB386AE85743C71B2D6}

The container architecture employed in the Segment Builder defines **[!UICONTROL Visitor]** as the outermost container, containing overarching data specific for the visitor across visits and page views. A nested **[!UICONTROL Visit]** container lets you set rules to break down the visitor's data based on visits, and a nested **[!UICONTROL Hit]** container lets you break down visitor information based on individual page views. Ogni contenitore consente di creare rapporti nella cronologia di un visitatore, interazioni suddivise per visita o suddividere hit singoli.

![](assets/sequential_segmentation_container_hierarchy.png)

**Contenitore visitatori**

Il contenitore Visitatore include ogni visita e visualizzazione pagina per i visitatori entro un intervallo di tempo specificato. Un segmento a livello di visitatore restituisce la pagina che soddisfa la condizione più tutte le altre pagine visualizzate dal visitatore (e vincolate solo da intervalli di date definiti). Come contenitore più definito, i report generati a livello del contenitore Visitatore restituiranno le visualizzazioni di pagina in tutte le visite e ti consentiranno di generare un'analisi multivisita. Di conseguenza, il contenitore Visitatore è il più suscettibile a modificare in base agli intervalli di date definiti.

I contenitori dei visitatori possono includere valori basati sulla cronologia globale di un visitatore:

* Giorni prima del primo acquisto
* Pagina di immissione originale
* Domini di riferimento originali

**Contenitore Visita**

Il contenitore Visita consente di identificare interazioni delle pagine, campagne o conversioni per una sessione Web specifica. Il contenitore Visita è il contenitore più comunemente utilizzato perché acquisisce i comportamenti per l'intera sessione di visita una volta che la regola è soddisfatta e ti consente di definire quali visite includere o escludere nella creazione e applicazione di un segmento. Può aiutarti a rispondere alla domanda di quanti visitatori hanno visualizzato la sezione News e Sport nella stessa visita? Or pages that attributed to a successful conversion to a sales?

I contenitori per visite includono valori basati su occorrenza per visita:

* Numero visita
* Pagina di immissione
* Restituisci frequenza
* Metriche di partecipazione
* Metriche allocate linearmente

**Contenitore hit**

Il contenitore Hit definisce quali hit di pagina includere o escludi da un segmento. È il più stretto dei contenitori disponibili per consentire di identificare specifici clic e visualizzazioni di pagina in cui una condizione è true, consentendoti di visualizzare un singolo codice di tracciamento o di isolare il comportamento all'interno di una particolare sezione del sito. Potresti anche voler individuare un valore specifico quando si verifica un'azione, ad esempio il canale di marketing quando un ordine è stato posizionato.

I contenitori Hit includono valori basati su singole pagine:

* Variabile  
* Proprietà elenco
* Evar elenco
* Evar per merchandising (nel contesto degli eventi)

   >[!NOTE]
   >
   >Se utilizzate questo contenitore su un valore che persiste, ad esempio un evar, viene eseguito ogni hit in cui tale valore è persistente. Nel caso di un codice di tracciamento scaduto dopo una settimana, tale valore potrebbe rimanere persistente in più visite.

**Contenitore gruppo logica**

Il contenitore Gruppo logica consente di fornire un contenitore separato all'interno delle regole del segmento per filtrare entità non basate sulla gerarchia. Ad esempio, potrebbe essere necessario fornire un contenitore nidificato all'interno del segmento in base al visitatore. Questo tipo di logica richiede l'interruzione della gerarchia (poiché hai già un contenitore Visitatore di livello principale) per filtrare solo i visitatori selezionati. Questo può essere ottenuto utilizzando il contenitore Gruppo logica. See [Logic Group examples](../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_83AEC78CD25F442EBEE364856A889560) for additional information.

## Nesting Containers {#section_7FDF47B3C6A94C38AE40D3559AFFAF70}

Durante la creazione di contenitori di segmenti all'interno di altri contenitori, si crea in pratica un segmento all'interno di un segmento. La logica seguente viene utilizzata con i contenitori nidificati:

1. Determinare quali dati includere utilizzando il contenitore più esterno. Tutti i dati che non corrispondono a questa regola esterna vengono eliminati nel rapporto segmentato.
1. Applica la regola nidificata ai dati rimanenti. La regola nidificata NON si applica agli hit che la prima regola genera.
1. Ripetete fino a quando tutte le regole contenitore nidificate non sono state calcolate. I restanti dati vengono quindi inclusi nel report risultante.

È possibile utilizzare la nidificazione sia tra contenitori che tra regole all'interno di un contenitore. Puoi nidificare in ogni contenitore:

| Nome contenitore | Elementi nidificabili |
|---|---|
| Hit | Solo eventi |
| Visita | Contenitore Hit, Eventi |
| Visitatore | Contenitore visita, Contenitore Hit, Eventi |
| Gruppo logica | Contenitore visitatore, Contenitore visita, Contenitore Hit |

**Includere più contenitori all'interno di una singola definizione**

L'inclusione di più segmenti in un nuovo segmento vi consente di perfezionare ulteriormente i dati. Se si trascinano due segmenti esistenti, si agisce come istruzione "OR" per filtrare i visitatori. Tutti i contenitori nel quadro vengono analizzati rispetto a tutti i dati e tutti i dati che corrispondono a uno qualsiasi dei contenitori sono inclusi nei rapporti.

Ad esempio, trascinando un contenitore Visita dove Paese = Stati Uniti con un contenitore Visita dove Ordine = True

```
Country = United States + Order = True
```

crea un segmento che si comporta in questo ordine:

1. Questo segmento controlla prima tutti i dati e identifica tutti i visitatori negli Stati Uniti.
1. Il segmento, quindi, visualizzerà di nuovo tutti i tuoi dati, cercando se alcuni visitatori hanno effettuato un ordine.
1. Entrambi i tipi di dati verranno quindi applicati al report.

## Containers for Sequential Segments {#section_324AF503F51A4A62806151FE440F3B2E}

Sequential segmentation employs the same basic containers, including [!UICONTROL Visitors], [!UICONTROL Visits], and [!UICONTROL Hits] (including page views or other dimensions) nested hierarchically.

![](assets/nesting_container.png)

[!UICONTROL Visitors] costituiscono il contenitore di ordine più alto nella segmentazione sequenziale, contenuto [!UICONTROL Visits] all'interno [!UICONTROL Visitors] del contenitore e [!UICONTROL Hits] contenuto all'interno dei contenitori [!UICONTROL Visitors] o [!UICONTROL Visits] contenitori. This [container hierarchy](../../components/c-segmentation/seg-overview.md#section_7FDF47B3C6A94C38AE40D3559AFFAF70) must be maintained to build well-ordered sequential segments.

**Per creare segmenti sequenziali**, i contenitori sono nidificati e logica sequenziale uniti utilizzando l' [!UICONTROL THEN] operatore che richiede che ogni contenitore sia true in base alla sequenza del visitatore.

![](assets/sequential_segmentation_nesting_3.png)

The only exception to this hierarchy of containers is when using the [Logic Group container](../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_83AEC78CD25F442EBEE364856A889560). [!UICONTROL Logic Group] Il contenitore consente di nidificare un hit all'interno di un contenitore senza l'ordine di acquisire eventi e dimensioni, al di fuori di un ordine sequenziale.

![](assets/logic_group_hierarchy.png)

## Reports based on Container Data {#concept_BE822C12F87C4F07B7147D80BEFBAB87}

I contenitori consentono di filtrare diversi dati in modo diverso in base ai valori di reporting durante la suddivisione dei segmenti e l'applicazione ai rapporti.

<!-- 

seg_container_reports.xml

 -->

I dati acquisiti a ogni livello della gerarchia Visitatore &gt; Visita &gt; Contenitori Hit influiscono sulla modalità di creazione dei segmenti. Se si applica lo stesso segmento allo stesso rapporto utilizzando lo stesso set di dati, si ottengono valori diversi in base al contenitore da cui si genera il report. Fattori quali il livello di rapporto sul contenitore e la persistenza dei valori tra gli hit possono comportare cambiamenti notevoli nella precisione dei report.

## Basics of Container Data {#section_9576D970F912450191AFB5B83F7F1656}

Ad esempio, il visitatore illustrato di seguito ha visitato un sito alla prima visita, è entrato nella pagina iniziale, quindi ha visitato tre pagine aggiuntive e ha convertito la visita a una vendita. In una visita separata, il visitatore è entrato in questa fase tramite la pagina Prodotto, quindi alla pagina Home, tornando alla pagina Prodotto e quindi chiuso la sessione dopo aver visualizzato l'inverno Hats. In base ai dati acquisiti per ciascun contenitore del segmento, nel rapporto saranno visualizzati valori diversi.

*Le pagine equivalgono a quello dell'inverno* di seguito, che viene applicato al report **Pagine**.

![](assets/page_winter_coat.png)

In base al contenitore selezionato, il rapporto visualizza risultati diversi.

![](assets/container_overview.png)

**Generazione di rapporti dal contenitore Hit**

When this condition is within a Hit container, then the report lists only pages where *Page = Winter Coats* is true. Poiché una sola pagina corrisponde a questa condizione in un contenitore di una sola pagina, viene visualizzata solo la pagina Inverno Coats.

![](assets/container_overview_PV.png)

La generazione di rapporti dal contenitore Hit consente di vedere come i rapporti provenienti da contenitori diversi influiscono sui valori complessivi di reporting. Visualizzare il rapporto sul segmento, notare che le visualizzazioni di pagina sono approssimativamente uguali alle visite (circa 2,000 visitatori hanno visto pagine duplicate all'interno di una visita che aggiungono al numero totale di visualizzazioni di pagina) e visitatori univoci sono circa uguali al numero di visite (circa 2,000 visitatori unici visitati più di una volta.)

![](assets/container_report_PV.png)

>[!IMPORTANT]
>
>A prescindere da come vengono visualizzati i dati, dai contenitori Hit, Visita o Visitatore, tutti hanno lo stesso numero di visitatori, 63, 541, in questo esempio. A prescindere dalla modalità di generazione del rapporto, la condizione iniziale del visitatore (Visitatori che hanno visualizzato la pagina Inverno Coats) rimane intatta. Si tratta del sottoinsieme di dati di cui esegui il reporting a diversi livelli.

**Generazione di rapporti dal contenitore visita**

If this same condition is within a Visit container, then the report lists all pages in the visit where *Page equals Winter Coats* is true. Filtra la pagina Inverno Coats, ma acquisisce anche tutte le altre pagine della visita in cui la condizione è true. Poiché il visitatore ha visitato anche le pagine Home, Prodotto e Acquisto all'interno della visita in cui è soddisfatta la condizione, queste pagine aggiuntive vengono elencate nel rapporto quando vengono riportate utilizzando i dati del contenitore Visitatori.

![](assets/container_overview_visit.png)

Se si mostrano i valori dei segmenti dal contenitore Visita, è possibile notare che il numero di visualizzazioni di pagina è aumentato in modo significativo. poiché il reporting dal Contenitore Visita identifica tutte le pagine che soddisfano le condizioni, più tutte le altre pagine visualizzate nella visita (con tutte le visualizzazioni pagina acquisite in ciascun contenitore Visita).

![](assets/container_report_Visit.png)

**Generazione di rapporti dal contenitore Visitatore**

If this same condition is within a Visitor container, the report lists all pages viewed by any visitor where *Page equals Winter Coats* is true. Ciò significa che se un visitatore ha visualizzato la pagina Inverno coats, vengono elencate tutte le pagine del contenitore Visitatore, incluse le visualizzazioni di pagina in altre visite. Di conseguenza, le pagine che non corrispondono alla condizione saranno elencate nel rapporto, in quanto il visitatore le ha visualizzate in precedenza. Tutte le pagine del contenitore Visitatore saranno elencate nel rapporto, anche se si sono svolte in precedenza e non soddisfano espressamente le condizioni.

![](assets/container_overview_visitors.png)

Visualizzando segmenti dal contenitore Visitatore, puoi notare che le visualizzazioni Pagina e Visite sono aumentate. poiché a partire dal livello di visitatore, se il visitatore ha visitato la pagina Inverno coats una sola volta (imposta la condizione true), tutte le altre visualizzazioni pagina e tutte le altre visite vengono acquisite per quel visitatore.

![](assets/container_report_Visitor.png)

In sintesi, comprendere il funzionamento della segmentazione su varie suddivisioni dati è fondamentale per interpretare i dati restituiti.

## Reporting based on the Container {#section_D0604748F2794327B8C668617A31EC18}

Ogni interruzione di dati del segmento ha un ambito a cui viene applicata. La maggior parte delle suddivisioni dei rapporti si basano sulle visualizzazioni di pagina, tuttavia, molti segmenti di valore sono basati sul contenitore Visita e in minor misura sul contenitore Visitatore. È importante comprendere i rapporti in base all'ambito del contenitore.

Based on the *Page = Winter Coats* segment example used previously, the issues listed below define other aspects of your segment based on how the container data is applied and how the scope of the data should match the segment type.

** Contenitore segmento in base alla regola del segmento corrispondente**

L'applicazione del contenitore segmenti rispetto a un ambito naturale di dati introduce risultati previsti in cui gli elementi della linea corrispondono alla regola del segmento.

* **Contenitore hit dove la pagina è uguale a "Inverno"**: La visualizzazione di un report Pagina con questo segmento restituisce solo i valori che equivalgono a "Inverno inverno". Tutte le altre pagine sono escluse dai rapporti.
* **Visitate il contenitore in cui la pagina di immissione è «Apparel inverno»**: La visualizzazione di un report Pagina di partecipazione con questo segmento restituisce solo la seconda visita perché la pagina di immissione corrisponde alla regola del segmento.
* **Visita il contenitore dove il numero di visita è uguale a 1**: La visualizzazione di Visita tutte le visualizzazioni pagina dalla prima visita è inclusa nel rapporto perché corrisponde alla regola del segmento.

**Visualizzazioni pagina a livello di contenitore Visita**

Molte regole di segmento identificano le visualizzazioni di pagina per visita. In tal caso, viene applicato l'intero contenitore Visitatore, se un solo hit corrisponde alla regola. Questo rapporto sul segmento è particolarmente prezioso perché le visualizzazioni di pagina basate sulle visite forniscono approfondimenti basati sulle visualizzazioni di pagina per visita.

* **Visita il contenitore dove la pagina corrisponde alla pagina**"Inverno" In un rapporto Pagina a livello del visitatore vengono visualizzate tutte le visualizzazioni di pagina delle visite che includono una visualizzazione della pagina «Apparentesi inverno». Se una pagina corrisponde alla regola del segmento, tutte le visualizzazioni di pagina associate a tale visita sono incluse nel rapporto.
* **Campo visita in cui la pagina corrisponde alla pagina «Home»**: In un rapporto Pagina con questo segmento vengono visualizzati solo i dati della prima visita. poiché nella seconda visita il visitatore non ha visualizzato una pagina «Home».
* **Contenitore visitatore dove la pagina è «Apparel inverno»**: In un rapporto Pagina, questo segmento recupera tutti i dati da entrambe le visite perché in entrambe le visite il visitatore ha visualizzato la pagina «Apparel inverno».

**Contenitore segmento che identifica hit più piccoli delle visualizzazioni pagina**

L'utilizzo di segmenti con un contenitore più piccolo rispetto all'ambito di suddivisione restituisce dati imprevisti. L'utilizzo di una suddivisione più piccola continua a riversarlo in tutti gli hit da quell'ambito di dati.

* **Contenitore Hit dove la pagina di immissione corrisponde alla pagina Prodotto**: Ogni pagina viene associata alla pagina di entrata della visita, facendola diventare una suddivisione basata su visite. L'utilizzo di questo segmento non riguarda solo la pagina Prodotto della pagina di immissione, ma anche tutti gli hit nella visita.
* **Contenitore Hit dove l'elenco Var 1 contiene valuea**: Se più valori erano definiti sullo stesso hit dell'elenco var, tutti i valori delle variabili vengono inclusi nel segmento. Non c'è modo di separare i valori che si verificano nella stessa visualizzazione di pagina, perché il contenitore Hit è il contenitore di segmenti più piccolo per suddividere gli hit.
* **Contenitore Hit dove Pagina è uguale a "Acquisto"**: Se utilizzate le visualizzazioni di pagina come metrica, viene visualizzata solo la pagina Acquisto (come previsto). Se utilizzate un rapporto Partecipazione alle entrate, tutte le pagine della prima visita ricevono $ 100, poiché le metriche di partecipazione sono basate su visite.
* **Contenitore Hit dove Page è uguale a "Inverno"**: Se utilizzate le visualizzazioni di pagina come metrica, viene visualizzata solo la pagina Inverno inverno (come previsto). Se utilizzate un rapporto sulle entrate, nessuna pagina riceve credito perché questa dimensione richiede una dimensione persistente. La visualizzazione della pagina che ha eseguito l'acquisto (la pagina Acquisto) non è inclusa nel contenitore Hit, pertanto non viene assegnata alcuna partecipazione alle entrate a qualsiasi elemento. Tuttavia, l'esecuzione di un report dal contenitore Visita includerà tutte le visualizzazioni di pagina in quella visita e distribuirebbe la partecipazione delle entrate ($ 100) in tutte le pagine visualizzate nella sessione.

## Persistence across Containers {#concept_E579D72B1C644AE9A4C4EAF6B47A4DCB}

Il filtraggio per dimensioni che si trovano su un intervallo di pagine, come una evar campagna o una Dimensione di provenienza, influisce sui dati raccolti a livello di contenitore e da comprendere per il reporting preciso.

<!-- 

seg_container_persistence.xml

 -->

I dati dei segmenti possono variare in base alla persistenza di una dimensione o a una variabile applicata tra le pagine selezionate. Alcune dimensioni, come la dimensione Pagina, forniscono valori univoci a livello di pagina e vengono filtrate in base ai dati del contenitore Hit. (See the [Reports based on Container Data](../../components/c-segmentation/seg-overview.md#concept_BE822C12F87C4F07B7147D80BEFBAB87) example). Altre dimensioni, come la dimensione Dominio di riferimento, rimangono in più pagine per una visita. Alcune dimensioni o variabili applicate, come Durata visita, si estendono nell'intera cronologia di un visitatore.

![](assets/RefDomain_aol.png)

Contrariamente alla dimensione Pagina, il valore di Dominio riferimento viene allegato a ogni pagina della visita. Ad esempio, il visitatore seguente accede alla home page da un sito con riferimento. Di conseguenza, a tutte le pagine all'interno della visita viene assegnato lo stesso valore di dominio di provenienza.

The *Referring Domain equals aol.com* segment below is applied to the **Pages Report**.

![](assets/container_overview_persist.png)

In una nuova visita, il visitatore viene richiamato da un altro sito. Di conseguenza, a tutte le pagine della nuova visita viene assegnato il nuovo valore di dominio di riferimento per ogni visualizzazione di pagina.

**Generazione di rapporti dal contenitore Hit**

Because all page views within the same visit are assigned the same Referring Domain value, reporting at the Hit container level where *Referring Domain = "aol.com"* returns all pages listed in the table below.

![](assets/container_overview_persist_Visit.png)

Visualizzando dati dal contenitore Hit, oltre 92,000 visualizzazioni di pagina venivano visualizzate in più di 32,000 visite da oltre 33,000 visitatori. In media, in ogni visita erano presenti tre visualizzazioni di pagina, e quasi tutte le visite erano da parte di visitatori univoci.

![](assets/container_report_persist_PV.png)

**Generazione di rapporti dal contenitore visita**

If this same condition is filtered in the Visit container for a Pages report, then all pages in the visit where *Referring Domain = "aol.com"* is true. Poiché il valore del dominio di riferimento è impostato a livello di visita, i report ai livelli Visualizzazione pagina e Visita sono identici.

![](assets/container_overview_persist_Visit.png)

In questo esempio, poiché tutte le pagine hanno lo stesso valore di dominio di riferimento basato sulla visita, il report dal livello di contenitore Visita è (quasi) lo stesso al rapporto dal contenitore Visualizzazione pagina (con leggera offset: 98, da 234 a 98,248, a causa di anomalie di dati).

![](assets/container_report_persist_Visit.png)

**Generazione di rapporti dal contenitore Visitatore**

From the Visitor container, the Page report lists all pages viewed by any visitor where *Referring Domain equals "aol.com"* is true. Consequently, if a visitor had *"aol.com"* as a referring domain at anytime in the history (within the defined time period), then all of the pages in the Visitor container—including page views in other visits—will be listed. Le pagine pari che non corrispondono alla condizione principale saranno elencate nel rapporto, perché queste pagine sono incluse nel contenitore Visitatore. Tutte le pagine del contenitore Visitatore saranno elencate nel rapporto, anche se si sono svolte in precedenza e non soddisfano espressamente le condizioni.

In a Referring Domain report, *Referring Domain = "aol.com"* is true in four page views, but *Referring Domain = "weather.com"* is true in the other pages the visitor hit. Dal contenitore Visitor (Visitatore) viene visualizzato un elenco di visitatori dove «aol.com» è true, ma contiene anche pagine in cui il dominio di provenienza è «weather.com», non quello che corrisponde alla richiesta iniziale nel segmento.

![](assets/container_overview_persist_Visitor.png)

Quando visualizzate i dati dal contenitore Visitatore, notate che le visualizzazioni di pagina sono aumentate notevolmente (da 98,248 a 112, 925). poiché sono state elencate tutte le visualizzazioni di pagina apportate dal visitatore, compresi quelli con altri valori di dominio di provenienza salvati a livello del contenitore Visitatore, (nonché le visite aggiuntive da parte del visitatore, aumentando le visite da 33,203 a 43,448).

![](assets/container_report_persist_Visitor.png)

Riepilogo,

* Il contenitore Visita restituisce tutte le pagine visualizzate in una visita in cui almeno una pagina soddisfa i criteri. Pertanto, se una pagina viene visualizzata solo dopo il 1 del giorno 1, tutte le pagine visualizzate nell'intera visita sono incluse nei dati.
* Prestate attenzione quando la condizione su cui state segmentando si trova su un evar o su un altro tipo di variabile persistente. Ad esempio, è possibile utilizzare la condizione «in cui la campagna contiene e-mail» e scade dopo 7 giorni. Pertanto, se la campagna è impostata alla prima visita, rimarrà persistente per altri 7 giorni. Ogni visita sarà inclusa anche se la campagna è stata impostata solo alla prima visita. Anche le altre visite saranno incluse (purché siano nell'intervallo di date del rapporto). Se desiderate evitare l'inclusione di valori persistenti, utilizzate l'evento «instance of» o una variabile Prop equivalente, se disponibile.

