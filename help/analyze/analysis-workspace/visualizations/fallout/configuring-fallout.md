---
description: Scopri come configurare e specificare i punti di contatto per creare una sequenza di abbandono multidimensionale.
title: Configurare Una Visualizzazione Abbandono
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
source-git-commit: 121fac9958dc34be513a23d5c3ad76d5f0e6b665
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 14%

---

# Configurare una visualizzazione dell’abbandono

Puoi specificare **punti di contatto** per creare una sequenza di abbandono multidimensionale. In molti casi, un punto di contatto è una pagina del sito. Tuttavia, i punti di contatto non sono limitati alle pagine. Ad esempio, puoi aggiungere eventi, come unità di misura, persone univoche e visite di ritorno. Puoi anche aggiungere dimensioni, come una categoria, un tipo di browser o un termine di ricerca interno.

Puoi anche aggiungere segmenti all’interno di un punto di contatto. Ad esempio, potrebbe essere utile confrontare segmenti, come gli utenti di iOS e Android. Trascina i segmenti desiderati nella parte superiore dell’abbandono per aggiungere al rapporto le informazioni su di essi. Se desideri visualizzare solo tali segmenti, puoi rimuovere la linea di base Tutte le visite.

Le visualizzazioni di fallout non hanno limiti sul numero di punti di contatto che puoi aggiungere o sul numero di componenti che puoi utilizzare.

Puoi eseguire la tracciatura di percorsi per dimensioni, metriche e segmenti. Si supponga, ad esempio, che un utente stia guardando `shoes, shirt` in una pagina e che nella pagina successiva guardi `shirt, socks`. il prossimo rapporto di flusso dei prodotti da “scarpe” sarà “camicie” e “calze” e NON “camicie”.

## Utilizzo

1. Aggiungi una visualizzazione ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]**. Consulta [Aggiungere una visualizzazione a un pannello](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Trascinare un componente nel menu a discesa **[!UICONTROL Add touchpoint]**.

   >[!TIP]
   >
   >Puoi aggiungere una singola pagina al rapporto di abbandono, anziché l’intera dimensione. Fare clic sulla freccia destra ![ChevronRight](/help/assets/icons/ChevronRight.svg) nella dimensione pagina per scegliere una pagina specifica, ad esempio **[!UICONTROL home]**, da aggiungere al report Abbandono.


   ![La home page dalla dimensione Home page è stata trascinata nel campo Aggiungi punto di contatto.](assets/fallout-drag.png)

1. Continua ad aggiungere punti di contatto fino al completamento della sequenza.

   I numeri cerchiati nella porzione grigia della barra mostrano l’abbandono tra i punti di contatto (non l’abbandono complessivo per quel punto). I numeri cerchiati nella parte verde della barra mostrano il passaggio riuscito dal punto di contatto precedente al punto di contatto corrente.

   ![Visualizzazione Abbandono](assets/fallout-visualization.png)

   Quando aggiungi punti di contatto, puoi effettuare una delle seguenti operazioni:

   * Combina più componenti trascinando uno o più componenti aggiuntivi su un singolo punto di contatto.

     >[!NOTE]
     >
     >Per unire più segmenti si usa l’operatore AND; per unire più elementi, ad esempio elementi dimensione, si usa l’operatore OR.

   * Riordina i punti di contatto trascinandoli a un livello diverso all’interno della gerarchia di abbandono.

   * Combinare due punti di contatto trascinandone uno su un altro. Rilasciare il punto di contatto quando viene visualizzata la parola **[!UICONTROL Combine]**.

   * Vincola singoli punti di contatto all&#39;hit successivo (anziché *alla fine*) all&#39;interno del percorso. Sotto ogni punto di contatto è presente un selettore con le opzioni **[!UICONTROL Eventual path]** e **[!UICONTROL Next hit]**, come illustrato di seguito:

     | Opzione | Descrizione |
     |---|---|
     | **[!UICONTROL Eventual path]** (predefinito) | Sono conteggiati i visitatori che *alla fine* approderanno sulla pagina successiva del percorso, ma non necessariamente sulla visita successiva. |
     | **[!UICONTROL Next hit]** | Sono conteggiati i visitatori che accederanno alla pagina successiva del percorso dell’hit successivo. |

   * Passa il puntatore del mouse su un punto di contatto per visualizzare l’abbandono e altre informazioni su tale livello. Le informazioni includono il nome del punto di contatto, il conteggio delle persone e la percentuale di successo. Puoi anche confrontare il tasso di successo con altri punti di contatto.

## Impostazioni

Sono disponibili le seguenti impostazioni di visualizzazione:

| Contenitore Fallout | Descrizione |
|--- |--- |
| **[!UICONTROL Visits]** o **[!UICONTROL Visitors]** | Passa da [!UICONTROL visits] a [!UICONTROL Visitors] per analizzare il percorso della persona. Il valore predefinito è [!UICONTROL Visitors]. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello dei singoli visitatori (attraverso più visite) o di limitare l’analisi a una singola visita. |


## Menu di scelta rapida

Come parte della visualizzazione, sono disponibili opzioni di menu di scelta rapida specifiche.

### Accedere al menu di scelta rapida

È possibile accedere al menu di scelta rapida in uno dei modi seguenti:

* Passa il puntatore del mouse su un punto di contatto nella visualizzazione, quindi seleziona **[!UICONTROL Click to analyze]**.

  ![Accedi al menu di scelta rapida dal passaggio del mouse](assets/fallout-tooltip-analyze.png)

* Fai clic con il pulsante destro del mouse su un punto di contatto nella visualizzazione.

  ![Opzioni di abbandono](assets/fallout-options.png)

### Opzioni del menu di scelta rapida

Sono disponibili le seguenti opzioni del menu di scelta rapida:

| Opzione | Descrizione |
|--- |--- |
| **[!UICONTROL Trend touchpoint]** | Vedi i dati di tendenza per un punto di contatto in un grafico a linee, con alcuni dati predefiniti di rilevamento delle anomalie. |
| **[!UICONTROL Trend touchpoint (%)]** | Genera tendenze sulla percentuale di abbandono totale. |
| **[!UICONTROL Trend all touchpoints (%)]** | Genera tendenze su tutte le percentuali dei punti di contatto nell&#39;abbandono (tranne **[!UICONTROL All Visitors]**, se incluso) nello stesso grafico. |
| **[!UICONTROL Breakdown fallthrough at this touchpoint]** | Puoi vedere cosa hanno fatto i visitatori tra due punti di contatto (questo e il successivo) se hanno continuato fino al punto di contatto successivo. Questa opzione crea una tabella a forma libera che mostra le dimensioni. Potete sostituire le quote e altri elementi della tabella. Ad esempio, una tabella etichettata **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** e contenente **[!UICONTROL Page]** come dimensione e **[!UICONTROL Unique Visitors]** segmentata dal [segmento rapido solo progetto](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** come metrica. Ispeziona il segmento per capire come viene determinato il segmento di fallthrough. |
| **[!UICONTROL Breakdown fallout at this touchpoint]** | Visualizza cosa hanno fatto immediatamente dopo il passaggio selezionato i visitatori che non hanno effettuato il passaggio in funnel. Questa opzione crea una tabella a forma libera che mostra le dimensioni. Potete sostituire le quote e altri elementi della tabella. Ad esempio, una tabella etichettata **[!UICONTROL Fallout: All Visitors > Page equals any of home]** e contenente **[!UICONTROL Page]** come dimensione e **[!UICONTROL Unique Visitors]** segmentata dal segmento rapido [solo progetto](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** come metrica. Ispeziona il segmento per capire come viene determinato il segmento di abbandono. |
| **[!UICONTROL Create segment from touchpoint]** | Crea un nuovo segmento dal punto di contatto selezionato. |

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni di visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida della visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

