---
description: nulle
seo-description: nulle
seo-title: Panoramica di Attribuzione IQ
title: Panoramica di Attribuzione IQ
uuid: bb 345642-4 f 45-4 fb 8-82 d 0-803248 dd 52 ea
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica di Attribuzione IQ

>[!IMPORTANT]
>
>L'IQ di attribuzione è disponibile per tutti i clienti negli SKU di Adobe Analytics Ultimate, Prime, Select e Foundation.

## Valore commerciale di Attribution IQ {#section_E82B97114E1641A8AE911F57AEB3240A}

Il “percorso del cliente” non è lineare ed è solo parzialmente prevedibile: è più organico, flessibile e spesso imprevedibile. Ogni cliente procede con il proprio ritmo, spesso tornando indietro, fermandosi, ricominciando e così via. Questo rende difficile conoscere l’impatto effettivo delle attività di marketing lungo il percorso dell’utente. Inoltre ostacola i tentativi di associare più canali di dati per specifiche esigenze commerciali e genera dati incompleti sui clienti.

Attribution IQ di Adobe Analytics consente di comprendere come si verifica un coinvolgimento significativo lungo il percorso del cliente, identificando in modo intelligente i punti di flesso che conducono i clienti verso gli obiettivi desiderati, ottimizzando in modo efficace le attività di marketing.

![](assets/attribution_iq_problem.png)

Adobe Analytics migliora l’attribuzione consentendo di:

* Definire l’attribuzione oltre i mezzi di comunicazione comprati: è possibile applicare ai modelli qualsiasi dimensione, metrica, canale o evento (ad es. ricerca interna), non solo le campagne di marketing.
* Utilizzare il confronto illimitato tra modelli di attribuzione: è possibile confrontare in modo dinamico tanti modelli quanti se ne desiderano.
* Evitare le modifiche di implementazione: con l’elaborazione al momento della generazione del rapporto e le sessioni in base al contesto, è possibile integrare e applicare il contesto del percorso del cliente in fase di esecuzione.
* Costruire la sessione che si adatta al meglio allo scenario di attribuzione.
* Suddividere l’attribuzione in base ai segmenti: è possibile confrontare facilmente le prestazioni dei canali di marketing in qualsiasi segmento importante (ad es. clienti nuovi rispetto a clienti di ritorno, prodotto X rispetto a prodotto Y, livello di fedeltà rispetto a Customer Lifetime Value).
* Ispezionare l’analisi incrociata e a più contatti dei canali: è possibile utilizzare diagrammi di Venn, istogrammi e risultati di attribuzione di tendenze.
* Analizzare visivamente sequenze di marketing principali: è possibile esplorare in modo visivo i percorsi che hanno condotto alla conversione, con visualizzazioni di abbandono e di flusso a più nodi.
* Costruire metriche calcolate: è possibile utilizzare un qualsiasi numero di metodi di allocazione di attribuzione.

## Come funziona Attribution IQ? {#section_63B421E9E75B4CCEBA96726CAA37D73E}

Attribution IQ in Analysis Workspace consente di aggiungere molti nuovi tipi di modelli di attribuzione a tabelle a forma libera, visualizzazioni e metriche calcolate. Tutti i modelli di attribuzione hanno due componenti:

* Un **modello di attribuzione** (ovvero, Primo contatto, Ultimo contatto, Lineare e così via). Il modello descrive la distribuzione delle conversioni negli hit in un gruppo.
* Un **intervallo di lookback di attribuzione** (ovvero, visita o visitatore). L’intervallo di lookback descrive quali gruppi di hit vengono considerati per ogni modello.

Il seguente esempio di percorso del cliente raffigura i punti di contatto di marketing di un singolo visitatore nell’arco di tre visite, tre conversioni e quattro canali di marketing (Ricerca, Visualizzazione, Social ed E-mail):

![](assets/attribution_example.png)

## Attribuzione basata su istanze {#section_A81DBC3B19014CE3894131F1CF72736F}

L’attribuzione in Analysis Workspace utilizza “l’istanza” di una qualsiasi dimensione. I modelli di attribuzione vengono pertanto applicati ai valori trasmessi ad Analytics, dopo le regole di elaborazione, le regole VISTA (Visitor Identification, Segmentation and Transformation Architecture) e le regole di elaborazione dei canali di marketing. Di fatto, ciò significa che non vi è alcuna differenza tra una proprietà o una variabile eVar (o qualsiasi altra dimensione) per quanto riguarda la modellazione dell’attribuzione. È possibile impostare le proprietà per renderle permanenti utilizzando uno qualsiasi degli intervalli di lookback o dei modelli seguenti; le impostazioni di allocazione e scadenza per le variabili eVar non vengono utilizzate (come specificato nelle impostazioni di amministrazione) se vengono applicati l’intervallo di lookback di attribuzione o i modelli.

## Intervallo di lookback di attribuzione {#section_A2782BB64171431EB370CDCD4AD8030D}

L’intervallo di lookback di attribuzione è un gruppo di hit al quale verrà applicato un modello di attribuzione. Sono presenti due impostazioni per gli intervalli di lookback di attribuzione in Analysis Workspace: visita e visitatore.

**Intervallo di lookback per visita**

L’intervallo di lookback per visita per impostazione predefinita è una qualsiasi sequenza di attività separata da 30 minuti di inattività. Tuttavia, se si preferisce modificare tale impostazione predefinita, sono supportate le [sessioni in base al contesto](https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html), tramite l’[elaborazione al momento della generazione del rapporto](https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html). Se si utilizza l’intervallo di lookback di attribuzione per visita all’interno di una suite di rapporti virtuali (VRS) utilizzando una sessione personalizzata, l’intervallo di lookback di attribuzione utilizzerà la definizione personalizzata di visita come base del suo calcolo. Nell’esempio precedente, ogni visita verrebbe considerata come un lookback di attribuzione indipendente.

**Intervallo di lookback per visitatore**

L’intervallo di lookback per visitatore considererà la totalità degli hit di un visitatore all’interno dell’intervallo di reporting del pannello Workspace, con l’aggiunta dei mesi interi che comprendono l’intervallo di reporting. Ad esempio, se l’intervallo di date dell’intervallo di reporting è dal 15 settembre al 30 settembre, l’intervallo di date del lookback per visitatore sarà dal 1° al 30 settembre. Per ulteriori informazioni sull’intervallo di lookback per visitatore, consulta [Visualizzazione di dati al di fuori dell’intervallo di reporting](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html).

**Esempio di intervallo di lookback di attribuzione**

Per illustrare l’impatto degli intervalli di lookback di attribuzione, applicheremo un modello lineare (che attribuisce lo stesso valore a tutti i punti di contatto) all’esempio precedente:

Quando si utilizza l’**intervallo di lookback di attribuzione per visita**, la conversione di ogni visita viene distribuita in modo indipendente:

* Il/$ 10 della prima visita viene suddiviso in modo uniforme tra Ricerca, Visualizzazione, Social ed E-mail, ogni destinatario che riceve/$ 2.50.
* Nella seconda visita, Cerca e invia per e-mail riceverebbe ogni metà della conversione/$ 5, quindi le opzioni E-mail e Ricerca riceveranno un altro/$ 2.50.
* Infine, alla visita finale, l'e-mail riceve tutto il credito per la conversione/$ 2.

Nell’**intervallo di lookback per visitatore**, tutte le conversioni sono considerate insieme, tuttavia il calcolo è leggermente più complesso poiché sono presenti più conversioni.

* La prima conversione di $ 10 viene suddivisa in modo uniforme tra Ricerca, Visualizzazione, Social ed E-mail.
* La conversione secondo/$ 5 verrà quindi suddivisa tra i canali presenti in quella visita e i canali precedenti dalla visita precedente: Cerca = (2/6) */$ 5 =/$ 1.67, Display = (1/6) */$ 5 =/$ 0.83, Social = (1/6) */$ 5 =/$ 0.83, Email = (2/6) */$ 5 =/$ 1.67.
* Infine, l'ultima conversione viene suddivisa in tutti i canali per il visitatore: Cerca = (2/7) */$ 2 =/$ 0.57, Display = (1/7) */$ 2 =/$ 0.29, Social = (1/7) */$ 2 =/$ 0.29, Email = (3/7) */$ 2 =/$ 0.86.

Segue un riepilogo dei risultati sotto forma di tabella:

| Canale | Entrate (lineare/visita) | Revenue (Linear/Visitor) |
|---|---|---|
| Cerca | /$5.00 | /$4.74 |
| Visualizzazione | /$2.50 | /$3.62 |
| Social | /$2.50 | /$3.62 |
| E-mail | /$7.00 | /$5.02 |
| Totale | /$17.00 | /$17.00 |

Questa differenza nell’intervallo di lookback di attribuzione funziona in modo simile con tutti i modelli di attribuzione descritti di seguito.

## Modelli di attribuzione {#section_4B9E7F83AE0B451A992397E55C3F5871}

Analysis Workspace supporta dieci diversi modelli di attribuzione: primo contatto, ultimo contatto, stesso contatto, lineare, a forma di U, curva a J, J inversa, decadimento nel tempo, partecipazione e personalizzato. Di seguito vengono mostrati i dettagli di ciascuno, con relativi esempi:

<table id="table_A3EB34CD52314F0393FF0D12E5F9779D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Icona </th> 
   <th colname="col2" class="entry"> Modello di attribuzione </th> 
   <th colname="col3" class="entry"> Definizione </th> 
   <th colname="col4" class="entry"> Caso di utilizzo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/last_touch.PNG" id="image_7D574182B1564109B0F1C3DD4FD9E8E9" /> </p> </td> 
   <td colname="col2"> <p>Ultimo contatto </p> </td> 
   <td colname="col3"> <p>Il modello Ultimo contatto attribuisce il 100% del valore al punto di contatto che si verifica subito prima della conversione. Nel caso precedente, al canale E-mail verrebbe attribuito l’intero valore di $ 17 in un lookback per visita o per visitatore, poiché è il canale che ha immediatamente preceduto tutte e tre le conversioni. </p> </td> 
   <td colname="col4"> <p>Questo è il modello di attribuzione più semplice e comune e viene utilizzato di frequente per conversioni con un ciclo di considerazione breve. </p> <p>Ultimo contatto viene comunemente utilizzato dai team che gestiscono il marketing di ricerca o che analizzano le parole chiave di ricerca interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/first_touch.png" id="image_D8CD48CB39D64A0386CBA38397BB69B0" /> </p> </td> 
   <td colname="col2"> <p>Primo contatto </p> </td> 
   <td colname="col3"> <p>Il modello Primo contatto attribuisce il 100% del valore al prima punto di contatto nell’intervallo di lookback di attribuzione. </p> <p>Nell’esempio precedente utilizzando il lookback per visita, $ 10 + $ 5 = $ 15 verrebbero attribuiti al canale Ricerca e $ 2 al canale E-mail. Con un lookback per visitatore, l’intero valore di $ 17 verrebbe assegnato al canale Ricerca poiché si è verificato per primo tra tutti gli hit per l’intervallo di reporting in questione. </p> </td> 
   <td colname="col4"> <p>Questo modello di attribuzione è utile per l’analisi dei canali di marketing destinati a generare brand awareness o acquisizione di clienti. </p> <p>Primo contatto viene utilizzato di frequente dai team di display/social marketing ma è ottimo anche per valutare l’efficacia dei prodotti consigliati durante la navigazione nel sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/same_touch.png" id="image_7E093A65BA4048F0B46E1110D9569C84" /> </p> </td> 
   <td colname="col2"> <p>Stesso contatto </p> </td> 
   <td colname="col3"> <p>Il modello Stesso contatto attribuisce il 100% del valore allo specifico hit in corrispondenza del quale si è verificata la conversione. </p> <p>Nell’esempio precedente, ogni conversione si è verificata in corrispondenza di un hit successivo al precedente punto di contatto di marketing, perciò l’intero valore di $ 17 verrebbe assegnato alla voce “Nessuno” nel rapporto. </p> </td> 
   <td colname="col4"> <p>Questo modello è utile quando si valuta l’esperienza utente o il contenuto presentato immediatamente nel momento della conversione. I team che si occupano di prodotti o design utilizzeranno spesso questo modello per valutare l’efficacia di una pagina in cui si verifica una conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/linear.png" id="image_FB96E57837EE47B5B6AE0066CC6DCF45" /> </p> </td> 
   <td colname="col2"> <p>Lineare </p> </td> 
   <td colname="col3"> <p>Il modello Lineare è un modello a più contatti che attribuisce lo stesso valore a ogni hit verificatosi prima di una conversione. </p> <p>Nelle situazioni in cui si verificano più ordini all’interno dello stesso lookback per visita o per visitatore, lo stesso valore viene attribuito a tutti i canali che si sono verificati prima della conversione. </p> </td> 
   <td colname="col4"> <p>Questo modello è utile per conversioni con esperienze utente o cicli di considerazione più lunghi che necessitano di un coinvolgimento del cliente più frequente/costante. </p> <p>L’attribuzione Lineare viene spesso utilizzata dai team che misurano l’efficacia delle notifiche delle app mobili o con prodotti basati su abbonamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/u_shaped.png" id="image_625BB199056D453E8DA8FA283A990DDD" /> </p> </td> 
   <td colname="col2"> <p>A forma di U </p> </td> 
   <td colname="col3"> <p>Il modello a forma di U attribuisce il 40% del valore alla prima interazione, il 40% all’ultima e divide il restante 20% tra le interazioni nel mezzo. </p> <p>Nei lookback di attribuzione con un solo punto di contatto, il 100% del valore viene attribuito al singolo punto di contatto, mentre nei casi in cui ve ne sono solo due, a entrambi viene attribuito il 50% del valore. </p> </td> 
   <td colname="col4"> <p>Questo è un ottimo modello per chi valorizza le interazioni che si sono verificate per prima o per ultima (introduttiva o conclusiva) in una conversione ma desidera comunque riconoscere il valore delle interazioni di supporto. </p> <p>L’attribuzione a forma di U viene spesso utilizzata dai team che adottano un approccio più bilanciato ma desiderano dare più valore ai canali di origine o conclusione di una conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/j_shaped.png" id="image_D062FD7277A947BC9802F8BDFC139427" /> </p> </td> 
   <td colname="col2"> <p>A forma di J </p> </td> 
   <td colname="col3"> <p>Il modello a forma di J attribuisce il 60% del valore all’ultima interazione, il 20% alla prima e divide il restante 20% tra le interazioni nel mezzo. </p> <p>Nei lookback di attribuzione con un solo punto di contatto, il 100% del valore viene attribuito al singolo punto di contatto, mentre nei casi in cui ve ne sono solo due, il 75% del valore viene attribuito all’ultimo punto di contatto e il 25% al primo. </p> </td> 
   <td colname="col4"> <p>Simile al modello a forma di U, questo è un ottimo modello per chi valorizza le interazioni che si sono verificate per prima o per ultima (introduttiva o conclusiva) in una conversione ma desidera evidenziare l’interazione con cui si è conclusa la conversione. </p> <p>L’attribuzione a forma di J viene spesso utilizzata dai team che adottano un approccio più bilanciato e desiderano dare più valore ai canali da cui è stata conclusa una conversione </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/inverse_j.png" id="image_20FFD4C9C9714901B3F54C049D129BC6" /> </p> </td> 
   <td colname="col2"> <p>J inversa </p> </td> 
   <td colname="col3"> <p>Il modello a J inversa attribuisce il 60% del valore alla prima interazione, il 20% all’ultima e divide il restante 20% tra le interazioni nel mezzo. </p> <p>Nei lookback di attribuzione con un solo punto di contatto, il 100% del valore viene attribuito al singolo punto di contatto, mentre nei casi in cui ve ne sono solo due, il 75% del valore viene attribuito al primo punto di contatto e il 25% all’ultimo. </p> </td> 
   <td colname="col4"> <p>Simile al modello a forma di U, questo è un ottimo modello per chi valorizza le interazioni che si sono verificate per prima o per ultima (introduttiva o conclusiva) in una conversione ma desidera evidenziare l’interazione che ha dato inizio alla conversione. </p> <p>L’attribuzione a J inversa viene spesso utilizzata dai team che adottano un approccio più bilanciato e desiderano dare più valore ai canali di origine della conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/custom.png" id="image_D46A787AC72248C7B28C402F5515B099" /> </p> </td> 
   <td colname="col2"> <p>Personalizzato </p> </td> 
   <td colname="col3"> <p>Il modello personalizzato è un modello basato sulla posizione che consente di specificare il peso che si desidera assegnare alle interazioni che si sono verificate per prima (apertura), per ultima (chiusura) e a metà (player). </p> <p>I valori specificati vengono normalizzati al 100% anche se la somma dei numeri immessi è inferiore a 100. Nei lookback di attribuzione con un solo punto di contatto, il 100% del valore viene assegnato al singolo punto di contatto, mentre in casi in cui ve ne sono solo due, il parametro “player” viene ignorato e la prima e l’ultima interazione vengono ponderate secondo il modello di attribuzione del peso dei parametri “apertura” e “chiusura”, con normalizzazione al 100%. </p> </td> 
   <td colname="col4"> <p>Se le impostazioni predefinite fornite da Adobe Analytics non risultano adeguate, è disponibile un modello personalizzato che consente di specificare i pesi ottimali per l’organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/time_decay.png" id="image_7976721B60454944BF516FCF8484D3A2" /> </p> </td> 
   <td colname="col2"> <p>Decadimento nel tempo </p> </td> 
   <td colname="col3"> <p>Il modello Decadimento nel tempo segue un decadimento esponenziale con un parametro di dimezzamento personalizzato (sette giorni per impostazione predefinita). </p> <p>Il peso di ciascun canale dipende dalla quantità di tempo trascorso tra il punto di contatto e l’eventuale conversione e viene determinato secondo la formula 2^(-t/dimezzamento) dove t è la quantità di tempo trascorso tra un punto di contatto e una conversione. Per lookback con un singolo punto di contatto, il 100% del valore viene attribuito al singolo punto di contatto, mentre per lookback con due punti di contatto, il valore è proporzionale al tempo dalla conversione. </p> </td> 
   <td colname="col4"> <p>Si tratta di un buon modello per i team che svolgono attività pubblicitarie in un numero predeterminato di giorni e desiderano evidenziare i canali più recenti. </p> <p>L’attribuzione Decadimento nel tempo viene spesso utilizzata dai team che trasmettono video pubblicitari o che programmano il proprio marketing in base a un evento significativo con una data predeterminata (ad esempio una conferenza o un evento sportivo). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/participation.png" id="image_19DD3CA5C0F24F05835D8522C6708DE4" /> </p> </td> 
   <td colname="col2"> <p>Partecipazione </p> </td> 
   <td colname="col3"> <p>Partecipazione attribuisce il 100% del valore a tutti i punti di contatto o canali unici all’interno di un intervallo di lookback di attribuzione. Con Partecipazione, il numero totale di conversioni sarà maggiore nel rapporto rispetto ad altri modelli di attribuzione. Tieni presente che Partecipazione deduplica i canali che si verificano più volte all’interno di un singolo intervallo di lookback di attribuzione prima di attribuire il valore. </p> <p>Nell’esempio precedente, con un intervallo di lookback per visitatore, i canali Ricerca, Visualizzazione, Social ed E-mail riceverebbero ciascuno $ 17. Utilizzando lo stesso esempio con un intervallo di lookback per visita, Ricerca riceverebbe $ 15, Visualizzazione $ 10, Social $ 10 ed E-mail $ 17. </p> </td> 
   <td colname="col4"> <p>Questo modello è ottimo per le attività di analisi e discovery al fine di comprendere quanto spesso gli utenti finali o i clienti vengono esposti a un canale, una pagina o un’interazione particolare. </p> <p>I team che si occupano dei mezzi di comunicazione utilizzeranno spesso questo modello per calcolare la velocità dei contenuti. Per le organizzazioni di vendita al dettaglio sarà invece utile per comprendere quali parti dell’app o del sito Web si trovano sul percorso critico della conversione. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Canali di marketing e regole di elaborazione dei canali di marketing {#section_FCBF08A9D7C94B67B7AD76E8633E7916}

I canali Primo contatto e Ultimo contatto, così come i relativi dettagli, possono essere utilizzati con i nuovi modelli di attribuzione. Tuttavia, per evitare confusione nel team in futuro, ti consigliamo piuttosto di utilizzare due nuove dimensioni: **canali di marketing** e **dettagli dei canali di marketing**. Operano esattamente nello stesso modo ma non presentano la poco chiara distinzione tra “Primo contatto” e “Ultimo contatto” nel nome. Se non viene applicato alcun modello di attribuzione, i canali di marketing e i dettagli dei canali di marketing daranno gli stessi risultati del canale Ultimo contatto e dei dettagli del canale Ultimo contatto, rispettivamente.

Quando si applicano modelli di attribuzione al canale Primo contatto o al canale Ultimo contatto, il modello di attribuzione selezionato avrà la precedenza su qualsiasi impostazione di attribuzione. Perciò nonostante il nome della dimensione sia “canale Primo contatto,” se si seleziona il modello Lineare (ad esempio), i risultati rifletterebbero l’attribuzione Lineare, non “primo contatto”.

Inoltre, poiché le variabili dei canali di marketing dipendono dalla visita tradizionale, (come definita dalle regole di elaborazione dei canali di marketing che vengono applicate durante il processo di raccolta dei dati), non sono adatte all’utilizzo con sessioni basate sul contesto.

## Attribuzione su suddivisioni di classificazione {#section_F9DE21758C4643879BE05EEAE9A34E5A}

Puoi applicare i modelli di attribuzione a qualsiasi valore e classificazione. Se un valore classificato viene suddiviso in base alla propria chiave, Analytics includerà solo le chiavi associate a quel particolare valore. Ad esempio, per un modello di attribuzione lineare applicato a una variabile eVar con i valori “mela”, “banana” e “carota” classificati in base ai valori “Frutta” e “Ortaggi”, ove il valore “Ortaggi” è suddiviso dalla variabile eVar di base, nella suddivisione figurerebbe solo “carota”. In modo analogo, se “Frutta” è suddiviso dalla variabile eVar di base, nei risultati di suddivisione verrebbero visualizzati solo i valori “mela” e “banana”, anche se l’attribuzione era stata ripartita fra tutti e tre i valori eVar di base.

Questo comportamento si applica anche ai rapporti in cui le dimensioni dei canali di marketing vengono suddivise secondo le dimensioni dei dettagli dei canali di marketing.

## Attribuzione per suddivisioni {#section_B2E87C768B6B4DBFA8EB7DB5E2DF881E}

Analysis Workspace consente di suddividere qualsiasi valore per qualsiasi altra dimensione e di specificare per la suddivisione le stesse o diverse impostazioni di attribuzione. Ad esempio, è possibile applicare un’attribuzione lineare a una dimensione Canale; ma se si suddivide Canale per Campagna è possibile specificare un modello di attribuzione diverso a livello delle singole campagne.

Questa soluzione è utile ad esempio per più team che utilizzano un modello di attribuzione a livello di canale (con suddivisione equa tra i vari canali), quando però singoli team desiderano utilizzare un modello di attribuzione diverso per le proprie campagne, i cui totali dovranno comunque corrispondere a quanto allocato a livello di canale.

## Elemento di attribuzione “Nessuno” {#section_BC71DA030E45487AA3C3F6ED247A3C4A}

L’elemento “Nessuno” è un elemento generico che rappresenta tutte le conversioni che si sono verificate quando non era presente alcun valore di dimensione. Tradizionalmente, l’elemento “Nessuno” esiste solo nei rapporti eVar o in altre dimensioni dotate di permanenza. Quando si applicano modelli di attribuzione, può essere visualizzato un elemento “Nessuno” in una posizione in cui non esisteva in precedenza. Questa condizione si verifica più comunemente quando si applicano modelli di attribuzione alle proprietà che introducono un elemento “Nessuno” non presente in precedenza.

## Attribuzione per variabili con più valori

Alcune dimensioni in Analytics possono contenere più valori in un singolo hit, come ad esempio listVars, la variabile di prodotto, le proprietà di elenco o eVars per merchandising. Analysis Workspace consente di applicare Attribution IQ a uno qualsiasi di questi tipi di variabili a livello di hit. Utilizzo dell’attribuzione “a forma di U” (40/20/40) come esempio per una singola visita:

| Numero hit | Variabile con più valori | Evento di conversione | Percentuale di credito attribuito per l’hit (a forma di U) |
|--- |--- |---|---|
| 1 | A,B,C | - | 40% |
| 2 | D | - | 20% |
| 3 | E,F | 1 | 40% |

In questo caso A, B e C erano tutti impostati allo stesso tempo sull’hit 1, D sull’hit 2, mentre E ed F sull’3.

Attribution IQ assegna tutto il credito percentuale per l’hit a qualsiasi valore presente su di esso. Nell’esempio precedente, A, B e C riceveranno quindi il 40%, ossia 0,4 conversioni; D riceverà il 20%, ossia 0,2 conversioni, mentre E ed F riceveranno ciascuno il 40% delle conversioni, ossia 0,4. Un rapporto sull’attribuzione a forma di U su questi hit genererebbe i seguenti dati:

| Variabile con più valori | Conversioni (a forma usa/U) |
|--- |---|
| A | 0,4 |
| B | 0,4 |
| C | 0,4 |
| D | 0,2 |
| E | 0,4 |
| F | 0,4 |
| Totale | 1 |

>[!NOTE]
>A causa dell'allocazione a livello di hit dei modelli di attribuzione, la somma di ogni elemento di riga del report potrebbe non corrispondere al totale a causa di ogni valore che riceve il credito totale della percentuale appartenente all'hit in cui era contenuto.