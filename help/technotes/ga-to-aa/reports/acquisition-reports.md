---
title: Rapporti di acquisizione in Adobe Analytics
description: Scopri come creare rapporti basati sull'acquisizione utilizzando Analysis Workspace.
feature: Third-party Integration
exl-id: 2929d34b-8eb0-4105-a49c-02d536929fe0
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 2%

---

# Rapporti di acquisizione

I rapporti di acquisizione mostrano come ottenere visitatori dal sito.

In Adobe Analytics, questi rapporti sono noti come **Canali marketing**. Richiedono una configurazione iniziale di base, ma consentono una visualizzazione dei canali molto più personalizzata.

>[!IMPORTANT]
>
> Imposta le regole di elaborazione del canale di marketing per utilizzare questi rapporti. Vedi [Guida introduttiva ai canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) per informazioni su come configurare al meglio i canali di marketing nella tua organizzazione.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Vedi [Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Tutto il traffico - Canali

Mostra una visualizzazione aggregata di tutti i canali utilizzati dai visitatori per raggiungere il sito.

1. Nel menu Componenti , individua la **Canale di marketing** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

## Tutto il traffico - Mappe ad albero

Mostra una mappa ad albero del traffico del canale. Questo rapporto è simile a Tutti i canali di traffico, ma viene visualizzato in modo diverso.

1. Fai clic sull’icona Visualizzazioni a sinistra e trascina la visualizzazione Mappa ad albero nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il **Canale di marketing** dimensione nell’area della tabella a forma libera di grandi dimensioni denominata &quot;Drop a dimension here&quot; (Rilascia una dimensione qui).
3. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.
4. Tieni presente che metriche aggiuntive creano ulteriori mappe ad albero. Se desideri una sola mappa ad albero:
   1. Fai clic sulla cella superiore della metrica desiderata per rappresentare la mappa ad albero.
   2. Maiusc+clic sull’ultima cella della stessa colonna metrica per evidenziare la colonna in blu. Se questa operazione viene eseguita correttamente, nella visualizzazione è presente una mappa ad albero.
   3. Fai clic sul punto colorato nell’angolo in alto a destra della visualizzazione mappa ad albero, quindi fai clic sulla casella di controllo &quot;Blocca selezione&quot;.

Le mappe ad albero possono essere applicate a qualsiasi dimensione, non solo ai canali di marketing.

## Tutto il traffico - Origine/Media

I rapporti sorgente e media mostrano i domini che generano traffico verso il sito.

* La **Origine** la dimensione primaria è disponibile in Analysis Workspace come **Dominio di riferimento** dimensione.
* La **Media** la dimensione primaria è disponibile in Analysis Workspace come  **Tipo referrer** dimensione.
* La **Parola chiave** la dimensione primaria è disponibile in Analysis Workspace come **Parola chiave di ricerca** dimensione.

1. Nel menu dei componenti, individua la dimensione desiderata indicata sopra e trascinala nell’area della tabella a forma libera di grandi dimensioni denominata &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida utente Componenti :

* [Dominio di riferimento](/help/components/dimensions/referring-domain.md)
* [Tipo di riferimento](/help/components/dimensions/referrer-type.md)
* [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md)

## Tutto il traffico - Riferimenti

* La **Origine** la dimensione primaria è disponibile in Analysis Workspace come **Dominio di riferimento** dimensione.
* La **Pagina di destinazione** la dimensione primaria è disponibile in Analysis Workspace come **Pagina di ingresso** dimensione.

1. Nel menu dei componenti, individua la **Dominio di riferimento** o **Pagina di ingresso** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Drop a dimension here&quot; (Rilascia qui una dimensione).
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

Consulta la sezione [Dominio di riferimento](/help/components/dimensions/referring-domain.md) nella guida utente Componenti per ulteriori informazioni.

## Rapporti Google Ads e rapporti della console di ricerca

Adobe utilizza una funzione in Analysis Workspace denominata Advertising Analytics per inserire dati pubblicitari e di ricerca da più piattaforme, incluso Google.

La funzione di analisi pubblicitaria richiede la configurazione per restituire i dati. Vedi [Guida di Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) per informazioni dettagliate su come abilitare queste dimensioni aggiuntive in Analysis Workspace.

## Relazioni sociali

Le relazioni sociali forniscono informazioni simili a quelle della loro relazione sul comportamento, tranne nel contesto dei social network. Questi dati sono disponibili in Analysis Workspace combinando una dimensione con un segmento.

A volte i visitatori raggiungono il tuo sito attraverso più canali nella stessa sessione. Ad esempio, un visitatore fa clic su una pagina social media, quindi qualche minuto dopo visita un motore di ricerca per raggiungere il tuo sito. In questi casi, i domini non social possono essere visualizzati in questo rapporto. Se desideri escludere i domini non social, ordina il rapporto per visite o crea una copia del segmento in base agli hit invece delle visite. Vedi [Contenitori di segmentazione](/help/components/segmentation/seg-overview.md) nella guida utente Componenti per ulteriori informazioni.

### Social - Riferimenti di rete

Il rapporto Riferimenti di rete mostra quali domini di social network hanno veicolato il traffico verso il sito. Questi dati sono disponibili in Analysis Workspace utilizzando **Dominio di riferimento** dimensione e **Visite da siti social** segmento.

1. Nel menu Componenti , individua la **Dominio di riferimento** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Nel menu Componenti , individua la **Visite da siti social** segmenta e trascina nell’area piccola appena sopra la tabella a forma libera denominata &quot;Rilascia qui un segmento&quot;.
3. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

### Social - Pagine di destinazione

Il rapporto Pagine di destinazione mostra le pagine sulle quali i visitatori sono arrivati dopo aver fatto clic su un collegamento tramite un social network. Questi dati sono disponibili in Analysis Workspace utilizzando **Pagina di ingresso** dimensione e **Visite da siti social** segmento.

1. Nel menu Componenti , individua la **Pagina di ingresso** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Nel menu Componenti , individua la **Visite da siti social** segmenta e trascina nell’area piccola appena sopra la tabella a forma libera denominata &quot;Rilascia qui un segmento&quot;.
3. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

### Social - Conversioni

Il rapporto Conversioni mostra i dati di e-commerce nel contesto dei social network. È necessaria un’ulteriore implementazione per utilizzare questi rapporti su entrambe le piattaforme; Adobe consiglia di lavorare con un consulente di implementazione per garantire che questi dati siano configurati correttamente per Analysis Workspace.

### Social - Plugins

Il rapporto Plugins mostra come i visitatori interagiscono con i plug-in di social media incorporati sul sito. È necessaria un’implementazione aggiuntiva per l’utilizzo in Analysis Workspace. Adobe consiglia di lavorare con un consulente di implementazione per garantire che questi dati vengano raccolti con precisione.

### Flusso utenti social

Il rapporto di flusso Utenti mostra i dati di percorso nel contesto in cui i visitatori arrivano attraverso un social network.

1. Fai clic sull’icona delle visualizzazioni a sinistra e trascina una visualizzazione Flusso nell’area di lavoro sopra la tabella a forma libera
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il **Visite da siti social** segmento nella piccola area appena sopra la visualizzazione di flusso con etichetta &quot;Drop a Segment here&quot; (Rilascia qui un segmento).
3. Individua il **Pagine** , quindi fai clic sull’icona Freccia per visualizzare i valori della pagina. Gli articoli di Dimension sono di colore giallo.
4. Individua il valore di pagina desiderato da iniziare e trascinalo nello spazio contrassegnato come &quot;Dimension o elemento&quot; al centro
5. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

## Campagne - Tutte

Il rapporto delle campagne è disponibile in Analysis Workspace utilizzando **Codice di tracciamento** dimensione. Tieni presente che l’utilizzo della dimensione Codice di tracciamento richiede un’implementazione aggiuntiva per raccogliere i dati.

È possibile raccogliere parametri UTM in Adobe Analytics utilizzando variabili personalizzate (eVar). Adobe consiglia di lavorare con un consulente di implementazione per garantire che i valori del codice di tracciamento vengano raccolti con precisione in Adobe Analytics.

1. Nel menu Componenti , individua la **Codice di tracciamento** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

## Campagne - Parole chiave a pagamento

Il rapporto sulle parole chiave a pagamento mostra le prestazioni di ogni parola chiave dopo che un visitatore fa clic su un collegamento di ricerca a pagamento da un motore di ricerca. La **Parole chiave di ricerca - Pagato** La dimensione è disponibile in Analysis Workspace, ma richiede una configurazione unica del rilevamento di ricerca a pagamento per raccogliere i dati. Vedi [Rilevamento ricerca a pagamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) nella guida utente Amministratore per i dettagli della configurazione.

1. Nel menu Componenti , individua la **Parola chiave di ricerca - Pagato** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

## Campagne - Parole chiave organiche

Il rapporto sulle parole chiave organiche mostra le prestazioni di ogni parola chiave dopo che un visitatore fa clic su un collegamento di ricerca organico da un motore di ricerca. La **Parole chiave di ricerca - Naturale** è disponibile in Analysis Workspace. Tieni presente che se non è impostato il rilevamento di ricerche a pagamento, questa dimensione raccoglie le parole chiave a pagamento e naturali.

1. Nel menu Componenti , individua la **Parola chiave di ricerca - Naturale** e trascinarlo nell’area grande della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro accanto alla creazione automatica **Occorrenze** metrica. Consulta la sezione [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica rispettiva.

## Analisi dei costi

Questo rapporto mostra i dati sulle prestazioni relativi a visite, costi e ricavi per i canali di marketing a pagamento. Adobe fornisce un prodotto dedicato per fornire informazioni denominato Adobe Advertising Cloud. Se la tua organizzazione è interessata all&#39;utilizzo di questo prodotto, contatta l&#39;Account Manager della tua organizzazione.
