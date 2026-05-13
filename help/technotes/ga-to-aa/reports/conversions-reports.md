---
title: Rapporti sulle conversioni in Adobe Analytics
description: Scopri come utilizzare i rapporti sulle conversioni in Adobe Analytics.
feature: Third-party Integration
exl-id: 315b7dc0-1cd9-4beb-8203-88e205375f84
TQID: https://experienceleague.adobe.com/nQEJ6fa-AOUAe3jg3sOpVaGWY1f7u27-SzfyWCrgykg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: dcae653e-62c6-4cc8-84e6-ee110b848296id: e38cbddc-1633-4cd5-bed5-9f289f2a6029id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1057
ht-degree: 0%

---

# Rapporti sulle conversioni

Una &quot;conversione&quot; è un’azione eseguita da un visitatore sul sito e tradotta direttamente negli indicatori chiave della tua organizzazione. I rapporti sulle conversioni mostrano i dettagli sulla conversione dei visitatori.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di Analysis Workspace. Se non conosci ancora lo strumento in Analysis Workspace, consulta [Creare un report di base in Adobe Analytics per gli utenti di Google Analytics](create-report.md).

## Rapporti sugli obiettivi

Gli obiettivi forniscono agli utenti di Google Analytics un modo per definire la conversione di un sito web. Sono il modo predefinito per creare funnel, invertire il flusso comportamentale, funnel multicanale e attribuzione. Gli obiettivi in Google Analytics non sono retroattivi e possono essere impostati solo sulla pagina di amministrazione. Inoltre, si basano solo su una pagina, un evento, il tempo trascorso o il numero medio di pagine.

In Adobe Analytics, il concetto di obiettivo non è necessario perché le metriche possono essere applicate in qualsiasi contesto. Se l’implementazione soddisfa gli eventi da monitorare, puoi modificare qualsiasi rapporto di conversione e ottenere immediatamente i risultati per i dati storici.

### Visualizzazione funnel

Il rapporto di visualizzazione di funnel consente agli analisti di concentrarsi su una particolare serie di passaggi necessari per la conversione. Ad esempio, prima di effettuare un acquisto, un visitatore su un sito di e-commerce deve accedere al carrello, alla pagina di fatturazione e spedizione, alla pagina di pagamento e alla pagina di revisione dell’ordine.

In Analysis Workspace, questi dati possono essere visualizzati utilizzando la Visualizzazione di fallout.

1. Fai clic sull’icona delle visualizzazioni a sinistra, quindi trascina una visualizzazione Fallout nell’area di lavoro sopra la tabella a forma libera
2. Fai clic sull&#39;icona dei componenti a sinistra, quindi individua la dimensione **Pagine**.
3. Fai clic sull’icona a forma di freccia accanto alla dimensione Pagine per visualizzare i valori della pagina. Gli elementi di Dimension sono di colore giallo.
4. Individua la pagina desiderata come primo punto di contatto e trascinala nello spazio etichettato &quot;Aggiungi punto di contatto&quot; nella visualizzazione.
5. Continua ad aggiungere i punti di contatto desiderati trascinando i valori di pagina nella visualizzazione.

La visualizzazione Abbandono non è limitata alla sola dimensione Pagine. Qualsiasi dimensione, metrica o segmento può essere utilizzato per adattare il rapporto di fallout in base alle esigenze della tua organizzazione.

![Visualizzazione Abbandono](/help/technotes/ga-to-aa/assets/fallout.png)

## Rapporti di e-commerce

I rapporti di e-commerce vengono generalmente utilizzati dai siti che vendono prodotti o servizi per misurare gli ordini e i ricavi relativi agli articoli acquistati. Questa funzione è disponibile in Adobe Analytics ed è nota come rapporti sui prodotti.

Sia i rapporti di e-commerce in Google Analytics che i rapporti sui prodotti in Adobe Analytics richiedono modifiche di implementazione personalizzate da utilizzare. Per ulteriori informazioni, consulta la dimensione [Prodotti](/help/components/dimensions/product.md) nella guida utente dei Componenti.

## Rapporti Funnel multicanale

I rapporti multicanale funnel forniscono dati di canale di marketing aggiuntivi oltre a quelli forniti dai rapporti di acquisizione. Questi rapporti si concentrano sulla conversione dei visitatori, anziché sul modo in cui i visitatori arrivano al sito.

>[!NOTE]
>
> L’utilizzo dei rapporti multicanale in Adobe Analytics richiede sia la configurazione di Canali di marketing sia un’implementazione personalizzata per contenere la variabile dei prodotti e l’evento di acquisto. Adobe consiglia di collaborare con un consulente per l’implementazione se queste funzioni non sono ancora configurate per la suite di rapporti.

### Multicanale - Conversioni assistite

Conversioni assistite mostra quante volte ogni canale ha assistito con una conversione. In Analysis Workspace è possibile utilizzare la metrica **Order Assists**.

1. Nel menu Componenti, individua la dimensione **Canale di marketing** e trascinala nella grande area della tabella a forma libera con l&#39;etichetta &#39;Rilascia qui un Dimension&#39;.
2. Trascina la metrica **Risorse ordine** sopra l&#39;intestazione della metrica **Occorrenze** creata automaticamente per sostituirla. Se necessario, puoi trascinare ulteriori metriche nell’area di lavoro.

### Multicanale - Percorsi di conversione principali

Il rapporto percorsi di conversione principali mostra i percorsi di canale principali seguiti da un utente prima della conversione. Analysis Workspace utilizza un rapporto di flusso per visualizzare i percorsi di conversione principali.

1. Fai clic sull’icona Pannelli a sinistra, quindi trascina un pannello Attribuzione sopra la tabella a forma libera.
2. Fai clic sull&#39;icona Componenti a sinistra, individua la dimensione **Canale di marketing** e trascinala nella casella denominata &#39;Aggiungi Dimension&#39;.
3. Individua l’evento di conversione desiderato in Metriche (ad esempio Ordini) e trascinalo nella casella &quot;Aggiungi metrica&quot;. Le metriche calcolate non sono supportate per il pannello Attribuzione.
4. Fai clic su Genera.
5. Nel rapporto risultante, individua la visualizzazione &quot;Flusso canale&quot;. Questo flusso mostra i percorsi principali che un visitatore ha toccato prima di un acquisto.

Questa visualizzazione del flusso è interattiva. Fare clic su ciascun canale per espandere il flusso in entrambe le direzioni.

![Visualizzazione flusso](/help/technotes/ga-to-aa/assets/flow.png)

### Multicanale - Ritardo

Il rapporto ritardo mostra la quantità di tempo, in giorni, necessaria per la conversione di un visitatore sul sito. In Analysis Workspace, questi dati sono disponibili utilizzando la dimensione **Giorni prima del primo acquisto**. È disponibile solo nel contesto di un evento di acquisto implementato correttamente.

1. Nel menu Componenti, individua la dimensione **Giorni prima del primo acquisto** e trascinala nella grande area della tabella a forma libera denominata &#39;Rilascia qui un Dimension&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Adobe consiglia di utilizzare le metriche **Ordini**, **Unità** o **Ricavi** con questa dimensione.

Per altri tipi di conversioni, inclusi gli eventi personalizzati, è disponibile la dimensione **Tempo precedente all&#39;evento**. Mostra la quantità di tempo, in minuti, impiegata da un visitatore per attivare l’evento all’interno della visita.

1. Nel menu Componenti, individua la dimensione **Tempo precedente all&#39;evento** e trascinala nella grande area della tabella a forma libera con l&#39;etichetta &#39;Rilascia qui un Dimension&#39;.
2. Trascina le metriche desiderate nell&#39;area di lavoro insieme alla metrica **Occorrenze** creata automaticamente. Per informazioni dettagliate su come ottenere ciascuna metrica, consulta la [guida alla traduzione delle metriche](common-metrics.md).

Adobe consiglia di utilizzare questa dimensione insieme a eventi personalizzati o eventi di acquisto.

### Multicanale - Lunghezza percorso

Il rapporto sulla lunghezza del percorso mostra il numero di canali toccati prima di un evento di conversione. In Analysis Workspace, il pannello Attribuzione contiene questi dati in una delle sue visualizzazioni.

1. Fai clic sull’icona Pannelli a sinistra, quindi trascina un pannello Attribuzione sopra la tabella a forma libera
2. Fai clic sull&#39;icona Componenti a sinistra, individua la dimensione **Canale di marketing** e trascinala nella casella denominata &#39;Aggiungi Dimension&#39;.
3. Individua l’evento di conversione desiderato in Metriche (ad esempio Ordini) e trascinalo nella casella &quot;Aggiungi metrica&quot;. Le metriche calcolate non sono supportate per il pannello Attribuzione.
4. Fai clic su Genera.
5. Nel rapporto risultante, individua la visualizzazione &quot;Punti di contatto al Percorso&quot;. Questo istogramma mostra il numero di canali toccati da un visitatore prima di un acquisto.
