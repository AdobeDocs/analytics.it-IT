---
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '2947'
ht-degree: 88%

---
# Snippet

## Report Builder legacy {#legacy-arb}

>[!IMPORTANT]
>
>Una nuova versione semplificata di [Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview) è stata rilasciata il 16 ottobre 2024. È supportato su Mac, Windows e browser web.
>>Questa versione legacy del componente aggiuntivo Report Builder funziona ancora. È possibile [convertire le cartelle di lavoro legacy](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) nella nuova Report Builder.

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
>La funzionalità descritta in questa sezione è disponibile solo per i clienti esistenti che dispongono già di una licenza per tale funzionalità. Questa funzionalità non viene più offerta come componente aggiuntivo per clienti nuovi o esistenti.
>



## Modelli di attribuzione {#attribution-models-details}

Un modello di attribuzione determina quali elementi dimensionali ricevono credito per una metrica quando vengono visualizzati più valori nell’intervallo di lookback di una metrica. I modelli di attribuzione si applicano solo quando nell’intervallo di lookback sono impostati più elementi dimensionali. Se è impostato un solo elemento dimensionale, a tale elemento viene assegnato un credito del 100% indipendentemente dal modello di attribuzione utilizzato.

| Icona | Modello di attribuzione | Definizione |
| :---: | :--- | --- |
| ![Ultimo contatto](/help/assets/icons/AttributeLastTouch.svg) | Ultimo contatto | Attribuisce un credito del 100% al punto di contatto più recente che si verifica prima della conversione. Questo modello di attribuzione è in genere il valore predefinito per qualsiasi metrica in cui un modello di attribuzione non è specificato diversamente. In genere, le organizzazioni utilizzano questo modello quando il tempo di conversione è relativamente breve, ad esempio con l’analisi delle parole chiave di ricerche interne. |
| ![Primo contatto](/help/assets/icons/AttributeFirstTouch.svg) | Primo contatto | Attribuisce un credito del 100% al punto di contatto visualizzato per la prima volta nell’intervallo di lookback dell’attribuzione. In genere, le organizzazioni utilizzano questo modello per comprendere la consapevolezza del brand o l’acquisizione della clientela. |
| ![Lineare](/help/assets/icons/AttributeLinear.svg) | Lineare | Attribuisce lo stesso credito a ogni punto di contatto che porta a una conversione. È utile quando i cicli di conversione sono più lunghi o richiedono un coinvolgimento più frequente della clientela. In genere le organizzazioni utilizzano questo modello di attribuzione per misurare l’efficacia delle notifiche delle app mobili o con prodotti basati su abbonamento. |
| ![Partecipazione](/help/assets/icons/AttributeParticipation.svg) | Partecipazione | Assegna il 100% di credito a tutti i punti di contatto univoci. Poiché ogni punto di contatto riceve un credito del 100%, i dati delle metriche in genere superano il 100%. Se un elemento dimensionale appare più volte separatamente, portando a una conversione, i valori vengono deduplicati al 100%. Questo modello di attribuzione è ideale nelle situazioni in cui desideri comprendere a quali punti di contatto la clientela è esposta maggiormente. Le società di comunicazioni generalmente utilizzano questo modello per calcolare la velocità del contenuto. Le società di commercio al dettaglio generalmente usano questo modello per capire quali parti del sito sono fondamentali per la conversione. |
| ![Stesso contatto](/help/assets/icons/AttributeSameTouch.svg) | Stesso contatto | Attribuisce un credito del 100% allo stesso evento in cui si è verificata la conversione. Se un punto di contatto non si verifica sullo stesso evento di una conversione, viene inserito in “Nessuno”. A volte questo modello di attribuzione viene equiparato all’assenza totale di un modello di attribuzione. È utile negli scenari in cui non desideri valori da altri eventi che influiscono sul modo in cui una metrica attribuisce credito agli elementi dimensionali. I team che si occupano di prodotti o design possono utilizzare questo modello per valutare l’efficacia di una pagina in cui si verifica una conversione. |
| ![A forma di U](/help/assets/icons/AttributeUShaped.svg) | A forma di U | Attribuisce il 40% di credito alla prima interazione, il 40% di credito all’ultima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto viene assegnato un credito del 50% a ciascuno. Questo modello di attribuzione funziona al meglio negli scenari in cui attribuisci il maggior valore alla prima e all’ultima interazione, ma non desideri escludere completamente ulteriori interazioni intermedie. |
| ![Curva J](/help/assets/icons/AttributeJCurve.svg) | Curva J | Attribuisce il 60% di credito all’ultima interazione, il 20% di credito alla prima interazione e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito all’ultima interazione e il 25% di credito alla prima. Simile al modello a forma di U, questo modello di attribuzione favorisce la prima e l’ultima interazione, ma dà credito in modo più significativo all’ultima interazione. |
| ![J inversa](/help/assets/icons/AttributeInverseJ.svg) | J inversa | Attribuisce un credito del 60% al primo punto di contatto, un credito del 20% all’ultimo punto di contatto e divide il restante 20% in qualsiasi punto di contatto intermedio. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le conversioni con due punti di contatto, viene assegnato il 75% di credito alla prima interazione e il 25% di credito all’ultima. Simile al modello a forma di J, questo modello di attribuzione favorisce la prima e l’ultima interazione, ma dà credito in modo più significativo alla prima interazione. |
| ![Decadimento nel tempo](/help/assets/icons/AttributeTimeDecay.svg) | Decadimento nel tempo | Segue un decadimento esponenziale con un parametro di mezza durata personalizzato, dove il valore predefinito è 7 giorni. Il valore di ciascun canale dipende dalla quantità di tempo trascorsa tra l’avvio del punto di contatto e l’eventuale conversione. La formula utilizzata per determinare il credito è `2^(-t/halflife)`, dove `t` è il tempo tra un punto di contatto e una conversione. Tutti i punti di contatto vengono quindi normalizzati al 100%. Ideale per scenari in cui desideri misurare l’attribuzione rispetto a un evento specifico e significativo. Più tempo passa perché si verifichi una conversione dopo un evento di marketing, meno credito viene assegnato. |
| ![Personalizzato](/help/assets/icons/AttributeCustom.svg) | Personalizzato | Consente di specificare i pesi da assegnare al primo punto di contatto, all’ultimo punti di contatto e a eventuali punti di contatto intermedi. I valori specificati vengono normalizzati al 100% anche se la somma dei numeri personalizzati immessi è inferiore a 100. Per le conversioni con un singolo punto di contatto, viene assegnato un credito del 100%. Per le interazioni con due punti di contatto, il parametro intermedio viene ignorato. Il primo e l’ultimo punto di contatto vengono quindi normalizzati al 100% e il credito viene assegnato di conseguenza. Questo modello è ideale per gli analisti che desiderano avere pieno controllo sul proprio modello di attribuzione e che hanno esigenze specifiche che altri modelli di attribuzione non soddisfano. |
| ![Algoritmico](/help/assets/icons/AttributeAlgorithmic.svg) | Algoritmico | Utilizza tecniche statistiche per determinare in modo dinamico l’allocazione ottimale del credito per la metrica selezionata. L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (che prende il nome da Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.<br>Ad alto livello, l’attribuzione viene calcolata come una coalizione di giocatori tra i quali deve essere equamente distribuito un surplus. La distribuzione del surplus di ciascuna coalizione è determinata in base al surplus creato in precedenza da ogni sub-coalizione (o dagli elementi dimensionali partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli, vedi gli articoli originali di John Harsanyi e Lloyd Shapley:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Contenitore attribuzione {#attribution-container}

Un contenitore attribuzione definisce l’ambito desiderato per l’attribuzione. Le opzioni possibili sono:

* **Visita**: esamina le conversioni dall&#39;ambito del contenitore Visita.
* **Visitatore**: esamina le conversioni dall&#39;ambito del contenitore visitatore.

## Finestra di lookback di attribuzione {#attribution-lookback-window}

Per intervallo di lookback si intende la quantità di tempo che una conversione deve esaminare in precedenza per includere i punti di contatto. Se un elemento dimensionale è impostato all’esterno dell’intervallo di lookback, il valore non viene incluso in alcun calcolo di attribuzione.

* **14 giorni**: esamina fino a 14 giorni precedenti dal momento in cui si è verificata la conversione.
* **30 giorni**: esamina fino a 30 giorni precedenti dal momento in cui si è verificata la conversione.
* **60 giorni**: esamina fino a 60 giorni precedenti dal momento in cui si è verificata la conversione.
* **90 giorni**: esamina fino a 90 giorni precedenti dal momento in cui si è verificata la conversione.
* **Orario personalizzato:** consente di impostare un intervallo di lookback personalizzato da quando si è verificata una conversione. È possibile specificare il numero di minuti, ore, giorni, settimane, mesi o trimestri. Ad esempio, per una conversione che si verifica il 20 febbraio, un intervallo di lookback di cinque giorni valuterebbe tutti i punti di contatto dimensionali dal 15 al 20 febbraio nel modello di attribuzione.

## Esempio di attribuzione {#attribution-example}

Prendi in considerazione l’esempio seguente:

1. Il 15 settembre, un visitatore arriva sul tuo sito tramite un annuncio pubblicitario di ricerca a pagamento, poi se ne va.
1. Il 18 settembre, il visitatore ritorna sul tuo sito tramite un collegamento social media ricevuto da un amico. Aggiunge diversi articoli al carrello, ma non acquista nulla.
1. Il 24 settembre, il team marketing gli invia un’e-mail con un coupon da utilizzare su alcuni degli elementi nel carrello. Applica il coupon, ma visita diversi altri siti per vedere se sono disponibili altri coupon. Ne trova un altro tramite un annuncio pubblicitario, quindi completa un acquisto dal valore di 50 $.

A seconda del modello di attribuzione, il contenitore e i canali ricevono un credito diverso. Consulta la tabella seguente per gli esempi:

| Modello | Contenitore | Intervallo di lookback | Spiegazione |
|---|---|---|---|
| Primo contatto | Visita | 30 giorni | L’attribuzione esamina solo la terza visita. Tra e-mail e visualizzazione, l’e-mail è avvenuta prima, quindi l’e-mail ottiene il 100% di credito per l’acquisto di 50 $. |
| Primo contatto | Visitatore | 30 giorni | L’attribuzione esamina tutte e tre le visite. La ricerca a pagamento è avvenuta prima, quindi ottiene il 100% di credito per l’acquisto di 50 $. |
| Lineare | Visita | 30 giorni | Il credito è suddiviso tra e-mail e visualizzazione. Entrambi questi canali ricevono un credito di 25 $. |
| Lineare | Visitatore | 30 giorni | Il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione. Ogni canale ottiene un credito di 12,50 $ per questo acquisto. |
| A forma di J | Visitatore | 30 giorni | Il credito è suddiviso tra ricerca a pagamento, social, e-mail e visualizzazione.<ul><li>Il 60% di credito è assegnato alla visualizzazione, per un valore di 30 $.</li><li>Il 20% di credito è assegnato alla ricerca a pagamento, per un valore di 10 $.</li><li>Il restante 20% è suddiviso tra social e e-mail, ovvero 5 $ ciascuno.</li></ul> |
| Decadimento nel tempo | Visitatore | 30 giorni | <ul><li>Intervallo di 0 giorni tra il punto di contatto visualizzazione e la conversione. `2^(-0/7) = 1`</li><li>Intervallo di 0 giorni tra il punto di contatto e-mail e la conversione. `2^(-0/7) = 1`</li><li>Intervallo di 6 giorni tra il punto di contatto social e la conversione. `2^(-6/7) = 0.552`</li><li>Intervallo di 9 giorni tra il punto di contatto ricerca a pagamento e la conversione. `2^(-9/7) = 0.41`</li>La normalizzazione di questi valori determina quanto segue:<ul><li>Visualizzazione: 33,8%, ovvero 16,88 $</li><li>E-mail: 33,8% ovvero 16,88 $</li><li>Social: 18,6%, ovvero 9,32 $</li><li>Ricerca a pagamento: 13,8%, ovvero 6,92 $</li></ul></li></ul> |

Gli eventi di conversione che in genere hanno numeri interi vengono suddivisi se il credito appartiene a più di un canale. Ad esempio, se due canali contribuiscono a un ordine utilizzando un modello di attribuzione lineare, entrambi i canali ottengono lo 0,5 di tale ordine. Queste metriche parziali vengono sommate tra tutte le persone, quindi arrotondate al numero intero più vicino per la generazione del rapporto.

## Visualizzazioni dei percorsi a confronto {#journey-visualization-comparisons}

Varie visualizzazioni di Customer Journey Analytics sono progettate per analizzare i percorsi forniti ai clienti.

Le seguenti informazioni ti aiuteranno a scegliere la visualizzazione più adatta per le tue esigenze.

| Funzione | Area di lavoro del percorso | Fallout | Flusso |
|---------|----------|---------|---------|
| **Sequenza di pagine predefinita** | Sì</br>Combina analisi predefinite ed esplorative. Il percorso finale viene utilizzato quando si utilizzano nodi predefiniti sul percorso (i visitatori vengono conteggiati purché alla fine passino da un nodo predefinito all’altro). È inoltre possibile visualizzare i nodi successivi immediati (non finali). | Sì</br>Il percorso può essere un percorso finale o essere vincolato al punto di contatto successivo | No |
| **Sequenza di pagine esplorativa (analisi ad hoc)** | Sì</br>Combina l’analisi predefinita ed esplorativa. Il percorso finale viene utilizzato quando si utilizzano nodi predefiniti sul percorso (i visitatori vengono conteggiati purché alla fine passino da un nodo predefinito all’altro). È inoltre possibile visualizzare i nodi successivi immediati (non finali). | Limitato</br>È possibile fare clic con il pulsante destro del mouse per visualizzare il fallout immediato in una tabella a forma libera. | Sì</br>Solo analisi esplorativa. Sempre all’interno di un’istanza di dimensione tra due nodi. Ogni nodo mostra il punto di contatto successivo immediato (non finale) lungo il percorso. |
| **Mostra dove le persone hanno abbandonato (fallout) e continuato (proseguito)** | Sì</br>Mostra per percorsi predefiniti ed esplorativi | Sì</br>Viene mostrato per percorsi predefiniti | Sì</br>Viene mostrato per percorsi esplorativi |
| **Percorsi lineari** | Sì | Sì | No |
| **Percorsi non lineari con più punti di ingresso e percorsi** | Sì | No | Sì |
| **Metrica primaria** | Qualsiasi metrica, comprese quelle calcolate | Solo sessione o persona | Solo occorrenze (visualizzazioni percorso) |
| **Metrica secondaria** | Sì<p>Qualsiasi metrica, comprese quelle calcolate</p> | No | No |
| **Supporto dei componenti nei nodi o nei punti di contatto** | Metriche, elementi dimensionali, filtri e intervalli di date. | Metriche, elementi dimensionali, filtri e intervalli di date. | Solo elementi dimensionali (ad eccezione del punto di contatto iniziale e finale) |
| **Confronta filtri** | No | Sì<p>Eseguire confronti affiancati di due diversi filtri nello stesso rapporto</p> | No |
| **Interazione tramite trascinamento per componenti** | Sì | Sì | No |
| **Percorsi Adobe Journey Optimizer** | Sì</br>Apri percorsi da Journey Optimizer per analisi più approfondite e personalizzazione | No | No |

{style="table-layout:auto"}



## Sezione filtro per tag {#tagfiltersection}

| Tag | Descrizione |
|---|---|
| ![Tag](/help/assets/filter-tag.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare in base ai tag. <ul><li>Puoi usare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca tag* per cercare i tag che puoi utilizzare come filtro.</li><li>Puoi selezionare più di un tag. I tag disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(1)**: numero di tag selezionati (se sono selezionati uno o più tag).</li><li>**2︎⃣**: numero di tag disponibili per gli elementi risultanti dal filtro corrente.</li><li>7︎⃣: numero di elementi associati al tag specifico.</li></ul></li></ul> |


## Sezione filtro suite di rapporti {#reportsuitefiltersection}

| Suite di rapporti | Descrizione |
|---|---|
| ![Ripubblica suite](/help/assets/filter-reportsuite.png){width="300"} | La sezione **[!UICONTROL Report suite]** ti consente di filtrare in base alle suite di rapporti. <ul><li>Puoi ![cercare](/help/assets/icons/Search.svg) *Cerca suite di rapporti* per cercare suite di rapporti che puoi utilizzare per filtrare.</li><li>Puoi selezionare più di una suite di rapporti. Le suite di rapporti disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(2)**: numero di suite di rapporti selezionate (se sono selezionate una o più suite di rapporti).</li><li>**3︎⃣**: numero di suite di rapporti disponibili per gli elementi risultanti dal filtro corrente.</li><li>4︎⃣: numero di elementi associati alla suite di rapporti specifica.</li></ul></li></ul> |

## Sezione filtro di stato abilitato {#enabledstatusfiltersection}

| Stato abilitato | Descrizione |
|---|---|
| ![Stato abilitato](/help/assets/filter-enabledstatus.png){width="300"} | La sezione **[!UICONTROL Enabled status]** consente di filtrare in base allo stato abilitato. <ul><li>Puoi selezionare più di uno stato.</li><li>I numeri indicano:<ul><li>**(2)**: numero di stati selezionati (se sono selezionati uno o più stati).</li><li>**2︎⃣**: numero di stati disponibili per gli elementi risultanti dal filtro corrente.</li><li>1︎⃣: numero di progetti associati allo stato specifico.</li></ul></li></ul> |

## Sezione tipo di filtro {#typefiltersection}

| Tipo | Descrizione |
|---|---|
| ![Tipo](/help/assets/filter-type.png){width="300"} | La sezione **[!UICONTROL Type]** consente di filtrare in base al tipo. <ul><li>Puoi selezionare più di un tipo.</li><li>I numeri indicano:<ul><li>**(2)**: numero di tipi selezionati (se sono selezionati uno o più tipi).</li><li>**1︎⃣**: numero di tipi disponibili per gli elementi risultanti dal filtro corrente.</li><li>3︎⃣: numero di elementi associati al tipo specifico.</li></ul></li></ul> |

## Sezione proprietario filtro {#ownerfiltersection}

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](/help/assets/filter-owners.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca proprietari* per cercare i proprietari da utilizzare per filtrare.</li><li>Puoi selezionare più di un proprietario. I proprietari disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(2)**: numero di proprietari selezionati (se sono selezionati uno o più proprietari).</li><li>**3︎⃣**: numero di proprietari disponibili per gli elementi risultanti dal filtro corrente.</li><li>4︎⃣: Il numero di elementi associati al proprietario specifico.</li></ul></li></ul> |

## Sezione filtro Altri filtri {#otherfiltersfiltersection}

| Altri filtri | Descrizione |
|---|---|
| ![Altri filtri](/help/assets/filter-other.png){width="300"} | La sezione **[!UICONTROL Other filters]** ti consente di filtrare in base ad un altro filtro predefinito.<ul><li>È possibile scegliere una o più delle opzioni seguenti:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> Ciò che puoi selezionare dipende dal tuo ruolo e dalle autorizzazioni.</li><li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**(1)**: numero di altri filtri selezionati (se sono selezionati uno o più altri filtri).</li><li>**5︎⃣**: numero di altri filtri disponibili per gli elementi risultanti dal filtro corrente.</li><li>4︎⃣: Il numero di elementi associati all’altro filtro specifico.</li></ul></li></ul> |

## Sezione filtro Intervallo di date  {#daterangefiltersection}

| Intervallo di date applicato | Descrizione |
|---|---|
| ![Intervallo date](/help/assets/filter-daterange.png){width="300"} | La sezione Intervallo di date applicato consente di filtrare in base a un intervallo di date applicabile agli elementi.<ol><li>Seleziona un intervallo di date.</li><li>Nel pop-up del calendario definisci un intervallo di date o seleziona uno dei predefiniti disponibili.<br>In alternativa, puoi anche specificare un intervallo di date direttamente nella sezione Intervallo date del pannello Filtro.</li></ol><ul><li>I numeri indicano:<ul><li>**(1)**: numero di intervalli di date modificati dai predefiniti preimpostati.</li><li>**5︎⃣**: numero di intervalli di date disponibili per gli elementi risultanti dal filtro corrente.</li></ul> |


## Obsolescenza importazione classificazioni {#classification-importer-deprecation}

>[!WARNING]
>
>L&#39;importazione di classificazioni è obsoleta e non sarà più accessibile dopo il **31 agosto 2026**. Passa all&#39;esperienza [Set di classificazione](/help/components/classifications/sets/overview.md) per garantire la continuità delle funzionalità.
>



## Generatore regole di classificazione obsoleto {#classification-rulebuilder-deprecation}

>[!WARNING]
>
>Il generatore di regole di classificazione è obsoleto e non sarà più accessibile dopo il **31 agosto 2026**. Passa all&#39;esperienza [Set di classificazione](/help/components/classifications/sets/overview.md) per garantire la continuità delle funzionalità.
>

