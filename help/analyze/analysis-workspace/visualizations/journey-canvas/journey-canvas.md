---
description: Scopri come utilizzare l’area di lavoro del percorso in Analysis Workspace.
title: Panoramica dell’area di lavoro del percorso
feature: Visualizations
role: User, Admin
source-git-commit: de95ae1176aa15b4d932f7a9dff27f91aae4f1e7
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 88%

---

# Panoramica dell’area di lavoro del percorso {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_journeycanvas_button"
>title="Area di lavoro del percorso"
>abstract="Mostra il modo in cui le persone procedono attraverso o escono da una serie di punti di contatto. Da utilizzare per percorsi con più punti di ingresso e percorsi."

>[!CONTEXTUALHELP]
>id="aa_journeycanvas_panel"
>title="Area di lavoro del percorso"
>abstract="Analizza il modo in cui le persone procedono attraverso o escono da un percorso definito. Crea analisi dei percorsi degli utenti realizzando un grafico flessibile con nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e segmenti. Trascina i nodi nell’area di lavoro per riorganizzare gli eventi e le condizioni del percorso. Man mano che procedi, i dati vengono aggiornati di conseguenza."

>[!CONTEXTUALHELP]
>id="journeycanvas_button2"
>title="Area di lavoro del percorso"
>abstract="Mostra il modo in cui le persone procedono attraverso o escono da una serie di punti di contatto. Da utilizzare per percorsi con più punti di ingresso e percorsi."

>[!CONTEXTUALHELP]
>id="journeycanvas_panel2"
>title="Area di lavoro del percorso"
>abstract="Analizza il modo in cui le persone procedono attraverso o escono da un percorso definito. Crea analisi dei percorsi degli utenti realizzando un grafico flessibile con nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e segmenti. Trascina i nodi nell’area di lavoro per riorganizzare gli eventi e le condizioni del percorso. Man mano che procedi, i dati vengono aggiornati di conseguenza."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_In questo articolo viene documentata la visualizzazione dell&#39;area di lavoro del Percorso in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**&#x200B;_.<br/><br/>_Vedere [Panoramica dell&#39;area di lavoro del Percorso](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas) per la versione_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** di questo articolo._

>[!ENDSHADEBOX]

{{release-limited-testing}}

La visualizzazione dell’area di lavoro del percorso consente di analizzare e ottenere informazioni approfondite sui percorsi forniti agli utenti e alla clientela. Consente di definire un percorso, quindi di vedere come le persone hanno abbandonato (abbandonato) o continuato (proseguito) il percorso.

Puoi [creare analisi dei percorsi degli utenti](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) utilizzando qualsiasi combinazione di eventi, elementi dimensionali, segmenti e intervalli di date per creare i nodi del percorso. Connetti i nodi per creare il flusso del percorso e includi più percorsi e punti di decisione. Trascina i nodi nell’area di lavoro per riorganizzare gli eventi e le condizioni del percorso. I dati vengono aggiornati in tempo reale man mano che apporti le modifiche.

[I nodi sono connessi](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) come &quot;percorso finale&quot;, il che significa che i visitatori vengono conteggiati finché passano da un nodo all&#39;altro, indipendentemente dagli eventi che si verificano tra i due nodi. Il tempo assegnato agli utenti per spostarsi lungo il percorso è determinato dalle impostazioni del contenitore.

![Area di lavoro del percorso](assets/journey-canvas.png)

## Funzioni chiave

Le funzioni chiave della visualizzazione dell’area di lavoro del percorso includono:

* Analisi approfondita dell’abbandono e del fallthrough che consente di gestire i percorsi degli utenti più complessi.

* Area di lavoro per la mappatura e la visualizzazione dei vari punti di ingresso, nodi e percorsi di un percorso utente.

* Interazioni tramite trascinamento per l’aggiunta di componenti all’area di lavoro e il riposizionamento dei nodi esistenti.

## Insight potenziali

L’area di lavoro del percorso fornisce informazioni approfondite fruibili per i percorsi più complessi.

### Percorso con il tasso di conversione più alto {#conversion-rate-caption}

L’approfondimento più rilevante in Area di lavoro del percorso viene visualizzata come una didascalia nella parte superiore dell’area stessa.

Questa didascalia riepiloga quale di tutti i percorsi, nel percorso, ha avuto il più alto tasso di conversione.

Se il percorso contiene più nodi iniziali, la didascalia avrà l’aspetto seguente:

![Didascalia approfondimento in Area di lavoro del percorso](assets/journey-canvas-caption.png)

Quando il percorso contiene un singolo nodo iniziale, la didascalia si presenta così:

![Didascalia approfondimento in Area di lavoro del percorso con nodo iniziale singolo](assets/journey-canvas-caption-singlestart.png)

Nell’interpretare questa opzione, prendi in considerazione quanto segue:

* Un _percorso_ è definito come un nodo iniziale connesso tramite frecce a un nodo finale, con un numero qualsiasi di nodi connessi tra loro.

* Il calcolo del tasso di conversione dipende dal tipo di percorso (il numero di nodi iniziali e finali contenuti nel percorso e se i percorsi sono intersecati tra loro).

  La tabella seguente descrive come vengono calcolati i tassi di conversione in base al tipo di percorso:

  | Tipo di percorso | Calcolo del tasso di conversione | Esempio |
  |---------|----------|---------|
  | **Un singolo nodo iniziale e un singolo nodo finale** | Il tasso di conversione viene calcolato dividendo il numero del nodo finale per quello del nodo iniziale. | ![Percorso con più nodi iniziali che convergono in un nodo comune](assets/journey-canvas-single-path.png) |
  | **Un singolo nodo iniziale e più nodi finali** | Il tasso di conversione viene calcolato individuando il nodo finale con il numero più alto e dividendo tale numero per quello del nodo iniziale. | ![Percorso con più nodi iniziali che convergono in un nodo comune](assets/journey-canvas-singlestart-multiend.png) |
  | **Più percorsi autonomi, ognuno contenente un singolo nodo iniziale e un singolo nodo finale** | Il tasso di conversione viene calcolato dividendo il numero del nodo finale per quello del nodo iniziale. Il percorso con il tasso di conversione più alto è descritto nella didascalia. | ![Percorso con più nodi iniziali che convergono in un nodo comune](assets/journey-canvas-multi-start-separate.png) |
  | **Più nodi iniziali che in qualsiasi punto del percorso convergono in un nodo comune** | Il tasso di conversione viene calcolato individuando il nodo finale con il numero più alto e dividendo tale numero per quello del nodo iniziale con il numero più basso. | ![Percorso con più nodi iniziali che convergono in un nodo comune](assets/journey-canvas-multi-start-converge.png) |

### Fallthrough, abbandono e altro ancora

Di seguito sono riportati alcuni esempi di altri approfondimenti che l’area di lavoro del percorso può fornire. Puoi scegliere se queste informazioni si basano su tutte le persone nella suite di rapporti, su tutte le persone che hanno avviato il percorso o su tutte le persone del nodo precedente del percorso.

#### Fallthrough

* Numero e percentuale di persone che hanno completato il percorso (arrivate al nodo finale)

* Numero e percentuale di persone arrivate a un determinato nodo del percorso

* Passaggio più comune che segue o precede un dato nodo del percorso

#### Abbandono

* Nodi del percorso in cui le persone generalmente sono uscite dal percorso (non sono mai arrivate ai nodi immediatamente successivi)

#### Dati aggiuntivi per ogni nodo

* Aggiungi una dimensione di raggruppamento su qualsiasi nodo del percorso per visualizzare ulteriori dati per quel nodo specifico

## Scegli tra le visualizzazioni Area di lavoro del percorso, Abbandono o Flusso

La visualizzazione Area di lavoro del percorso presenta analogie con la [visualizzazione Abbandono](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) e la [visualizzazione Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), ma con differenze importanti.

### Comprendere le differenze

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando utilizzare l’Area di lavoro del percorso

L’Area di lavoro del percorso è essenziale per:

* Analisi dell’abbandono che coinvolge percorsi con più punti di ingresso e percorsi.

* Percorsi non lineari con più punti di ingresso e percorsi, con una sequenza di pagine predefinita.

* Analisi esplorativa ad hoc basata su un percorso predefinito.

* Analisi che richiede una metrica primaria diversa da Sessione, Persona o Occorrenze.

Utilizza [la tabella precedente](#understand-the-differences) per comprendere le differenze tra le visualizzazioni Area di lavoro del percorso, Abbandono e Flusso.

## Generare analisi nell’Area di lavoro del percorso

Puoi generare analisi nell’Area di lavoro del percorso basate su qualsiasi dimensione o metrica disponibile in Analysis Workspace. Per ulteriori informazioni, consulta [Configurare le visualizzazioni in un’Area di lavoro del percorso](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


>[!MORELIKETHIS]
>
> * [Guida alla visualizzazione delle aree di lavoro del percorso in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

