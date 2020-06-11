---
title: Report di acquisizione in Adobe Analytics
description: Scopri come creare rapporti basati sull’acquisizione tramite Analysis Workspace.
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 0%

---


# Rapporti sull&#39;acquisizione

I rapporti di acquisizione mostrano come si ottengono i visitatori del sito.

In Adobe Analytics, questi rapporti sono noti come canali **** marketing. Richiedono una configurazione iniziale di base, ma consentono una visualizzazione dei canali molto più personalizzata.

>[!IMPORTANT]
>
> Configurate le regole di elaborazione del canale di marketing per utilizzare questi rapporti. Consultate [Guida introduttiva ai canali](/help/components/c-marketing-channels/c-getting-started-mchannel.md) di marketing per informazioni su come configurare al meglio i canali di marketing nella vostra organizzazione.

Questa pagina presuppone che l’utente disponga di conoscenze di base sull’utilizzo di Analysis Workspace. Consultate [Creare un rapporto di base in Analysis Workspace per gli utenti](create-report.md) di Google Analytics se non avete ancora familiarità con lo strumento in Adobe Analytics.

## Tutto il traffico - Canali

Mostra una visualizzazione aggregata di tutti i canali utilizzati dai visitatori per raggiungere il sito.

1. Nel menu Componenti, individua la dimensione Canale **** marketing e trascinala sull’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

## Tutto il traffico - Treemap

Mostra una mappa ad albero del traffico del canale. Questo rapporto è simile a Tutti i canali di traffico, ma viene visualizzato in modo diverso.

1. Fai clic sull’icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa ad albero nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fate clic sull&#39;icona Componenti a sinistra, quindi trascinate la dimensione Canale **** marketing sull&#39;area grande della tabella a forma libera con l&#39;etichetta &quot;Rilascia qui una dimensione&quot;.
3. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.
4. È opportuno notare che metriche aggiuntive creano altre mappature. Se si desidera una sola mappa ad albero:
   1. Fate clic sulla cella superiore della metrica desiderata per rappresentare la mappa ad albero.
   2. Maiusc+clic sull’ultima cella della stessa colonna metrica per evidenziare la colonna in blu. Se questa operazione viene eseguita correttamente, nella visualizzazione è presente una mappa ad albero.
   3. Fai clic sul punto colorato nell&#39;angolo superiore destro della visualizzazione mappa ad albero, quindi fai clic sulla casella di controllo &quot;Blocca selezione&quot;.

Le mappe ad albero possono essere applicate a qualsiasi dimensione, non solo ai canali di marketing.

## Tutto il traffico - Origine/Medio

I rapporti di origine e media mostrano i domini che hanno portato il traffico al sito.

* La dimensione principale **Origine** è disponibile in Analysis Workspace come dimensione Dominio **di** riferimento.
* La dimensione primaria **Media** è disponibile in Analysis Workspace come dimensione Tipo **** referente.
* La dimensione principale della parola **chiave** è disponibile in Analysis Workspace come dimensione della parola chiave **di** ricerca.

1. Nel menu dei componenti, individuare la dimensione desiderata indicata sopra e trascinarla nell’area grande della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida per l’utente Componenti:

* [Dominio di riferimento](/help/components/dimensions/referring-domain.md)
* [Tipo di riferimento](/help/components/dimensions/referrer-type.md)
* [Cerca parola chiave](/help/components/dimensions/search-keyword.md)

## Tutto il traffico - Riferimenti

* La dimensione principale **Origine** è disponibile in Analysis Workspace come dimensione Dominio **di** riferimento.
* La dimensione principale della pagina **di** destinazione è disponibile in Analysis Workspace come dimensione della pagina **di** immissione.

1. Nel menu dei componenti, individua la dimensione Dominio **di** riferimento o Pagina **di** immissione e la trascina sull’area della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni, consulta la sezione relativa alla dimensione [Dominio](/help/components/dimensions/referring-domain.md) di riferimento nella guida utente Components (Componenti).

## Rapporti Google Ads e Search Console

Adobe utilizza una funzione in Analysis Workspace denominata Analisi della pubblicità per inserire dati di pubblicità e ricerca da più piattaforme, incluso Google.

La funzione di analisi pubblicitaria richiede la configurazione per restituire i dati. Per informazioni dettagliate su come abilitare queste dimensioni aggiuntive in Analysis Workspace, consulta la guida [Analisi della](/help/integrate/c-advertising-analytics/overview.md) pubblicità.

## Report social

I rapporti sui social network forniscono informazioni simili ai rispettivi rapporti sul comportamento, tranne nel contesto dei social network. Questi dati sono disponibili in Analysis Workspace combinando una dimensione con un segmento.

A volte i visitatori raggiungono il sito attraverso più canali nella stessa sessione. Ad esempio, un visitatore fa clic su una pagina social media, quindi qualche minuto dopo visita un motore di ricerca per raggiungere il sito. In questi casi, i domini non social possono essere visualizzati in questo rapporto. Se desiderate escludere domini non social, ordinate il rapporto per visite o create una copia del segmento in base agli hit invece che alle visite. Per ulteriori informazioni, consulta Contenitori [di](/help/components/c-segmentation/seg-overview.md) segmentazione nella guida utente Componenti.

### Social - Riferimenti alla rete

Il rapporto Riferimenti di rete mostra quali domini di social network hanno portato il traffico al sito. Questi dati sono disponibili in Analysis Workspace utilizzando la dimensione Dominio **di** riferimento e il segmento **Visite dai siti** social.

1. Nel menu Componenti, individua la dimensione Dominio **di** riferimento e trascinala nell’area della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Nel menu Componenti, individua il segmento **Visite dai siti** social e trascina nell’area piccola appena sopra la tabella a forma libera con l’etichetta &quot;Rilascia qui un segmento&quot;.
3. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

### Social - Pagine di destinazione

Il rapporto Pagine di destinazione mostra le pagine sulle quali i visitatori sono arrivati dopo aver fatto clic su un collegamento tramite un social network. Questi dati sono disponibili in Analysis Workspace utilizzando la dimensione **Pagina** di immissione e il segmento **Visite dai siti** social.

1. Nel menu Componenti, individua la dimensione Pagina **** di immissione e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Nel menu Componenti, individua il segmento **Visite dai siti** social e trascina nell’area piccola appena sopra la tabella a forma libera con l’etichetta &quot;Rilascia qui un segmento&quot;.
3. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

### Social - Conversioni

Il rapporto Conversioni mostra i dati e-commerce nel contesto dei social network. Per utilizzare tali rapporti su entrambe le piattaforme è necessaria un&#39;ulteriore implementazione; Adobe consiglia di collaborare con un consulente per l’implementazione per verificare che i dati siano configurati correttamente per Analysis Workspace.

### Social - Plugin

Il rapporto Plugins mostra in che modo i visitatori interagiscono con i plug-in per social media incorporati nel sito. È richiesta un’ulteriore implementazione per l’utilizzo in Analysis Workspace. Adobe consiglia di collaborare con un consulente per l&#39;implementazione per garantire che i dati vengano raccolti con precisione.

### Social - Flusso utenti

Il rapporto Flusso utenti mostra i dati del percorso nel contesto in cui i visitatori arrivano attraverso un social network.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso nell’area di lavoro sopra la tabella a forma libera
2. Fai clic sull&#39;icona Componenti a sinistra, quindi trascina il segmento **Visite da Social Sites** sull&#39;area piccola appena sopra la visualizzazione di flusso con l&#39;etichetta &quot;Rilascia qui un segmento&quot;.
3. Individuare la dimensione **Pagine** , quindi fare clic sull&#39;icona freccia per visualizzare i valori della pagina. I valori delle dimensioni sono di colore giallo.
4. Individuate il valore della pagina con cui iniziare e trascinatelo nello spazio contrassegnato come &quot;Dimensione o elemento&quot; al centro
5. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.

## Campagne - Tutte

Il rapporto sulle campagne è disponibile in Analysis Workspace utilizzando la dimensione Codice **di** tracciamento. Tenere presente che l&#39;utilizzo della dimensione Codice di tracciamento richiede un&#39;implementazione aggiuntiva per la raccolta dei dati.

È possibile raccogliere parametri UTM in Adobe Analytics utilizzando variabili personalizzate (eVar). Adobe consiglia di collaborare con un consulente per l&#39;implementazione per garantire che i valori dei codici di tracciamento vengano raccolti con precisione in Adobe Analytics.

1. Nel menu Componenti, individua la dimensione Codice **di** tracciamento e trascinala nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

## Campagne - Parole chiave pagate

Il rapporto sulle parole chiave pagate mostra le prestazioni di ogni parola chiave dopo che un visitatore fa clic su un collegamento di ricerca a pagamento da un motore di ricerca. La dimensione **Cerca parole chiave - A pagamento** è disponibile in Analysis Workspace, ma per raccogliere i dati è necessaria una configurazione una tantum del rilevamento a pagamento. Consultate Rilevamento [ricerca a](/help/admin/admin/paid-search-detection/paid-search-detection.md) pagamento nella guida utente per l’amministratore per i dettagli di configurazione.

1. Nel menu Componenti, individuate la dimensione **Cerca parola chiave - Pagato** e trascinatela nell’area grande della tabella a forma libera con l’etichetta &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

## Campagne - Parole chiave organiche

Il rapporto sulle parole chiave organiche mostra le prestazioni di ogni parola chiave dopo che un visitatore fa clic su un collegamento di ricerca organico da un motore di ricerca. La dimensione naturale **** Cerca parole chiave è disponibile in Analysis Workspace. Se il rilevamento della ricerca a pagamento non è impostato, questa dimensione raccoglie le parole chiave a pagamento e naturali.

1. Nel menu Componenti, individuate la parola chiave **Cerca - Dimensione naturale** e trascinatela nell’area grande della tabella a forma libera con l’etichetta &quot;Rilasciate qui una dimensione&quot;.
2. Trascina le metriche desiderate nell&#39;area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

## Analisi costi

Questo rapporto mostra i dati sulle prestazioni di visite, costi e ricavi per i canali di marketing a pagamento. Adobe fornisce un prodotto dedicato per fornire informazioni approfondite denominate Adobe Advertising Cloud. Se l&#39;azienda è interessata a utilizzare questo prodotto, contatta l&#39;Account Manager dell&#39;organizzazione.
