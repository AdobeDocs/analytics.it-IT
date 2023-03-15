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

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Consulta [Creazione di un rapporto di base in Analysis Workspace per gli utenti Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Utenti attivi

Gli utenti attivi mostrano il numero cumulativo di utenti del sito negli ultimi 1, 7, 14 o 28 giorni. Anche se Adobe non dispone del calcolo esatto utilizzato nelle Google Analytics, puoi utilizzare la metrica Visitatori univoci per visualizzare un conteggio deduplicato degli utenti nel sito in base all’intervallo di date selezionato.

Per ottenere un grafico a linee di visitatori univoci:

1. Fai clic sull’icona delle Visualizzazioni a sinistra, quindi trascina la visualizzazione Linee nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il file **Visitatori univoci** metrica nello spazio più piccolo etichettato &quot;Drop a Metric here&quot; (Rilascia qui una metrica).
3. Per ottenere una granularità diversa, trascina l’intervallo di date desiderato (ad es. **Giorno**, **Settimana**, **Mese**, ecc.) sopra l’intestazione della dimensione data esistente.

Consulta [Visitatori univoci](/help/components/metrics/unique-visitors.md) nella guida utente dei Componenti, per informazioni su come Adobe calcola i visitatori univoci.

## Valore del ciclo di vita

Il valore del ciclo di vita è una funzione che richiede un’implementazione aggiuntiva specializzata su entrambe le piattaforme. L’Adobe consiglia di collaborare con un consulente per l’implementazione per ottenere questi dati.

## Analisi per coorte

L’analisi per coorte mostra con quale frequenza gli stessi utenti ritornano al sito.

Per creare una tabella coorte:

1. Fai clic sull’icona Visualizzazione a sinistra e trascina la visualizzazione Tabella coorte nell’area di lavoro.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il file **Visite** metrica sia per i criteri di inclusione che per i criteri di ritorno.
3. Fai clic su Genera.

Consulta [Analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) nella guida utente di Analysis Workspace per informazioni dettagliate su ulteriori personalizzazioni della visualizzazione per coorte.

## Tipi di pubblico

Il rapporto Tipi di pubblico in Google Analytics richiede la configurazione di Tipi di pubblico. I tipi di pubblico richiedono anche la configurazione in Adobe tramite Adobe Audience Manager. Per ulteriori informazioni, consulta la guida utente di Adobe Audience Manager.

## Esplora utenti

Il rapporto User Explorer consente a un analista di visualizzare le singole visite tramite identificatori anonimi. Adobe non fa emergere gli identificatori di backend al di fuori dei feed di dati, che sono esportazioni di dati non elaborate a livello di hit.

* Se questi dati sono desiderati in Analysis Workspace, è possibile collaborare con un consulente per l’implementazione per trasmettere in un eVar il valore cookie dell’identificatore univoco anonimo. Tieni presente che questo funziona solo con implementazioni più piccole costituite da meno di 1 milione di visitatori univoci al mese.
* Se questi dati sono desiderati all’interno dei feed di dati, le colonne concatenate `visid_high` e `visid_low` sono il modo più comune per identificare i visitatori univoci. Ulteriori informazioni su [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente Esporta.

## Rapporti Demografia e interessi

I dati demografici e relativi agli interessi forniscono informazioni su età, genere e interessi degli utenti del sito. Tali dati vengono raccolti da Google tramite le loro funzionalità di tracciamento intersito.

I dati demografici e relativi agli interessi non vengono raccolti automaticamente dagli Adobi. Tuttavia, se la tua organizzazione ottiene questi dati, puoi utilizzare Attributi del cliente, una funzione all’interno di Adobe Experience Cloud Platform. Consente il pieno controllo sull’organizzazione dei dati per attributi e non è limitato solo a dati demografici o interessi.

Per ulteriori informazioni, consulta la Guida di Attributi del cliente.

## Geo - Language

Il rapporto di lingua geografica mostra il traffico del sito in base all’impostazione della lingua nel browser del visitatore.

Per creare un rapporto lingua:

1. Nel menu Componenti, individua **Lingua** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Lingua](/help/components/dimensions/language.md) nella guida utente dei Componenti per ulteriori informazioni.

## Geo - Location

Il rapporto di geolocalizzazione fornisce una visualizzazione mappa mondiale, suddividendo i dati per paese.

Per creare un rapporto di geolocalizzazione:

1. Fai clic sull’icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il file **Visitatori univoci** metrica nello spazio etichettato &quot;Aggiungi metrica&quot;.
3. Fai clic su Genera.

Se la tabella è anche desiderata in aggiunta alla mappa:

1. Nel menu Componenti, individua **Paesi** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Paesi](/help/components/dimensions/countries.md) dimensioni nella guida utente dei Componenti per ulteriori informazioni.

## Comportamento - Novità e ritorno

Il rapporto Nuovo/Ritorno offre una visualizzazione semplificata delle prime sessioni (nuove visite) rispetto alle sessioni successive (visite di ritorno).

Per creare un nuovo rapporto sulle visite e sulle visite di ritorno:

1. Nel menu dei componenti, individua **Prime visite** e trascinarlo sulla grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;. Tieni presente che **Prime visite** è un segmento, mentre Workspace in genere utilizza le dimensioni per rappresentare le righe.
2. Individua il **Visite di ritorno** e trascinarlo sopra l’intestazione di riga Segmenti. Questo aggiunge il segmento come dimensione sotto Prime visite, consentendo un facile confronto.
3. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Se desideri anche un grafico a linee:

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Linee nell’area di lavoro sopra la tabella a forma libera
2. Utilizza i comandi Ctrl-clic (Windows) o Comando-clic (Mac) su ogni riga della tabella a forma libera per evidenziarle. Questo consente di visualizzare entrambe le tendenze nella visualizzazione delle linee.
3. Fai clic sul piccolo punto rotondo colorato nell’angolo superiore sinistro della visualizzazione delle linee, quindi fai clic sulla casella di controllo &quot;Blocca selezione&quot;.

## Comportamento - Frequenza e attualità

Il rapporto di frequenza e attualità è approssimativamente uguale al **Numero di visite** in Analysis Workspace.

1. Nel menu dei componenti, individua **Numero di visite** e trascinarla nella grande area della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Numero di visite](/help/components/dimensions/visit-number.md) nella guida utente dei Componenti per ulteriori informazioni.

## Comportamento - Coinvolgimento

Il rapporto di coinvolgimento è approssimativamente uguale al **Tempo trascorso per visita - Bucket** dimensione.

1. Nel menu dei componenti, individua **Tempo trascorso per visita - Bucket** e trascinarla nella grande area della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Tempo trascorso per visita](/help/components/dimensions/time-spent-per-visit.md) nella guida utente dei Componenti per ulteriori informazioni.

## Tecnologia - Browser e sistema operativo

Nel rapporto Browser &amp; OS sono disponibili più dimensioni principali.

* Il **Browser** la dimensione primaria è disponibile anche in Analysis Workspace as a dimension.
* Il **Sistema operativo** la dimensione primaria è disponibile anche in Analysis Workspace as a dimension.
* Il **Risoluzione dello schermo** la dimensione primaria è disponibile in Analysis Workspace come **Risoluzione monitor** dimensione.
* Il **Colori schermo** la dimensione primaria è disponibile in Analysis Workspace come **Profondità colore** dimensione.
* Il **Versione Flash** la dimensione primaria non è disponibile in Adobe Analytics, tuttavia questi dati possono essere raccolti da un eVar, se necessario.

1. Nel menu dei componenti, individua la dimensione desiderata indicata sopra e trascinala sulla grande area della tabella a forma libera denominata &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida utente dei Componenti:

* [Browser](/help/components/dimensions/browser.md)
* [Sistema operativo](/help/components/dimensions/operating-systems.md)
* [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md)
* [Profondità colore](/help/components/dimensions/color-depth.md)

## Tecnologia - Rete

Il rapporto di rete è approssimativamente uguale al **Dominio** dimensione.

1. Nel menu dei componenti, individua **Dominio** e trascinarla nella grande area della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Dominio](/help/components/dimensions/domain.md) nella guida utente dei Componenti per ulteriori informazioni.

## Mobile - Panoramica

Il rapporto di panoramica mobile è approssimativamente uguale al **Tipo di dispositivo mobile** dimensione. Il valore &quot;Altro&quot; equivale al traffico sul desktop.

1. Nel menu dei componenti, individua **Tipo di dispositivo mobile** e trascinarla nella grande area della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Tipo di dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) nella guida utente dei Componenti per ulteriori informazioni.

## Mobile - Devices

Il rapporto sui dispositivi mobili è approssimativamente uguale al **Dispositivo mobile** dimensione.

1. Nel menu dei componenti, individua **Dispositivo mobile** e trascinarla nella grande area della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) nella guida utente dei Componenti per ulteriori informazioni.

## Personalizzato

I rapporti personalizzati vengono definiti in base all’implementazione. Per interpretare questi rapporti, rivolgiti all’amministratore di Analytics e/o al consulente per l’implementazione della tua organizzazione. In genere un’organizzazione gestisce un [Documento progettazione soluzione](/help/implement/prepare/solution-design.md) per tenere traccia dei valori delle variabili personalizzate e del modo in cui vengono compilati.

## Benchmarking

I rapporti di benchmark consentono di vedere come i facet dei dati si confrontano con le medie del settore. Adobe non condivide i dati di benchmarking tra i suoi clienti in questo momento.

## Flusso utenti

Il rapporto di flusso è disponibile su entrambe le piattaforme. Per creare un rapporto di flusso:

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul workspace sopra la tabella a forma libera
2. Individua il **Pagine** , quindi fai clic sull’icona a forma di freccia per visualizzare i valori della pagina. Gli elementi Dimension sono di colore giallo.
3. Individua il valore di pagina desiderato per iniziare, quindi trascinalo nello spazio al centro con l’etichetta &quot;Dimension o elemento&quot;
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.
