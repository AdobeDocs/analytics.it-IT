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


# zip

Le variabili e sono variabili di conversione.

<!-- 

zip.xml

 -->

Sono come eVar in quanto catturano eventi, ma a differenza delle eVar, non persistono. Le variabili *`zip`* e *`state`* sono come eVar che scadono immediatamente.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 50 byte | zip | Conversione &gt; Profilo visitatore &gt; Codici postali | "" |

Poiché le *`state`* variabili e le *`zip`* variabili scadono immediatamente, gli unici eventi associati sono gli eventi attivati sulla stessa pagina e compilati. Ad esempio, se si utilizza *`zip`* per confrontare i tassi di conversione per CAP, è consigliabile compilare *`zip`* in ogni pagina del processo di estrazione. Adobe consiglia di utilizzare l'indirizzo di fatturazione come origine per il CAP. È possibile scegliere di utilizzare l'indirizzo di spedizione invece (supponendo che vi sia un solo indirizzo di spedizione per l'ordine). Un sito multimediale può scegliere di utilizzare *`zip`* e *`state`* per la registrazione o il tracciamento del click-through degli annunci.

**Sintassi e valori** possibili {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

La *`zip`* variabile non impone alcuna limitazione di valore o formato. Non esistono limitazioni *`zip`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Impostazioni** di configurazione {#section_7987084EECC34DD38B643B94F82385CA}

Nessuno

**Insidie, domande e suggerimenti**{#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Compilate [!UICONTROL zip] su ogni pagina in cui viene attivato un evento rilevante (ad esempio ogni pagina del processo di estrazione).
* Le *`zip`* variabili e *`state`* le variabili si comportano come eVar che scadono nella visualizzazione pagina.

