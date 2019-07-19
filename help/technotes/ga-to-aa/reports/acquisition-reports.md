---
title: Report di acquisizione in Adobe Analytics
description: Scopri come creare rapporti basati sull'acquisizione tramite Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Report di acquisizione

I rapporti di acquisizione mostrano come ottenere i visitatori sul sito.

In Adobe Analytics, these reports are known as **Marketing Channels**. Richiedono una configurazione iniziale di base, ma consentono una visualizzazione più personalizzata dei canali.

> [!IMPORTANT]
>
> Configurate le regole di elaborazione Canale marketing per utilizzare tali rapporti. See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

Questa pagina presuppone che l'utente abbia una conoscenza di base sull'utilizzo di Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Tutto il traffico - Canali

Mostra una visualizzazione aggregata di tutti i canali utilizzati dai visitatori per raggiungere il sito.

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Traffico completo - Ad albero

Mostra un'ampiezza del traffico dei canali. Questo rapporto è simile a Tutti i canali - Canali, ma viene visualizzato in modo diverso.

1. Fai clic sull'icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa ad albero nell'area di lavoro sopra la tabella a forma libera vuota.
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled 'Drop a dimension here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. Tieni presente che ulteriori metriche creano altre metriche. Se è desiderata una sola mappa:
   1. Fai clic sulla cella superiore della metrica desiderata per rappresentare il mappa verticale.
   2. Maiusc + clic sull'ultima cella della stessa colonna di metrica per evidenziare la colonna blu. Se eseguito correttamente, nella visualizzazione è presente un'mappa ad albero.
   3. Fai clic sul punto colorato nell'angolo superiore destro della visualizzazione treemap, quindi fai clic sulla casella Blocca selezione.

Le aperture possono essere applicate a qualsiasi dimensione, non solo ai canali di marketing.

## Tutto il traffico - Sorgente/Medio

I rapporti sorgente e medium mostrano i domini che hanno portato il traffico al tuo sito.

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Medium** primary dimension is available in Analysis Workspace as the  **Referrer Type** dimension.
* The **Keyword** primary dimension is available in Analysis Workspace as the **Search Keyword** dimension.

1. Nel menu dei componenti, individua la dimensione desiderata sopra e trascinala nella grande area della tabella a forma libera etichettata «Rilascia una dimensione qui».
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella Guida utente dei componenti:

* [Dominio di riferimento](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [Tipo referente](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [Ricerca parola chiave](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## Traffico - Referenti

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Landing Page** primary dimension is available in Analysis Workspace as the **Entry Page** dimension.

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Rapporti Google Ads e rapporti sulle console di ricerca

Adobe utilizza una funzionalità di Analysis Workspace denominata Analisi della pubblicità per importare dati pubblicitari e di ricerca da più piattaforme, incluso Google.

La funzione analisi della pubblicità richiede la configurazione per restituire i dati. See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Rapporti social

I rapporti Social forniscono informazioni simili come il rispettivo rapporto Comportamento, tranne nel contesto delle reti social. Questi dati sono disponibili in Analysis Workspace combinando una dimensione con un segmento.

A volte i visitatori raggiungono il sito tramite più canali nella stessa sessione. Ad esempio, un visitatore fa clic su una pagina social media, quindi qualche minuto dopo visita un motore di ricerca per raggiungere il sito. In questi casi, in questo rapporto i domini non social possono essere visualizzati. Se desiderate escludere domini non social, ordinate il rapporto per visita, oppure create una copia del segmento in base agli hit invece delle visite. See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social - Referenti di rete

Il rapporto di Network Referrals mostra quali domini di social network hanno portato il traffico al sito. This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Pagine di destinazione

Il rapporto Pagine di destinazione mostra a quali pagine sono arrivati i visitatori dopo aver fatto clic su un collegamento tramite una rete social network. This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Conversioni

Il rapporto Conversioni mostra i dati di ecommerce nel contesto delle reti social. Per utilizzare tali rapporti su entrambe le piattaforme è necessario un'implementazione aggiuntiva; Adobe consiglia di lavorare con un consulente di implementazione per garantire che questi dati siano correttamente configurati per Analysis Workspace.

### Social - Plugin

Il rapporto Plug-in mostra in che modo i visitatori interagiscono con i plug-in per social media incorporati sul sito. È necessaria un'implementazione aggiuntiva per l'utilizzo in Analysis Workspace. Adobe consiglia di lavorare con un consulente di implementazione per garantire la raccolta accurata di questi dati.

### Social - Flusso utenti

Il rapporto sul flusso utenti mostra i dati percorsi nel contesto dei visitatori che arrivano attraverso una rete social network.

1. Fai clic sull'icona visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sull'area di lavoro sopra la tabella a forma libera.
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled 'Drop a Segment here'.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. I valori dimensione sono colorati.
4. Individuate il valore della pagina da iniziare e trascinatelo nello spazio «Dimensione o elemento» al centro
5. Questo rapporto di flusso è interattivo. Fare clic su uno qualsiasi dei valori per espandere i flussi nelle pagine successive o precedenti. Usate il menu di scelta rapida per espandere o comprimere le colonne. Dimensioni diverse possono essere utilizzate anche nello stesso rapporto sul flusso.

## Campagne - Tutto

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. Tieni presente che l'utilizzo della dimensione Codice di tracciamento richiede un'implementazione aggiuntiva per raccogliere dati.

È possibile raccogliere i parametri UTM in Adobe Analytics utilizzando variabili personalizzate (evars). Adobe consiglia di collaborare con un consulente di implementazione per garantire la corretta raccolta dei valori del codice di tracciamento in Adobe Analytics.

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campagne - Parole chiave a pagamento

Il rapporto sulle parole chiave a pagamento mostra come ogni parola chiave esegue una volta che un visitatore fa clic su un collegamento di ricerca a pagamento da un motore di ricerca. The **Search Keywords - Paid** dimension is available in Analysis Workspace, but requires a one-time setup of paid search detection to collect data. See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campagne - Parole chiave organiche

Il rapporto sulle parole chiave organico mostra come ogni parola chiave viene eseguita dopo che un visitatore fa clic su un collegamento di ricerca organico da un motore di ricerca. **La funzione Cerca parole chiave - Naturale** è disponibile in Analysis Workspace. Se non è configurato il rilevamento della ricerca a pagamento, questa dimensione raccoglie sia le parole chiave pagate che quelle naturali.

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Analisi costi

Questo rapporto mostra i dati sulle prestazioni di visita, costo e profitto per i canali di marketing a pagamento. Adobe fornisce un prodotto dedicato per fornire approfondimenti denominati Adobe Advertising Cloud. Se la vostra organizzazione è interessata all'utilizzo di questo prodotto, contattate l'Account Manager della vostra organizzazione.
