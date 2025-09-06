---
title: eVar di merchandising e metodi di ricerca dei prodotti
description: Approfondisci i concetti alla base delle eVar di merchandising e come vengono elaborati e allocati i dati.
feature: Admin Tools
role: Admin
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '5248'
ht-degree: 86%

---

# eVar di merchandising e metodi di ricerca dei prodotti

Questo documento molto dettagliato spiega i concetti alla base delle eVar di merchandising, che elaborano e allocano i dati in modo diverso rispetto alle eVar standard. Inoltre, spiega la correlazione tra le eVar di merchandising e i metodi di ricerca dei prodotti.

## Panoramica

Utilizzando le eVar di merchandising è possibile allocare le attività di successo ai valori acquisiti dalle eVar a livello di *prodotto* anziché a livello di *visita/ordine*.

Nella maggior parte dei siti web di vendita al dettaglio esistono diversi modi per trovare i prodotti. I metodi seguenti sono considerati fondamentali da Adobe, e pertanto consigliamo a tutti i clienti retail di tenerne traccia in Adobe Analytics:

* Parole chiave per la ricerca interna
* Codici di tracciamento di campagne interne
* Categorie di merchandising/navigazione
* Link di cross-selling

Ai fini del presente documento, abbiniamo alcune eVar a queste soluzioni come segue:

* eVar2: Parole chiave per la ricerca interna
* eVar3: Codici di tracciamento di campagne interne
* eVar4: Categorie di merchandising/navigazione
* eVar5: link di cross-selling

Possiamo utilizzare un’ulteriore eVar per misurare le prestazioni di tutti i metodi di ricerca dei prodotti in relazione tra loro. Oltre ai metodi di ricerca descritti in precedenza, l’eVar include nel confronto altri metodi di ricerca, ad esempio i link da siti web esterni alle pagine dei dettagli dei prodotti.

* eVar1: Metodi di ricerca dei prodotti

Invece di configurare queste variabili come eVar standard, configurale come eVar di merchandising.

Per dimostrare come si impostano queste variabili, ecco un esempio in cui un visitatore decide di usare la funzione di ricerca del sito e cerca il termine (parola chiave) “sandals” per trovare un prodotto. Nella pagina dei risultati della ricerca per parola chiave, devi acquisire dati in almeno due eVar:

* `eVar2` corrisponde alla parola chiave utilizzata nella ricerca (“sandals”).
* `eVar1` corrisponde al metodo di ricerca del prodotto utilizzato (“internal keyword search”, ricerca interna per parola chiave).

Se imposti queste due variabili su questi valori specifici, sai che il visitatore, per trovare un prodotto, utilizza il termine “sandals” nella ricerca interna per parola chiave. Allo stesso tempo, sai che il visitatore non utilizza gli altri metodi di ricerca dei prodotti per trovare i prodotti (ad esempio, non sfoglia le categorie di prodotti esattamente nello stesso momento in cui esegue una ricerca per parola chiave). Per garantire la corretta allocazione per prodotto, i metodi non utilizzati non devono ricevere alcun merito per la ricerca di un prodotto trovato tramite una ricerca interna per parole chiave. Pertanto, devi inserire nel codice una logica (ad esempio AppMeasurement, Adobe Experience Platform Web SDK e così via) che imposti automaticamente le eVar associate agli altri metodi di ricerca su un valore di tipo &quot;non-finding method&quot;.

Ad esempio, quando un utente cerca prodotti utilizzando la parola chiave &quot;sandals&quot;, la logica del codice Analytics deve impostare le variabili come segue, nella pagina dei risultati della ricerca per parola chiave interna:

* eVar2=&quot;sandals&quot;: è stata utilizzata la parola chiave “sandals” nella ricerca interna per parola chiave
* eVar1=&quot;internal keyword search&quot;: è stato utilizzato il metodo di ricerca interna per parola chiave
* eVar3=&quot;non-internal campaign&quot;: non è stata utilizzata una campagna interna per accedere alla pagina dei risultati della ricerca
* eVar4=&quot;non-browse&quot;: non è stato eseguito l’accesso a una categoria di navigazione nella pagina dei risultati della ricerca
* eVar5=&quot;non-cross-sell&quot;: non è stato fatto clic su un link di cross-selling nella pagina dei risultati di ricerca

## Impostazioni per le eVar di merchandising

Di seguito sono elencate le diverse impostazioni che puoi utilizzare con le eVar di merchandising. La schermata seguente proviene da Report Suite Manager. Per accedervi, passa a [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Conversion Variables] > [!UICONTROL Add new] > [!UICONTROL Enable Merchandising].

![eVar di merch](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/merch-evars1.png)

Ulteriori informazioni su queste impostazioni sono disponibili nelle sezioni sotto la tabella.

| Impostazione | Descrizione |
|--- | --- |
| Nome | Nome o dimensione di reporting a cui la variabile deve essere associata. Se `eVar1` deve acquisire i metodi di ricerca dei prodotti, il campo Name (Nome) per `eVar1` deve essere impostato su “Product Finding Methods” (Metodi di ricerca dei prodotti). |
| Merchandising | Tipo di sintassi che verrà utilizzato per acquisire i valori delle eVar di merchandising |
| Allocazione | Consente di determinare il valore dell’eVar di merchandising a cui assegnare il merito quando si verifica un evento di successo. |
| Expire After (Scade dopo) | Determina quando le associazioni tra prodotti e eVar di merchandising esistenti non devono più essere effettive. |
| Type (Tipo) | Tipo di dati raccolti nell’eVar di merchandising |
| Merchandising Binding Event (Evento di binding merchandising) | Eventi che determinano quando un prodotto deve essere associato a un valore eVar di merchandising |
| Reset (Ripristina) | Un trigger che ripristina tutti i dati di backend per l’eVar a quel punto |
| Enable Merchandising (Abilita merchandising) | Flag che deve essere “Abilitato” per trasformare un eVar standard in un eVar Merchandising |

### Enable Merchandising (Abilita merchandising)

Quando l’impostazione “Abilita merchandising” è abilitata, in Report Suite Manager vengono visualizzate tutte le impostazioni come descritto di seguito. Quando l’impostazione “Abilita merchandising” è disabilitata, sono disponibili solo le impostazioni eVar standard.

### Merchandising

Questa opzione non è disponibile per le eVar standard. L’impostazione [!UICONTROL Merchandising] consente di scegliere [!UICONTROL Conversion Variable Syntax] o [!UICONTROL Product Syntax] come metodo per acquisire il valore dell’eVar merchandising.

**[!UICONTROL Conversion Variable Syntax]** significa che si imposta il valore eVar nella propria variabile. Ad esempio, con la sintassi per variabile di conversione, il valore `eVar1` &quot;internal keyword search&quot; (ricerca interna per parole chiave) viene impostato come segue nel codice della pagina (o nel codice di AppMeasurement, di Adobe Experience Platform Web SDK e così via):

`s.eVar1="internal keyword search";`

Con **[!UICONTROL Product Syntax]**, tuttavia, l’eVar è impostata solo nella variabile dei prodotti di Adobe Analytics. La variabile dei prodotti di Analytics è suddivisa in sei diverse parti per prodotto:

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Category] e [!UICONTROL Name] identificano il prodotto specificato.
* [!UICONTROL Quantity] e [!UICONTROL Revenue] sono utili quando si tiene traccia di un acquisto di prodotto.
* [!UICONTROL Events] è utile per registrare valori di evento incrementali o di valuta personalizzati che non devono essere conteggiati come ricavi (come spedizione, sconti, ecc.)

Le eVar di merchandising configurate per l’utilizzo della Product Syntax (Sintassi prodotto) sono impostate all’interno della parte finale della variabile dei prodotti. Ad esempio, supponiamo che un visitatore abbia utilizzato una ricerca interna per parole chiave per trovare l’ID prodotto “12345”. Il modo basato sulla sintassi prodotto per impostare eVar1 in questo esempio sarà simile al seguente:

`s.products=";12345;;;;eVar1=internal keyword search";`

Tieni presente che esistono ancora segnaposto delimitati da punti e virgola per le parti di quantità, ricavi ed eventi della variabile prodotti.  Senza questi segnaposto, l’impostazione `eVar1` della ricerca interna per parole chiave verrebbe completamente ignorata.

### Allocazione

Il termine “Allocazione” per le eVar di merchandising è fuorviante, soprattutto per le eVar di merchandising che utilizzano la sintassi per variabile di conversione. Tutte le eVar standard possono avere una propria impostazione di allocazione individuale. Tuttavia, le eVar di merchandising con sintassi per variabile di conversione utilizzano solo l’impostazione di allocazione “Most Recent (Last)” (Più recente, ultimo), indipendentemente dalle impostazioni di allocazione visualizzate in Report Suite Manager.

Comprendere cosa fa questa impostazione significa comprendere la differenza tra l’allocazione eVar e il binding eVar di merchandising. Per le eVar di merchandising, “Binding eVar di merchandising” è più appropriato per questa impostazione “Allocazione”.

#### Impostazione di allocazione standard di eVar

Ogni volta che un’eVar con sintassi standard viene raccolta da una richiesta di immagine, i server di elaborazione Adobe Analytics inseriscono dati in un’altra colonna del database, denominata `post_evar`. Poiché le eVar sono intese come persistenti (nella maggior parte dei casi scadono a un certo punto oltre l’hit corrente), i server impostano questa colonna `post_evar` su ogni richiesta di immagine successiva. È impostata come ultimo valore passato nell’eVar corrispondente. Per le eVar standard, quando si verifica un evento di successo, Adobe Analytics utilizza la colonna `post_evar` al posto della colonna eVar standard per determinare il valore eVar a cui deve essere dato il merito per l’evento.

Per le eVar standard, l’impostazione Allocazione determina se il primo o l’ultimo valore eVar raccolto durante un determinato periodo verrà inserito nella colonna `post_evar`. Se l’impostazione Allocazione per un’eVar standard è “Original Value (First)” (Valore originale, primo), il primo valore eVar raccolto dal visitatore viene inserito nella colonna `post_evar` per tutte le richieste di immagini successive. Questo continua per tutte le richieste future inviate dal browser del visitatore fino alla scadenza dell’eVar per l’impostazione “Expire After” (Scade dopo).

Se l’impostazione Allocazione di un’eVar standard è uguale a “Most Recent (Last)”(Più recente, ultimo), il valore di eVar più recente raccolto dal visitatore viene inserito nella colonna `post_evar` per tutte le richieste di immagini successive. L’allocazione “Most Recent (Last)” (Più recente, ultima) implica che il valore `post_evar` cambia ogni volta che il relativo eVar corrispondente viene impostato su un nuovo valore in una richiesta di immagine. L’allocazione “Original Value (First)” (Valore originale, primo) implica che la colonna `post_evar` non cambia da un hit all’altro anche se l’eVar corrispondente potrebbe essere impostata su un valore diverso in una futura richiesta di immagine.

#### Impostazione di allocazione (binding) di Merchandising eVar

Come accennato in precedenza, per tutte le eVar di merchandising con sintassi per variabile di conversione è disponibile solo l’allocazione &quot;Most Recent (Last)&quot; (Più recente, ultimo). Pertanto, l’impostazione Allocazione per le eVar di merchandising non determina quali valori vengono inseriti nella colonna post_evar mentre un visitatore continua a utilizzare il sito. Questa impostazione determina piuttosto il valore di eVar associato a un prodotto e il modo in cui tali prodotti riassegnano i propri eventi di successo ai valori di eVar a cui sono associati.

Quando un’impostazione di allocazione di eVar merchandising (ovvero binding) è impostata su &quot;Original Value (First)&quot; (Valore originale, primo), si verifica quanto segue: tutti i prodotti impostati accanto alla colonna post_evar e che non sono stati precedentemente associati all’eVar &quot;pre-elaborato&quot; corrispondente della colonna post_evar saranno associati al valore contenuto nella colonna post_evar.  Il binding tra il valore di eVar e il prodotto non cambia mai fino alla scadenza dell’eVar per l’impostazione &quot;Expire After&quot; (Scade dopo) nelle impostazioni della suite di rapporti.

Ogni volta che una richiesta di immagine soddisfa i criteri che altrimenti vincolerebbero un prodotto già associato al valore di eVar impostato più di recente, l’impostazione “Original Value (First)” (Valore originale, primo) forza i server di raccolta dati di Adobe Analytics a ignorare eventuali ulteriori tentativi di questo tipo. L’opposto si verifica con le eVar di merchandising con l’impostazione Allocazione (binding) uguale a “Più recente (ultimo)”. Ogni volta che una richiesta di immagine soddisfa i criteri che associano un prodotto a un’eVar di merchandising, il prodotto si associa (e si riassocia) al valore più recente passato nell’eVar o al valore (sempre) contenuto nella colonna `post_evar`.

Come accennato in precedenza, le eVar per merchandising consentono di allocare eventi di successo ai valori di eVar a livello di singolo prodotto, anziché di singola visita o singolo ordine. Pertanto, ogni volta che un prodotto è associato a un evento di successo (ad esempio un articolo aggiunto al carrello o un acquisto), il merito per l’evento di successo viene attribuito sia al prodotto che ai valori eVar di merchandising a cui è associato il prodotto in quel momento.

### Expire After (Scade dopo)

L’impostazione di scadenza di un’eVar di merchandising consente di scegliere:

* quando scadono le associazioni prodotto/eVar e

* quando la colonna post_evar non deve più essere compilata automaticamente dopo che un’eVar è stata passata in una richiesta di immagine.

La scadenza di un’eVar può avvenire quando viene registrato un evento di successo o una volta trascorso un determinato periodo di tempo. Adobe Analytics consente una sola impostazione di scadenza alla volta per ogni eVar.

Per il metodo di ricerca dei prodotti, per best practice la scadenza di un’eVar di merchandising dovebbe corrispondere a uno dei seguenti valori:

* la quantità di tempo per cui un prodotto viene tenuto nel carrello di un sito prima che questo lo rimuova automaticamente dal carrello (ad esempio 14 giorni, 30 giorni, ecc.)
* OPPURE il momento in cui si verifica l’evento di acquisto.

Con entrambe le impostazioni, per tutti i prodotti acquistati da un visitatore, il merito per ordine/unità/ricavo viene assegnato ai valori di eVar merchandising a cui erano associati i prodotti in quel momento.

### Type (Tipo)

L’impostazione del tipo di eVar determina il tipo di dati inserito nell’eVar. Nella maggior parte dei casi, questo valore deve essere uguale a “Text”. Raramente viene usato “Counter” per un eVar merchandising. Tuttavia, “Counter” può essere utilizzato per allocare il successo ai valori eVar di tipo Counter in base a singoli prodotti.  Una discussione sulle soluzioni idonee per il tipo “Contatore” esula dall’ambito di questo documento.

### Merchandising Binding Event (Evento di binding merchandising)

L’impostazione Merchandising Binding Event (Evento di binding di merchandising) consente di specificare le condizioni che determinano l’associazione di un prodotto al valore di un’eVar di merchandising. Queste condizioni sono limitate all’attivazione di eventi di successo specifici o solo eVar. Le variabili di traffico attivate (ad esempio, prop) non hanno alcun effetto sui binding di merchandising.

Tieni presente che con l’impostazione Merchandising Binding Event (Evento di binding merchandising) è possibile associare un prodotto a un valore di eVar tramite più eventi. Esempi:

* Tramite un evento di visualizzazione prodotto
* Tramite un evento di aggiunta al carrello
* Tramite un evento di acquisto

Per impostazione predefinita, l’impostazione associa un prodotto a un valore di eVar merchandising ogni volta che nella stessa richiesta di immagine del prodotto è presente anche un altro evento/eVar (merchandising o standard).

### Reset (Ripristina)

L’impostazione Reste (Ripristina) consente di “far scadere” immediatamente tutti i valori eVar per tutti i visitatori che al momento hanno un valore `post_evar` nel database backend di Adobe Analytics. Inoltre, elimina tutte le associazioni prodotti/eVar correnti.

>[!IMPORTANT]
>Adobe sconsiglia di utilizzare l’impostazione Reset (Ripristina). a meno che non si intenda far ripartire l’eVar da zero a partire dal momento in cui avviene il ripristino.

## Quali impostazioni utilizzare?

Tra le tante combinazioni di impostazione disponibili, quali sono quelle consigliate?

Per associare una “internal keyword search” (ricerca interna per parole chiave) all’ID prodotto 12345, la variabile prodotti deve essere impostata come segue:

`s.products=";12345;;;;eVar1=internal keyword search";`

Eventuali eventi di successo (articoli aggiunti al carrello, acquisti) acquisiti contemporaneamente al productID 12345 vengono attribuiti sia all’ID prodotto 12345 che al valore eVar1 &quot;internal keyword search&quot; (ricerca interna per parole chiave). Il merito per gli eventi di successo associati all’ID prodotto 12345 potrà essere attribuito a un valore eVar1 diverso unicamente se eVar1 venisse successivamente impostato su un valore diverso all’interno della variabile prodotti (insieme all’ID prodotto 12345).

Esempio:

```js
s.products=";12345;;;;eVar1=internal campaign";
```

Questa impostazione della variabile cambia il binding dell’ID prodotto 12345 dal valore eVar1 &quot;internal keyword search&quot; (ricerca interna per parole chiave) al valore eVar1 &quot;internal campaign&quot; (campagna interna). Inoltre, questo rebinding avviene quando eVar è configurato per l’utilizzo della sintassi prodotto e dell’impostazione di allocazione (binding) &quot;Most Recent (Last)&quot; (Più recente, ultimo). Se invece l’impostazione Allocazione (binding) è impostata su &quot;Original Value (First)&quot; (Valore originale, primo), l’impostazione eVar1 uguale a &quot;internal campaign&quot; insieme all’ID prodotto 12345 non riassocia l’ID prodotto 12345 al valore eVar1 &quot;internal campaign&quot;. Il binding rimarrà invece valido per il valore originariamente associato, ovvero &quot;internal keyword search&quot; (ricerca interna per parole chiave).

### Problemi associati all’utilizzo della sintassi prodotto

Senza un’attenta pianificazione, possono sorgere diversi problemi quando si utilizza la sintassi prodotto. Prendiamo il caso dell’utilizzo di più eVar per monitorare i metodi di ricerca dei prodotti sul sito web. In questo caso, ogni singola eVar di metodo di ricerca dei prodotti deve essere impostata allo stesso tempo affinché venga attribuito il merito a una particolare eVar di metodo di ricerca (e nessun merito alle altre eVar di metodo di ricerca). In tali scenari è possibile utilizzare la sintassi prodotto, ma il codice risultante da distribuire è più complicato.

Se utilizziamo l’esempio originale “sandals” e lo adattiamo per utilizzare la sintassi prodotto (supponendo che il visitatore abbia trovato un prodotto con l’ID “sandal123” utilizzando il termine di ricerca “sandals”), la variabile di prodotti risultante deve essere impostata come segue:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

In questo esempio la sintassi della variabile di prodotti è lunga, ma associerà ciascuno dei valori eVar elencati all’ID prodotto “sandal123”. Dopodiché tutti gli eventi di successo (ad esempio, aggiunte al carrello, acquisti) che vengono acquisiti contemporaneamente al prodotto “sandal123” vengono attribuiti agli ultimi valori eVar associati al prodotto. Questo esempio di codice indica se un acquisto di 1 unità del prodotto “sandal123” (per un valore di $ 79,95) avviene dopo che le eVar di cui sopra sono stati associate al prodotto “sandal123”:

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

A tutti i seguenti valori verrebbero attribuiti 1 ordine, 1 unità e $ 79,95 di ricavi:

* Valore eVar2 “sandals”
* Valore eVar1 “internal keyword search”
* Valore eVar3 “non-internal campaign”
* Valore eVar4 “non-browse”
* Valore eVar5 di &quot;non-cross-selling&quot;

Questa è l’attribuzione corretta, il che non è un problema. Piuttosto, il problema principale con questo approccio sta nel determinare come e quando impostare le eVar del metodo di ricerca dei prodotti.

Nella maggior parte dei casi con sintassi prodotto, le eVar di metodo di ricerca dei prodotti devono essere impostate su una pagina di dettagli del prodotto anziché sulla pagina in cui è stato effettivamente utilizzato il metodo di ricerca (ad esempio la pagina dei risultati della ricerca per parola chiave, la pagina Sfoglia, la pagina di destinazione della campagna interna e così via). È ragionevole supporre che un prodotto non sia stato effettivamente “trovato” finché un visitatore non interagisce in qualche modo con esso. Di conseguenza, queste eVar (con sintassi prodotto) non devono essere impostate sulla pagina del metodo di ricerca dato che, in genere, più prodotti vengono visualizzati su tali pagine. Il valore del metodo di ricerca deve essere associato solo ai prodotti con cui il visitatore ha effettivamente interagito.

Inoltre, su una pagina del metodo di ricerca, potrebbe essere possibile sia fare clic su un link per passare alla pagina dei dettagli di uno specifico singolo, sia aggiungere direttamente un singolo prodotto al carrello. Utilizzando l’esempio della parola chiave di ricerca &quot;sandals&quot;, se un visitatore aggiunge il prodotto &quot;sandal123&quot; al carrello direttamente da una pagina dei risultati della ricerca, il codice per acquisire l’aggiunta al carrello (tramite l’evento onClick del pulsante Add-to-Cart, ecc.) deve essere generato in modo dinamico nel momento in cui l’aggiunta al carrello avviene o &quot;codificato&quot; direttamente tramite il codice della pagina o un sistema di gestione dei tag.  Il codice da attivare in questi casi sarà comunque simile al seguente:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Questo codice associa correttamente i valori eVar sopra indicati al prodotto “sandal123”. Tuttavia, per impostare correttamente questi valori quando si verifica l’evento di clic, lo sviluppatore deve:

* aggiungere una logica lato server alla pagina dei risultati di ricerca con cui determinare i valori da inserire nelle eVar del metodo di ricerca dei prodotti e
* assemblare l’intera variabile products di cui sopra senza errori di sintassi.

Inoltre, se un visitatore “trova” il prodotto facendo clic su un link della relativa pagina dei dettagli, lo sviluppatore deve:

* trasmettere i dettagli del metodo di ricerca del prodotto (come mostrato sopra) dalla pagina del metodo di ricerca alla pagina dei dettagli del prodotto e
* ricreare lo stesso valore di variabile dei prodotti dagli elementi appena passati dalla pagina precedente.

### Quando risulta utile la sintassi prodotto

La sintassi prodotto risulta utile quando:

* si interagisce contemporaneamente con più prodotti con lo stesso ID prodotto e
* le eVar da associare a tali prodotti devono avere valori di ID prodotto diversi.

Ad esempio, molti articoli di abbigliamento hanno codici SKU secondari che indicano la taglia, il colore, lo stile ed eventuali altri attributi. Questi attributi consentono di distinguere un singolo prodotto secondario da altri appartenenti allo stesso prodotto principale. Supponiamo di voler acquistare una maglietta blu nella taglia M e una rossa nella taglia L. Supponiamo quindi che entrambe le magliette abbiano come ID prodotto principale “tshirt123” e che `eVar10` sia stata configurata per acquisire i codici SKU secondari. Le variabili definite nella pagina di conferma dell’acquisto vengono impostate come segue:

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

In questo caso, a entrambi i valori `eVar10` “tshirt123-m-blue” e “tshirt123-l-red” (codici SKU secondari) viene assegnato il merito per l’acquisto delle rispettive istanze di ID prodotto “tshirt123”.

### Problemi associati all’allocazione “Più recente”

Potresti riscontrare ulteriori problemi utilizzando l’impostazione di allocazione (binding) &quot;Most Recent (Last)&quot; (Più recente, ultimo). In molte esperienze di navigazione web, i visitatori &quot;trovano di nuovo&quot; un prodotto che hanno già visualizzato e/o aggiunto al carrello. Questo di solito avviene drante una visita successiva o appena prima di completare un acquisto. Supponiamo che durante una visita al sito, un visitatore trovi il prodotto &quot;sandal123&quot; tramite la ricerca per parola chiave di &quot;sandals&quot;. Il visitatore aggiunge subito l’articolo al carrello, dalla pagina dei risultati della ricerca per parola chiave. Il codice con cui viene acquisito questo evento di aggiunta al carrello viene impostato come segue:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

Di conseguenza, ciascuno dei valori eVar presenti in questa richiesta di immagine è associato al prodotto “sandal123”.

Ora, immagina che il visitatore non acquisti il prodotto durante questa visita, ma ritorni sul sito tre giorni dopo con il prodotto &quot;sandals123&quot; ancora nel carrello. Il visitatore vuole saperne di più sul prodotto prima di effettuare l’acquisto. Invece di usare una ricerca per parola chiave per trovare il prodotto, questa volta il visitatore naviga nel sito. Arrivano alla sezione di navigazione merchandising &quot;womens > shoes > sandals&quot; poco prima di &quot;trovare di nuovo&quot; il prodotto. Quando il visitatore alla fine &quot;trova di nuovo&quot; la pagina dei dettagli del prodotto &quot;sandal123&quot;, le variabili vengono impostate come segue (al caricamento della pagina):

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Con l’impostazione di allocazione (binding) “Most Recent (Last)” (Più recente, ultimo), il prodotto “sandal123” si basa su valori di eVar completamente diversi rispetto a quelli a cui era originariamente associato. Inoltre, se il visitatore completa l’acquisto di “sandal123”, tutto il merito per l’acquisto viene attribuito a questi nuovi valori di associazione eVar anziché a quelli precedenti.

La domanda è: a quali valori eVar deve essere attribuito il merito per l’acquisto? Il visitatore inizialmente aveva trovato il prodotto “sandal123” tramite una ricerca interna per parole chiave, e l’aveva aggiunto al carrello direttamente dalla pagina dei risultati della ricerca. Pertanto, il merito per l’acquisto deve essere attribuito al valore eVar1 “internal keyword search” (e al valore eVar2 “sandals”). Tuttavia, l’impostazione di allocazione (binding) è “Most Recent (Last)” (Più recente, ultimo). Quindi, il merito dell’acquisto viene attribuito al valore eVar1 “browse” (e al valore eVar4 “womens > shoes > sandals”). Questi infatti erano gli ultimi valori associati a “sandal123” prima che il visitatore completasse l’acquisto.

Per ovviare a questo problema si può cambiare l’impostazione di allocazione (binding) dell’eVar di merchandising da “Most Recent (Last)” (Più recente, ultimo) a “Original Value (First)” (Valore originale, primo). In questo modo, al momento dell’acquisto il merito viene attribuito ai valori eVar originali associati al prodotto “sandal123”.

Se il visitatore aggiunge un prodotto al carrello ma non lo acquista mai, la scadenza dell’eVar consente di associare al prodotto un nuovo valore di metodo di ricerca. La scadenza dell’eVar deve corrispondere al tempo di permanenza nel carello consentito dal sito web prima che un articolo venga rimosso automaticamente dal carrello.

### Utilizzo della sintassi per variabile di conversione

Torniamo al confronto tra “sintassi prodotto” e “sintassi per variabile di conversione”. Adobe ha scoperto un metodo più semplice sia per raccogliere le eVar di merchandising per il metodo di ricerca dei prodotti, sia per associare i relativi valori ai prodotti trovati dai visitatori: la sintassi per variabile di conversione riduce il lavoro di implementazione di cui sono responsabili gli sviluppatori del cliente. Offre comunque le stesse informazioni, o addirittura informazioni migliori, rispetto al metodo di sintassi prodotto. Gli sviluppatori devono semplicemente seguire le istruzioni di distribuzione ricevute e il resto del codice può essere inserito nel file Adobe AppMeasurement/Adobe Experience Platform Web SDK.

Vediamo ad esempio la soluzione consigliata per il tracciamento delle prestazioni della ricerca interna per parola chiave. Nella pagina dei risultati della ricerca per parole chiave, il codice acquisisce la parola chiave cercata tramite un elemento prop (ad esempio, prop4) e un altro elemento prop (ad esempio, prop5). Questi elementi prop tengono traccia del numero di risultati mostrati dalla ricerca. Ogni volta che una richiesta di immagine di Adobe Analytics viene generata nella pagina dei risultati della ricerca, vengono utilizzati gli oggetti livello dati (o codice pagina) implementati dagli sviluppatori per compilare le variabili di cui sopra (prop).

Un’ulteriore logica contenuta nel file AppMeasurement/Adobe Experience Platform Web SDK può compilare le altre variabili (eVar/dimensioni di merchandising) che devono essere impostate contemporaneamente.\
Ad esempio, se un nuovo visitatore cerca la parola chiave “sandals” che restituisce 25 risultati nella pagina dei risultati di ricerca, il codice da attivare (tramite il codice della pagina OPPURE l’acquisizione del livello dati) si presenta così:

```js
s.prop4="sandals";
s.prop5="25";
```

La logica nel file AppMeasurement/Analytics SDK può quindi trasformare automaticamente questo snippet di codice come segue:

```js
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Non è necessario preoccuparsi di passare dati da pagina a pagina né tentare di creare una stringa lunga e complessa da inserire nella variabile prodotti. Piuttosto, gli sviluppatori possono implementare la propria parte di soluzioni di tracciamento (ovvero ciò che viene inserito negli elementi prop) e lasciare il resto dell’implementazione al codice personalizzato fornito da Adobe Consulting.

Come spiegato in precedenza, per tutte le eVar di merchandising che utilizzano la sintassi per variabile di conversione, l’impostazione di allocazione è “Most Recent (Last)” (Più recente, ultimo). Una volta impostata un’eVar uguale a qualsiasi valore, tale valore persiste in tutti gli hit successivi (tramite la colonna post_evar). Persiste finché non viene impostato un valore diverso o fino alla scadenza dell’eVar. Pertanto, tutti i prodotti con cui si interagisce dopo che sono state impostate le eVar, se non sono già stati associati a tali eVar, vengono associati ai valori “Most Recent (Last)” (Più recente, ultimo) passati nell’eVar.

Nell’esempio precedente, i valori `eVar2` “sandals”, eVar1 “internal keyword search” ecc. persistono in tutte le pagine visualizzate dopo la ricerca per parole chiave. Persistono finché le eVar non vengono sovrascritte con altri valori. Supponiamo che, dalla pagina dei risultati della ricerca per parola chiave, un visitatore faccia clic su un collegamento alla pagina dei dettagli del prodotto con ID prodotto “sandal123”.  L’ID prodotto “sandal123” (se non è ancora stato associato) viene quindi associato a ciascuno dei valori contenuti nelle colonne post_evar o ai valori eVar raccolti dalla pagina precedente (risultati di ricerca).

C’è un altro aspetto da riconsiderare riguardo alla sintassi per variabile di conversione. Gli eventi di associazione devono essere impostati in modo da associare un valore eVar a un prodotto. La semplice impostazione di un’eVar di merchandising (nella sua variabile) insieme a un prodotto (nella variabile dei prodotti) in una richiesta di immagine di Adobe Analytics non associa necessariamente il valore eVar al prodotto.  L’impostazione dell’evento di binding merchandising, specificata in Report Suite Manager, determina i criteri secondo i quali un valore eVar viene associato a un prodotto.

Poiché vogliamo che i valori eVar del metodo di ricerca dei prodotti vengano associati ai prodotti ogni volta che si verifica un’interazione con i prodotti (ossia ogni volta che un prodotto viene “trovato”), è possibile presumere che le interazioni più comuni per “prodotti trovati” che possono verificarsi siano la visualizzazione del prodotto (i visitatori accedono alla pagina dei dettagli del prodotto) o l’aggiunta al carrello (i visitatori aggiungono il prodotto al carrello direttamente da una pagina di metodo di ricerca dei prodotti).

Pertanto, possiamo scegliere questi due eventi (prodView, scAdd) come eventi di binding di merchandising “fondamentali”.
Questo è ciò che accade quando uno di questi eventi di binding è presente all’interno di una richiesta di immagine. Eventuali ID prodotto presenti nella stessa richiesta (nella variabile prodotti) e non associati a un’eVar di merchandising verranno associati ai valori più recenti passati nell’eVar di merchandising (colonne post_evar). Se l’impostazione di allocazione (binding) equivale a “Original Value (First)” (Valore originale, primo), qualsiasi tentativo di ridefinire l’associazione di questi prodotti dopo il binding originale viene ignorato.

### Impostazioni consigliate per best practice

Di seguito sono riportate le impostazioni consigliate come best practice. Consentono di implementare facilmente il metodo di ricerca dei prodotti con i migliori risultati. Adobe consiglia di configurare ciascuna delle eVar di merchandising per i metodi di ricerca dei prodotti (in generale) come segue:

* Enable Merchandising (Abilita merchandising): abilitato
* [Sintassi] Merchandising: Conversion Variable Syntax (Sintassi per variabili di conversione)
* Allocation [binding] (Associazione per allocazione): Original Value (First) (Valore originale, primo)
* Expire After (Scade dopo): per quanto tempo un prodotto resta nel carrello prima di essere rimosso automaticamente (ad esempio 14 giorni, 30 giorni, ecc.).  Se tale periodo di tempo non esiste, imposta la scadenza al verificarsi dell’evento di acquisto (“Purchase”).
* Type: Text (Tipo: testo)
* Merchandising Binding Events (Eventi di binding merchandising): Product View, Cart Add, Purchase (Visualizzazione prodotto, Aggiunta al carrello, Acquisto)

## Cosa fanno in realtà gli eventi di binding?

Quando un evento di binding (o associazione) è presente nella stessa chiamata server della variabile prodotti, i valori dell’eVar merchandising (con sintassi per variabile di conversione) nella colonna post vengono associati alla variabile prodotti. In base all’esempio precedente, supponiamo che una chiamata al server contenga i seguenti valori di eVar di merchandising:

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Come spiegato in precedenza, le eVar di cui sopra persistono oltre l’hit corrente tramite la rispettiva colonna post_evar. Pertanto, i server di Adobe trasformano le eVar di cui sopra nelle seguenti:

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Queste colonne post vengono memorizzate nel database di Adobe e persistono oltre l’hit corrente in cui sono state inizialmente impostate, fintanto che la variabile non abbia una scadenza o non venga ripristinata. Nei server di Adobe, questi valori post_evar sono “disponibili” al momento dell’elaborazione di chiamate server future che contengono sia l’evento di binding che la variabile prodotti.

L’associazione avviene unicamente tra questi valori post_evar e il contenuto della variabile prodotti. L’evento di binding non viene necessariamente associato alle variabili eVar o prodotti. Funge da “catalizzatore” e comunica ai server di Adobe di associare i valori post_evar ai prodotti.

Supponiamo che in un hit futuro siano impostate le seguenti variabili:

```js
s.products=";sandals123"
s.events="prodView";
```

Nelle colonne post_evar, i server di elaborazione Adobe ricevono questo hit come segue:

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Supponiamo che eVar1, eVar2, eVar3, eVar4 ed eVar5 siano state configurate per utilizzare l’evento di binding `prodView`. Se una di queste eVar non è configurata per utilizzare prodView come evento di binding, non sarà possibile associare tra tale eVar (non configurata correttamente) alla variabile prodotti.

Il binding produce alcuni risultati molto interessanti, visibili nel valore della colonna post_products. Il binding trasforma il codice di cui sopra e imposta alcune altre colonne post, come segue:

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

Il valore presente nella colonna post_products potrebbe esserti familiare. Scorri verso l’alto in questo documento e confronta questo valore post_products con il valore s.products come mostrato nella. La colonna post_products viene impostata utilizzando la sintassi per variabili di prodotto.

In pratica, il binding “copia” i valori della eVar con sintassi per variabile di conversione e li inserisce nella variabile prodotti tramite la sintassi prodotto. Questa azione di copia ha luogo solo se la variabile prodotti e un evento di binding (impostato tramite la configurazione di eVar) sono presenti nella stessa richiesta. A questo punto, i valori contenuti nelle colonne post_eVar sono associati al prodotto. Questo binding è rappresentato dalla sintassi prodotto memorizzata nella colonna post_products.

## eVar di merchandising, metrica Istanze e Attribuzione

Quando una eVar standard viene inviata in una chiamata al server Analytics, al valore nella colonna post_evar viene sempre attribuita un’istanza. Le istanze rappresentano il numero di volte in cui una eVar è stata impostata come valore specifico in una richiesta di immagine.

Ad esempio, supponiamo che `eVar10` sia una eVar standard con attribuzione [!UICONTROL Last Touch]. Se si imposta `s.eVar10="hello world"` su qualsiasi pagina, il valore “hello world” viene trasmesso alla colonna post_evar10 quando Adobe elabora l’hit. La metrica delle istanze è uguale a “1” per ogni singola impostazione di `eVar10` pari a `hello world`. Tieni presente che un’istanza non viene sempre registrata quando la colonna post_evar ha un valore. Piuttosto, la colonna post_evar determina quale valore ottiene l’istanza quando questa viene registrata.

Le istanze per una eVar di merchandising assegnano l’attribuzione ai valori che essa raccoglie. Ma questo accade solo se allo stesso tempo si verifica un’interazione con un prodotto associato al valore dell’eVar di merchandising.

Ad esempio, l’impostazione `s.eVar1="Internal Keyword Search"` di per sé non attribuisce alcun merito per la metrica Istanza al valore eVar1 “Internal Keyword Search”. A quel punto viene registrata un’istanza. Tuttavia, a meno che un prodotto non sia associato al valore “Internal Keyword Search” allo stesso momento in cui `eVar1` viene impostata, l’istanza viene attribuita al bucket Non specificato. In altre parole, il valore `eVar1` “Internal Keyword Search” può ottenere un’istanza. Ma questo accade solo quando un prodotto associato al valore di “Internal Keyword Search” appare nella variabile dei prodotti nella stessa richiesta di immagine.

In sintesi, senza configurazioni aggiuntive, la metrica Istanze predefinita per un eVar di merchandising non ha alcuna utilità. Fortunatamente, Adobe ha rilasciato [Attribuzione](/help/analyze/analysis-workspace/attribution/overview.md). Questa funzione consente di applicare più modelli di attribuzione per qualsiasi metrica personalizzata raccolta da Adobe Analytics. Le metriche che applicano questi modelli di attribuzione non utilizzano i valori presenti nelle colonne post_evar né i valori associati a uno specifico prodotto. Piuttosto, queste metriche utilizzano solo i valori trasmessi tramite le richieste di immagini stesse (o i valori acquisiti tramite le regole di elaborazione di Adobe Analytics). Puoi utilizzare le funzioni di Attribution per ottenere una metrica di istanze con attribuzione accurata per tutte le eVar di merchandising che utilizzano la sintassi per variabile di conversione.

![Selezione attribuzione](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/attribution-select.png)

Quando si aggiunge a un rapporto una metrica di istanza per un’eVar di merchandising, il modello di attribuzione corretto è il modello &quot;Last Touch&quot; (Ultimo contatto). In questo caso, l’impostazione della finestra di lookback per il modello non ha importanza. Infatti, un modello di attribuzione Ultimo contatto “forzato” attribuisce sempre all’istanza il merito di ogni singolo valore trasmesso tramite una richiesta. Ciò indipendentemente dal fatto che le impostazioni di attribuzione/binding effettive dell’eVar siano impostate su “Most Recent (Last)” (Più recente, ultimo) o “Original Value (First)” (Valore originale, primo).
