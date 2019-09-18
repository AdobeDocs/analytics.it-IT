---
description: I segmenti sequenziali vengono creati utilizzando l'operatore THEN, anziché AND o OR. Ciò implica che si verifica un criterio di segmento, seguito da un altro. Per impostazione predefinita, un segmento sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I segmenti sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni "Solo prima della sequenza" e "Solo dopo la sequenza".
seo-description: I segmenti sequenziali vengono creati utilizzando l'operatore THEN, anziché AND o OR. Ciò implica che si verifica un criterio di segmento, seguito da un altro. Per impostazione predefinita, un segmento sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I segmenti sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni "Solo prima della sequenza" e "Solo dopo la sequenza".
seo-title: Creare segmenti sequenziali
solution: Analytics
title: Creare segmenti sequenziali
topic: Segmenti
uuid: 7fb9f1c7-a738-416a-aaa2-d77e40fa7e61
translation-type: tm+mt
source-git-commit: a8d34022b07dbb18a83559045853fa11acc9c3dd

---


# Creare segmenti sequenziali

I segmenti sequenziali vengono creati utilizzando l'operatore THEN, anziché AND o OR. Ciò implica che si verifica un criterio di segmento, seguito da un altro. Per impostazione predefinita, un segmento sequenziale identifica tutti i dati corrispondenti, mostrando il filtro "Includi tutti". I segmenti sequenziali possono essere ulteriormente filtrati in un sottoinsieme di hit corrispondenti utilizzando le opzioni "Solo prima della sequenza" e "Solo dopo la sequenza".

![](assets/before-after-sequence.png)

È inoltre possibile vincolare i segmenti sequenziali a una durata specifica di tempo, granularità e conteggi tra i punti di controllo utilizzando gli operatori [Dopo e Entro](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_07708877D06742998C6237DD9FD194EA).

## Includi tutti {#section_75ADDD5D41F04800A09E592BB2940B35}

Quando si crea un segmento in cui è impostata l'opzione "Includi tutti", il segmento identifica i percorsi che corrispondono al pattern specificato nel suo insieme. Questo è un esempio di segmento di sequenza di base alla ricerca di un hit (Pagina A) seguito da un altro (Pagina B) visitato dallo stesso visitatore. Il segmento è impostato su Includi tutti.

![](assets/sequence-filter.png)

| Se risultato... | Sequenza |
|--- |--- |
| Corrisponde | A poi<br>BA (in una visita diversa)<br>BA poi D e poi B |
| Non corrisponde | B e A |

## Solo prima della sequenza e solo dopo la sequenza {#section_736E255C8CFF43C2A2CAAA6D312ED574}

Le opzioni **[!UICONTROL Only Before Sequence]** e il **[!UICONTROL Only After Sequence]** filtro del segmento a un sottoinsieme di dati prima o dopo la sequenza specificata.

* **Solo prima della sequenza**: Include tutti gli hit prima di una sequenza + il primo hit della sequenza stessa (vedere l’esempio 1, 3). Se una sequenza appare più volte in un percorso, "Only Before Sequence" include il primo hit dell'ultima occorrenza della sequenza e tutti gli hit precedenti (vedere l'esempio 2).
* **Solo dopo la sequenza**: Include tutti gli hit dopo una sequenza + l’ultimo hit della sequenza stessa (vedere l’esempio 1, 3). Se una sequenza appare più volte in un percorso, "Only After" include l’ultimo hit della prima occorrenza della sequenza e tutti gli hit successivi (vedere l’esempio 2).

Ad esempio, considerate una sequenza di B -&gt; D. I tre filtri identificano gli hit come segue:

**Esempio 1: B e D appaiono una volta**

| Esempio  | Una  | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Includi tutti | Una  | B | C | D | E | F |
| Solo prima della sequenza | Una  | B |  |  |  |  |
| Solo dopo la sequenza |  |  |  | D | E | F |

**Esempio 2: B e D appaiono più volte**

| Esempio  | Una  | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Includi tutti | Una  | B | C | D | B | C | D | E |
| Solo prima della sequenza | Una  | B | C | D | B |  |  |  |
| Solo dopo la sequenza |  |  |  | D | B | C | D | E |

Inquadriamo questo concetto anche con la dimensione Profondità di Hit.

**Esempio 3: Profondità Hit 3 poi 5**

![](assets/hit-depth.png)

## Vincoli dimensione {#section_EAFD755F8E674F32BCE9B642F7F909DB}

In una clausola “within” (entro), tra istruzioni THEN, è possibile aggiungere, ad esempio, “within 1 search keyword instance”, “within 1 eVar 47 instance”. In questo modo si vincola il segmento entro un’istanza di una dimensione.

L'impostazione di una clausola "Within Dimension" tra le regole consente a un segmento di limitare i dati alle sequenze in cui tale clausola è soddisfatta. Vedere l'esempio seguente, in cui il vincolo è impostato su "Entro 1 pagina":

![](assets/sequence-filter4.png)

| Se risultato... | Sequenza |
|--- |--- |
| Corrisponde | A poi B |
| Non corrisponde | <br> A poi C poi B (perché B non era all'interno di 1 pagina di A)**** Nota:  Se si elimina la restrizione della dimensione, "A then B" e "A then C then B" corrisponderanno entrambi. |

## Sequenza Visualizzazione pagina semplice

Identificare i visitatori che hanno visualizzato una pagina e un’altra pagina. I dati a livello di hit filtreranno questa sequenza indipendentemente dalle sessioni di visita precedenti, passate o intermedie o dall'ora o dal numero di visualizzazioni di pagina che si verificano tra due.

**Esempio**: Il visitatore ha visualizzato la pagina A, quindi la pagina B nella stessa o in un'altra visita.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo del segmento.

1. I visitatori di un sito sportivo visualizzano la pagina di destinazione del calcio e quindi visualizzano la pagina di destinazione del basket in ordine sequenziale, ma non necessariamente nella stessa visita. Questo provoca una campagna per trasmettere i contenuti della pallacanestro ai telespettatori durante la stagione calcistica.
1. Il rivenditore di automobili identifica una relazione tra coloro che accedono alla pagina di fedeltà del cliente e poi vanno alla pagina video in qualsiasi momento durante la visita o un'altra visita.

**Crea questo segmento**

È possibile nidificare due regole di pagina all'interno di un [!UICONTROL Visitor] contenitore di livello principale e sequenziare gli hit di pagina utilizzando l' [!UICONTROL THEN] operatore .

![](assets/segment_sequential_1.png)

## Sequenza di visitatori tra le visite

Identificare i visitatori che sono usciti da una campagna e sono quindi tornati alla sequenza di visualizzazioni di pagina in un’altra sessione.

**Esempio**: Il visitatore ha visualizzato la pagina A in una visita, quindi ha visualizzato la pagina B in un’altra visita.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Visitatori alla pagina Sport di un sito di notizie, quindi rivede la pagina Sport in un'altra sessione.
* Un rivenditore di vestiti vede una relazione tra i visitatori che accedono a una pagina di destinazione in una sessione e poi vanno direttamente alla pagina di estrazione in un'altra sessione.

**Crea questo segmento**

In questo esempio vengono nidificati due **[!UICONTROL Visit]** contenitori all'interno del **[!UICONTROL Visitor]** contenitore di primo livello e il segmento viene sequenze utilizzando l' [!UICONTROL THEN] operatore.

![](assets/visitor_seq_across_visits.png)

## Sequenza a livello misto

Identificare i visitatori che visualizzano due pagine in un numero indeterminato di visite, ma poi una terza pagina in una visita separata.

**Esempio**: I visitatori visitano la pagina A e quindi la pagina B in una o più visite, seguita da una visita alla pagina C in una visita separata.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* I visitatori visitano prima un sito di notizie e poi visualizzano la pagina sportiva nella stessa visita. In un'altra visita il visitatore visita la pagina meteo.
* Il rivenditore definisce i visitatori che accedono alla pagina Principale e quindi alla pagina Account personale. In un’altra visita, visita la pagina Visualizza carrello.

**Crea questo segmento**

1. Rilasciate due dimensioni pagina dai riquadri a sinistra all’interno di un contenitore di [!UICONTROL Visitor] livello principale.
1. Aggiungere l'operatore THEN tra di essi.
1. Fate clic **[!UICONTROL Options]** &gt; **[!UICONTROL Add container]** , quindi aggiungete un [!UICONTROL Visit] contenitore sotto il [!UICONTROL Visitor] livello e create una sequenza utilizzando l' [!UICONTROL THEN] operatore.

![](assets/mixed_level_checkpoints.png)

## Aggrega contenitori

L'aggiunta di più [!UICONTROL Hit] contenitori all'interno di un [!UICONTROL Visitor] contenitore consente di utilizzare gli operatori appropriati tra lo stesso tipo di contenitori e di utilizzare regole e dimensioni quali Pagina e Numero visita per definire la visualizzazione della pagina e fornire una dimensione di sequenza all'interno del [!UICONTROL Hit] contenitore. L’applicazione della logica a livello di Hit consente di vincolare e combinare le corrispondenze a uno stesso livello di hit all’interno del [!UICONTROL Visitor] contenitore per creare una serie di tipi di segmenti.

**Esempio**: I visitatori hanno visitato la pagina A dopo il primo hit nella sequenza di visualizzazioni di pagina (pagina D nell’esempio), quindi hanno visitato la pagina B o la pagina C, senza tenere conto del numero di visite.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Identificare i visitatori che accedono alla pagina di destinazione Principale in una visita, quindi visualizzare la pagina di abbigliamento Uomo in un'altra visita, quindi visualizzare la pagina di destinazione Donna o Bambini in un'altra visita.
* Un e-zine cattura i visitatori che accedono alla home page in una visita, alla pagina Sport in un'altra visita e alla pagina Opinioni in un'altra visita.

**Crea questo segmento**

1. Selezionate il [!UICONTROL Visitor] contenitore come contenitore di primo livello.
1. Aggiungete contenitori a due [!UICONTROL Hit]livelli, una dimensione con una dimensione numerica appropriata unita allo stesso [!UICONTROL Hit] livello dall' [!UICONTROL AND] operatore e [!UICONTROL OR] .
1. All'interno del [!UICONTROL Visit] contenitore, aggiungere un altro [!UICONTROL Hit] contenitore e nidificare altri due [!UICONTROL Hit] contenitori uniti a un [!UICONTROL OR] operatore o [!UICONTROL AND] .

   Sequenza di questi [!UICONTROL Hit] contenitori nidificati con l' [!UICONTROL THEN] operatore .

![](assets/aggregate_checkpoints2.png)

## "Nidificazione" nei segmenti sequenziali

Posizionando i punti di controllo sia a livello [!UICONTROL Visit] che [!UICONTROL Hit] a livello, potete vincolare il segmento a soddisfare i requisiti all’interno di una visita specifica, nonché a un hit specifico.

**Esempio**: Il visitatore ha visitato la pagina A e quindi la pagina B nella stessa visita. In una nuova visita, il visitatore è quindi passato alla pagina C.

**Crea questo segmento**

1. Sotto un contenitore di [!UICONTROL Visit] livello principale, trascinate in due dimensioni di pagina.
1. Selezionate entrambe le regole, fate clic su **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]** e modificatelo in un [!UICONTROL Visit] contenitore.
1. Unitevi a loro con un [!UICONTROL THEN] operatore.
1. Crea un contenitore Hit come peer per il [!UICONTROL Visit] contenitore e trascina in una dimensione di pagina.
1. Unisci la sequenza nidificata nel [!UICONTROL Visit] contenitore con il [!UICONTROL Hit] contenitore utilizzando un altro [!UICONTROL THEN] operatore.

![](assets/nesting_sequential_seg.png)

## Escludi hit

Le regole di segmento includono tutti i dati a meno che non escludiate [!UICONTROL Visitor]specificamente [!UICONTROL Visit]o [!UICONTROL Hit] i dati utilizzando la [!UICONTROL Exclude] regola. Consente di ignorare i dati comuni e creare segmenti con maggiore attenzione. Oppure consente di creare segmenti, escludendo i gruppi trovati, per identificare il set di dati rimanente, ad esempio la creazione di una regola che includa i visitatori di successo che hanno effettuato gli ordini e che li escluda per identificare i "non acquirenti". Tuttavia, nella maggior parte dei casi, è meglio creare regole che escludano valori ampi piuttosto che cercare di utilizzare la [!UICONTROL Exclude] regola per eseguire il targeting di valori specifici.

Ad esempio:

* **Escludi pagine**. Utilizza una regola del segmento per eliminare una pagina specifica (ad esempio *`Home Page`*) da un rapporto, creare una regola Hit in cui la pagina sia uguale a "Home Page", quindi escluderla. Questa regola include automaticamente tutti i valori eccetto Pagina iniziale.
* **Escludi i domini** di riferimento. Utilizza una regola che include solo i domini di riferimento da Google.com ed esclude tutti gli altri.
* **Identificare i non acquirenti**. Identificare quando gli ordini sono maggiori di zero e quindi escludere il [!UICONTROL Visitor].

L' [!UICONTROL Exclude] operatore può essere utilizzato per identificare una sequenza in cui visite o hit specifici non vengono eseguiti dal visitatore. [!UICONTROL Exclude Checkpoints] può essere incluso anche all'interno di un gruppo [](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112)logico.

### Escludi tra punti di controllo

Applica la logica per segmentare i visitatori in cui un checkpoint non si è verificato in modo esplicito tra altri due checkpoint.

**Esempio**: Visitatori che hanno visitato la pagina A e quindi la pagina C, ma non la pagina B.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Visitatori a una pagina LifeStyle e poi alla sezione Theatre senza andare alla pagina Arti.
* Un rivenditore automatico vede una relazione tra coloro che visitano la pagina di destinazione principale e poi vanno direttamente alla campagna Nessun interesse senza andare alla pagina Veicolo.

**Crea questo segmento**

Create un segmento come fareste per un segmento sequenziale semplice, misto o nidificato, quindi impostate l' [!UICONTROL EXCLUDE] operatore per l'elemento contenitore. L'esempio seguente è un segmento di aggregazione in cui i tre [!UICONTROL Hit] contenitori vengono trascinati nel quadro, l' [!UICONTROL THEN] operatore assegnato per partecipare alla logica del contenitore, quindi escludete il contenitore della visualizzazione della pagina centrale per includere solo i visitatori che sono passati dalla pagina A alla pagina C nella sequenza.

![](assets/exclude_between_checkpoints.png)

### Escludi all'inizio della sequenza

Se il punto di controllo di esclusione si trova all'inizio di un segmento sequenziale, si assicura che la visualizzazione della pagina esclusa non sia avvenuta prima del primo hit non escluso.

**Esempio**: Il visitatore ha visitato la pagina A e non la pagina B.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Visitatori che hanno visitato la pagina A e non hanno visitato la pagina B.
* Un ristorante vuole vedere utenti inveterati che evitano la pagina di destinazione principale e vanno direttamente alla pagina Ordina per uscire.

**Crea questo segmento**

Crea due contenitori Hit separati all’interno di un contenitore Visitor di livello principale. Quindi, impostare l' [!UICONTROL EXCLUDE] operatore per il primo contenitore.

![](assets/exclude_beginning_sequence.png)

### Escludi alla fine della sequenza

Se il checkpoint di esclusione si trova alla fine di una sequenza, assicura che il checkpoint non si sia verificato tra l’ultimo checkpoint non escluso e la fine della sequenza di visitatori.

**Esempio**: I visitatori visitano la pagina A e non hanno visitato la pagina B nelle visite correnti o successive.

**Casi d'uso**

Di seguito sono riportati alcuni esempi di utilizzo di questo tipo di segmento:

* Visitatori che hanno visitato la pagina A e non hanno visitato la pagina B.
* Un ristorante vuole vedere utenti inveterati che evitano la pagina di destinazione principale e vanno direttamente alla pagina Ordina per uscire.

**Crea questo segmento**

Create un segmento di sequenza semplice trascinando due [!UICONTROL Hit] contenitori sul quadro e collegandoli utilizzando l' [!UICONTROL THEN] operatore. Quindi assegnate l' [!UICONTROL EXCLUDE] operatore al secondo [!UICONTROL Hit] contenitore della sequenza.

![](assets/exclude_end_sequence.png)

## Contenitori del gruppo Logica

I contenitori del gruppo logico sono necessari per raggruppare le condizioni in un singolo punto di controllo del segmento sequenziale. Il contenitore del gruppo logico speciale è disponibile solo nella segmentazione sequenziale, per assicurarsi che le sue condizioni siano soddisfatte dopo qualsiasi checkpoint sequenziale precedente e prima di qualsiasi checkpoint sequenziale successivo. Le condizioni all'interno del punto di controllo del gruppo logico stesso possono essere soddisfatte in qualsiasi ordine. Per contro, i contenitori non sequenziali (hit, visit, visitor) non richiedono che le loro condizioni siano soddisfatte all'interno della sequenza globale, generando risultati non intuitivi se utilizzati con un operatore THEN.
Il [!UICONTROL Logic Group] contenitore è stato progettato per trattare *diversi checkpoint come un gruppo*, *senza alcun ordine* tra i checkpoint raggruppati. In altre parole, non ci interessa l'ordine dei checkpoint all'interno di quel gruppo. Ad esempio, non è possibile nidificare un [!UICONTROL Visitor] contenitore all'interno di un [!UICONTROL Visitor] contenitore. È invece possibile nidificare un [!UICONTROL Logic Group] contenitore all’interno di un [!UICONTROL Visitor] contenitore con checkpoint di [!UICONTROL Visit]livello e [!UICONTROL Hit]livello specifici.

>[!NOTE]
>
>Un [!UICONTROL Logic Group] può essere definito solo in un segmento sequenziale, il che significa che l' [!UICONTROL THEN] operatore è utilizzato all'interno dell'espressione.

| Gerarchia contenitore | Illustrazione | Definizione |
|---|---|---|
| Gerarchia contenitore standard | ![](assets/nesting_container.png) | All’interno del [!UICONTROL Visitor] contenitore, i contenitori [!UICONTROL Visit] e [!UICONTROL Hit] i contenitori sono nidificati in sequenza per estrarre segmenti in base agli hit, al numero di visite e al visitatore. |
| Gerarchia contenitore logica | ![](assets/logic_group_hierarchy.png) | La gerarchia di contenitori standard è necessaria anche all'esterno del [!UICONTROL Logic Group] contenitore. Ma all'interno del [!UICONTROL Logic Group] contenitore, i checkpoint non richiedono un ordine o una gerarchia stabiliti; questi checkpoint devono semplicemente essere soddisfatti dal visitatore in qualsiasi ordine. |

I gruppi logici possono sembrare scoraggianti: ecco alcune best practice per utilizzarli:

**Gruppo logico o contenitore Hit/Visit?**
Se si desidera raggruppare i checkpoint sequenziali, il "contenitore" è Logic Group. Tuttavia, se tali checkpoint sequenziali devono verificarsi all'interno di un singolo hit o di un ambito di visita, è necessario un contenitore "hit" o "visit". (Naturalmente, l'hit non ha senso per un gruppo di checkpoint sequenziali, quando un hit può accreditare non più di un checkpoint).

**I gruppi logici semplificano la creazione di segmenti sequenziali?**
Sì, possono. Supponiamo che tu stia cercando di rispondere a questa domanda: Un visitatore ha visto le pagine B, C o D dopo la pagina A? È possibile creare questo segmento senza un contenitore del gruppo logico, ma è complesso e laborioso:
Contenitore visitatori [Pagina A POI Pagina B POI Pagina C POI Pagina D] o Contenitore visitatore [Pagina A POI Pagina B POI Pagina D POI Pagina C] o Contenitore visitatori [Pagina A POI Pagina C POI Pagina B POI Pagina D] o Contenitore visitatori [Pagina A POI Pagina C POI Pagina D POI Pagina] O Contenitore visitatori [A IT Pagina D POI Pagina B POI Pagina C] [o Contenitore visitatori Pagina A POI Pagina D POI Pagina C POI Pagina B]

Un contenitore di gruppo logico semplifica notevolmente il segmento, come illustrato di seguito:

![](assets/logic-grp-example.png)


### Crea un segmento del gruppo logico {#section_A5DDC96E72194668AA91BBD89E575D2E}

Come altri contenitori, [!UICONTROL Logic Group] i contenitori possono essere costruiti in più modi all'interno del [!UICONTROL Segment Builder]. Questo è il modo preferito per nidificare [!UICONTROL Logic Group] i contenitori:

1. Trascina dimensioni, eventi o segmenti dai riquadri a sinistra.
1. Cambia il contenitore superiore in [!UICONTROL Visitor] contenitore.
1. Modificare l'operatore [!UICONTROL AND] o [!UICONTROL OR] inserito per impostazione predefinita nell'operatore THEN.
1. Selezionate i [!UICONTROL Hit] contenitori (Dimensione, Evento o Elemento) e fate clic su **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]**.
1. Fate clic sull'icona del contenitore e selezionate **[!UICONTROL Logic Group]**.  ![](assets/logic_group_checkpoints.png)
1. Ora è possibile impostare l' [!UICONTROL Hit] interno del [!UICONTROL Logic Group] contenitore senza considerare la gerarchia.

### Checkpoint del gruppo logico in qualsiasi ordine

L’ [!UICONTROL Logic Group] utilizzo consente di soddisfare le condizioni all’interno del gruppo che risiedono al di fuori della sequenza. Questo consente di creare segmenti in cui un [!UICONTROL Visit] [!UICONTROL Hit] contenitore o un contenitore si verifica indipendentemente dalla gerarchia normale.

**Esempio**: I visitatori che hanno visitato la pagina A, hanno visitato la pagina B e la pagina C in qualsiasi ordine.

**Crea questo segmento**

Le pagine B e C sono nidificate in un [!UICONTROL Logic Group] contenitore all'interno del [!UICONTROL Visitor] contenitore esterno. Il [!UICONTROL Hit] contenitore per A è seguito dal [!UICONTROL Logic Group] contenitore con B e C identificato utilizzando l' [!UICONTROL AND] operatore. Poiché si trova in [!UICONTROL Logic Group], la sequenza non è definita e premendo entrambe le pagine B e C in un qualsiasi ordine l'argomento risulta vero.

![](assets/logic_group_any_order2.png)

**Un altro esempio**: Visitatori che hanno visitato la pagina B o la pagina C, quindi visitato la pagina A:

![](assets/logic_group_any_order3.png)

Il segmento deve corrispondere al lease di uno dei checkpoint del gruppo logico (B o C). Inoltre, le condizioni di gruppo logico possono essere soddisfatte nello stesso hit o tra più hit&#x200B;.

### Prima corrispondenza del gruppo logico

L’ [!UICONTROL Logic Group] utilizzo consente di soddisfare le condizioni all’interno del gruppo che risiedono al di fuori della sequenza. In questo primo segmento di corrispondenza non ordinato, le [!UICONTROL Logic Group] regole sono identificate per prime come una visualizzazione di pagina della pagina B o della pagina C, quindi come visualizzazione richiesta della pagina A.

**Esempio**: Visitatori che hanno visitato la pagina B o la pagina C, quindi hanno visitato la pagina A.

**Crea questo segmento**

Le dimensioni delle pagine B e C sono raggruppate all'interno di un [!UICONTROL Logic Group] contenitore con l' [!UICONTROL OR] operatore selezionato, quindi il [!UICONTROL Hit]contenitore che identifica come valore la visualizzazione della pagina A.

![](assets/logic_group_1st_match.png)

### Logic Group exclude AND

Creare segmenti utilizzando le [!UICONTROL Logic Group] visualizzazioni di più pagine aggregate per definire quali pagine devono essere hit mentre altre pagine non sono state specificamente visualizzate. ****

**Esempio**: Il visitatore ha visitato la pagina A, quindi non ha visitato esplicitamente la pagina B o C, ma la pagina hit D.

**Crea questo segmento**

Crea questo segmento trascinando Dimensioni, Eventi e Segmenti predefiniti dai riquadri a sinistra. Vedere [Creazione di un segmento](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112)di gruppo logico.

Dopo aver nidificato i valori all’interno del [!UICONTROL Logic Group], fate clic sul **[!UICONTROL Exclude]** pulsante all’interno del [!UICONTROL Logic Group] contenitore.

![](assets/logic_exclude_and.png)

### Esclusione gruppo logica OR

Creare segmenti utilizzando le [!UICONTROL Logic Group] visualizzazioni di più pagine aggregate per definire quali pagine devono essere hit mentre altre pagine non sono state specificamente visualizzate.

**Esempio**: Visitatori che hanno visitato la pagina A, ma non la pagina B o la pagina C prima della pagina A.

**Crea questo segmento**

Le pagine B e C iniziali sono identificate in un [!UICONTROL Logic Group] contenitore escluso, quindi seguite da un hit per la pagina A da parte del visitatore.

Crea questo segmento trascinando Dimensioni, Eventi e Segmenti predefiniti dai riquadri a sinistra.

Dopo aver nidificato i valori all’interno del [!UICONTROL Logic Group], fate clic sul **[!UICONTROL Exclude]** pulsante all’interno del [!UICONTROL Logic Group] contenitore.

![](assets/logic_exclude_or.png)

## Creazione di segmenti temporali e time-after

Utilizzate gli operatori [!UICONTROL Within] e [!UICONTROL After] gli operatori incorporati nell'intestazione di ciascun contenitore per definire ora, eventi e conteggio.

![](assets/then_within_operators.png)

È possibile limitare la corrispondenza a una determinata durata utilizzando i [!UICONTROL Within] contenitori e [!UICONTROL After] specificando una granularità e un conteggio. L' [!UICONTROL Within] operatore viene utilizzato per specificare un limite massimo per il periodo di tempo tra due checkpoint. L' [!UICONTROL After] operatore viene utilizzato per specificare un limite minimo per il periodo di tempo tra due checkpoint.

### Operatori After e Within {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

La durata è specificata da una singola lettera maiuscola che rappresenta la granularità seguita da un numero che rappresenta il conteggio di ripetizioni della granularità.

**[!UICONTROL Within]** include l'endpoint (minore o uguale a).

**[!UICONTROL After]** non include l'endpoint (maggiore di).

| Operatori | Descrizione |
|--- |--- |
| DOPO | L'operatore After viene utilizzato per specificare un limite minimo per il periodo di tempo tra due checkpoint. Quando si impostano i valori Dopo, il limite di tempo inizia quando il segmento viene applicato. Ad esempio, se l'operatore After è impostato su un contenitore per identificare i visitatori che visitano la pagina A ma non tornano alla pagina B fino a dopo un giorno, quel giorno inizierà quando il visitatore esce dalla pagina A.  Affinché il visitatore sia incluso nel segmento, devono trascorrere almeno 1440 minuti (un giorno) dopo aver lasciato la pagina A per visualizzare la pagina B. |
| ALL'INTERNO | L'operatore Within viene utilizzato per specificare un limite massimo per il periodo di tempo tra due checkpoint. Ad esempio, se l'operatore Within è impostato su un contenitore per identificare i visitatori che visitano la pagina A e poi ritornano a visitare la pagina B entro un giorno, quel giorno inizierà quando il visitatore esce dalla pagina A. Per essere incluso nel segmento, il visitatore avrà un tempo massimo di un giorno prima di aprire la pagina B.   Per includere il visitatore nel segmento, la visita alla pagina B deve avvenire entro un massimo di 1440 minuti (un giorno) dopo aver lasciato la pagina A per visualizzare la pagina B. |
| DOPO/INTERNO | Quando si utilizzano gli operatori After e Within, è importante comprendere che entrambi gli operatori inizieranno e finiranno in parallelo, non in sequenza.   Ad esempio, se si crea un segmento con il contenitore impostato su:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Allora le condizioni per identificare i visitatori nel segmento sono soddisfatte solo tra 1 e 2 settimane. Entrambe le condizioni vengono applicate dal momento dell'hit della prima pagina. |

### Utilizzo dell'operatore After

* Ora dopo consente di monitorare per anno, mese, giorno, ora e minuto per far corrispondere le visite.
* Time After può essere applicato solo a un [!UICONTROL Hit] contenitore, perché è l'unico livello per il quale è definita tale granularità fine.

**Esempio**: I visitatori che hanno visitato la pagina A hanno visitato la pagina B solo dopo 2 settimane.***

![](assets/time_between_after_operator.png)

**Crea il segmento**: Questo segmento viene creato aggiungendo un [!UICONTROL Visitor] contenitore con due [!UICONTROL Hit] contenitori. È quindi possibile impostare l' [!UICONTROL THEN] operatore, aprire il menu a discesa [!UICONTROL AFTER] dell'operatore e impostare il numero di settimane.

![](assets/after_operator.png)

**Corrisponde**

Se viene indicato "Dopo 2 settimane", se un hit per la pagina A si verifica il 1° giugno 2019, alle 00:01, l'hit seguente per la pagina B corrisponderà a condizione che venga prima del 15 giugno 2019 00:01 (14 giorni dopo).

| Hit A | Hit B | Corrispondente |
|--- |--- |--- |
| **Un** hit: 1 giugno 2019 00:01 | **B** hit: 15 giugno 2019 00:01 | **** Corrisponde: Questo vincolo di tempo corrisponde perché è Dopo il 1 giugno 2019 (due settimane). |
| **Un** hit: 1 giugno 2019 00:01 | **B** hit: 8 giugno 2019 00:01 B hit: 15 giugno 2019 00:01 | **** Non corrisponde: Il primo hit sulla pagina B non corrisponde perché è in conflitto con il vincolo che lo richiede dopo due settimane. |

### Utilizzare l'operatore Within

* [!UICONTROL Within] consente di monitorare per anno, mese, giorno, ora e minuto per far corrispondere le visite.
* [!UICONTROL Within] può essere applicato solo a un [!UICONTROL Hit] contenitore perché è l'unico livello per il quale è definita tale granularità fine.

>[!IMPORTANT]
>
>In una clausola “within” (entro), tra istruzioni THEN, è possibile aggiungere, ad esempio, “within 1 search keyword instance”, “within 1 eVar 47 instance”. In questo modo si vincola il segmento entro un’istanza di una dimensione.

**Esempio**: I visitatori che hanno visitato la pagina A hanno quindi visitato la pagina B in 5 minuti.

![](assets/time_between_within_operator.png)

**Crea il segmento**: Questo segmento viene creato aggiungendo un [!UICONTROL Visitor] contenitore, quindi trascinandolo con due [!UICONTROL Hit] contenitori. È quindi possibile impostare l' [!UICONTROL THEN] operatore, aprire l'elenco a discesa dell' [!UICONTROL AFTER] operatore e impostare l'intervallo: hit, visualizzazioni di pagina, visite, minuti, ore, giorni, settimane, mesi, trimestri o anni.

![](assets/within_operator.png)

**Corrisponde**

Le corrispondenze devono verificarsi entro il limite di tempo. Per l'espressione , se un visitatore accede alla pagina A a 00:01, l'hit seguente alla pagina B corrisponderà a condizione che sia attivato o precedente alle 00:06 (cinque minuti dopo, incluso lo stesso minuto). Anche gli hit nello stesso minuto corrisponderanno.

### Gli operatori Within e After

Utilizzate [!UICONTROL Within] e [!UICONTROL After] per fornire un endpoint massimo e minimo a entrambe le estremità di un segmento.

**Esempio**: I visitatori che hanno visitato la pagina A hanno quindi visitato la pagina B dopo 2 settimane, ma entro 1 mese.

![](assets/time_between_using_both_operators.png)

**Crea il segmento**: Crea il segmento sequenziando due [!UICONTROL Hit] contenitori all’interno di un [!UICONTROL Visitor] contenitore. Quindi impostate gli [!UICONTROL After] operatori e [!UICONTROL Within] .

![](assets/within_after_together.png)

**Corrisponde**

Tutti i visitatori che hanno raggiunto la pagina A il 1° giugno 2019 ritornano dopo il 15 giugno 2019 00:01, ma *prima* del 1° luglio 2019 sono inclusi nel segmento. Confronta con [Time Between Exclusions](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_C5CB0A391B7C4AC8A95B9724A14E28E8)(Tempo tra le esclusioni).

Gli operatori [!UICONTROL After] e [!UICONTROL Within] possono essere utilizzati insieme per definire un segmento sequenziale.

![](assets/time_between_within_after.png)

In questo esempio viene illustrata una seconda visita alla pagina B dopo due settimane, ma entro un mese.
