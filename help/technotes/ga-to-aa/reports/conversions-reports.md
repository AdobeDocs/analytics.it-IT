---
title: Rapporti sulle conversioni in Adobe Analytics
description: Scopri come utilizzare i rapporti sulle conversioni in Adobe Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Rapporti sulle conversioni

Una "conversione" è un'azione eseguita da un visitatore sul sito che si traduce direttamente negli indicatori chiave dell'organizzazione. I rapporti sulle conversioni mostrano i dettagli sulla modalità di conversione dei visitatori.

Questa pagina presuppone che l’utente disponga di conoscenze di base sull’utilizzo di Analysis Workspace. Consultate [Creare un rapporto di base in Analysis Workspace per gli utenti](create-report.md) di Google Analytics se non avete ancora familiarità con lo strumento in Adobe Analytics.

## Obiettivi, rapporti

Gli obiettivi forniscono agli utenti di Google Analytics un modo per definire la conversione di un sito Web. Sono il modo predefinito per creare funnel, invertire il flusso comportamentale, funnel multicanale e l'attribuzione. Gli obiettivi in Google Analytics non sono retroattivi e possono essere impostati solo sulla pagina di amministrazione. Inoltre, si basano solo su una pagina, un evento, il tempo trascorso o il numero medio di pagine.

In Adobe Analytics, il concetto di obiettivo non è richiesto perché le metriche possono essere applicate in qualsiasi contesto. Fintanto che l'implementazione include gli eventi da monitorare, puoi modificare qualsiasi rapporto di conversione e ottenere immediatamente risultati per i dati storici.

### Visualizzazione funnel

Il rapporto di visualizzazione funnel aiuta gli analisti a concentrarsi su una serie particolare di passaggi necessari per la conversione. Ad esempio, prima di effettuare un acquisto, un visitatore su un sito di eCommerce dovrà accedere al carrello, alla pagina di fatturazione e spedizione, alla pagina di pagamento e alla pagina di revisione degli ordini.

In Analysis Workspace, questi dati possono essere visualizzati mediante la visualizzazione Abbandono.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Abbandono nell’area di lavoro sopra la tabella a forma libera
2. Fate clic sull’icona dei componenti a sinistra, quindi individuate la dimensione **Pagine** .
3. Fate clic sull’icona freccia accanto alla dimensione Pagine per visualizzare i valori della pagina. I valori delle dimensioni sono di colore giallo.
4. Individua la pagina desiderata come primo punto di contatto e trascinala nello spazio con l’etichetta "Aggiungi punto di contatto" nella visualizzazione.
5. Continua ad aggiungere i punti di contatto desiderati trascinando i valori della pagina sulla visualizzazione.

La visualizzazione Abbandono non si limita alla dimensione Pagine. Qualsiasi dimensione, metrica o segmento può essere utilizzato per adattare il rapporto di abbandono alle esigenze della tua organizzazione.

![Visualizzazione abbandono](/help/technotes/ga-to-aa/assets/fallout.png)

## Rapporti eCommerce

I rapporti e-commerce sono generalmente utilizzati dai siti che vendono prodotti o servizi per misurare gli ordini e le entrate sugli articoli acquistati. Questa funzione è disponibile in Adobe Analytics ed è nota come Rapporti sui prodotti.

Entrambi i rapporti e-commerce in Google Analytics e i rapporti sui prodotti in Adobe Analytics richiedono modifiche di implementazione personalizzate da utilizzare. Per ulteriori informazioni, consulta la dimensione [Prodotti](/help/components/c-variables/dimensionslist/reports-products.md) nella guida utente Componenti.

## Rapporti Funnel multicanale

I report funnel multicanale forniscono dati aggiuntivi sui canali di marketing oltre a quelli forniti dai report di acquisizione. Tali rapporti si concentrano sul modo in cui i visitatori si convertono invece di quello in cui arrivano al sito.

> [!NOTE]
>
> L'utilizzo di report con più canali in Adobe Analytics richiede sia l'impostazione di Marketing Channels, sia un'implementazione personalizzata per contenere la variabile del prodotto e l'evento di acquisto. Adobe consiglia di lavorare con un consulente per l'implementazione se queste funzioni non sono ancora configurate per la suite di rapporti.

### Multi-canale - Conversioni Assistite

Conversioni assistite mostra quante volte ogni canale ha assistito con una conversione. In Analysis Workspace, è possibile utilizzare la metrica **Order Assist** .

1. Nel menu Componenti, individua la dimensione Canale **** marketing e trascinala sull’area grande della tabella a forma libera con l’etichetta "Rilascia qui una dimensione".
2. Trascinate la metrica **Order Assists** sopra l’intestazione della metrica **Occorrenze** creata automaticamente per sostituirla. Se necessario, è possibile trascinare ulteriori metriche nell'area di lavoro.

### Multi-canale - Percorsi di conversione superiori

Il rapporto sui percorsi di conversione principali mostra i percorsi dei canali superiori seguiti dall'utente prima della conversione. Analysis Workspace utilizza un rapporto sul flusso per visualizzare i percorsi di conversione principali.

1. Fate clic sull’icona Pannelli a sinistra, quindi trascinate un pannello Attribuzione sopra la tabella a forma libera.
2. Fate clic sull'icona Componenti a sinistra, individuate la dimensione Canale **** marketing e trascinatela nella casella con l'etichetta "Aggiungi dimensione".
3. Individuate l'evento di conversione desiderato in Metriche (ad esempio, Ordini) e trascinatelo nella casella con l'etichetta "Aggiungi metrica". Le metriche calcolate non sono supportate per il pannello Attribuzione.
4. Fai clic su Genera.
5. Nel rapporto risultante, individuate la visualizzazione "Flusso canale". Questo flusso mostra i percorsi principali che un visitatore ha toccato prima di un acquisto.

Questa visualizzazione del flusso è interattiva. Fate clic su ciascun canale per espandere il flusso in una delle due direzioni.

![Visualizzazione flusso](/help/technotes/ga-to-aa/assets/flow.png)

### Multi-canale - Time Lag

Il rapporto sull'intervallo di tempo mostra il tempo in giorni impiegato dal visitatore per effettuare la conversione sul sito. In Analysis Workspace, questi dati sono disponibili nella dimensione **Giorni prima del primo acquisto** . È disponibile solo nel contesto di un evento di acquisto correttamente implementato.

1. Nel menu Componenti, individua la dimensione **Giorni prima del primo acquisto** e trascinala nell’area grande della tabella a forma libera con l’etichetta "Rilascia qui una dimensione".
2. Trascina le metriche desiderate nell'area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Adobe consiglia di utilizzare le metriche **Ordini**, **Unità** o **Entrate** con questa dimensione.

Per altri tipi di conversioni, compresi gli eventi personalizzati, è disponibile la dimensione **Tempo precedente all’evento** . Mostra il tempo, in minuti, impiegato dal visitatore per attivare l’evento all’interno della visita.

1. Nel menu Componenti, individuate la dimensione **Tempo precedente all’evento** e trascinatela nell’area della tabella a forma libera con l’etichetta "Rilascia qui una dimensione".
2. Trascina le metriche desiderate nell'area di lavoro accanto alla metrica **Occorrenze** creata automaticamente. Consulta la guida [alla traduzione](common-metrics.md) Metrica per informazioni dettagliate su come ottenere ciascuna metrica.

Adobe consiglia di utilizzare questa dimensione insieme agli eventi personalizzati o agli eventi di acquisto.

### Multi-canale - Lunghezza percorso

Il rapporto sulla lunghezza del percorso mostra il numero di canali toccati prima di un evento di conversione. In Analysis Workspace, il pannello Attribuzione contiene questi dati in una delle sue visualizzazioni.

1. Fate clic sull’icona Pannelli a sinistra, quindi trascinate un pannello Attribuzione sopra la tabella a forma libera
2. Fate clic sull'icona Componenti a sinistra, individuate la dimensione Canale **** marketing e trascinatela nella casella con l'etichetta "Aggiungi dimensione".
3. Individuate l'evento di conversione desiderato in Metriche (ad esempio, Ordini) e trascinatelo nella casella con l'etichetta "Aggiungi metrica". Le metriche calcolate non sono supportate per il pannello Attribuzione.
4. Fai clic su Genera.
5. Nel rapporto risultante, individua la visualizzazione "Punti di contatto per viaggio". Questo istogramma mostra il numero di canali che un visitatore ha toccato prima di un acquisto.
