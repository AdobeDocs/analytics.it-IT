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


# state

Le variabili e sono variabili di conversione.

<!-- 

state.xml

 -->

Sono come eVar in quanto catturano eventi, ma a differenza delle eVar, non persistono. Le variabili *`zip`* e *`state`* sono come eVar che scadono immediatamente.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 50 byte | state | Conversione &gt; Profilo visitatore &gt; Stato visitatore | "" |

Poiché le *`state`* variabili e le *`zip`* variabili scadono immediatamente, gli unici eventi associati sono gli eventi attivati sulla stessa pagina in cui sono popolati. Ad esempio, se si utilizza *`state`* per confrontare i tassi di conversione per stato, è necessario compilare la *`state`* variabile in ogni pagina del processo di estrazione. Per i siti di conversione, Adobe consiglia di utilizzare l'indirizzo di fatturazione come origine per il Codice postale, ma potete scegliere di utilizzare l'indirizzo di spedizione al posto (supponendo che esista un solo indirizzo di spedizione per l'ordine). Un sito multimediale può scegliere di utilizzare *`zip`* e *`state`* per la registrazione o il tracciamento del click-through degli annunci.

**Sintassi e valori** possibili {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

La *`state`* variabile non impone alcuna limitazione di valore o di formato speciale. Non esistono limitazioni *`state`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Impostazioni** di configurazione {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Nessuno

**Insidie, domande e suggerimenti**{#section_02F1620D0BB14AA6A838966FDB9A234F}

* Compilate *`state`* su ogni pagina un evento rilevante (ad esempio ogni pagina del processo di estrazione).
* Le *`zip`* variabili e *`state`* le variabili si comportano come eVar che scadono nella visualizzazione pagina.
