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



# Proprietà elenco

Le proprietà elenco sono un elenco delimitato di valori che vengono passati in una variabile e quindi segnalati come singole voci. Le proprietà elenco sono comunemente implementate nelle pagine che contengono valori selezionabili dall'utente, come gli elementi elencati con caselle di controllo o pulsanti di scelta. Sono utili in qualsiasi circostanza in cui si desidera definire più valori in una variabile senza inviare più richieste di immagini.

<!-- 

list_props.xml

 -->

**Considerazioni**

* Le proprietà elenco sono abilitate solo sulle variabili di traffico ( [prop](/help/implement/js-implementation/c-variables/page-variables.md)).
* Impossibile abilitare percorsi e correlazioni per le proprietà dell'elenco.
* Analytics fornisce visite e visitatori unici a quasi tutti i report, inclusi tutti i report prop degli elenchi.
* Le classificazioni sono supportate per le proprietà elenco.
* Qualsiasi variabile di traffico personalizzata può diventare una proprietà elenco. (Eccezioni: [pageName](/help/implement/js-implementation/c-variables/page-variables.md), [channel](/help/implement/js-implementation/c-variables/page-variables.md)e [server](/help/implement/js-implementation/c-variables/page-variables.md).)

* Quando si definiscono valori duplicati nella stessa richiesta di immagine, le istanze non vengono deduplicate.

È possibile modificare una proprietà in una proprietà elenco nella pagina Strumenti di amministrazione &gt; Suite di rapporti &gt; Variabili di traffico abilitando Supporto elenco e selezionando un carattere di delimitazione. I delimitatori più comuni sono due punti, due punti e virgola, una virgola o un’estremità. Il delimitatore può essere tecnicamente uno dei primi 127 caratteri ASCII.

**Esempi** di implementazione {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

Quando si richiede l'abilitazione di prop elenco, indicare il delimitatore da utilizzare. Dopo aver attivato *`s.prop`* la scelta, nella variabile possono essere impostati più valori, come illustrato negli esempi seguenti:

Un prop di elenco delimitato da una tubazione, che trasmette due valori:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Un prop elenco delimitato da una virgola che trasmette diversi valori:

```js
s.prop2="cerulean,vermilion,saffron"
```

Le proprietà elenco possono essere inviate anche con un singolo valore:

```js
s.prop3="Single value"
```

Il delimitatore può essere modificato in qualsiasi momento. Tuttavia, l'implementazione deve corrispondere al nuovo delimitatore. Se non si utilizza il delimitatore corretto, nel reporting il valore prop dell'elenco viene trattato come un singolo elemento concatenato.

Poiché un prop elenco è ancora una variabile di traffico, è soggetto a limitazioni della variabile di traffico. Le proprietà elenco sono limitate a 100 byte di dati e sono influenzate dalle impostazioni di sensibilità maiuscole/minuscole.

