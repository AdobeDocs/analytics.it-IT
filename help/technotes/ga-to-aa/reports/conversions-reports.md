---
title: Rapporti sulle conversioni in Adobe Analytics
description: Scopri come utilizzare i rapporti sulle conversioni in Adobe Analytics.
feature: Third-party Integration
exl-id: 315b7dc0-1cd9-4beb-8203-88e205375f84
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Rapporti sulle conversioni

Una &quot;conversione&quot; è un’azione eseguita da un visitatore sul sito e tradotta direttamente negli indicatori chiave della tua organizzazione. I rapporti sulle conversioni mostrano i dettagli sulla conversione dei visitatori.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Consulta [Creazione di un rapporto di base in Analysis Workspace per gli utenti Google Analytics](create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Rapporti sugli obiettivi

Gli obiettivi forniscono agli utenti Google Analytics un modo per definire la conversione di un sito web. Sono il modo predefinito per creare funnel, invertire il flusso comportamentale, funnel multicanale e attribuzione. Gli obiettivi nelle Google Analytics non sono retroattivi e possono essere impostati solo sulla pagina di amministrazione. Inoltre, si basano solo su una pagina, un evento, il tempo trascorso o il numero medio di pagine.

In Adobe Analytics, il concetto di obiettivo non è necessario perché le metriche possono essere applicate in qualsiasi contesto. Se l’implementazione soddisfa gli eventi da monitorare, puoi modificare qualsiasi rapporto di conversione e ottenere immediatamente i risultati per i dati storici.

### Visualizzazione funnel

Il rapporto di visualizzazione funnel aiuta gli analisti a concentrarsi su una particolare serie di passaggi necessari per la conversione. Ad esempio, prima di effettuare un acquisto, un visitatore su un sito di e-commerce deve accedere al carrello, alla pagina di fatturazione e spedizione, alla pagina di pagamento e alla pagina di revisione dell’ordine.

In Analysis Workspace, questi dati possono essere visualizzati utilizzando la Visualizzazione di fallout.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Fallout nell’area di lavoro sopra la tabella a forma libera
2. Fai clic sull’icona dei componenti a sinistra, quindi individua **Pagine** dimensione.
3. Fai clic sull’icona a forma di freccia accanto alla dimensione Pagine per visualizzare i valori della pagina. Gli elementi Dimension sono di colore giallo.
4. Individua la pagina desiderata come primo punto di contatto e trascinala nello spazio etichettato &quot;Aggiungi punto di contatto&quot; nella visualizzazione.
5. Continua ad aggiungere i punti di contatto desiderati trascinando i valori di pagina nella visualizzazione.

La visualizzazione Abbandono non è limitata alla sola dimensione Pagine. Qualsiasi dimensione, metrica o segmento può essere utilizzato per adattare il rapporto di fallout in base alle esigenze della tua organizzazione.

![Visualizzazione del fallout](/help/technotes/ga-to-aa/assets/fallout.png)

## Rapporti di e-commerce

I rapporti di e-commerce vengono generalmente utilizzati dai siti che vendono prodotti o servizi per misurare gli ordini e i ricavi relativi agli articoli acquistati. Questa funzione è disponibile in Adobe Analytics ed è nota come rapporti sui prodotti.

Sia i rapporti di e-commerce nelle Google Analytics che i rapporti sui prodotti in Adobe Analytics richiedono modifiche di implementazione personalizzate da utilizzare. Consulta la [Prodotti](/help/components/dimensions/product.md) nella guida utente dei Componenti per ulteriori informazioni.

## Rapporti Funnel multicanale

I rapporti funnel multicanale forniscono dati di canale di marketing aggiuntivi oltre a quelli forniti dai rapporti di acquisizione. Questi rapporti si concentrano sulla conversione dei visitatori, anziché sul modo in cui i visitatori arrivano al sito.

>[!NOTE]
>
> L’utilizzo dei rapporti multicanale in Adobe Analytics richiede sia la configurazione di Canali di marketing sia un’implementazione personalizzata per contenere la variabile dei prodotti e l’evento di acquisto. L’Adobe consiglia di lavorare con un consulente per l’implementazione se queste funzioni non sono ancora configurate per la suite di rapporti.

### Multicanale - Conversioni assistite

Conversioni assistite mostra quante volte ogni canale ha assistito con una conversione. In Analysis Workspace, il **Ordina assistenze** può essere utilizzata.

1. Nel menu Componenti, individua **Canale di marketing** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina **Ordina assistenze** metrica sopra il creato automaticamente **Occorrenze** per sostituirla. Se necessario, puoi trascinare ulteriori metriche nell’area di lavoro.

### Multicanale - Percorsi di conversione principali

Il rapporto percorsi di conversione principali mostra i percorsi di canale principali seguiti da un utente prima della conversione. Analysis Workspace utilizza un rapporto di flusso per visualizzare i percorsi di conversione principali.

1. Fai clic sull’icona Pannelli a sinistra, quindi trascina un pannello Attribuzione sopra la tabella a forma libera.
2. Fai clic sull’icona Componenti a sinistra, individua la **Canale di marketing** e trascinarlo nella casella denominata &#39;Aggiungi Dimension&#39;.
3. Individua l’evento di conversione desiderato in Metriche (ad esempio Ordini) e trascinalo nella casella &quot;Aggiungi metrica&quot;. Le metriche calcolate non sono supportate per il pannello Attribuzione.
4. Fai clic su Genera.
5. Nel rapporto risultante, individua la visualizzazione &quot;Flusso canale&quot;. Questo flusso mostra i percorsi principali che un visitatore ha toccato prima di un acquisto.

Questa visualizzazione del flusso è interattiva. Fare clic su ciascun canale per espandere il flusso in entrambe le direzioni.

![Visualizzazione del flusso](/help/technotes/ga-to-aa/assets/flow.png)

### Multicanale - Ritardo

Il rapporto ritardo mostra la quantità di tempo, in giorni, necessaria per la conversione di un visitatore sul sito. In Analysis Workspace, questi dati sono disponibili utilizzando **Giorni precedenti al primo acquisto** dimensione. È disponibile solo nel contesto di un evento di acquisto implementato correttamente.

1. Nel menu Componenti, individua **Giorni precedenti al primo acquisto** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

L’Adobe consiglia di utilizzare **Ordini**, **Unità**, o **Ricavi** con questa dimensione.

Per altri tipi di conversioni, inclusi gli eventi personalizzati, il **Tempo precedente all’evento** dimensione è disponibile. Mostra la quantità di tempo, in minuti, impiegata da un visitatore per attivare l’evento all’interno della visita.

1. Nel menu Componenti, individua **Tempo precedente all’evento** e trascinarlo nella grande area della tabella a forma libera denominata &quot;Rilascia qui un Dimension&quot;.
2. Trascina le metriche desiderate nell’area di lavoro insieme al file creato automaticamente **Occorrenze** metrica. Consulta la [Guida alla traduzione delle metriche](common-metrics.md) per informazioni dettagliate su come ottenere ciascuna metrica.

L’Adobe consiglia di utilizzare questa dimensione insieme a eventi personalizzati o eventi di acquisto.

### Multicanale - Lunghezza percorso

Il rapporto sulla lunghezza del percorso mostra il numero di canali toccati prima di un evento di conversione. In Analysis Workspace, il pannello Attribuzione contiene questi dati in una delle sue visualizzazioni.

1. Fai clic sull’icona Pannelli a sinistra, quindi trascina un pannello Attribuzione sopra la tabella a forma libera
2. Fai clic sull’icona Componenti a sinistra, individua la **Canale di marketing** e trascinarlo nella casella denominata &#39;Aggiungi Dimension&#39;.
3. Individua l’evento di conversione desiderato in Metriche (ad esempio Ordini) e trascinalo nella casella &quot;Aggiungi metrica&quot;. Le metriche calcolate non sono supportate per il pannello Attribuzione.
4. Fai clic su Genera.
5. Nel rapporto risultante, individua la visualizzazione &quot;Punti di contatto al Percorso&quot;. Questo istogramma mostra il numero di canali toccati da un visitatore prima di un acquisto.
