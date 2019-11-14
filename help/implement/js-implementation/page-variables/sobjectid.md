---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# s_objectID

La variabile è una variabile globale che deve essere impostata in [!UICONTROL onClick] caso di collegamento.

<!-- 

s_objectID.xml

 -->

Creando un ID oggetto univoco per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il tracciamento dell’attività del visitatore oppure utilizzare [!UICONTROL Activity Map] per creare rapporti su un tipo o una posizione di collegamento, anziché sull’URL del collegamento.

> [!NOTE] È necessario un punto e virgola finale (;) quando si utilizza s_objectID con [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | URL assoluto di un collegamento con clic |

Esistono tre motivi comuni per utilizzare *`s_objectID`*:

* Per aggregare l'attività del visitatore che cambia spesso durante un giorno.
* Per separare l'attività dei collegamenti che [!UICONTROL Activity Map] si combina.
* Per migliorare la precisione della generazione di rapporti [!UICONTROL Activity Map] sui dati.

**Aggrega clic su collegamenti** altamente dinamici {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Se il sito è altamente dinamico e i collegamenti su alcune pagine cambiano durante la giornata, *`s_objectID`* può essere utilizzato per identificare la posizione di un collegamento sulla pagina. Se *`s_objectID`* è impostato su "top left 1" o "top left 2", che ad esempio rappresenta il primo collegamento in alto a sinistra della pagina, tutti i collegamenti che compaiono in quella posizione (o che hanno *`s_objectID`* impostato lo stesso valore) vengono segnalati insieme alla mappa clic del visitatore. Se non si utilizza *`s_objectID`*, viene visualizzato il numero di volte in cui è stato fatto clic su un collegamento specifico, ma si perde la comprensione di come tutti gli altri collegamenti in tale posizione sono stati utilizzati dai visitatori del sito.

**Clic Separate**{#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Se la *`pageName`* variabile sul sito viene utilizzata per mostrare la sezione o il modello che un visitatore sta visualizzando, anziché la pagina specifica che il visitatore sta visualizzando, potete utilizzare *`s_objectID`* per separare i collegamenti visualizzati su più versioni di tale modello di pagina. Ad esempio, se disponete di una pagina di modello per tutti i prodotti sul sito, è probabile che esista un collegamento alla pagina principale e a una casella di ricerca da tale modello su tutte le pagine. Se desiderate visualizzare il modo in cui tali collegamenti vengono utilizzati in base a un singolo prodotto (anziché in base a un modello), potete compilare *`s_objectID`* con un valore specifico del prodotto, ad esempio "prod 123789 home page" o "prod 123789 search". Una volta completati, [!UICONTROL Activity Map] rapporti su tali collegamenti a livello di singolo prodotto.

**Maggiore[!UICONTROL Activity Map]precisione**{#section_08B3406821294DCCABEEB99C90CF5C52}

In alcuni casi, i browser diversi da Internet Explorer, Firefox, Netscape, Opera e Safari non vengono segnalati. Anche se si tratta di una percentuale ridotta, può gestire alcuni clic e altre metriche. Utilizzate *`s_objectID`* all'interno dei collegamenti per identificare in modo univoco gli indirizzi del problema di reporting del browser. Di seguito è riportato un esempio di come aggiornare i collegamenti da utilizzare *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintassi e valori** possibili {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID può contenere qualsiasi identificatore di testo.

```js
s_objectID="unique_id" 
```

Non esistono limitazioni *`s_objectID`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Impostazioni** di configurazione {#section_95396657D55B41ECB66B83D0534EA827}

Nessuno
