---
title: Rapporti sul pubblico in Adobe Analytics
description: Scopri come creare rapporti basati sul pubblico utilizzando Analysis Workspace.
feature: Third-party Integration
exl-id: 739b0c3d-3f74-41fa-a2cc-f02c17d85ce2
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 3%

---

# Rapporti sul pubblico

I rapporti sul pubblico mostrano informazioni sui tipi di persone che visitano il tuo sito.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Se non conosci ancora lo strumento in Analysis Workspace, consulta [Creare un report di base in Adobe Analytics per gli utenti di Google Analytics](create-report.md).

## Utenti attivi

Gli utenti attivi mostrano il numero cumulativo di utenti del sito negli ultimi 1, 7, 14 o 28 giorni. Anche se Adobe non dispone del calcolo esatto utilizzato in Google Analytics, puoi utilizzare la metrica Visitatori univoci per visualizzare un conteggio deduplicato degli utenti nel sito in base all’intervallo di date selezionato.

Per ottenere un grafico a linee di visitatori univoci:

1. Fai clic sull’icona delle Visualizzazioni a sinistra, quindi trascina la visualizzazione Linee nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull&#39;icona Componenti a sinistra, quindi trascina la metrica **Visitatori univoci** nello spazio più piccolo denominato &#39;Rilascia qui una metrica&#39;.
3. Se desideri una granularità diversa, trascina l’intervallo di date desiderato (ad esempio **Giorno**, **Settimana**, **Mese**, ecc.) sopra l’intestazione della dimensione data esistente.

Per informazioni dettagliate su come Adobe calcola i visitatori univoci, consulta [Visitatori univoci](/help/components/metrics/unique-visitors.md) nella guida utente dei Componenti.

## Valore del ciclo di vita

Il valore del ciclo di vita è una funzione che richiede un’implementazione aggiuntiva specializzata su entrambe le piattaforme. Adobe consiglia di collaborare con un consulente per l’implementazione per ottenere questi dati.

## Analisi per coorte

L’analisi per coorte mostra con quale frequenza gli stessi utenti ritornano al sito.

Per creare una tabella coorte:

1. Fai clic sull’icona Visualizzazione a sinistra e trascina la visualizzazione Tabella coorte nell’area di lavoro.
2. Fai clic sull&#39;icona Componenti a sinistra, quindi trascina la metrica **Visite** sia sui criteri di inclusione che sui criteri di ritorno.
3. Fai clic su Genera.

Consulta [Analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) nella guida utente di Analysis Workspace per informazioni dettagliate su ulteriori personalizzazioni della visualizzazione per coorte.

## Tipi di pubblico

Il rapporto Tipi di pubblico in Google Analytics richiede la configurazione di Tipi di pubblico. I tipi di pubblico richiedono anche la configurazione in Adobe tramite Adobe Audience Manager. Per ulteriori informazioni, consulta la guida utente di Adobe Audience Manager.

## Esplora utenti

Il rapporto User Explorer consente a un analista di visualizzare le singole visite tramite identificatori anonimi. Adobe non fa emergere gli identificatori di backend al di fuori dei feed di dati, che sono esportazioni di dati non elaborati a livello di hit.

* Se questi dati sono desiderati in Analysis Workspace, è possibile collaborare con un consulente per l’implementazione per trasmettere il valore cookie dell’identificatore univoco anonimo in un eVar. Tieni presente che questo funziona solo con implementazioni più piccole costituite da meno di 1 milione di visitatori univoci al mese.
* Se questi dati sono desiderati all&#39;interno dei feed di dati, le colonne concatenate `visid_high` e `visid_low` sono il modo più comune per identificare i visitatori univoci. Ulteriori informazioni su [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente per l&#39;esportazione.

## Rapporti Demografia e interessi

I dati demografici e relativi agli interessi forniscono informazioni su età, genere e interessi degli utenti del sito. Tali dati vengono raccolti da Google tramite le loro funzionalità di tracciamento intersito.

I dati demografici e relativi agli interessi non vengono raccolti automaticamente da Adobe. Tuttavia, se l’organizzazione ottiene questi dati, puoi utilizzare gli attributi del cliente, una funzione all’interno di Adobe Experience Cloud Platform. Consente il pieno controllo sull’organizzazione dei dati per attributi e non è limitato solo a dati demografici o interessi.

Per ulteriori informazioni, consulta la guida Attributi del cliente.

## Geo - Language

Il rapporto di lingua geografica mostra il traffico del sito in base all’impostazione della lingua nel browser del visitatore.

Per creare un rapporto lingua:

1. Nel menu Componenti, individua la dimensione **Lingua** e trascinala nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, consulta la dimensione [Lingua](/help/components/dimensions/language.md) nella guida utente dei Componenti.

## Geo - Location

Il rapporto di geolocalizzazione fornisce una visualizzazione mappa mondiale, suddividendo i dati per paese.

Per creare un rapporto di geolocalizzazione:

1. Fai clic sull’icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull&#39;icona Componenti a sinistra, quindi trascina la metrica **Visitatori univoci** nello spazio denominato &#39;Aggiungi metrica&#39;.
3. Fai clic su Genera.

Se la tabella è anche desiderata in aggiunta alla mappa:

1. Nel menu Componenti, individua la dimensione **Paesi** e trascinala nella grande area della tabella a forma libera denominata &#39;Rilascia qui un Dimension&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, consulta le dimensioni [Paesi](/help/components/dimensions/countries.md) nella guida utente dei Componenti.

## Comportamento - Novità e ritorno

Il rapporto Nuovo/Ritorno offre una visualizzazione semplificata delle prime sessioni (nuove visite) rispetto alle sessioni successive (visite di ritorno).

Per creare un nuovo rapporto sulle visite e sulle visite di ritorno:

1. Nel menu dei componenti, individua il segmento **Visite per la prima volta** e trascinalo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;. Tieni presente che **Visite per la prima volta** è un segmento, mentre Workspace in genere utilizza dimensioni per rappresentare le righe.
2. Individua il segmento **Visite di ritorno** e trascinalo sopra l&#39;intestazione della riga Segmenti. Questo aggiunge il segmento come dimensione sotto Prime visite, consentendo un facile confronto.
3. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Se desideri anche un grafico a linee:

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Linee nell’area di lavoro sopra la tabella a forma libera
2. Utilizza i comandi Ctrl-clic (Windows) o Comando-clic (Mac) su ogni riga della tabella a forma libera per evidenziarle. Questo consente di visualizzare entrambe le tendenze nella visualizzazione delle linee.
3. Fai clic sul piccolo punto rotondo colorato nell’angolo superiore sinistro della visualizzazione delle linee, quindi fai clic sulla casella di controllo &quot;Blocca selezione&quot;.

## Comportamento - Frequenza e attualità

Il rapporto di frequenza e aggiornamento è approssimativamente uguale alla dimensione **Numero visite** in Analysis Workspace.

1. Nel menu dei componenti, individua la dimensione **Numero visita** e trascinala nella grande area della tabella a forma libera con l&#39;etichetta &#39;Rilascia qui una dimensione&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, consulta la dimensione [Numero visite](/help/components/dimensions/visit-number.md) nella guida utente dei Componenti.

## Comportamento - Coinvolgimento

Il report di coinvolgimento è approssimativamente uguale alla dimensione **Tempo trascorso per visita - Bucket**.

1. Nel menu dei componenti, individua la dimensione **Tempo trascorso per visita - Bucket** e trascinala nella grande area della tabella a forma libera denominata &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, consulta la dimensione [Tempo trascorso per visita](/help/components/dimensions/time-spent-per-visit.md) nella guida utente dei Componenti.

## Tecnologia - Browser e sistema operativo

Nel rapporto Browser &amp; OS sono disponibili più dimensioni principali.

* La dimensione primaria **Browser** è disponibile anche in Analysis Workspace come dimensione.
* La dimensione primaria **Sistema operativo** è disponibile anche in Analysis Workspace come dimensione.
* La dimensione primaria **Risoluzione schermo** è disponibile in Analysis Workspace come dimensione **Risoluzione monitor**.
* La dimensione principale **Colori schermo** è disponibile in Analysis Workspace come dimensione **Profondità colore**.
* La dimensione primaria **Flash versione** non è disponibile in Adobe Analytics, tuttavia questi dati possono essere raccolti da un eVar, se necessario.

1. Nel menu dei componenti, individua la dimensione desiderata indicata sopra e trascinala sulla grande area della tabella a forma libera denominata &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida utente dei Componenti:

* [Browser](/help/components/dimensions/browser.md)
* [Sistema operativo](/help/components/dimensions/operating-systems.md)
* [Risoluzione del monitor](/help/components/dimensions/monitor-resolution.md)
* [Profondità colore](/help/components/dimensions/color-depth.md)

## Tecnologia - Rete

Il report di rete è approssimativamente uguale alla dimensione **Dominio**.

1. Nel menu dei componenti, individua la dimensione **Dominio** e trascinala nella grande area della tabella a forma libera denominata &#39;Rilascia qui una dimensione&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, vedere la dimensione [Dominio](/help/components/dimensions/domain.md) nella guida utente dei Componenti.

## Mobile - Panoramica

Il report di panoramica mobile è approssimativamente uguale alla dimensione **Tipo di dispositivo mobile**. Il valore &quot;Altro&quot; equivale al traffico sul desktop.

1. Nel menu dei componenti, individua la dimensione **Tipo di dispositivo mobile** e trascinala nella grande area della tabella a forma libera con l&#39;etichetta &#39;Rilascia qui una dimensione&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, consulta la dimensione [Tipo di dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) nella guida utente dei Componenti.

## Mobile - Devices

Il report dei dispositivi mobili è approssimativamente uguale alla dimensione **Dispositivo mobile**.

1. Nel menu dei componenti, individua la dimensione **Dispositivo mobile** e trascinala nella grande area della tabella a forma libera con l&#39;etichetta &#39;Rilascia qui una dimensione&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Per ulteriori informazioni, consulta la dimensione [Dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) nella guida utente dei Componenti.

## Personalizzato

I rapporti personalizzati vengono definiti in base all’implementazione. Per interpretare questi rapporti, rivolgiti all’amministratore di Analytics e/o al consulente per l’implementazione della tua organizzazione. In genere un&#39;organizzazione gestisce un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) per tenere traccia dei valori delle variabili personalizzate e del modo in cui vengono compilati.

## Benchmarking

I rapporti di benchmark consentono di vedere come i facet dei dati si confrontano con le medie del settore. Al momento, Adobe non condivide i dati di benchmark tra i suoi clienti.

## Flusso utenti

Il rapporto di flusso è disponibile su entrambe le piattaforme. Per creare un rapporto di flusso:

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul workspace sopra la tabella a forma libera
2. Individua la dimensione **Pagine**, quindi fai clic sull&#39;icona a forma di freccia per visualizzare i valori della pagina. Gli elementi di Dimension sono di colore giallo.
3. Individua il valore di pagina desiderato per iniziare, quindi trascinalo nello spazio al centro con l’etichetta &quot;Dimension o elemento&quot;
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.
