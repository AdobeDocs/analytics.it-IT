---
description: I segmenti sequenziali vengono creati utilizzando l'operatore THEN, anziché AND o OR. THEN implica che si verifichi un criterio di segmento, seguito da un altro. Per impostazione predefinita, un segmento sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I segmenti sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni «Only Before Sequence» (Solo prima della sequenza) e «Only After Sequence» (Solo dopo la sequenza).
seo-description: I segmenti sequenziali vengono creati utilizzando l'operatore THEN, anziché AND o OR. THEN implica che si verifichi un criterio di segmento, seguito da un altro. Per impostazione predefinita, un segmento sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I segmenti sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni «Only Before Sequence» (Solo prima della sequenza) e «Only After Sequence» (Solo dopo la sequenza).
seo-title: Creare segmenti sequenziali
solution: Analytics
title: Creare segmenti sequenziali
topic: Segmenti
uuid: 7 fb 9 f 1 c 7-a 738-416 a-aaa 2-d 77 e 40 fa 7 e 61
translation-type: tm+mt
source-git-commit: 22aec2a6e8e0c0aa3e0a404a7cb0bc44a392a1a9

---


# Creare segmenti sequenziali

I segmenti sequenziali vengono creati utilizzando l'operatore THEN, anziché AND o OR. THEN implica che si verifichi un criterio di segmento, seguito da un altro. Per impostazione predefinita, un segmento sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I segmenti sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni «Only Before Sequence» (Solo prima della sequenza) e «Only After Sequence» (Solo dopo la sequenza).

![](assets/before-after-sequence.png)

Inoltre, potete vincolare i segmenti sequenziali a una durata specifica di tempo, granularità e conteggio tra i punti di controllo utilizzando gli operatori [After e Within](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_07708877D06742998C6237DD9FD194EA).

## Includi tutti {#section_75ADDD5D41F04800A09E592BB2940B35}

Quando si crea un segmento in cui «Includi tutti» è impostato, il segmento identifica i percorsi che corrispondono al pattern specificato. Si tratta di un esempio di segmento di sequenza di base che cerca un hit (Pagina A) seguito da un altro (Pagina B) come visitato dallo stesso visitatore. Il segmento è impostato su Includi tutti.

![](assets/sequence-filter.png)

| Se risultato… | Sequenza |
|--- |--- |
| Corrisponde | A then BA<br>then (in a different visit) BA<br>then D then B |
| Non corrisponde | B then A |

## Solo prima della sequenza e solo dopo la sequenza {#section_736E255C8CFF43C2A2CAAA6D312ED574}

Le opzioni **[!UICONTROL Only Before Sequence]** e **[!UICONTROL Only After Sequence]** filtrare il segmento a un sottoinsieme di dati prima o dopo la sequenza specificata.

* **Solo prima della sequenza**: Include tutti gli hit prima di una sequenza + il primo hit della sequenza stessa (vedere l'esempio 1, 3). Se una sequenza viene visualizzata più volte in un percorso, «Solo prima sequenza» include il primo hit dell'ultima occorrenza della sequenza e tutti gli hit precedenti (vedere Esempio 2).
* **Solo dopo la sequenza**: Include tutti gli hit dopo una sequenza + l'ultimo hit della sequenza stessa (vedere l'esempio 1, 3). Se una sequenza viene visualizzata più volte in un percorso, «Solo dopo» include l'ultimo hit della prima occorrenza della sequenza e tutti gli hit successivi (vedere Esempio 2).

Ad esempio, considerate una sequenza di B -&gt; D. I tre filtri identificherebbero gli hit come segue:

**Esempio 1: B quindi viene visualizzata una volta**

| Esempio  | Una  | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Includi tutti | Una  | B | C | D | E | F |
| Solo prima della sequenza | Una  | B |  |  |  |  |
| Solo dopo la sequenza |  |  |  | D | E | F |

**Esempio 2: B viene visualizzato più volte**

| Esempio  | Una  | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Includi tutti | Una  | B | C | D | B | C | D | E |
| Solo prima della sequenza | Una  | B | C | D | B |  |  |  |
| Solo dopo la sequenza |  |  |  | D | B | C | D | E |

Atteniamo anche questo concetto con la dimensione Profondità hit.

**Esempio 3: Hit profondità 3 then 5**

![](assets/hit-depth.png)

## Vincoli dimensione {#section_EAFD755F8E674F32BCE9B642F7F909DB}

In una clausola “within” (entro), tra istruzioni THEN, è possibile aggiungere, ad esempio, “within 1 search keyword instance”, “within 1 eVar 47 instance”. In questo modo si vincola il segmento entro un’istanza di una dimensione.

L'impostazione di una clausola «Within Dimension» tra le regole consente a un segmento di limitare i dati alle sequenze in cui tale clausola viene soddisfatta. Vedere l'esempio seguente, dove il vincolo è impostato su «Within 1 page»:

![](assets/sequence-filter4.png)

| Se risultato… | Sequenza |
|--- |--- |
| Corrisponde | A then B |
| Non corrisponde | A then C then B (because B was not within 1 page of A)<br>**Nota:** Se la restrizione della dimensione è ridotta, «A then B» e «A then C then B» corrispondono entrambe. |

## Sequenza semplice di visualizzazione pagina

Identificare i visitatori che hanno visualizzato una pagina e quindi visualizzarne un'altra. I dati a livello di hit filtreranno questa sequenza indipendentemente dalle sessioni di visita precedenti, passate o provvisorie o dal numero o numero di visualizzazioni di pagina che si verificano tra.

**Esempio**: Il visitatore ha visualizzato la pagina A, quindi la pagina B nella stessa visita o un'altra visita.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo del segmento.

1. I visitatori di un sito sportivo visualizzano la pagina di destinazione calcio, quindi visualizzano la pagina di destinazione della palla in ordine sequenziale, ma non necessariamente nella stessa visita. Questo richiede una campagna per inviare il contenuto di pallacerchi ai visualizzatori football durante la stagione di calcio.
1. Il rivenditore di automobili identifica una relazione tra coloro che arrivano sulla pagina di fedeltà del cliente e quindi accedono alla pagina video in qualsiasi momento durante la visita o un'altra visita.

**Crea questo segmento**

Nidificate due regole di pagina all'interno di [!UICONTROL Visitor] un contenitore di livello principale e sequenza gli hit delle pagine utilizzando l' [!UICONTROL THEN] operatore.

![](assets/segment_sequential_1.png)

## Sequenza di visitatori tra visite

Identificare i visitatori che hanno abbandonato una campagna, ma poi ritornano alla sequenza di visualizzazioni di pagina in un'altra sessione.

**Esempio**: Il visitatore ha visualizzato la pagina A in una visita, quindi la pagina B in un'altra visita.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* I visitatori della pagina Sport di un sito di notizie rivedono la pagina Sport in un'altra sessione.
* Un rivenditore di abbigliamento vede una relazione tra i visitatori che arrivano su una pagina di destinazione in una sessione, quindi passa direttamente alla pagina di cassa in un'altra sessione.

**Crea questo segmento**

Questo esempio nidifica due **[!UICONTROL Visit]** contenitori nel contenitore di livello principale **[!UICONTROL Visitor]** e sequerà il segmento utilizzando l [!UICONTROL THEN] 'operatore.

![](assets/visitor_seq_across_visits.png)

## Sequenza a livello misto

Identificare i visitatori che visualizzano due pagine in un numero di visite non determinato, quindi visualizzare una terza pagina in una visita separata.

**Esempio**: I visitatori visitano la pagina A e quindi la pagina B in una o più visite, seguita da una visita alla pagina C in una visita separata.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* I visitatori visitano prima un sito di notizie e quindi visualizzano la pagina sportiva nella stessa visita. Su un'altra visita il visitatore visita la pagina del calendario.
* Il rivenditore definisce i visitatori che entrano nella pagina Principale e quindi accedono alla pagina Account personale. In un'altra visita, visita la pagina Visualizza carrello.

**Crea questo segmento**

1. Rilascia due dimensioni Pagina dai riquadri a sinistra all'interno [!UICONTROL Visitor] di un contenitore di livello principale.
1. Aggiungete l'operatore THEN tra di essi.
1. Fate clic **[!UICONTROL Options]** &gt; **[!UICONTROL Add container]** e aggiungete un [!UICONTROL Visit] contenitore sotto il [!UICONTROL Visitor] livello e in sequenza utilizzando l [!UICONTROL THEN] 'operatore.

![](assets/mixed_level_checkpoints.png)

## Contenitori aggregati

L'aggiunta [!UICONTROL Hit] di più contenitori all'interno di [!UICONTROL Visitor] un contenitore consente di impiegare gli operatori appropriati tra lo stesso tipo di contenitori e di utilizzare regole e dimensioni quali Pagina e Numero visita per definire la visualizzazione pagina e fornire una dimensione della sequenza all'interno [!UICONTROL Hit] del contenitore. L'applicazione logica a livello di hit consente di vincolare e combinare le corrispondenze allo stesso livello di hit nel [!UICONTROL Visitor] contenitore per creare diversi tipi di segmenti.

**Esempio**: I visitatori visitano la pagina A dopo il primo hit nella sequenza di visualizzazioni di pagina (pagina D nell'esempio), quindi hanno visitato la pagina B o la pagina C senza considerare il numero di visite.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Identificare i visitatori che arrivano alla pagina di destinazione Principale in una visita, quindi visualizzare la pagina abbigliamento da Uomo in un'altra visita, quindi visualizzare la pagina di destinazione della donna o figlio in una visita diversa.
* Un e-zine acquisisce i visitatori che arrivano alla pagina iniziale in una visita, la pagina Sport in un'altra visita e la pagina Opinioni in un'altra visita.

**Crea questo segmento**

1. Selezionare [!UICONTROL Visitor] il contenitore come contenitore di livello principale.
1. Aggiungere contenitori a due [!UICONTROL Hit]livelli: una dimensione con una dimensione numerica appropriata unita allo stesso [!UICONTROL Hit] livello dall'operatore [!UICONTROL AND] e [!UICONTROL OR] .
1. All'interno del [!UICONTROL Visit] contenitore, aggiungete un altro [!UICONTROL Hit] contenitore e nidificate due [!UICONTROL Hit] contenitori aggiuntivi uniti a un operatore [!UICONTROL OR] o [!UICONTROL AND] operatore.

   Sequenza i [!UICONTROL Hit] contenitori nidificati con l' [!UICONTROL THEN] operatore.

![](assets/aggregate_checkpoints2.png)

## «Nidificazione» nei segmenti sequenziali

Posizionando i punti di controllo sia a [!UICONTROL Visit] livello di e [!UICONTROL Hit] livello, puoi vincolare il segmento in base ai requisiti in una visita specifica, nonché un hit specifico.

**Esempio**: Visitatore visitato la pagina A quindi la pagina B nella stessa visita. In una nuova visita, il visitatore passava alla pagina C.

**Crea questo segmento**

1. Sotto un [!UICONTROL Visit] contenitore di livello principale, trascinate in due dimensioni della pagina.
1. Selezionate più regole, fate clic **[!UICONTROL Options]** su &gt; **[!UICONTROL Add container from selection]** e modificatele in [!UICONTROL Visit] un contenitore.
1. Unisciti a un [!UICONTROL THEN] operatore.
1. Crea un contenitore Hit come peer e [!UICONTROL Visit] trascina in una dimensione pagina.
1. Unitevi alla sequenza nidificata nel [!UICONTROL Visit] contenitore con il [!UICONTROL Hit] contenitore utilizzando un altro [!UICONTROL THEN] operatore.

![](assets/nesting_sequential_seg.png)

## Escludere gli hit

Le regole dei segmenti includono tutti i dati, a meno che tu non escluda [!UICONTROL Visitor]espressamente, [!UICONTROL Visit]o [!UICONTROL Hit] dati utilizzando la [!UICONTROL Exclude] regola. Consente di ignorare i dati comuni e di creare segmenti con maggiore attenzione. Oppure consente di creare segmenti esclusivi per gruppi individuati per identificare il set di dati rimanenti, ad esempio creando una regola che include i visitatori che hanno effettuato i primi ordini e quindi li escluda per identificare "non acquirenti". Nella maggior parte dei casi, tuttavia, è meglio creare regole che escludano valori ampi piuttosto che tentare di utilizzare la [!UICONTROL Exclude] regola per eseguire il targeting di specifici valori.

Ad esempio:

* **Escludete le pagine**. Utilizzate una regola di segmento per rimuovere una pagina specifica (ad esempio *`Home Page`*) da un rapporto, creare una regola Hit in cui la pagina è «Home Page» e quindi escluderla. Questa regola include automaticamente tutti i valori eccetto la Home Page.
* **Escludere domini di riferimento**. Utilizzate una regola che includa solo domini di riferimento da Google.com ed esclude tutti gli altri.
* **Identificare i non acquirenti**. Identificare quando gli ordini sono superiori a zero e quindi escluderli.[!UICONTROL Visitor]

L' [!UICONTROL Exclude] operatore può essere impiegato per identificare una sequenza in cui il visitatore non esegue visite o hit specifici. [!UICONTROL Exclude Checkpoints] possono essere incluse anche all'interno di un [gruppo logico](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112).

### Escludi tra i punti di controllo

Applicare logica per segmentare i visitatori in cui un punto di controllo non si è verificato in modo esplicito tra due altri checkpoint.

**Esempio**: Visitatori che hanno visitato la pagina A e quindi hanno visitato la pagina C, ma non hanno visitato la pagina B.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Visitatori della pagina History (Stili) e quindi della sezione Teatro senza passare alla pagina Arts (Arti).
* Un rivenditore automatico vede una relazione tra coloro che visitano la pagina di destinazione principale, quindi passa direttamente alla campagna No Interest senza passare alla pagina Vehicle.

**Crea questo segmento**

Create un segmento come fareste per un segmento sequenziale semplice, a livello misto o nidificato, quindi impostate l' [!UICONTROL EXCLUDE] operatore per l'elemento contenitore. L'esempio seguente è un segmento complessivo in cui i tre [!UICONTROL Hit] contenitori vengono trascinati nell'area di lavoro, l' [!UICONTROL THEN] operatore assegnato per partecipare alla logica del contenitore, quindi escludendo il contenitore di visualizzazione centrale della pagina per includere solo i visitatori che sono passati dalla pagina A alla pagina C nella sequenza.

![](assets/exclude_between_checkpoints.png)

### Escludi all'inizio della sequenza

Se l'eccezione di controllo si trova all'inizio di un segmento sequenziale, la visualizzazione di pagina esclusa non viene eseguita prima del primo hit non escluso.

**Esempio**: Visitatore visitato la pagina A e non la pagina B.

**Casi d'uso**

Di seguito sono riportati alcuni esempi d'uso di questo tipo di segmento:

* Visitatori che hanno visitato la pagina A e che non hanno visitato la pagina B.
* Un ristorante vuole visualizzare gli utenti che hanno evitato la pagina di destinazione principale e andare direttamente alla pagina Ordine di acquisto.

**Crea questo segmento**

Crea due contenitori Hit distinti all'interno di un contenitore Visitatore di livello principale. Quindi, impostate l' [!UICONTROL EXCLUDE] operatore per il primo contenitore.

![](assets/exclude_beginning_sequence.png)

### Escludi alla fine della sequenza

Se l'eccezione di controllo si trova alla fine di una sequenza, il punto di controllo non si verifica tra l'ultimo punto di controllo non escluso e la fine della sequenza dei visitatori.

**Esempio**: I visitatori visitano la pagina A e quindi non visitavano la pagina B nella visita corrente o successive.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Visitatori che hanno visitato la pagina A e che non hanno visitato la pagina B.
* Un ristorante vuole visualizzare gli utenti che hanno evitato la pagina di destinazione principale e andare direttamente alla pagina Ordine di acquisto.

**Crea questo segmento**

Create un segmento di sequenza semplice trascinando due [!UICONTROL Hit] contenitori nel quadro e collegandoli utilizzando l [!UICONTROL THEN] 'operatore. Quindi, assegnate l' [!UICONTROL EXCLUDE] operatore al secondo [!UICONTROL Hit] contenitore della sequenza.

![](assets/exclude_end_sequence.png)

## Contenitori Gruppo logica

Nella segmentazione sequenziale, è necessario che i contenitori siano ordinati rigorosamente all'interno della [gerarchia dei contenitori](../../../components/c-segmentation/seg-overview.md#concept_A38E7000056547399E346559D85E2551). [!UICONTROL Logic Group] Il contenitore è stato progettato per gestire *diversi punti di controllo come gruppo*, *senza ordinarlo* tra i punti di controllo raggruppati. In altre parole, non ci interessano l'ordine dei punti di controllo all'interno del gruppo. Ad esempio, non è possibile nidificare un [!UICONTROL Visitor] contenitore all'interno di [!UICONTROL Visitor] un contenitore. Al contrario, potete nidificare un [!UICONTROL Logic Group] contenitore all'interno di un [!UICONTROL Visitor] contenitore con punti di controllo specifici [!UICONTROL Visit]a livello e [!UICONTROL Hit]a livello.

| Gerarchia contenitore standard |
|---|
| ![](assets/nesting_container.png) |
| All'interno [!UICONTROL Visitor] del contenitore, i [!UICONTROL Visit] contenitori e [!UICONTROL Hit] i contenitori sono nidificati in sequenza per estrarre segmenti in base agli hit, al numero di visite e al visitatore. |

>[!NOTE]
>
>A [!UICONTROL Logic Group] può essere definito solo in un segmento sequenziale, il che significa che l' [!UICONTROL THEN] operatore viene utilizzato all'interno dell'espressione.

| Gerarchia logica non standard - Gerarchia |
|---|
| ![](assets/logic_group_hierarchy.png) |
| La gerarchia contenitore standard è necessaria anche all'esterno [!UICONTROL Logic Group] del contenitore. Tuttavia, all'interno del [!UICONTROL Logic Group] contenitore, i punti di controllo non richiedono un ordine o una gerarchia stabilita. Questi punti di controllo devono semplicemente essere soddisfatti dal visitatore in qualsiasi ordine. |

### Creare un segmento gruppo logica {#section_A5DDC96E72194668AA91BBD89E575D2E}

Come per altri contenitori, [!UICONTROL Logic Group] i contenitori possono essere definiti in diversi modi all'interno della [!UICONTROL Segment Builder]. Ecco un metodo preferito [!UICONTROL Logic Group] per nidificare i contenitori:

1. Trascina dimensioni, eventi o segmenti dai riquadri sinistro.
1. Cambia il contenitore principale in [!UICONTROL Visitor] un contenitore.
1. Modificate l'operatore [!UICONTROL AND] o [!UICONTROL OR] l'operatore inserito per impostazione predefinita all'operatore THEN.
1. Selezionate [!UICONTROL Hit] i contenitori (Dimensione, Evento o Elemento) e fate clic **[!UICONTROL Options]** su &gt; **[!UICONTROL Add container from selection]**.
1. Fate clic sull'icona del contenitore e selezionate **[!UICONTROL Logic Group]**. ![](assets/logic_group_checkpoints.png)
1. È ora possibile impostare l' [!UICONTROL Hit] interno del [!UICONTROL Logic Group] contenitore in base alla gerarchia.

### Punti di controllo Gruppo logica in qualsiasi ordine

L'utilizzo di questo [!UICONTROL Logic Group] metodo consente di rispettare le condizioni all'interno del gruppo che risiede all'esterno della sequenza. Questo consente di creare segmenti in cui un [!UICONTROL Visit] contenitore o [!UICONTROL Hit] un contenitore si verificano indipendentemente dalla normale gerarchia. ****

**Esempio**: Visitatori che hanno visitato la pagina A, quindi la pagina B e la pagina C in qualsiasi ordine.

**Crea questo segmento**

Le pagine B e C sono nidificate in [!UICONTROL Logic Group] un contenitore all'interno del [!UICONTROL Visitor] contenitore esterno. [!UICONTROL Hit] Il contenitore A è seguito dal [!UICONTROL Logic Group] contenitore con B e C identificato utilizzando l [!UICONTROL AND] 'operatore. Poiché si trova nella [!UICONTROL Logic Group], la sequenza non è definita e se si preme la pagina B o C l'argomento vero.

![](assets/logic_group_any_order2.png)

### Logica logica gruppo logica

L'utilizzo di questo [!UICONTROL Logic Group] metodo consente di rispettare le condizioni all'interno del gruppo che risiede all'esterno della sequenza. In questo segmento non ordinato, le [!UICONTROL Logic Group] regole sono identificate prima in una visualizzazione pagina della pagina B o della pagina C, quindi nella vista richiesta della pagina A.

**Esempio**: Visitatori che hanno visitato la pagina B o la pagina C, quindi la pagina A.

**Crea questo segmento**

La pagina B e le dimensioni della pagina C sono raggruppate all'interno di un [!UICONTROL Logic Group] contenitore con l' [!UICONTROL OR] operatore selezionato, quindi il [!UICONTROL Hit]contenitore identifica una visualizzazione pagina della pagina A come valore.

![](assets/logic_group_1st_match.png)

### Logical Group esclude AND

Creare segmenti utilizzando l' [!UICONTROL Logic Group] aggregazione di più visualizzazioni di pagina per definire quali pagine erano necessarie quando altre pagine sono state esplicitamente tralasciate. ****

**Esempio**: Il visitatore ha visitato la Pagina A, quindi non ha visitato la pagina B o C, ma ha fatto pagina D.

**Crea questo segmento**

Crea questo segmento trascinando Dimensioni, Eventi e Segmenti pregenerati dai riquadri sinistro. Consultate [Creazione di un segmento di gruppo logica](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112).

Dopo aver nidificato i valori all'interno del [!UICONTROL Logic Group]contenitore, fare clic sul **[!UICONTROL Exclude]** pulsante all'interno del [!UICONTROL Logic Group] contenitore.

![](assets/logic_exclude_and.png)

### Loggroup exclude OR

Creare segmenti utilizzando l' [!UICONTROL Logic Group] aggregazione di più visualizzazioni di pagina per definire quali pagine erano necessarie quando altre pagine sono state esplicitamente tralasciate.

**Esempio**: Visitatori che hanno visitato la pagina A, ma non hanno visitato la Pagina B o la Pagina C prima della pagina A.

**Crea questo segmento**

Le pagine iniziali B e C sono identificate in [!UICONTROL Logic Group] un contenitore escluso e quindi da un hit alla pagina A da parte del visitatore.

Crea questo segmento trascinando Dimensioni, Eventi e Segmenti pregenerati dai riquadri sinistro.

Dopo aver nidificato i valori all'interno del [!UICONTROL Logic Group]contenitore, fare clic sul **[!UICONTROL Exclude]** pulsante all'interno del [!UICONTROL Logic Group] contenitore.

![](assets/logic_exclude_or.png)

## Creare segmenti time-within e time-after

Utilizzare gli [!UICONTROL Within][!UICONTROL After] operatori e gli operatori incorporati all'intestazione di ciascun contenitore per definire l'ora, gli eventi e il conteggio.

![](assets/then_within_operators.png)

È possibile limitare la corrispondenza a una durata specificata utilizzando i [!UICONTROL Within][!UICONTROL After] contenitori e specificando una granularità e un conteggio. [!UICONTROL Within] L'operatore viene utilizzato per specificare un limite massimo per il tempo tra due punti di controllo. [!UICONTROL After] L'operatore viene utilizzato per specificare un limite minimo per il tempo tra due punti di controllo.

### After and Within Operator {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

La durata è specificata da una singola lettera maiuscola che rappresenta la granularità seguita da un numero che rappresenta il conteggio ripetibile della granularità.

**[!UICONTROL Within]** include l'endpoint (minore o uguale a).

**[!UICONTROL After]** non include l'endpoint (maggiore di).

| Operatori | Descrizione |
|--- |--- |
| AFTER | L'operatore After viene utilizzato per specificare un limite minimo per il tempo tra due punti di controllo. Quando si impostano i valori di After, il limite di tempo inizia quando il segmento viene applicato. Ad esempio, se l'operatore Dopo è impostato su un contenitore per identificare i visitatori che visitano la pagina A ma non torna per visitare la pagina B fino a un giorno, quel giorno avrà inizio quando il visitatore lascia la pagina A. Affinché il visitatore sia incluso nel segmento, almeno 1440 minuti (un giorno) devono essere dinamici dopo aver abbandonato la pagina A alla visualizzazione della pagina B. |
| WITHIN | L'operatore Within viene utilizzato per specificare un limite massimo per il tempo compreso tra due punti di controllo. Ad esempio, se l'operatore Within è impostato su un contenitore per identificare i visitatori che visitano la pagina A e quindi ritornano alla pagina B entro un giorno, quel giorno inizierà quando il visitatore lascia la pagina A. Per essere inclusi nel segmento, il visitatore avrà un tempo massimo di un giorno prima di aprire la pagina B. Affinché il visitatore sia incluso nel segmento, l'accesso alla pagina B deve avvenire entro un massimo di 1440 minuti (un giorno) dopo aver abbandonato la pagina A alla visualizzazione della pagina B. |
| AFTER/INSIDE | Quando si utilizzano sia gli operatori After che Inside, è importante comprendere che entrambi gli operatori iniziano e termineranno in parallelo, non in sequenza. Ad esempio, se crei un segmento con il contenitore impostato su:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Le condizioni per identificare i visitatori nel segmento sono soddisfatte solo tra 1 e 2 settimane. Entrambe le condizioni sono applicate dal momento dell'hit della prima pagina. |

### Usare l'operatore Dopo

* Ora dopo ti consente di effettuare una traccia per anno, mese, giorno, ora e minuti per far corrispondere le visite.
* Ora dopo può essere applicata solo [!UICONTROL Hit] a un contenitore, perché è l'unico livello per il quale è definito tale granularità.

**Esempio**: Visitatori che hanno visitato la pagina A quindi hanno visitato la pagina B solo dopo 2 settimane. ****

![](assets/time_between_after_operator.png)

**Crea il segmento**: Questo segmento viene creato aggiungendo un [!UICONTROL Visitor] contenitore con due [!UICONTROL Hit] contenitori. Potete quindi impostare [!UICONTROL THEN] l'operatore, quindi aprire il [!UICONTROL AFTER] menu a discesa dell'operatore e impostare il numero di settimane.

![](assets/after_operator.png)

**Corrisponde**

Se viene indicato "Dopo 2 settimane", se un hit alla pagina A viene eseguito il 1 giugno 2019, alle 00:01, un hit successivo alla pagina B corrisponderà a condizione che arrivi prima del 15 giugno 00:01 (14 giorni dopo).

| Hit A | Hit B | Corrispondenza |
|--- |--- |--- |
| **** Un hit: 1 giugno 2019 00:01 | **Hit B** : Jun 15, 2019 00:01 | **Corrisponde:** Questo limite di tempo corrisponde a quanto segue dal 1 giugno 2019 (due settimane). |
| **** Un hit: 1 giugno 2019 00:01 | **Hit B** : Hit 8 giugno 2019 00:01 B hit: 15 giugno 2019 00:01 | **Non corrisponde:** Il primo hit sulla pagina B non corrisponde perché in conflitto con il vincolo che lo richiede dopo due settimane. |

### Usare l'operatore Inside

* [!UICONTROL Within] consente di effettuare una traccia per anno, mese, giorno, ora e minuti per far corrispondere le visite.
* [!UICONTROL Within] può essere applicato solo a [!UICONTROL Hit] un contenitore perché è l'unico livello per il quale è definito tale granularità.

>[!IMPORTANT]
>
>In una clausola “within” (entro), tra istruzioni THEN, è possibile aggiungere, ad esempio, “within 1 search keyword instance”, “within 1 eVar 47 instance”. In questo modo si vincola il segmento entro un’istanza di una dimensione.

**Esempio**: Visitatori che hanno visitato la pagina A quindi hanno visitato la pagina B entro 5 minuti.

![](assets/time_between_within_operator.png)

**Crea il segmento**: Questo segmento viene creato aggiungendo un [!UICONTROL Visitor] contenitore, quindi trascinandolo con due [!UICONTROL Hit] contenitori. Potete quindi impostare [!UICONTROL THEN] l'operatore, quindi aprire il [!UICONTROL AFTER] menu a discesa dell'operatore e impostare l'intervallo: hit, visualizzazioni di pagina, visite, minuti, ore, giorni, settimane, mesi, trimestri o anni.

![](assets/within_operator.png)

**Corrisponde**

Le corrispondenze devono avvenire entro il limite temporale. Per l'espressione, se la pagina A del visitatore è impostata su 00:01, un hit seguente alla pagina B corrisponderà finché arriva o prima di 00:06 (cinque minuti dopo, compreso lo stesso minuto). Anche gli hit che rientrano nello stesso minuto corrispondono.

### Operatori Dentro e Dopo

Utilizza [!UICONTROL Within] e [!UICONTROL After] per fornire un endpoint massimo e minimo a entrambe le estremità di un segmento.

**Esempio**: Visitatori che hanno visitato la pagina A quindi hanno visitato la pagina B dopo 2 settimane ma entro 1 mesi.

![](assets/time_between_using_both_operators.png)

**Crea il segmento**: Create il segmento sequenziando due [!UICONTROL Hit] contenitori all'interno di un [!UICONTROL Visitor] contenitore. Quindi impostate gli [!UICONTROL After] operatori e gli [!UICONTROL Within] operatori.

![](assets/within_after_together.png)

**Corrisponde**

Tutti i visitatori che hanno partecipato alla pagina A il 1 giugno 2019 torneranno dopo il 15 giugno 2019, ma *prima del* 1 luglio 2019 saranno inclusi nel segmento. Confronta con [ora tra esclusioni](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_C5CB0A391B7C4AC8A95B9724A14E28E8).

Gli [!UICONTROL After] operatori e [!UICONTROL Within] possono essere utilizzati insieme per definire un segmento sequenziale.

![](assets/time_between_within_after.png)

Questo esempio illustra una seconda visita per accedere alla pagina B dopo due settimane, ma nel giro di un mese.
