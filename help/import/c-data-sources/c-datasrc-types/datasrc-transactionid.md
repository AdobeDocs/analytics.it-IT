---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell’utilizzo delle origini dati ID transazione.
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 4497ca252c4ee05175141e58d784ca2df215cb94
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Origini dati ID transazione

Le origini dati ID transazione consentono non solo di visualizzare i dati online e offline affiancati, ma anche di collegare i dati. Richiede l’utilizzo della variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md) nell’implementazione di Analytics.

Quando invii un hit online contenente un valore `transactionID`, Adobe crea uno &quot;snapshot&quot; di tutte le variabili impostate o persistenti in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite Origini dati, i dati offline e online vengono legati tra loro.

Per utilizzare le transazioni, è necessario che l’hit online con un ID transazione sia stato inviato ed elaborato prima che vengano inviati i dati di origine dei dati di transazione con tale ID transazione. L’hit online contiene variabili (eVar, ecc.), ma non eventi, che si trovavano sull’hit online salvato con le informazioni ID transazione.

Quando viene inviato un hit dell’origine dati della transazione, l’ID della transazione nell’hit della transazione dell’origine dati cerca le variabili, ecc. (non eventi) associati all&#39;hit online originale con quell&#39;ID transazione. Utilizza le variabili nel risultato della transazione dell&#39;origine dati, se non c&#39;era un valore per una variabile passata nell&#39;hit della transazione dell&#39;origine dati.

## Esempio

Se viene passato un hit online con ID transazione 1256 e su di esso `evar1=blue`, `evar2=water` e `event1` sono impostati, i dati della transazione per ID transazione 1256 vengono salvati con `evar1=blue`, `evar2=water`. Nessun valore evento viene salvato come parte delle informazioni sulla transazione.

Ora supponiamo che un hit di transazione dell’origine dati venga quindi trasmesso attraverso il sistema con ID transazione 1256 e `evar1=yellow`, `evar3=mountain` e `event2` impostati. Il sistema trova i dati della transazione salvati e nei set di hit della transazione dell’origine dati `evar2=water` (poiché questo è ciò che è stato impostato sull’hit originale). Non imposta `evar1=blue` (come nell&#39;hit originale) perché c&#39;era un valore per `evar1` (giallo) già impostato sull&#39;hit della transazione dell&#39;origine dati.  Pertanto, l’hit della transazione dell’origine dati si traduce in `evar1=yellow`, `evar2=water` (dall’hit online originale) e `evar3=mountain`. I 3 valori eVar hanno `event2` impostato - l&#39;evento dall&#39;hit della transazione dell&#39;origine dati.

Nessun valore dall&#39;hit della transazione dell&#39;origine dati viene impostato `event1` quando l&#39;hit della transazione dell&#39;origine dati viene elaborato.

## Flusso di lavoro complessivo delle origini dati ID transazione

Utilizza il seguente flusso di lavoro generico per iniziare a utilizzare le origini dati ID transazione:

1. Creare un’origine dati (tipo &quot;Generic&quot; (categoria generico) e &quot;Generic Data Source (Transaction ID)&quot;).
1. Segui la procedura guidata di configurazione dell’origine dati per ottenere una posizione FTP per caricare dati e scaricare un file modello origini dati.
1. Aggiorna l’implementazione per includere la variabile `transactionID` .
1. Carica un file origini dati sul sito FTP con un file `.fin` .

## Esempio di caricamento di file e codice di implementazione

Se hai caricato il seguente file di origini dati e implementato il seguente codice sul tuo sito, vedrai i dati collegati nel reporting. Il file origini dati utilizza eVar1 e event1, mentre l’implementazione online utilizza eVar2 e event2. Poiché l’ID transazione corrisponde, è possibile visualizzare i dati event2 per eVar1 e i dati event1 per eVar2.

### Esempio di file

Scarica il modello, aggiorna i valori, quindi caricalo nel percorso FTP delle origini dati:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Esempio di codice di implementazione

Per una spiegazione più dettagliata sull&#39;ID transazione, vedi [`transactionID`](/help/implement/vars/page-vars/transactionid.md) nella guida utente Implementa.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
