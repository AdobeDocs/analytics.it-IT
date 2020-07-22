---
title: Rapporti sul pubblico in Adobe  Analytics
description: Scopri come creare rapporti basati sul pubblico utilizzando  Analysis Workspace.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 0%

---


# Rapporti sul pubblico

I rapporti sul pubblico mostrano informazioni sui tipi di persone che visitano il sito.

Questa pagina presuppone che l&#39;utente disponga di conoscenze di base sull&#39;utilizzo  Analysis Workspace. Consultate [Creare un rapporto di base in  Analysis Workspace per gli utenti](create-report.md) di Google  Analytics se non avete ancora familiarità con lo strumento in Adobe  Analytics.

## Utenti attivi

Gli utenti attivi mostrano il numero cumulativo di utenti sul sito nei precedenti 1, 7, 14 o 28 giorni. Anche se Adobe non dispone del calcolo esatto utilizzato in Google  Analytics, puoi utilizzare la metrica Visitatori unici per visualizzare un numero deduplicato di utenti nel tuo sito in base all&#39;intervallo di date selezionato.

Per ottenere un grafico a linee di visitatori univoci:

1. Fai clic sull’icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Linea nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina la metrica Visitatori **** unici nello spazio più piccolo con l’etichetta &quot;Rilascia qui una metrica&quot;.
3. Se desiderate una granularità diversa, trascinate l’intervallo di date desiderato (ad esempio **Giorno**, **Settimana**, **Mese** ecc.) sopra l’intestazione della dimensione data esistente.

Consulta Visitatori [](/help/components/metrics/unique-visitors.md) univoci nella guida utente Componenti per informazioni dettagliate sul modo in cui Adobe calcola i visitatori univoci.

## Valore del ciclo di vita

Il valore &quot;lifetime&quot; del ciclo di vita è una funzione che richiede un’ulteriore implementazione specializzata su entrambe le piattaforme. Per ottenere questi dati, Adobe consiglia di collaborare con un consulente per l&#39;implementazione.

## Analisi per coorte

L’analisi per coorte mostra la frequenza con cui gli stessi utenti ritornano al sito.

Per creare una tabella di coorte:

1. Fate clic sull’icona Visualizzazione a sinistra, quindi trascinate la visualizzazione Tabella coorte nell’area di lavoro.
2. Fate clic sull&#39;icona Componenti a sinistra, quindi trascinate la metrica **Visite** sia sui criteri di inclusione che sui criteri di restituzione.
3. Fai clic su Genera.

Consulta Analisi [per](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) coorte nella guida per l’utente di Analysis Workspace  per informazioni dettagliate sulle personalizzazioni aggiuntive alla visualizzazione per coorte.

## Tipi di pubblico

Il rapporto Audiences in Google  Analytics richiede l&#39;impostazione di audience. Le audience richiedono anche la configurazione in Adobe tramite  Adobe Audience Manager. Per ulteriori informazioni, consultate la guida utente  Adobe Audience Manager.

## Esplora utenti

Il rapporto di Esplora utenti consente a un analista di visualizzare singole visite tramite identificatori anonimi. Adobe non visualizza gli identificatori di backend al di fuori dei feed di dati, che sono esportazioni di dati non elaborati a livello di hit.

* Se questi dati sono desiderati in  Analysis Workspace, è possibile collaborare con un consulente di implementazione per passare il valore del cookie univoco dell&#39;identificatore anonimo in un&#39;eVar. Questo funziona solo con implementazioni più piccole, consistenti in meno di 1 milione di visitatori unici al mese.
* Se questi dati sono desiderati all&#39;interno dei feed di dati, le colonne concatenate `visid_high` e `visid_low` rappresentano il modo più comune per identificare i visitatori univoci. Per ulteriori informazioni sui feed [di](/help/export/analytics-data-feed/data-feed-overview.md) dati, consulta la guida per l’utente relativa all’esportazione.

## Rapporti su demografia e interessi

I dati demografici e degli interessi forniscono informazioni su età, sesso e interessi degli utenti del sito. Tali dati vengono raccolti da Google attraverso le loro capacità di monitoraggio intersito.

I dati demografici e di interessi non vengono raccolti automaticamente da Adobe. Tuttavia, se l&#39;organizzazione ottiene tali dati, puoi utilizzare Attributi cliente, una funzione all&#39;interno dell&#39;Platform Adobe Experience Cloud. Consente il pieno controllo sull&#39;organizzazione dei dati per attributi, e non è limitato solo a dati demografici o interessi.

Per ulteriori informazioni, vedere la Guida sugli attributi del cliente.

## Geo - Lingua

Il rapporto sulla lingua geografica mostra il traffico del sito in base all&#39;impostazione della lingua nel browser del visitatore.

Per creare un rapporto sulla lingua:

1. Nel menu Componenti, individua la dimensione **Lingua** e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la dimensione [Lingua](/help/components/dimensions/language.md) nella guida utente Componenti.

## Geo - Posizione

Il rapporto sulla geolocalizzazione offre una vista mappa globale, suddividendo i dati per paese.

Per creare un rapporto sulla geolocalizzazione:

1. Fai clic sull’icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull&#39;icona Componenti a sinistra, quindi trascina la metrica Visitatori **** unici nello spazio con l&#39;etichetta &quot;Aggiungi metrica&quot;.
3. Fai clic su Genera.

Se la tabella è desiderata in aggiunta alla mappa:

1. Nel menu Componenti, individuare la dimensione **Paesi** e trascinarla sull’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta le dimensioni [Paesi](/help/components/dimensions/countries.md) nella guida utente Componenti.

## Comportamento - Nuovo/Ritorno

Il nuovo rapporto Confronto tra restituzione e ritorno offre una visualizzazione semplificata delle prime sessioni (nuove visite) e delle sessioni successive (visite di ritorno).

Per creare un rapporto sulle visite nuovo o di ritorno:

1. Nel menu dei componenti, individua il segmento **First Time Visits (Prima visita** ) e trascinalo nell’area grande della tabella a forma libera con l’etichetta &quot;Drop a Dimension here&quot; (Rilascia qui una dimensione). Si noti che **First Time Visits (Prima visita** ) è un segmento, mentre Workspace utilizza solitamente le dimensioni per rappresentare le righe.
2. Individua il segmento **Return Visits (Visite** di ritorno) e trascinalo sopra l’intestazione della riga Segments (Segmenti). Questo aggiunge il segmento come una dimensione sotto First Time Visits (Visite per la prima volta), consentendo un confronto semplice.
3. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Se si desidera anche un grafico a linee:

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Linea nell’area di lavoro sopra la tabella a forma libera
2. Per evidenziare le righe nella tabella a forma libera, tenete premuto Ctrl (Windows) o Comando (Mac OS) e fate clic. Questo consente a entrambe le tendenze di essere visualizzate nella visualizzazione linea.
3. Fare clic sul punto rotondo piccolo nell&#39;angolo superiore sinistro della visualizzazione linea, quindi fare clic sulla casella di controllo &quot;Blocca selezione&quot;.

## Comportamento - Frequenza e Recency

Il rapporto frequenza e recency è approssimativamente uguale alla dimensione Numero **** visita in  Analysis Workspace.

1. Nel menu dei componenti, individua la dimensione Numero **** visita e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la dimensione Numero [di](/help/components/dimensions/visit-number.md) visite nella guida utente Componenti.

## Comportamento - Coinvolgimento

Il rapporto di coinvolgimento è all&#39;incirca uguale alla dimensione **Tempo trascorso per visita - Rilievo** .

1. Nel menu dei componenti, individua la dimensione **Tempo trascorso per visita - Dimensione** appiattita e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la dimensione [Tempo trascorso per visita](/help/components/dimensions/time-spent-per-visit.md) nella guida utente Componenti.

## Tecnologia - Browser e sistema operativo

Nel rapporto Browser e sistema operativo sono disponibili più dimensioni principali.

* La dimensione principale del **browser** è disponibile anche in  Analysis Workspace come dimensione.
* La dimensione primaria del sistema **** operativo è disponibile anche in  Analysis Workspace come dimensione.
* La dimensione principale Risoluzione **** schermo è disponibile in  Analysis Workspace come dimensione Risoluzione **** monitor.
* La dimensione principale Colori **** schermo è disponibile in  Analysis Workspace come dimensione Profondità **** colore.
* La dimensione principale della versione **** Flash non è disponibile in Adobe  Analytics, ma questi dati possono essere raccolti da un&#39;eVar, se necessario.

1. Nel menu dei componenti, individuare la dimensione desiderata indicata sopra e trascinarla nell’area grande della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida per l’utente Componenti:

* [Browser](/help/components/dimensions/browser.md)
* [Sistema operativo](/help/components/dimensions/operating-systems.md)
* [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md)
* [Profondità colore](/help/components/dimensions/color-depth.md)

## Tecnologia - Rete

Il rapporto sulla rete è approssimativamente uguale alla dimensione **Dominio** .

1. Nel menu dei componenti, individua la dimensione **Dominio** e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la dimensione [Dominio](/help/components/dimensions/domain.md) nella guida utente Componenti.

## Mobile - Panoramica

Il rapporto sulla panoramica mobile è approssimativamente uguale alla dimensione Tipo **dispositivo** mobile. Il valore &quot;Altro&quot; è equivalente al traffico desktop.

1. Nel menu dei componenti, individua la dimensione Tipo **dispositivo** mobile e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la sezione relativa al tipo [di dispositivo](/help/components/dimensions/mobile-dimensions.md) mobile nella guida per l’utente dei componenti.

## Dispositivi mobili

Il rapporto sui dispositivi mobili è approssimativamente uguale alla dimensione Dispositivo **** mobile.

1. Nel menu dei componenti, individua la dimensione Dispositivo **** mobile e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la dimensione Dispositivo [](/help/components/dimensions/mobile-dimensions.md) mobile nella guida utente Componenti.

## Personalizzato

I report personalizzati sono definiti in base alla singola implementazione. Per interpretare questi rapporti, rivolgiti all&#39;amministratore  Analytics della tua organizzazione e/o al consulente di implementazione. In genere, un&#39;organizzazione mantiene un documento [di progettazione della](/help/implement/prepare/solution-design.md) soluzione per tenere traccia dei valori delle variabili personalizzate e della relativa compilazione.

## Benchmarking

I rapporti di analisi comparativa consentono di vedere in che modo i facet dei dati sono confrontati con le medie di settore. Al momento, Adobe non condivide i dati di benchmarking tra i propri clienti.

## Flusso utenti

Il rapporto sul flusso è disponibile su entrambe le piattaforme. Per creare un rapporto di flusso:

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso nell’area di lavoro sopra la tabella a forma libera
2. Individuare la dimensione **Pagine** , quindi fare clic sull&#39;icona freccia per visualizzare i valori della pagina. Gli elementi dimensione sono colorati in giallo.
3. Individuate il valore della pagina con cui iniziare e trascinatelo nello spazio contrassegnato come &quot;Dimensione o elemento&quot; al centro
4. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.
