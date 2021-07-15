---
title: eVar per merchandising e metodi di ricerca dei prodotti
description: Approfondisci i concetti alla base degli eVar di merchandising e le modalità di elaborazione e allocazione dei dati.
source-git-commit: 6f98366a58c7c249c474d9f4474faa1676cdf1ea
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 0%

---

# eVar per merchandising e metodi di ricerca dei prodotti

Questo documento spiega i concetti alla base degli eVar di merchandising, che elaborano e allocano i dati in modo diverso rispetto agli eVar standard. Inoltre, spiega come le eVar per merchandising si rapportano ai metodi di ricerca dei prodotti.

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

Il termine &quot;Allocazione&quot; per le eVar di merchandising è un nome errato, soprattutto per le eVar di merchandising che utilizzano la sintassi della variabile di conversione. Tutte le eVar che utilizzano la sintassi standard possono avere una propria impostazione di allocazione individuale, ma le eVar di merchandising con sintassi variabile di conversione utilizzano solo un&#39;impostazione di allocazione di &quot;Più recente (ultimo)&quot;, indipendentemente da ciò che mostrano le impostazioni di allocazione in Report Suite Manager.

Per comprendere cosa fa questa impostazione, è necessario comprendere la differenza tra allocazione eVar e binding eVar merchandising.  Per le eVar di merchandising, &quot;Merchanding eVar Binding&quot; potrebbe essere considerato un nome più appropriato per questa impostazione di &quot;Allocazione&quot;.
Ogni volta che un eVar con sintassi standard viene raccolto da una richiesta di immagine, i server di elaborazione Adobe Analytics inseriscono i dati in un’altra colonna di database, denominata colonna post_evar, insieme alla normale colonna eVar.  Poiché le eVar sono intese come persistenti (ovvero scadono ad un certo punto oltre l’hit corrente nella maggior parte dei casi), i server imposteranno quindi questa colonna post_evar su ogni richiesta di immagine successiva e la imposteranno come ultimo valore passato nel relativo eVar. Per le eVar standard (cioè non merchandising), quando si verifica un evento di successo, Adobe Analytics utilizza la colonna post_evar invece della colonna normale eVar per determinare il valore di eVar a cui deve essere assegnato un credito per l’evento.
Per le eVar standard (ovvero non merchandising), l’impostazione Allocazione determina se il primo o l’ultimo valore eVar raccolto durante un determinato periodo verrà inserito nella colonna post_evar. Se l’impostazione Allocazione per un eVar standard è uguale a &quot;Valore originale (primo)&quot;, il primo valore eVar raccolto dal visitatore verrà inserito nella colonna post_evar per tutte le richieste di immagini successive.  Questo continuerà per tutte le richieste future inviate dal browser del visitatore fino alla scadenza dell’eVar per l’impostazione &quot;Scadenza dopo&quot;.\
Se l’impostazione Allocazione di un eVar standard è uguale a &quot;Più recente (ultimo)&quot;, il valore di eVar più recente raccolto dal visitatore verrà inserito nella colonna post_evar per tutte le richieste di immagini successive. L’allocazione &quot;Più recente (ultima)&quot; implica che il valore post_evar cambierà ogni volta che il relativo eVar corrispondente viene impostato su un nuovo valore in qualsiasi richiesta di immagine.  L’allocazione &quot;Valore originale (primo)&quot; implica che la colonna post_evar non verrà modificata tra i risultati anche se il relativo eVar corrispondente potrebbe essere impostato su un valore diverso in una richiesta di immagine futura.
Come accennato in precedenza, tutte le eVar di merchandising con sintassi a variabile di conversione hanno solo l’allocazione &quot;Più recente (Ultimo)&quot; (secondo la definizione standard di eVar).  Quindi, devo spiegare cosa significa l&#39;impostazione &quot;Allocazione&quot; per le eVar di merchandising.  Come implicito in precedenza, questa impostazione non determina quali valori vengono inseriti nella colonna post_evar mentre un visitatore continua a utilizzare il sito.  Piuttosto, l’impostazione Allocazione per eVar di merchandising determina quale valore di eVar si lega a un prodotto e come tali prodotti allocano


