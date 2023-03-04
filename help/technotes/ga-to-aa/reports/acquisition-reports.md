---
title: Rapporti di acquisizione in Adobe Analytics
description: Scopri come creare rapporti basati sull’acquisizione utilizzando Analysis Workspace.
feature: Third-party Integration
exl-id: 2929d34b-8eb0-4105-a49c-02d536929fe0
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 2%

---

# Rapporti di acquisizione

I rapporti di acquisizione mostrano come ottenere i visitatori sul sito.

In Adobe Analytics, questi rapporti sono noti come **Canali di marketing**. Richiedono una configurazione iniziale di base, ma consentono una visualizzazione dei canali molto più personalizzata.

>[!IMPORTANT]
>
> Imposta le regole di elaborazione del canale di marketing per utilizzare questi rapporti. Consulta [Introduzione ai canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) per informazioni su come configurare al meglio i canali di marketing all’interno della tua organizzazione.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Consulta [Creazione di un rapporto di base in Analysis Workspace per gli utenti Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Tutto il traffico - Canali

Mostra una visualizzazione aggregata di tutti i canali utilizzati dai visitatori per raggiungere il sito.

1. Nel menu Componenti, individua **Canale di marketing** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

## Tutto il traffico - Mappa ad albero

Mostra una mappa ad albero del traffico del canale. Questo rapporto è simile a Tutto il traffico - Canali, ma viene visualizzato in modo diverso.

1. Fai clic sull’icona Visualizzazioni a sinistra, quindi trascina la visualizzazione Mappa ad albero nell’area di lavoro sopra la tabella a forma libera vuota.
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il file **Canale di marketing** nella grande area della tabella a forma libera denominata &quot;Rilasciare qui una dimensione&quot;.
3. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.
4. Tieni presente che metriche aggiuntive creano mappe ad albero aggiuntive. Se si desidera una sola mappa ad albero:
   1. Fai clic sulla cella superiore della metrica desiderata per rappresentare la mappa ad albero.
   2. Maiusc+fai clic sull’ultima cella della stessa colonna di metriche per evidenziare la colonna in blu. Se eseguita correttamente, nella visualizzazione è presente una mappa ad albero.
   3. Fai clic sul punto colorato nell’angolo superiore destro della visualizzazione Mappa ad albero, quindi fai clic sulla casella di controllo &quot;Blocca selezione&quot;.

Le mappe ad albero possono essere applicate a qualsiasi dimensione, non solo ai canali di marketing.

## Tutto il traffico - Origine/media

I rapporti di origine e media mostrano i domini che hanno portato il traffico al sito.

* Il **Sorgente** la dimensione primaria è disponibile in Analysis Workspace come **Dominio di riferimento** dimensione.
* Il **Medio** la dimensione primaria è disponibile in Analysis Workspace come  **Tipo di referrer** dimensione.
* Il **Parola chiave** la dimensione primaria è disponibile in Analysis Workspace come **Parola chiave di ricerca** dimensione.

1. Nel menu dei componenti, individua la dimensione desiderata indicata sopra e trascinala sulla grande area della tabella a forma libera denominata &quot;Rilascia qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Per ulteriori informazioni sulle rispettive dimensioni, consulta le pagine seguenti nella guida utente dei Componenti:

* [Dominio di riferimento](/help/components/dimensions/referring-domain.md)
* [Tipo di riferimento](/help/components/dimensions/referrer-type.md)
* [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md)

## Tutto il traffico - Riferimenti

* Il **Sorgente** la dimensione primaria è disponibile in Analysis Workspace come **Dominio di riferimento** dimensione.
* Il **Pagina di destinazione** la dimensione primaria è disponibile in Analysis Workspace come **Pagina di ingresso** dimensione.

1. Nel menu dei componenti, individua **Dominio di riferimento** o **Pagina di ingresso** e trascinarla nella grande area della tabella a forma libera con l’etichetta &quot;Rilasciare qui una dimensione&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

Consulta la [Dominio di riferimento](/help/components/dimensions/referring-domain.md) nella guida utente dei Componenti per ulteriori informazioni.

## Rapporti di Google Ads e rapporti della console di ricerca

Adobe utilizza una funzione di Analysis Workspace denominata Advertising Analytics per inserire dati pubblicitari e di ricerca da più piattaforme, tra cui Google.

La funzione di analisi della pubblicità richiede una configurazione per restituire i dati. Consulta [Guida di Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) per informazioni dettagliate su come abilitare queste dimensioni aggiuntive in Analysis Workspace.

## Rapporti social

I rapporti sociali forniscono informazioni simili ai rispettivi rapporti sul comportamento, tranne che nel contesto dei social network. Questi dati sono disponibili in Analysis Workspace combinando una dimensione con un segmento.

A volte i visitatori raggiungono il tuo sito attraverso più canali nella stessa sessione. Ad esempio, un visitatore fa clic su una pagina di social media, quindi pochi minuti dopo visita un motore di ricerca per raggiungere il tuo sito. In questi casi, in questo rapporto possono essere visualizzati domini non social. Se desideri escludere i domini non social, ordina il rapporto in base alle visite o crea una copia del segmento in base agli hit anziché alle visite. Consulta [Contenitori di segmentazione](/help/components/segmentation/seg-overview.md) nella guida utente Componenti per ulteriori informazioni.

### Social - Riferimenti rete

Il rapporto Riferimenti rete mostra quali domini di social network hanno indirizzato il traffico verso il sito. Questi dati sono disponibili in Analysis Workspace utilizzando **Dominio di riferimento** dimensione e **Visite da siti social** segmento.

1. Nel menu Componenti, individua **Dominio di riferimento** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Nel menu Componenti, individua **Visite da siti social** e trascinali sull’area piccola appena sopra la tabella a forma libera con l’etichetta &quot;Rilascia qui un segmento&quot;.
3. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

### Social - Pagine di destinazione

Il rapporto Pagine di destinazione mostra le pagine sulle quali i visitatori sono arrivati dopo aver fatto clic su un collegamento tramite un social network. Questi dati sono disponibili in Analysis Workspace utilizzando **Pagina di ingresso** dimensione e **Visite da siti social** segmento.

1. Nel menu Componenti, individua **Pagina di ingresso** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Nel menu Componenti, individua **Visite da siti social** e trascinali sull’area piccola appena sopra la tabella a forma libera con l’etichetta &quot;Rilascia qui un segmento&quot;.
3. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

### Social - Conversioni

Il rapporto Conversioni mostra i dati di e-commerce nel contesto dei social network. È necessaria un’implementazione aggiuntiva per utilizzare questi rapporti su entrambe le piattaforme; l’Adobe consiglia di collaborare con un consulente per l’implementazione per garantire che i dati siano configurati correttamente per Analysis Workspace.

### Social - Plug-in

Il rapporto Plugin mostra come i visitatori interagiscono con i plug-in per social media incorporati sul sito. È necessaria un’implementazione aggiuntiva per l’utilizzo in Analysis Workspace. L’Adobe consiglia di collaborare con un consulente per l’implementazione per garantire la raccolta accurata di questi dati.

### Social - Flusso utenti

Il rapporto di flusso Utenti mostra i dati di percorso nel contesto dei visitatori che arrivano tramite un social network.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul workspace sopra la tabella a forma libera
2. Fai clic sull’icona Componenti a sinistra, quindi trascina il file **Visite da siti social** sulla piccola area appena sopra la visualizzazione del flusso con l’etichetta &quot;Rilascia qui un segmento&quot;.
3. Individua il **Pagine** , quindi fai clic sull’icona a forma di freccia per visualizzare i valori della pagina. Gli elementi Dimension sono di colore giallo.
4. Individua il valore di pagina desiderato per iniziare, quindi trascinalo nello spazio al centro con l’etichetta &quot;Dimension o elemento&quot;
5. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

## Campagne - Tutto

Il rapporto delle campagne è disponibile in Analysis Workspace utilizzando **Codice di tracciamento** dimensione. L’utilizzo della dimensione Codice di tracciamento richiede un’implementazione aggiuntiva per raccogliere i dati.

È possibile raccogliere i parametri UTM in Adobe Analytics utilizzando variabili personalizzate (eVar). L’Adobe consiglia di collaborare con un consulente per l’implementazione per garantire che i valori del codice di tracciamento vengano raccolti accuratamente in Adobe Analytics.

1. Nel menu Componenti, individua **Codice di tracciamento** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

## Campagne - Parole chiave a pagamento

Il report delle parole chiave a pagamento mostra il comportamento di ciascuna parola chiave dopo che un visitatore ha fatto clic su un collegamento di ricerca a pagamento da un motore di ricerca. Il **Parole chiave di ricerca - Pagato** La dimensione è disponibile in Analysis Workspace, ma richiede una configurazione una tantum del rilevamento di ricerche a pagamento per raccogliere i dati. Consulta [Rilevamento ricerca a pagamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) nella guida utente Admin per informazioni dettagliate sulla configurazione.

1. Nel menu Componenti, individua **Parola chiave di ricerca - A pagamento** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

## Campagne - Parole chiave organiche

Il rapporto delle parole chiave organiche mostra il comportamento di ciascuna parola chiave dopo che un visitatore ha fatto clic su un collegamento di ricerca organica da un motore di ricerca. Il **Parole chiave di ricerca - Naturale** è disponibile in Analysis Workspace. Tieni presente che se il rilevamento di ricerche a pagamento non è impostato, questa dimensione raccoglie sia le parole chiave a pagamento che quelle naturali.

1. Nel menu Componenti, individua **Parola chiave di ricerca - Naturale** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

## Analisi dei costi

Questo rapporto mostra i dati sulle prestazioni di visite, costi e ricavi per i canali di marketing a pagamento. Adobe fornisce un prodotto dedicato per fornire approfondimenti chiamato Adobe Advertising Cloud. Se la tua organizzazione è interessata a utilizzare questo prodotto, contatta il team del tuo account Adobe.
