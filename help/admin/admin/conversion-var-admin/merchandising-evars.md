---
title: eVar per merchandising e metodi di ricerca dei prodotti
description: Approfondisci i concetti alla base degli eVar di merchandising e le modalità di elaborazione e allocazione dei dati.
source-git-commit: eb508167930019c51823e652fc16122e9e416d07
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# eVar per merchandising e metodi di ricerca dei prodotti

Questo documento dettagliato spiega i concetti alla base degli eVar di merchandising, che elaborano e allocano i dati in modo diverso rispetto agli eVar standard. Inoltre, spiega come le eVar per merchandising si rapportano ai metodi di ricerca dei prodotti.

Mentre la maggior parte dei siti web per la vendita al dettaglio ha molti modi per trovare i prodotti, l&#39;Adobe considera i seguenti metodi fondamentali per la ricerca dei prodotti che ogni cliente al dettaglio dovrebbe monitorare in Adobe Analytics:

* Parole chiave di ricerca interne
* Codici di tracciamento delle campagne interne
* Categorie di merchandising/Sfoglia
* Collegamenti cross-selling

Ai fini del presente documento, mappamo alcuni eVar alle soluzioni come segue:

* eVar 2: Parole chiave di ricerca interne
* eVar 3: Codici di tracciamento delle campagne interne
* eVar 4: Categorie di merchandising/Sfoglia
* eVar 5: Collegamenti cross-selling

Possiamo utilizzare un eVar aggiuntivo per misurare le prestazioni di tutti i metodi di ricerca dei prodotti in relazione tra loro. Oltre ai metodi di ricerca descritti in precedenza, nel confronto di eVar sono inclusi altri metodi di ricerca, ad esempio i collegamenti alle pagine di dettaglio dei prodotti da siti web esterni.

* eVar 1: Metodi di ricerca dei prodotti

Invece di configurare una qualsiasi di queste variabili come eVar standard, configurale come eVar per merchandising. L’utilizzo delle eVar per merchandising consente di allocare qualsiasi attività di successo ai valori acquisiti dalle eVar a un livello *per prodotto* invece di un livello *per visita/per ordine*. Questo documento chiarisce la differenza tra l&#39;allocazione per prodotto e per ordine in tutto.

Per dimostrare come impostare queste variabili, ecco un esempio in cui un visitatore decide di utilizzare la parola chiave interna &quot;sandali&quot; per trovare un prodotto sul sito. Nella pagina dei risultati della ricerca per parola chiave, devi acquisire dati in almeno due eVar:

* `eVar2` è uguale alla parola chiave utilizzata nella ricerca (&quot;sandali&quot;)
* `eVar1` è uguale al metodo di ricerca del prodotto utilizzato (&quot;ricerca di parole chiave interna&quot;).

Quando imposti queste due variabili uguali a questi valori specifici, sai che il visitatore sta utilizzando il termine di ricerca per parola chiave interno di &quot;sandali&quot; per trovare un prodotto. Allo stesso tempo, sai che il visitatore non utilizza gli altri metodi di ricerca dei prodotti per trovare i prodotti (ad esempio, il visitatore non sta navigando tra le categorie di prodotti nello stesso momento in cui esegue una ricerca per parola chiave). Per garantire un&#39;allocazione corretta per prodotto, questi metodi non utilizzati non devono ottenere credito per la ricerca di un prodotto trovato tramite una ricerca di parole chiave interna. Pertanto, devi inserire una logica nel codice (ad esempio AppMeasurement, AEP Web SDK e così via) che imposta automaticamente le eVar associate a questi altri metodi di ricerca uguali al valore del &quot;metodo di non ricerca&quot;.

Ad esempio, quando un utente cerca prodotti utilizzando la parola chiave &quot;sandali&quot;, la logica del codice Analytics deve impostare le variabili uguali alle seguenti nella pagina dei risultati interni della ricerca per parola chiave:

* eVar2=&quot;sandali&quot;: la parola chiave &quot;sandali&quot; è stata utilizzata nella ricerca interna di parole chiave
* eVar1=&quot;ricerca di parole chiave interna&quot;: è stato utilizzato il metodo di ricerca &quot;internal keyword search&quot;
* eVar3=&quot;campagna non interna&quot;: non è stata utilizzata una campagna interna per accedere alla pagina dei risultati della ricerca
* eVar4=&quot;non-browse&quot;: non è stato possibile accedere a una categoria Sfoglia nella pagina dei risultati della ricerca
* eVar5=&quot;non-cross-selling&quot;: non è stato fatto clic su un collegamento di cross-selling nella pagina dei risultati di ricerca

## Impostazioni eVar di Merchandising

Prima di continuare con l’esempio &quot;sandali&quot;, ecco le diverse impostazioni che puoi utilizzare con le eVar di merchandising.  La schermata seguente proviene da Report Suite Manager. Accedi a questa pagina selezionando Analytics > Amministratore > Suite di rapporti > Modifica impostazioni > Conversione > Variabili di conversione > Aggiungi nuovo > Abilita merchandising.

![](assets/merch-evars1.png)

Le sezioni sotto la tabella contengono ulteriori dettagli su queste impostazioni.

| Impostazione | Descrizione |
|--- | --- |
| Nome | Nome o dimensione di reporting a cui la variabile deve essere associata. Se `eVar1` è destinato a acquisire i metodi di ricerca dei prodotti, il campo Nome per `eVar1` deve essere impostato su &quot;Metodi di ricerca dei prodotti&quot;. |
| Merchandising | Il tipo di sintassi che verrà utilizzato per acquisire i valori eVar di merchandising |
| Allocazione | Aiuta a determinare il valore dell’eVar di merchandising che deve ricevere credito quando si verifica un evento di successo. |
| Scade dopo | Determina quando i binding dei prodotti e degli eVar di merchandising esistenti non devono più essere effettivi. |
| Tipo | Tipo di dati raccolti nell&#39;eVar merchandising |
| Evento di associazione Merchandising | Eventi che determinano quando un prodotto deve essere associato a un valore eVar di merchandising |
| Ripristino | Un trigger che reimposta tutti i dati di back-end per l’eVar a quel punto |
| Abilita merchandising | Flag che deve essere impostato su &quot;Abilitato&quot; per trasformare l’eVar da un eVar standard a un eVar Merchandising |

### Abilita merchandising

Quando l’impostazione &quot;Abilita merchandising&quot; è impostata su &quot;Abilitato&quot;, in Report Suite Manager vengono visualizzate tutte le impostazioni come descritto di seguito. Quando l’impostazione &quot;Abilita merchandising&quot; è impostata su &quot;Disabilitato&quot;, sono disponibili solo le impostazioni standard di eVar.

### Merchandising

Questa opzione non è disponibile per le eVar normali. L’impostazione [!UICONTROL Merchandising] ti consente di scegliere [!UICONTROL Conversion Variable Syntax] o [!UICONTROL Product Syntax] come metodo per acquisire il valore dell’eVar di merchandising.

**[!UICONTROL Conversion Variable Syntax]** significa che si imposta il valore eVar nella propria variabile. Ad esempio, con Sintassi della variabile di conversione, il valore `eVar1` di &quot;ricerca di parole chiave interna&quot; viene impostato come segue all’interno del codice della pagina (o del codice AppMeasurement, del codice SDK per web AEP e così via):

`s.eVar1="internal keyword search";`

Con **[!UICONTROL Product Syntax]**, tuttavia, l’eVar è impostato solo all’interno della variabile dei prodotti Adobe Analytics. La variabile dei prodotti Analytics è suddivisa in sei diverse parti per prodotto:

`s.products="[category];[productID];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Category] è una funzione obsoleta e non è più consigliata come opzione valida per mantenere traccia delle prestazioni della categoria di prodotti.  La sua mera esistenza dimostra perché nella maggior parte delle implementazioni della variabile products , un singolo punto e virgola precede la parte productID del valore della variabile.
* [!UICONTROL Quantity] e  [!UICONTROL Revenue] sono utili quando si tiene traccia di un acquisto di prodotto.
* [!UICONTROL Events] è utile per registrare valori di evento incrementali o di valuta personalizzati che non devono essere conteggiati come ricavi (come spedizione, sconti, ecc.)

Le eVar di merchandising configurate per l’utilizzo della sintassi di prodotto sono impostate all’interno della parte finale della variabile dei prodotti. Ad esempio, supponiamo che un visitatore abbia utilizzato una ricerca per parola chiave interna per trovare l’ID prodotto &quot;12345&quot;. Il modo basato sulla sintassi del prodotto per impostare eVar1 in questo esempio sarà simile al seguente:

`s.products=";12345;;;;eVar1=internal keyword search";`

Tieni presente che esistono ancora segnaposto delimitati da punti e virgola per le parti di quantità, ricavi ed eventi della variabile prodotti.  Senza questi segnaposto, l&#39;impostazione `eVar1` di ricerca di parole chiave interna verrebbe completamente ignorata.

### Allocazione

Il termine &quot;Allocazione&quot; per le eVar di merchandising è fuorviante, soprattutto per le eVar di merchandising che utilizzano la sintassi della variabile di conversione. Tutte le eVar standard possono avere una propria impostazione di allocazione individuale. Tuttavia, le eVar di merchandising con sintassi a variabile di conversione utilizzano solo l’impostazione di allocazione &quot;Più recente (ultimo)&quot;, indipendentemente dalle impostazioni di allocazione visualizzate in Report Suite Manager.

Comprendere cosa fa questa impostazione significa comprendere la differenza tra l’allocazione eVar e il binding eVar merchandising. Per le eVar di merchandising, &quot;Merchandising eVar Binding&quot; è un nome più appropriato per questa impostazione &quot;Allocazione&quot;.

**Impostazione di allocazione standard eVar**

Ogni volta che un eVar con sintassi standard viene raccolto da una richiesta di immagine, i server di elaborazione Adobe Analytics inseriscono i dati in un’altra colonna di database, denominata colonna `post_evar` . Poiché le eVar sono intese come persistenti - scadono ad un certo punto oltre l’hit corrente nella maggior parte dei casi - i server impostano quindi questa colonna `post_evar` su ogni richiesta di immagine successiva. È impostato come ultimo valore passato nel relativo eVar corrispondente. Per le eVar standard, quando si verifica un evento di successo, Adobe Analytics utilizza la colonna `post_evar` invece della normale colonna eVar per determinare il valore di eVar a cui deve essere assegnato il credito per l’evento.

Per le eVar standard, l’impostazione Allocazione determina se il primo o l’ultimo valore eVar raccolto durante un determinato periodo verrà inserito nella colonna `post_evar`. Se l’impostazione Allocazione per un eVar standard è uguale a &quot;Valore originale (primo)&quot;, il primo valore eVar raccolto dal visitatore viene inserito nella colonna `post_evar` per tutte le richieste di immagini successive. Questo continua per tutte le richieste future inviate dal browser del visitatore fino alla scadenza dell’eVar per l’impostazione &quot;Scade dopo&quot;.

Se l’impostazione Allocazione di un eVar standard è uguale a &quot;Più recente (ultimo)&quot;, il valore di eVar più recente raccolto dal visitatore viene inserito nella colonna `post_evar` per tutte le richieste di immagini successive. L’allocazione &quot;Più recente (ultima)&quot; implica che il valore `post_evar` cambia ogni volta che il relativo eVar corrispondente viene impostato su un nuovo valore in qualsiasi richiesta di immagine. L’allocazione &quot;Valore originale (primo)&quot; implica che la colonna `post_evar` non cambia tra i risultati anche se il relativo eVar corrispondente potrebbe essere impostato su un valore diverso in una richiesta di immagine futura.

**Impostazione dell’allocazione eVar merchandising (vincolante)**

Come accennato in precedenza, tutte le eVar di merchandising con sintassi a variabile di conversione hanno solo l’allocazione &quot;Più recente (Ultimo)&quot;.  Questo è ciò che l’impostazione &quot;Allocazione&quot; in realtà significa per le eVar per merchandising: Come implicito in precedenza, questa impostazione non determina quali valori vengono inseriti nella colonna `post_evar` mentre un visitatore continua a utilizzare il sito. Piuttosto, l’impostazione Allocazione per eVar di merchandising determina il valore di eVar associato a un prodotto e il modo in cui tali prodotti riassegnano i propri eventi di successo ai valori di eVar a cui sono associati.

Discutiamo di cosa succede se un’impostazione di allocazione di eVar merchandising (ovvero binding) è impostata su &quot;Valore originale (primo)&quot;. Tutti i prodotti impostati accanto alla colonna `post_evar` che non sono stati precedentemente associati all’eVar &quot;pre-elaborato&quot; corrispondente della colonna post_evar saranno associati al valore contenuto nella colonna `post_evar`. Il binding tra il valore eVar e il prodotto non verrà mai modificato fino alla scadenza dell’eVar per le impostazioni di impostazione &quot;Scade dopo&quot; nelle impostazioni della suite di rapporti.

Ogni volta che una richiesta di immagine soddisfa i criteri che altrimenti vincolerebbero un prodotto già associato al valore di eVar impostato più di recente, l’impostazione &quot;Valore originale (primo)&quot; forza i server di raccolta dati Adobe Analytics a ignorare eventuali ulteriori tentativi di questo tipo. L’opposto si verifica con gli eVar di merchandising con l’impostazione Allocazione (binding) uguale a &quot;Più recente (ultimo)&quot;. Ogni volta che una richiesta di immagine soddisfa i criteri che associano un prodotto a un eVar di merchandising, il prodotto si associa (e si riassocia) al valore più recente passato nell’eVar o al valore (sempre) contenuto nella colonna `post_evar` .

Come accennato in precedenza, le eVar per merchandising consentono di allocare eventi di successo ai valori di eVar a livello di singolo prodotto, anziché a livello di singola visita/ordine. Pertanto, ogni volta che un prodotto associato presenta un evento di successo (ad esempio un componente aggiuntivo o un acquisto del carrello) associato a esso, l’evento di successo attribuisce il proprio credito sia al prodotto che ai valori eVar di merchandising a cui è associato il prodotto in quel momento.

### Scade dopo

L’impostazione di scadenza di un eVar di merchandising consente di scegliere quando scade il binding prodotto/eVar e quando la colonna post_evar non deve più essere compilata automaticamente dopo che un eVar è stato trasmesso in una richiesta di immagine. La scadenza per un eVar può avvenire quando viene registrato un evento di successo (a scelta) o un certo periodo di tempo, di nuovo a scelta, viene superato. Adobe Analytics consente una sola impostazione di scadenza alla volta per eVar.

Per la soluzione Product Finding Method, la best practice per impostare la scadenza di un eVar di merchandising dovrebbe essere quella di impostarlo su uguale o al tempo in cui un prodotto viene conservato nel carrello prima che il sito lo elimini automaticamente dal carrello O quando si verifica l&#39;evento di acquisto. Con entrambe le impostazioni di scadenza, a tutti i prodotti acquistati da un visitatore verrà assegnato il credito ordine/unità/ricavo ai valori di eVar merchandising a cui erano associati i prodotti in quel momento.

### Tipo

L’impostazione del tipo di eVar determina il tipo di dati inserito nell’eVar. Nella maggior parte dei casi, se non tutti, durante la configurazione di un eVar di merchandising, questo valore dovrebbe essere uguale a &quot;Testo&quot;. L’utilizzo di un tipo di &quot;Contatore&quot; per un eVar di merchandising è raro, ma, a seconda delle esigenze di tracciamento, potrebbe essere utilizzato in modo efficace per allocare il successo ai valori di Counter eVar a livello di prodotto.  La discussione delle soluzioni con un tipo di &quot;Contatore&quot; non rientra nell&#39;ambito di questo documento.

### Evento di associazione Merchandising

L’impostazione Evento di binding di merchandising consente di specificare le condizioni che determinano l’associazione di un prodotto al valore di un eVar di merchandising. Tali condizioni sono limitate all&#39;attivazione di eventi di successo specifici o solo eVar; l’attivazione delle variabili di traffico (ad esempio proprietà) non ha alcun effetto sui binding di merchandising.

Una delle funzioni più utili dell’impostazione Evento di associazione Merchandising è la capacità di associare un prodotto a un valore di eVar attraverso più di un evento. Ad esempio, l’impostazione potrebbe consentire ai prodotti di essere associati a un valore eVar di merchandising tramite un evento di visualizzazione del prodotto, un evento di aggiunta del carrello o un evento di acquisto. L’impostazione potrebbe persino - e per impostazione predefinita - associare un prodotto a un valore di eVar merchandising ogni volta che un altro evento/eVar - merchandising o altro - è contenuto nella stessa richiesta di immagine del prodotto.

### Ripristino

L’impostazione Reset ti consente di &quot;scadere&quot; immediatamente tutti i valori eVar per tutti i visitatori che attualmente hanno un valore `post_evar` nel database di back-end di Adobe Analytics. Elimina anche tutti i binding dei prodotti/eVar correnti.

>[!IMPORTANT]
>L&#39;Adobe sconsiglia di utilizzare l&#39;impostazione Reset a meno che non si intenda completamente far ripartire l&#39;eVar con una &quot;tabula rasa&quot; completamente pulita dei dati dal momento in cui avviene la reimpostazione.

## Quali impostazioni utilizzare?

Tra le numerose combinazioni di impostazioni disponibili, potreste chiedervi quali sono le impostazioni &quot;best practice&quot;.

Se desideri eseguire un binding della &quot;ricerca per parola chiave interna&quot; con l’ID prodotto 12345, la variabile prodotti viene impostata come segue:

`s.products=";12345;;;;eVar1=internal keyword search";`

Eventuali eventi di successo (aggiunti dal carrello, acquisti) acquisiti contemporaneamente al productID 12345 vengono accreditati sia all’ID prodotto 12345 che al valore `eVar1` di &quot;ricerca di parole chiave interna&quot;. L&#39;unico modo in cui un diverso valore `eVar1` ha ricevuto credito per eventi di successo associati all&#39;ID prodotto 12345 è se `eVar1` è stato successivamente impostato su un valore **diverso** all&#39;interno della variabile prodotti (insieme all&#39;ID prodotto 12345). Esempio:

`s.products=";12345;;;;eVar1=internal campaign";`

Questa configurazione modifica il binding dell’ID prodotto 12345 dal valore `eVar1` di &quot;ricerca di parole chiave interna&quot; al valore `eVar1` di &quot;campagna interna&quot;. Questo rebinding avviene ogni volta che si utilizza Product Syntax (Sintassi prodotto) e l&#39;impostazione Allocation (binding) per l&#39;eVar è impostata su &quot;Most Recent (Last)&quot; (Più recente). Cosa succede se l’impostazione Allocazione (binding) è invece impostata su &quot;Valore originale (primo)&quot;? Quindi l&#39;impostazione eVar1 uguale a &quot;campagna interna&quot; insieme all&#39;ID prodotto 12345 non effettua il rebind product ID 12345 al valore eVar1 di &quot;campagna interna&quot;. Il binding rimane con il valore originariamente associato, ovvero &quot;ricerca di parole chiave interna&quot;.

### Sfide nell&#39;utilizzo della sintassi del prodotto

Senza un&#39;attenta pianificazione, possono sorgere diversi problemi utilizzando la sintassi del prodotto. Prendiamo il caso dell’utilizzo di più eVar per monitorare i metodi di ricerca dei prodotti sul sito web. In questo caso, ogni singolo metodo di ricerca del prodotto deve essere impostato allo stesso tempo per dare un particolare metodo di ricerca eVar credito (e l&#39;altro metodo di ricerca eVars nessun credito). La sintassi del prodotto può essere utilizzata in tali scenari, ma il codice risultante da distribuire è più complicato.

Se utilizziamo il nostro esempio originale &quot;sandali&quot; e lo adattiamo per utilizzare Product Syntax (supponendo che il visitatore abbia trovato un prodotto con l’ID di &quot;sandal123&quot; utilizzando il termine parola chiave &quot;sandali&quot;), la variabile di prodotti risultante deve essere impostata come segue:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Anche se la sintassi della variabile products è lunga in questo esempio, eseguirà il binding di ciascuno dei valori eVar visualizzati all’ID prodotto di &quot;sandal123&quot;. Da allora in poi, tutti gli eventi di successo (ad esempio, gli acquisti del carrello) che vengono acquisiti contemporaneamente al prodotto &quot;sandal123&quot; vengono accreditati ai valori eVar che sono stati collegati per ultimo al prodotto.  Questo esempio di codice mostra se un acquisto di 1 unità del prodotto &quot;sandal123&quot; (per un valore di $ 79,95) avviene dopo che gli eVar sopra sono stati associati al prodotto &quot;sandal123&quot;:

```
s.products=";sandal123;1;79.95";
s.events="purchase";
```

I seguenti valori avrebbero 1 ordine, 1 unità e 79,95 $ di ricavi attribuiti:

* Valore eVar2 di &quot;sandali&quot;
* Valore eVar1 di &quot;ricerca di parole chiave interna&quot;
* Valore eVar3 di &quot;campagna non interna&quot;
* Valore eVar4 di &quot;non-browse&quot;

Questa è l’attribuzione corretta, il che non è un problema. Piuttosto, il dilemma principale con questo approccio è determinare come e quando impostare le eVar del metodo di ricerca dei prodotti.

Nella maggior parte dei casi con Sintassi prodotto, le eVar del metodo di ricerca dei prodotti devono essere impostate su una pagina di dettaglio del prodotto anziché sulla pagina in cui è stato effettivamente utilizzato il metodo di ricerca (ad esempio nella pagina dei risultati della ricerca per parola chiave, nella pagina di ricerca, nella pagina di destinazione della campagna interna, ecc.). È ragionevole supporre che un prodotto non sia stato effettivamente &quot;trovato&quot; finché un visitatore non interagisce in qualche modo con un prodotto. Di conseguenza, queste eVar (che utilizzano la sintassi del prodotto) non devono essere impostate nella pagina del metodo di ricerca perché più prodotti sono (in genere) visualizzati su tali pagine. Vogliamo associare il valore del metodo di ricerca solo ai prodotti con cui il visitatore ha interagito.

Inoltre, durante la visualizzazione di una pagina del metodo di ricerca, i visitatori potrebbero avere la possibilità di fare clic su un collegamento che li porta a una singola pagina dei dettagli del prodotto o di aggiungere un singolo prodotto al carrello direttamente dalla pagina del metodo di ricerca. Utilizzando il nostro esempio di parola chiave di ricerca &quot;sandali&quot;, se un visitatore aggiunge il prodotto &quot;sandal123&quot; al carrello direttamente da una pagina dei risultati della ricerca di parole chiave, il codice per catturare l&#39;aggiunta del carrello (tramite l&#39;evento onClick del pulsante Add-to-Cart, ecc.) dovrebbe essere generato in modo dinamico nel momento in cui si verifica l’aggiunta del carrello o &quot;hardcoded&quot; direttamente tramite il codice della pagina o un sistema di gestione dei tag.  Indipendentemente dal fatto che il codice da attivare in questi casi sarà simile al seguente:

```
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Questo codice associa correttamente i valori eVar sopra indicati al prodotto &quot;sandal123&quot;. Tuttavia, per impostare correttamente questi valori quando si verifica l’evento di clic, lo sviluppatore deve:

* Aggiungi una logica lato server alla pagina dei risultati di ricerca che determina i valori da inserire nel metodo di ricerca dei prodotti eVar e
* Assembla l&#39;intera variabile prodotti vista sopra senza errori di sintassi.

Inoltre, se un visitatore decide di &quot;trovare&quot; il prodotto facendo clic su un collegamento alla pagina dei dettagli del prodotto, lo sviluppatore deve:

* Passa i dettagli del metodo di ricerca del prodotto (come mostrato sopra) dalla pagina del metodo di ricerca alla pagina dei dettagli del prodotto, e * * Assembla lo stesso valore della variabile dei prodotti dagli elementi appena passati dalla pagina precedente.

Questa soluzione richiede un elevato livello di complessità che potrebbe non essere fattibile.

### Dove la sintassi del prodotto è utile

La sintassi del prodotto è ancora utile quando

* Più prodotti con lo stesso ID prodotto interagiscono contemporaneamente e
* Le eVar da associare a tali prodotti devono avere valori diversi per ID prodotto.

Ad esempio, molti prodotti di abbigliamento hanno &quot;SKU bambini&quot;, che designano la dimensione, il colore, lo stile e qualsiasi altro attributo. Questi attributi separano un singolo prodotto secondario da altri prodotti di pari livello che appartengono allo stesso prodotto principale. Supponiamo che tu decida di acquistare una maglietta blu media più una grande t-shirt rossa. Supponiamo che entrambe le camicie abbiano l&#39;ID prodotto principale di &quot;tshirt123&quot; e che eVar10 sia stato configurato per acquisire SKU figlio. Le variabili impostate nella pagina di conferma dell’acquisto vengono impostate come segue:

```
s.events='purchase';
s.products=';tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red"
```

In questo caso, entrambi i valori `eVar10` (childSKU) di &quot;tshirt123-m-blue&quot; e &quot;tshirt123-l-red&quot; ricevono credito per l’acquisto delle rispettive istanze di ID prodotto &quot;tshirt123&quot;.

### Sfide con l&#39;allocazione &quot;più recente&quot;

Puoi riscontrare ulteriori problemi utilizzando l’impostazione di allocazione (binding) di &quot;Più recente (ultimo)&quot;. In molte esperienze di navigazione web, i visitatori &quot;ritrovano&quot; un prodotto che hanno già visto e/o aggiunto al carrello. Questo di solito avviene tramite una visita successiva o appena prima che decidano di completare un acquisto. Supponiamo che durante la loro prima visita al sito, hanno trovato il prodotto &quot;sandal123&quot; tramite la ricerca per parola chiave di &quot;sandali&quot;. L’hanno aggiunta immediatamente al carrello dalla pagina dei risultati della ricerca per parola chiave. Il codice che acquisisce l’aggiunta del carrello viene impostato come segue:

```
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross
```

Di conseguenza, ciascuno dei valori eVar visualizzati in questa richiesta di immagine è associato al prodotto &quot;sandal123&quot;.

Ora, immagina che il visitatore non acquisti il prodotto durante questa visita, ma ritorni al sito tre giorni dopo. Sanno che hanno già aggiunto il prodotto &quot;sandali123&quot; al carrello. Ma vogliono ancora saperne di più prima di fare l&#39;acquisto. Invece di utilizzare una ricerca per parola chiave per trovare il prodotto, il visitatore naviga attraverso il sito. Finiscono nella sezione di ricerca merchandising &quot;womens > shoes > sandals&quot; poco prima di &quot;ri-trovare&quot; il prodotto. Quando finiscono per &quot;ritrovare&quot; la pagina dei dettagli del prodotto per il prodotto &quot;sandal123&quot;, le variabili vengono impostate come segue (al caricamento della pagina):

```
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Con un’impostazione di Allocazione (binding) di &quot;Più recente (Ultimo)&quot;, il prodotto &quot;sandal123&quot; si basa su valori di eVar completamente diversi rispetto a quelli a cui era originariamente associato. Inoltre, se il visitatore completa l&#39;acquisto di &quot;sandal123&quot;, tutto il credito d&#39;acquisto viene dato a questi valori di eVar appena associati invece dei valori originariamente associati!

La domanda è la seguente: Quali valori eVar devono ottenere credito per l&#39;acquisto&quot;? Ricorda che il visitatore ha inizialmente trovato il prodotto &quot;sandal123&quot; tramite una ricerca di parole chiave interna. L’hanno quindi aggiunto al carrello direttamente dalla pagina dei risultati della ricerca. Pertanto, il valore eVar1 di &quot;ricerca di parole chiave interna&quot; (e il valore eVar2 di &quot;sandali&quot;) dovrebbe ottenere credito per l&#39;acquisto. Tuttavia, le impostazioni di Allocazione (binding) sono state impostate su &quot;Più recente (ultimo)&quot;. Quindi, il valore eVar1 di &quot;browse&quot; (e il valore eVar4 di &quot;womens > shoes > sandals&quot;) ottiene invece il credito di acquisto. Il motivo è che erano gli ultimi valori associati a &quot;sandal123&quot; prima che il visitatore completasse l’acquisto.

Una soluzione a questo problema è cambiare l’impostazione di Allocazione (binding) dell’eVar merchandising da &quot;Più recente (ultimo)&quot; a &quot;Valore originale (primo)&quot;. In questo modo, i valori originali di eVar associati al prodotto &quot;sandal123&quot; ricevono credito al momento dell’acquisto, indipendentemente dal numero di volte in cui il visitatore &quot;ri-trova&quot; il prodotto.

Se il visitatore aggiunge un prodotto al carrello ma non lo acquista mai, la scadenza di eVar consente di associare un nuovo valore del metodo di ricerca al prodotto. La scadenza dell’eVar deve corrispondere al tempo in cui un sito web consente a un prodotto di rimanere nel carrello prima che venga rimosso automaticamente.

### Utilizzo della sintassi della variabile di conversione

Torniamo alla &quot;sintassi del prodotto&quot; rispetto a Domanda &quot;Sintassi variabile di conversione&quot;. Adobe ha scoperto un metodo più semplice sia per la raccolta degli eVar del metodo di ricerca dei prodotti che per il merchandising e per il binding dei loro valori ai prodotti trovati dai visitatori: L’utilizzo della sintassi della variabile di conversione riduce il lavoro di implementazione di cui sono responsabili gli sviluppatori del cliente. Offre comunque le stesse informazioni - o migliori - del metodo di sintassi del prodotto. Gli sviluppatori devono semplicemente seguire le istruzioni di distribuzione date e il resto del codice può essere inserito nel file Adobe AppMeasurement/AEP Web SDK.

Ad esempio, osserviamo la soluzione consigliata per il tracciamento delle prestazioni interne di ricerca per parola chiave. Dice che nella pagina dei risultati della ricerca di parole chiave, il codice acquisisce la parola chiave cercata tramite una prop (ad esempio, prop4) e un altro prop (ad esempio, prop5). Queste proprietà tengono traccia del numero di risultati mostrati dalla ricerca. Ogni volta che una richiesta di immagine Adobe Analytics viene generata nella pagina dei risultati della ricerca, utilizzava gli oggetti livello dati (o codice pagina) distribuiti dagli sviluppatori per compilare le variabili di cui sopra (le proprietà).

La logica aggiuntiva contenuta nel file AppMeasurement/AEP Web SDK può compilare il resto delle variabili (eVar/dimensioni per merchandising) che devono essere impostate contemporaneamente.\
Ad esempio, se un nuovo visitatore effettuasse una ricerca per parola chiave per &quot;sandali&quot;, che restituiva 25 risultati nella pagina dei risultati di ricerca, il codice da attivare (tramite il codice della pagina O l’acquisizione del livello dati) apparirebbe così:

```
s.prop4="sandals";
s.prop5="25";
```

La logica all’interno del file SDK AppMeasurement/Analytics può quindi trasformare automaticamente questo frammento di codice nel seguente:

```
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Non è necessario preoccuparsi di passare dati da pagina a pagina e cercare di creare una stringa piuttosto grande e ingombrante da inserire nella variabile prodotti. Al contrario, gli sviluppatori possono implementare la propria parte delle soluzioni di tracciamento, ovvero ciò che è inserito nella proprietà, e lasciare il resto dell’implementazione al codice personalizzato fornito da Adobe Consulting.

Come spiegato in precedenza, tutte le eVar di merchandising che utilizzano la sintassi della variabile di conversione hanno l’impostazione Allocazione di &quot;Più recente (Ultimo)&quot;. Una volta impostato un eVar uguale a qualsiasi valore, tale valore persiste in tutti gli hit successivi (tramite la colonna post_evar ). Continua finché non viene impostato su un valore diverso o fino alla scadenza dell’eVar. Pertanto, tutti i prodotti con cui interagiscono dopo che sono stati impostati gli eVar, se non sono già stati associati a tali eVar, si legano ai valori &quot;Più recenti (Ultimi)&quot; passati nell’eVar.

Utilizzando il nostro esempio precedente, il valore `eVar2` di &quot;sandali&quot; e il valore eVar1 di &quot;ricerca di parole chiave interna&quot;, ecc. persistere in tutte le pagine visualizzate dopo la ricerca di parole chiave. Permangono finché le eVar non vengono sovrascritte con altri valori. Supponiamo che un visitatore faccia clic su un collegamento alla pagina dei dettagli del prodotto per l’ID prodotto &quot;sandal123&quot; dalla pagina dei risultati della ricerca di parole chiave.  Quindi l&#39;ID prodotto &quot;sandal123&quot; (se non è ancora stato associato) si lega a ciascuno dei valori contenuti nelle colonne post_evar o ai valori eVar raccolti dalla pagina precedente (risultati di ricerca).

C&#39;è un&#39;altra cosa da riconsiderare con la sintassi della variabile di conversione. È quindi necessario impostare gli eventi di binding per associare un valore eVar a un prodotto. La semplice impostazione di un eVar merchandising (nella propria variabile) accanto a un prodotto (nella variabile dei prodotti) in una richiesta di immagine Adobe Analytics non necessariamente associa il valore eVar al prodotto.  L’impostazione Evento di associazione Merchandising, impostata in Report Suite Manager, determina invece i criteri che vincolano un valore di eVar a un prodotto

Poiché vogliamo associare i valori eVar del metodo di ricerca dei prodotti ai prodotti ogni volta che si verifica un’interazione con il prodotto, il che implica che un prodotto è stato &quot;trovato&quot;, è possibile presumere che le interazioni più comuni tra i &quot;prodotti trovati&quot; che possono verificarsi siano una visualizzazione di prodotto (quando i visitatori accedono a una pagina di dettaglio del prodotto) o un’aggiunta di carrello (quando i visitatori aggiungono un prodotto al carrello direttamente da una pagina di metodo di ricerca dei prodotti).  Pertanto, possiamo scegliere questi due eventi (prodView, scAdd) come eventi di binding di merchandising &quot;fondamentali&quot;.
Ogniqualvolta uno di questi eventi di binding è contenuto in una richiesta di immagine, gli ID prodotto contenuti nella stessa richiesta (all’interno della variabile products ) e non sono già stati associati a un eVar merchandising si associano ai valori più recenti passati nell’eVar merchandising (come contenuto nelle colonne post_evar ). Qualsiasi tentativo di ridefinire questi prodotti dopo aver effettuato questo binding originale verrà ignorato quando l’impostazione Allocazione (binding) è impostata su &quot;Valore originale (primo)&quot;.

### Impostazioni delle best practice

Di seguito sono riportate le impostazioni relative alle best practice. Implementano il metodo di ricerca dei prodotti il più facilmente possibile con il set più potente di risultati. Adobe consiglia ai clienti di configurare ciascuna delle eVar per merchandising dei metodi di ricerca dei prodotti (in generale) come segue:

* Merchandising abilitato: Abilitato
* Sintassi del merchandising []: Sintassi della variabile di conversione
* Allocazione [binding]: Valore originale (primo)
* Scade dopo: Il periodo di tempo durante il quale un prodotto rimane in un carrello prima che venga rimosso automaticamente (ad esempio 14 giorni, 30 giorni, ecc.).  Se non esiste un tale tempo, dopo l’evento &quot;purchase&quot;
* Tipo: Testo
* Eventi Di Binding Di Merchandising:  Visualizzazione prodotto, aggiunta carrello e acquisto

## Cosa fanno in realtà gli eventi di binding?

Quando un evento di binding è contenuto nella stessa chiamata server della variabile products , i valori Merchandising eVar (utilizzando la sintassi della variabile di conversione) nella colonna post si associano alla variabile products . In base all’esempio precedente , si supponga che una chiamata al server contenga i seguenti valori di Merchandising eVar:

```
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Come spiegato in precedenza, le eVar di cui sopra persistono oltre l’hit corrente tramite la rispettiva colonna post_evar. Pertanto, i server di Adobe trasformano gli eVar di cui sopra in quanto seguenti:

```
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Queste colonne di post vengono memorizzate nel database di Adobe e persistono oltre l&#39;hit corrente in cui sono state inizialmente impostate. Ciò presuppone che non si verifichi alcuna reimpostazione di scadenza o variabile.  I server di Adobe dispongono di questi valori post_evar &quot;disponibili&quot; al momento dell’elaborazione di chiamate server future che contengono sia l’evento di binding che la variabile prodotti.

Il binding che avviene è unicamente tra questi valori post_evar e il contenuto della variabile products. L&#39;evento di binding non viene necessariamente associato alle variabili eVar o products . È il &quot;catalizzatore&quot; che comunica ai server di Adobe di associare i valori post_evar ai prodotti.

Supponiamo che in un hit futuro siano impostate le seguenti variabili:

```
s.products=";sandals123"
s.events="prodView";
```

Considerando le colonne post_evar, gli Adobi server di elaborazione vedono questo hit come segue:

```
s.products=";sandals123"
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Supponiamo che eVar1, eVar2, eVar3, eVar4 e eVar5 siano stati configurati per utilizzare `prodView` come evento di binding. Se una di queste eVar non è configurata per l&#39;utilizzo di prodView come evento di binding, il binding tra tale eVar (non configurato correttamente) e la variabile prodotti non avrà luogo.

Il binding produce alcuni risultati molto interessanti, visibili nel valore della colonna post_products . Il binding trasforma il codice di cui sopra e imposta alcune altre colonne di post, come segue:

```
post_events="prodView"
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell"
```

Il valore contenuto nella colonna post_products potrebbe essere familiare. Scorri verso l’alto in questo documento e confronta il valore post_products e il valore s.products come mostrato in .  Noterai che la colonna post_products è impostata utilizzando Sintassi delle variabili di prodotto! Ciò significa che il binding &quot;copia&quot; i valori dell’eVar di sintassi della variabile di conversione nella variabile prodotti tramite Sintassi prodotto. Questa azione di copia ha luogo solo quando la variabile dei prodotti e un evento di binding (impostato tramite la configurazione di eVar) sono contenuti nella stessa richiesta. A questo punto, i valori contenuti nelle colonne post_eVar sono associati al prodotto. Questo Binding è rappresentato tramite la sintassi prodotto memorizzata nella colonna post_products .
