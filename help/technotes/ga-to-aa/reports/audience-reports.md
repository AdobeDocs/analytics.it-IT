---
title: Report di audience in Adobe Analytics
description: Scopri come creare rapporti basati sul pubblico tramite Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Rapporti di audience

I rapporti sull'audience mostrano informazioni sui tipi di persone visitate sul sito.

Questa pagina presuppone che l'utente abbia una conoscenza di base sull'utilizzo di Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Utenti attivi

Gli utenti attivi mostrano il numero cumulativo di utenti al sito nei precedenti 1, 7, 14 o 28 giorni. Adobe non dispone del calcolo esatto utilizzato in Google Analytics, ma puoi utilizzare la metrica Visitatori univoci per visualizzare un conteggio ridotto degli utenti sul tuo sito in base all'intervallo date selezionato.

Per ottenere un grafico a linee di visitatori unici:

1. Fai clic sull'icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Linea nell'area di lavoro sopra la tabella a forma libera vuota.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled 'Drop a Metric here'.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) sopra l'intestazione della dimensione della data esistente.

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## Valore del ciclo di vita

Il valore del ciclo di vita è una funzione che richiede un'implementazione specializzata aggiuntiva su entrambe le piattaforme. Adobe consiglia di utilizzare un consulente di implementazione per ottenere questi dati.

## Analisi per coorte

Analisi coorte mostra la frequenza con cui gli utenti tornano al sito.

Per creare una tabella coorte:

1. Fai clic sull'icona Visualizzazione a sinistra, quindi trascina la visualizzazione Cohort Table (Tabella coorte) nell'area di lavoro.
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. Fai clic su Genera.

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## Tipi di pubblico

Il report Audience in Google Analytics richiede la configurazione del pubblico. Le audience richiedono inoltre la configurazione in Adobe tramite Adobe Audience Manager. Consulta la guida utente di Adobe Audience Manager per ulteriori informazioni.

## Esplora risorse

Il rapporto di Esplora risorse consente a un analista di visualizzare le singole visite attraverso identificatori anonimi. Adobe non applica la superficie agli identificatori di backend al di fuori dei feed di dati, che sono esportazioni di dati non disponibili a livello di hit.

* Se questi dati sono desiderati in Analysis Workspace, è possibile collaborare con un consulente di implementazione per passare il valore del cookie univoco anonimo in una evar. Questo funziona solo con implementazioni più piccole costituite da meno di 1 milioni di visitatori unici al mese.
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## Rapporti demografici e interessi

I dati demografici e degli interessi forniscono informazioni sull'età, il genere e gli interessi degli utenti del sito. Questi dati vengono raccolti da Google attraverso le loro capacità di tracciamento cross-site.

I dati demografici e degli interessi non vengono raccolti automaticamente da Adobe. Tuttavia, se la tua organizzazione ottiene questi dati, puoi utilizzare Attributi cliente, una funzione all'interno della piattaforma Adobe Experience Cloud. Consente il controllo completo dell'organizzazione dei dati per attributi e non è limitato esclusivamente a elementi demografici o interessi.

Consulta Aiuto attributi cliente per ulteriori informazioni.

## Geo - Lingua

Il rapporto sul geolocalizzazione mostra il traffico del sito in base all'impostazione della lingua nel browser del visitatore.

Per creare un rapporto sulla lingua:

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## Geo - Posizione

Il rapporto sulla geolocalizzazione fornisce una mappa mappa globale, scomposizione dei dati per paese.

Per creare un rapporto sulla geolocalizzazione:

1. Fai clic sull'icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa nell'area di lavoro sopra la tabella a forma libera vuota.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled 'Add Metric'.
3. Fai clic su Genera.

Se anche la tabella è desiderata, oltre alla mappa:

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## Comportamento - Nuovo rispetto alla restituzione

Il report nuovo e di ritorno fornisce una visualizzazione semplificata delle prime sessioni (nuove visite) e delle sessioni successive (visite di ritorno).

Per creare un nuovo rapporto sulle visite di restituzione:

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled 'Drop a Dimension here'. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. Questo aggiunge il segmento come dimensione al di sotto della prima visita, consentendo un confronto semplice.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Se anche un grafico a linee è desiderato:

1. Fai clic sull'icona visualizzazioni a sinistra, quindi trascina una visualizzazione Linea nell'area di lavoro sopra la tabella a forma libera.
2. Per evidenziarle, utilizzate Ctrl + clic (Windows) o Comando + clic (Mac) su ciascuna riga nella tabella a forma libera. Questo consente di visualizzare entrambe le tendenze nella visualizzazione della riga.
3. Fai clic sul piccolo punto colorato nell'angolo in alto a sinistra della visualizzazione della riga, quindi fai clic sulla casella Blocca selezione.

## Comportamento - Frequenza e recency

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## Comportamento - Coinvolgimento

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## Tecnologia - Browser e sistema operativo

Nel rapporto Browser e sistema operativo sono disponibili più dimensioni principali.

* The **Browser** primary dimension is also available in Analysis Workspace as a dimension.
* The **Operating System** primary dimension is also available in Analysis Workspace as a dimension.
* The **Screen Resolution** primary dimension is available in Analysis Workspace as the **Monitor Resolution** dimension.
* The **Screen Colors** primary dimension is available in Analysis Workspace as the **Color Depth** dimension.
* The **Flash Version** primary dimension is not available in Adobe Analytics, however this data can be collected by an eVar if wanted.

1. Nel menu dei componenti, individua la dimensione desiderata sopra e trascinala nella grande area della tabella a forma libera etichettata «Rilascia una dimensione qui».
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella Guida utente dei componenti:

* [Browser](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [Versione](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [Risoluzione monitor](../../../components/c-variables/dimensionslist/reports-technology.md)
* [Profondità colore](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## Tecnologia - Rete

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## Mobile - Panoramica

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. Il valore "Altro" è equivalente al traffico sul desktop.

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## Dispositivi mobili - Dispositivi

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## Personalizzato

I rapporti personalizzati sono definiti a livello di implementazione. Consultate l'amministratore di Analytics della vostra organizzazione e/o il consulente di implementazione per interpretare questi report. Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## Benchmarking

I report di benchmarking consentono di vedere come i facet dei dati confrontano con le medie del settore. Al momento, Adobe non condivide i dati di benchmarking tra i clienti.

## Flusso utenti

Il rapporto sul flusso è disponibile su entrambe le piattaforme. Per creare un rapporto sul flusso:

1. Fai clic sull'icona visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sull'area di lavoro sopra la tabella a forma libera.
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. I valori dimensione sono colorati.
3. Individuate il valore della pagina da iniziare e trascinatelo nello spazio «Dimensione o elemento» al centro
4. Questo rapporto di flusso è interattivo. Fare clic su uno qualsiasi dei valori per espandere i flussi nelle pagine successive o precedenti. Usate il menu di scelta rapida per espandere o comprimere le colonne. Dimensioni diverse possono essere utilizzate anche nello stesso rapporto sul flusso.
