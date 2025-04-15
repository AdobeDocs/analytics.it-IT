---
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '2353'
ht-degree: 35%

---
# Snippet

## Report Builder legacy {#legacy-arb}

>[!IMPORTANT]
>
>Una nuova e semplificata [Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview) è stata rilasciata il 16 ottobre 2024. È supportato su Mac, Windows e browser web.
>Questa versione del componente aggiuntivo Legacy Report Builder funziona ancora. È possibile [convertire le cartelle di lavoro](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) legacy al nuovo Report Builder.

## Annuncio sulla fine del ciclo di vita di Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>A decorrere dal **17 gennaio 2024**, Adobe ha interrotto Reports &amp; Analytics e i relativi rapporti e funzioni. In quel momento Reports &amp; Analytics e tutti i suoi rapporti e pianificazioni cessarono di funzionare. I rapporti, le visualizzazioni e la tecnologia alla base di Reports &amp; Analytics non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di Reports &amp; Analytics sono disponibili in Analysis Workspace. Per informazioni, vedere [Utilizzare i modelli](/help/analyze/analysis-workspace/templates/use-templates.md).
> 
>Dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di Reports &amp; Analytics sono state spostate in Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. Questo avviso spiega il processo di fine del ciclo di vita.
>
>Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://www.adobe.com/go/analytics_rnaeol_it) di Reports &amp; Analytics.

## Opzioni di ordinamento dei componenti {#components-sort-options}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Consigliato**] | Ordina i componenti a partire da quelli consigliati. I componenti utilizzati più di frequente e più di recente da te o da altri nella tua organizzazione vengono visualizzati più in alto nell’elenco. |
| [!UICONTROL **Alfabetico**] | Ordina alfabeticamente i componenti. |
| [!UICONTROL **Per categorie**] | Ordina i componenti in base al tipo (dimensione, metrica, segmento, intervallo di date). |

{style="table-layout:auto"}

## Fase di test del rilascio {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

## Sezione della fase di test del rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Adobe Analytics](/help/release-notes/releases.md).


## Esclusione di responsabilità del plug-in {#plug-in}

>[!IMPORTANT]
>
>Questo plug-in è fornito a titolo di cortesia da Adobe Consulting per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, per la sua installazione né per la risoluzione di problemi. Se hai bisogno di aiuto con questo plug-in, contatta il team dell’account Adobe della tua organizzazione. Il team può organizzare una riunione con un consulente per l’assistenza.


## Disponibile solo per i clienti esistenti {#available-existing-customers}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione è disponibile solo per i clienti esistenti che dispongono già di una licenza per la funzionalità. La funzionalità non viene più offerta come componente aggiuntivo aggiuntivo ai clienti esistenti o nuovi.
>



## Modelli di attribuzione {#attribution-models-details}

Un modello attribuzione determina quali elementi di dimensione ottengono il credito per una metrica quando vengono visualizzati più valori all&#39;interno dell&#39;intervallo di lookback di una metrica. I modelli di attribuzione si applicano solo quando nell’intervallo di lookback sono impostati più elementi dimensionali. Se è impostato un solo elemento dimensionale, a tale elemento viene assegnato un credito del 100% indipendentemente dal modello di attribuzione utilizzato.

| Icona | Modello di attribuzione | Definizione |
| :---: | :--- | --- |
| ![Ultimo contatto](/help/assets/icons/AttributeLastTouch.svg) | Ultimo contatto | Attribuisce un credito del 100% al punto di contatto che si verifica più di recente prima della conversione. Questo modello di attribuzione è in genere il valore predefinito per qualsiasi metrica in cui un modello di attribuzione non è specificato altrimenti. In genere, le organizzazioni utilizzano questo modello quando il tempo di conversione è relativamente breve, ad esempio con l’analisi delle parole chiave di ricerca interne. |
| ![Primo contatto](/help/assets/icons/AttributeFirstTouch.svg) | Primo contatto | Attribuisce un credito del 100% al punto di contatto visualizzato per la prima volta nell’intervallo di lookback dell’attribuzione. Le organizzazioni utilizzano in genere questo modello per comprendere notorietà del brand o acquisizione clienti. |
| ![Lineare](/help/assets/icons/AttributeLinear.svg) | Lineare | Attribuisce lo stesso credito a ogni punto di contatto che porta a una conversione. È utile quando i cicli di conversione sono più lunghi o richiedono un coinvolgimento più frequente dei clienti. Le organizzazioni in genere utilizzano questo modello attribuzione per misurare l&#39;efficacia delle app mobili notifica o con prodotti basati su abbonamento. |
| ![Partecipazione](/help/assets/icons/AttributeParticipation.svg) | Partecipazione | Assegna il 100% di credito a tutti i punti di contatto univoci. Poiché ogni punto di contatto riceve un credito del 100%, i dati delle metriche in genere superano il 100%. Se un elemento dimensionale appare più volte separatamente, portando a una conversione, i valori vengono deduplicati al 100%. Questo modello di attribuzione è ideale nelle situazioni in cui desideri comprendere a quali punti di contatto i clienti sono più esposti. Le organizzazioni di media in genere utilizzano questo modello per calcolare la velocità dei contenuti. Le organizzazioni di vendita al dettaglio in genere utilizzano questo modello per comprendere quali parti del sito sono fondamentali per la conversione. |
| ![Stesso contatto](/help/assets/icons/AttributeSameTouch.svg) | Stesso contatto | Attribuisce un credito del 100% allo stesso evento in cui si è verificata la conversione. Se un punto di contatto non si verifica nello stesso evento di una conversione, viene inserito in &quot;None&quot;. A volte questo modello di attribuzione viene equiparato all’assenza totale di un modello di attribuzione. È utile negli scenari in cui non desideri valori da altri eventi che influiscono sul modo in cui una metrica attribuisce credito agli elementi dimensionali. I team di prodotto o di progettazione possono utilizzare questo modello per valutare l’efficacia di una pagina in cui si verifica una conversione. |
| ![U a forma di](/help/assets/icons/AttributeUShaped.svg) | A forma di U | Attribuisce il 40% di credito alla prima interazione, il 40% di credito all’ultima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato un credito del 50% a entrambi. Questo modello attribuzione è utilizzato al meglio negli scenari in cui si apprezzano maggiormente la prima e l&#39;ultima interazione, ma non si desidera ignorare completamente ulteriori interazioni intermedie. |
| ![Curva a J](/help/assets/icons/AttributeJCurve.svg) | Curva J | Attribuisce il 60% di credito all’ultima interazione, il 20% di credito alla prima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito all’ultima interazione e il 25% di credito alla prima. Simile al modello a forma di U, questo modello di attribuzione favorisce la prima e l’ultima interazione, ma favorisce in modo più significativo l’ultima interazione. |
| ![J inversa](/help/assets/icons/AttributeInverseJ.svg) | J inversa | Attribuisce un credito del 60% al primo punto di contatto, un credito del 20% all’ultimo punto di contatto e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito alla prima interazione e il 25% di credito all’ultima. Simile al modello a forma di J, questo modello di attribuzione favorisce la prima e l’ultima interazione, ma favorisce in modo più significativo la prima interazione. |
| ![Decadimento nel tempo](/help/assets/icons/AttributeTimeDecay.svg) | Decadimento nel tempo | Segue un decadimento esponenziale con un parametro di mezza durata personalizzato, dove il valore predefinito è 7 giorni. Il valore di ciascun canale dipende dalla quantità di tempo trascorsa tra l’avvio del punto di contatto e l’eventuale conversione. La formula utilizzata per determinare il credito è `2^(-t/halflife)`, dove `t` è il tempo tra un punto di contatto e una conversione. Tutti i punti di contatto vengono quindi normalizzati al 100%. Ideale per scenari in cui desideri misurare l’attribuzione rispetto a un evento specifico e significativo. Più si verifica una conversione dopo questo evento, meno credito viene assegnato. |
| ![Personalizzato](/help/assets/icons/AttributeCustom.svg) | Personalizzato | Consente di specificare i valori da assegnare al primo punto di contatto, all&#39;ultimo punto di contatto e a eventuali punti di contatto intermedi. I valori specificati vengono normalizzati al 100% anche se la somma dei numeri personalizzati immessi è inferiore a 100. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le interazioni con due punti di contatto, il parametro intermedio viene ignorato. Il primo e l’ultimo punto di contatto vengono quindi normalizzati al 100% e il credito viene assegnato di conseguenza. Questo modello è ideale per gli analisti che desiderano un controllo completo sul proprio modello di attribuzione e hanno esigenze specifiche che altri modelli di attribuzione non soddisfano. |
| ![Algoritmica](/help/assets/icons/AttributeAlgorithmic.svg) | Algoritmico | Utilizza tecniche statistiche per determinare in modo dinamico l’allocazione ottimale del credito per la metrica selezionata. L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (che prende il nome da Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.<br>Ad alto livello, l&#39;attribuzione viene calcolata come una coalizione di giocatori a cui deve essere equamente distribuito un surplus. La distribuzione del surplus di ciascuna coalizione è determinata in base al surplus creato in precedenza da ogni subcoalizione (o dagli elementi dimensionali partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli, vedi gli articoli originali di John Harsanyi e Lloyd Shapley:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Intervallo di lookback per l&#39;attribuzione {#attribution-lookback-window}

Per intervallo di lookback si intende la quantità di tempo che una conversione deve recuperare nel passato per includere i punti di contatto. Se un elemento dimensione è impostato all’esterno dell’intervallo di lookback, il valore non viene incluso in alcun calcolo di attribuzione.

* **14 giorni**: cerca fino a 14 giorni dal momento in cui si è verificata la conversione.
* **30 giorni**: cerca fino a 30 giorni da quando si è verificata la conversione.
* **60 giorni**: cerca fino a 60 giorni da quando si è verificata la conversione.
* **90 giorni**: cerca fino a 90 giorni dal momento in cui si è verificata la conversione.
* **Visita**: considera fino l&#39;inizio della visita in cui si è verificata una conversione.
* **Visitatore (intervallo di reporting)**: esamina tutte le visite fino al primo del mese dell&#39;intervallo di date corrente. Ad esempio, se l’intervallo di date del rapporto è dal 15 settembre al 30 settembre, l’intervallo di date del lookback su visitatore includerà il periodo dal 1° al 30 settembre. Se utilizzi questo intervallo di lookback, puoi notare occasionalmente che gli elementi dimensionali sono attribuiti a date al di fuori dell’intervallo di reporting.
* **Ora personalizzata:** consente di impostare un intervallo di lookback personalizzato da quando si è verificata una conversione. È possibile specificare il numero di minuti, ore, giorni, settimane, mesi o trimestri. Ad esempio, se si verificasse una conversione il 20 febbraio, un intervallo di lookback di cinque giorni valuterebbe tutti i punti di contatto delle dimensioni dal 15 febbraio al 20 febbraio nel modello di attribuzione.

## Esempio di attribuzione {#attribution-example}

Prendi in considerazione l’esempio seguente:

1. Il 15 settembre, una persona arriva sul tuo sito attraverso un annuncio ricerca a pagamento, poi se ne va.
1. Il 18 settembre, la persona arriva di nuovo sul tuo sito attraverso un social media collegare ha ricevuto da un amico. Aggiunge diversi articoli al carrello, ma non acquista nulla.
1. Il 24 settembre, il team marketing gli invia un’e-mail con un coupon da utilizzare su alcuni degli elementi nel carrello. Applica il coupon, ma visita diversi altri siti per vedere se sono disponibili altri coupon. Ne trova un altro tramite un annuncio pubblicitario, quindi completa un acquisto dal valore di 50 $.

A seconda dell’intervallo di lookback e del modello di attribuzione definiti, ai canali saranno assegnati crediti diversi. Di seguito sono riportati alcuni esempi:

* Utilizzando **il primo contatto** e un intervallo di lookback di **sessione**, l&#39;attribuzione considera solo la terza visita. Tra e-mail e visualizzazione, e-mail è avvenuta prima, quindi e-mail ottiene 100% di credito per l’acquisto di 50 $.

* Utilizzando **il primo contatto** e un intervallo di lookback di **persona**, l&#39;attribuzione esamina tutte e tre le visite. La ricerca a pagamento è avvenuta prima, quindi ottiene il 100% di credito per l’acquisto di 50 $.

* Utilizzando **linear** e un intervallo di lookback di **sessione**, il credito è suddiviso tra e-mail e visualizzazione. Entrambi questi canali ricevono un credito di 25 $.
Utilizzando **linear** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Ogni canale ottiene un credito di 12,50 $ per questo acquisto.

* Utilizzando **a forma di J** e un intervallo di lookback di **persona**, il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione.

   * Il 60% di credito è assegnato alla visualizzazione, per un valore di 30 $.
   * Il 20% di credito è assegnato alla ricerca a pagamento, per un valore di 10 $.
   * Il restante 20% è suddiviso tra social e e-mail, ovvero 5 $ ciascuno.

* Utilizzando **il decadimento** temporale e l&#39;intervallo **di lookback di una** persona, il credito viene suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Utilizzando la mezza durata predefinita di 7 giorni:

   * Intervallo di zero giorni tra il punto di contatto di visualizzazione e la conversione. `2^(-0/7) = 1`
   * Intervallo di zero giorni tra l&#39;punto di contatto e-mail e la conversione. `2^(-0/7) = 1`
   * Intervallo di sei giorni tra il punto di contatto social e la conversione. `2^(-6/7) = 0.552`
   * Intervallo di nove giorni tra il punto di contatto ricerca a pagamento e la conversione. `2^(-9/7) = 0.41`
   * La normalizzazione di questi valori determina quanto segue:

      * Visualizzazione: 33,8%, ovvero 16,88 $
      * E-mail: 33,8% ovvero 16,88 $
      * Social: 18,6%, ovvero 9,32 $
      * Ricerca a pagamento: 13,8%, ovvero 6,92 $

Gli eventi di conversione che in genere hanno numeri interi vengono suddivisi se il credito appartiene a più di un canale. Ad esempio, se due canali contribuiscono a un ordine utilizzando un modello di attribuzione lineare, entrambi i canali ottengono 0,5 di tale ordine. Queste metriche parziali vengono sommate tra tutte le persone e quindi arrotondate al numero intero più vicino per il reporting.

## Confronti nella visualizzazione percorso {#journey-visualization-comparisons}

Varie visualizzazioni nell’analisi del Percorso di clienti sono progettate per analizzare i percorsi forniti ai clienti.

Utilizza le seguenti informazioni per scegliere la visualizzazione che meglio soddisfa le tue esigenze.

| Funzione | Area di lavoro percorso | Fallout (abbandono) | Flusso |
|---------|----------|---------|---------|
| **Sequenza di pagine predefinita** | Sì</br>Combina analisi predefinite ed esplorative. Il percorso finale viene utilizzato quando si utilizzano nodi predefiniti sul percorso (i visitatori vengono conteggiati purché passino infine da un nodo predefinito all’altro). È inoltre possibile visualizzare i nodi successivi immediati (non finali). | Sì</br>Il percorso può essere un percorso finale o essere vincolato al punto di contatto successivo | No |
| **Sequenza esplorativa di pagine (analisi ad hoc)** | Sì</br>Combina analisi predefinite ed esplorative. Il percorso finale viene utilizzato quando si utilizzano nodi predefiniti sul percorso (i visitatori vengono conteggiati purché passino infine da un nodo predefinito all’altro). È inoltre possibile visualizzare i nodi successivi immediati (non finali). | Limitato</br>Consente di fare clic con il pulsante destro del mouse e visualizzare l&#39;abbandono immediato in una tabella a forma libera. | Sì</br>Solo analisi esplorativa. Sempre all’interno di un’istanza della dimensione tra nodi. Ciò significa che ogni nodo mostra il punto di contatto successivo immediato (non finale) lungo il percorso. |
| **Mostra dove le persone hanno lasciato (abbandonato) e continuato (proseguito)** | Sì</br>Mostra per percorsi predefiniti ed esplorativi | Sì</br>Mostra percorsi predefiniti | Sì</br>Mostra per percorsi esplorativi |
| **percorsi lineari** | Sì | Sì | No |
| **percorsi non lineari con più punti di ingresso e percorsi** | Sì | No | Sì |
| **Metrica primaria** | Qualsiasi metrica, comprese quelle calcolate | Solo sessione o persona | Solo occorrenze (viste di percorso) |
| **Metrica secondaria** | Sì<p>Qualsiasi metrica, incluse le metriche calcolate</p> | No | No |
| **Supporto dei componenti nei nodi o nei punti di contatto** | Metriche, elementi dimensionali, filtri e intervalli di date. | Metriche, elementi dimensionali, filtri e intervalli di date. | Solo elementi dimensionali (ad eccezione del punto di contatto iniziale e finale) |
| **Confronta filtri** | No | Sì<p>Eseguire confronti affiancati di due diversi filtri nello stesso rapporto</p> | No |
| **Interazione dei componenti tramite trascinamento** | Sì | Sì | No |
| **percorsi Adobe Journey Optimizer** | Sì</br>Apri percorsi da Journey Optimizer per analisi più approfondite e personalizzazione | No | No |

{style="table-layout:auto"}
