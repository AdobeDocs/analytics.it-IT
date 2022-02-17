---
title: Rapporti sul pubblico in Adobe Analytics
description: Scopri come creare rapporti basati sul pubblico utilizzando Analysis Workspace.
feature: Third-party Integration
exl-id: 739b0c3d-3f74-41fa-a2cc-f02c17d85ce2
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 3%

---

# Rapporti sul pubblico

I rapporti sul pubblico mostrano informazioni sui tipi di persone che visitano il tuo sito.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Vedi [Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Utenti attivi

Gli utenti attivi mostrano il numero cumulativo di utenti sul tuo sito nei precedenti 1, 7, 14 o 28 giorni. Sebbene Adobe non disponga del calcolo esatto utilizzato nelle Google Analytics, è possibile utilizzare la metrica Visitatori unici per visualizzare un conteggio deduplicato degli utenti sul sito in base all’intervallo di date selezionato.

Per ottenere un grafico a linee dei visitatori unici:

1. Fai clic sull’icona Visualizzazioni a sinistra e trascina la visualizzazione Linee nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il **Visitatori unici** nello spazio più piccolo etichettato &quot;Drop a Metric here&quot; (Rilascia qui una metrica).
3. Se desideri una granularità diversa, trascina l’intervallo di date desiderato (ad es. **Giorno**, **Settimana**, **Mese**, ecc.) sopra l’intestazione della dimensione data esistente.

Vedi [Visitatori unici](/help/components/metrics/unique-visitors.md) nella guida utente Componenti per informazioni dettagliate su come Adobe calcola i visitatori univoci.

## Valore del ciclo di vita

Il valore del ciclo di vita è una funzione che richiede un’implementazione specializzata aggiuntiva su entrambe le piattaforme. Adobe consiglia di lavorare con un consulente di implementazione per ottenere questi dati.

## Analisi per coorte

L’analisi per coorte mostra la frequenza con cui gli stessi utenti ritornano al tuo sito.

Per creare una tabella coorte:

1. Fai clic sull’icona Visualizzazione a sinistra e trascina la visualizzazione Tabella coorte nell’area di lavoro.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il **Visite** su criteri di inclusione e criteri di ritorno.
3. Fai clic su Genera.

Vedi [Analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) nella guida utente di Analysis Workspace per informazioni su personalizzazioni aggiuntive alla visualizzazione per coorte.

## Tipi di pubblico

Il rapporto Tipi di pubblico in Google Analytics richiede la configurazione di tipi di pubblico. I tipi di pubblico richiedono anche la configurazione in Adobe tramite Adobe Audience Manager. Per ulteriori informazioni, consulta la guida utente di Adobe Audience Manager .

## Esplora utenti

Il rapporto User Explorer consente a un analista di visualizzare visite individuali tramite identificatori anonimi. Ad Adobe, gli identificatori back-end non vengono visualizzati al di fuori dei feed di dati, che sono esportazioni non elaborate dei dati a livello di hit.

* Se questi dati sono desiderati in Analysis Workspace, puoi lavorare con un consulente di implementazione per passare il valore del cookie di identificatore univoco anonimo in un eVar. Tieni presente che questo funziona solo con implementazioni più piccole costituite da meno di 1 milione di visitatori unici al mese.
* Se questi dati sono desiderati nei feed di dati, le colonne concatenate `visid_high` e `visid_low` sono il modo più comune per identificare visitatori univoci. Ulteriori informazioni [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente Export.

## Rapporti demografici e di interesse

I dati demografici e di interesse forniscono informazioni su età, genere e interessi degli utenti del sito. Tali dati vengono raccolti da Google attraverso le loro capacità di tracciamento tra siti.

I dati demografici e di interesse non vengono raccolti automaticamente per Adobe. Tuttavia, se la tua organizzazione ottiene questi dati, puoi utilizzare Attributi del cliente, una funzione all’interno della piattaforma Adobe Experience Cloud. Consente il pieno controllo sull&#39;organizzazione dei dati per attributi e non è limitato solo alla demografia o agli interessi.

Per ulteriori informazioni, consulta la Guida sugli attributi del cliente .

## Geo - Language

Il rapporto sulla lingua geografica mostra il traffico del sito in base all’impostazione della lingua nel browser del visitatore.

Per creare un rapporto sulla lingua:

1. Nel menu Componenti , individua la **Lingua** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Lingua](/help/components/dimensions/language.md) nella guida utente Componenti per ulteriori informazioni.

## Geo - Location

Il rapporto sulla geolocalizzazione fornisce una mappa globale, suddividendo i dati per paese.

Per creare un report di geolocalizzazione:

1. Fai clic sull’icona Visualizzazioni a sinistra e trascina la visualizzazione Mappa nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il **Visitatori unici** nello spazio con etichetta &quot;Aggiungi metrica&quot;.
3. Fai clic su Genera.

Se la tabella è anche ricercata oltre alla mappa:

1. Nel menu Componenti , individua la **Paesi** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Paesi](/help/components/dimensions/countries.md) dimensioni nella guida utente Componenti per ulteriori informazioni.

## Comportamento: nuovo rispetto a ritorno

Il nuovo rapporto di confronto offre una visualizzazione semplificata delle prime sessioni (nuove visite) rispetto alle sessioni successive (visite di ritorno).

Per creare un rapporto nuove visite rispetto a visite di ritorno:

1. Nel menu dei componenti, individua la **Prime visite** segmenta e trascinala sull’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;. Tieni presente che **Prime visite** è un segmento, mentre Workspace in genere utilizza le dimensioni per rappresentare le righe.
2. Individua il **Visite di ritorno** segmentare e trascinarlo sopra l’intestazione di riga Segmenti. Questo aggiunge il segmento come dimensione sotto First Time Visits (Visite per la prima volta), consentendo un confronto semplice.
3. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Se si desidera anche un grafico a linee:

1. Fai clic sull’icona delle visualizzazioni a sinistra e trascina una visualizzazione Linee nell’area di lavoro sopra la tabella a forma libera
2. Per evidenziarli, premi Ctrl+clic (Windows) o Comando+clic (Mac) su ciascuna riga della tabella a forma libera. Questo consente a entrambe le tendenze di apparire nella visualizzazione delle linee.
3. Fai clic sul punto tondo nell’angolo in alto a sinistra della visualizzazione delle linee, quindi fai clic sulla casella di controllo &quot;Blocca selezione&quot;.

## Comportamento - Frequenza e recency

Il rapporto di frequenza e recency è approssimativamente uguale a **Numero visita** in Analysis Workspace.

1. Nel menu dei componenti, individua la **Numero visita** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Drop a dimension here&quot; (Rilascia qui una dimensione).
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Numero visita](/help/components/dimensions/visit-number.md) nella guida utente Componenti per ulteriori informazioni.

## Comportamento - Coinvolgimento

Il rapporto di coinvolgimento è approssimativamente uguale al **Tempo trascorso per visita - Bucket** dimensione.

1. Nel menu dei componenti, individua la **Tempo trascorso per visita - Bucket** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Drop a dimension here&quot; (Rilascia qui una dimensione).
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Tempo trascorso per visita](/help/components/dimensions/time-spent-per-visit.md) nella guida utente Componenti per ulteriori informazioni.

## Tecnologia - Browser &amp; OS

Nel rapporto Browser &amp; OS sono disponibili più dimensioni principali.

* La **Browser** la dimensione primaria è disponibile anche in Analysis Workspace as a dimension.
* La **Sistema operativo** la dimensione primaria è disponibile anche in Analysis Workspace as a dimension.
* La **Risoluzione dello schermo** la dimensione primaria è disponibile in Analysis Workspace come **Risoluzione monitor** dimensione.
* La **Colori schermo** la dimensione primaria è disponibile in Analysis Workspace come **Profondità colore** dimensione.
* La **Versione Flash** la dimensione primaria non è disponibile in Adobe Analytics, tuttavia questi dati possono essere raccolti da un eVar, se lo desideri.

1. Nel menu dei componenti, individua la dimensione desiderata indicata sopra e trascinala nell’area della tabella a forma libera di grandi dimensioni denominata &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida utente Componenti :

* [Browser](/help/components/dimensions/browser.md)
* [Sistema operativo](/help/components/dimensions/operating-systems.md)
* [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md)
* [Profondità colore](/help/components/dimensions/color-depth.md)

## Tecnologia - Rete

Il rapporto sulla rete è approssimativamente uguale al **Dominio** dimensione.

1. Nel menu dei componenti, individua la **Dominio** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Drop a dimension here&quot; (Rilascia qui una dimensione).
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Dominio](/help/components/dimensions/domain.md) nella guida utente Componenti per ulteriori informazioni.

## Mobile - Panoramica

Il rapporto di panoramica mobile è approssimativamente uguale a **Tipo di dispositivo mobile** dimensione. Il valore &quot;Altro&quot; equivale al traffico desktop.

1. Nel menu dei componenti, individua la **Tipo di dispositivo mobile** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Drop a dimension here&quot; (Rilascia qui una dimensione).
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Tipo di dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) nella guida utente Componenti per ulteriori informazioni.

## Dispositivi mobili

Il rapporto sui dispositivi mobili è approssimativamente uguale al **Dispositivo mobile** dimensione.

1. Nel menu dei componenti, individua la **Dispositivo mobile** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Drop a dimension here&quot; (Rilascia qui una dimensione).
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) nella guida utente Componenti per ulteriori informazioni.

## Personalizzato

I rapporti personalizzati sono definiti in base a ciascuna implementazione. Per interpretare questi rapporti, collabora con l’amministratore di Analytics e/o con il consulente di implementazione della tua organizzazione. In genere un&#39;organizzazione mantiene un [Documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) per tenere traccia dei valori delle variabili personalizzate e della modalità di compilazione.

## Benchmarking

I rapporti di Benchmarking ti consentono di vedere come le sfaccettature dei tuoi dati si confrontano con le medie del settore. Al momento, Adobe non condivide dati di benchmarking tra i propri clienti.

## Flusso degli utenti

Il rapporto di flusso è disponibile su entrambe le piattaforme. Per creare un rapporto di flusso:

1. Fai clic sull’icona delle visualizzazioni a sinistra e trascina una visualizzazione Flusso nell’area di lavoro sopra la tabella a forma libera
2. Individua il **Pagine** , quindi fai clic sull’icona Freccia per visualizzare i valori della pagina. Gli articoli di Dimension sono di colore giallo.
3. Individua il valore di pagina desiderato da iniziare e trascinalo nello spazio contrassegnato come &quot;Dimension o elemento&quot; al centro
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.
