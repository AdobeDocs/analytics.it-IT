---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell’utilizzo delle origini dati ID transazione.
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 1ee6a1e69a277f0d3c0ffd1defca0d4cb098cc6c
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Origini dati ID transazione

Le origini dati ID transazione consentono non solo di visualizzare i dati online e offline affiancati, ma anche di collegare i dati. Richiede l’utilizzo della variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md) nell’implementazione di Analytics.

Quando invii un hit online contenente un valore `transactionID`, Adobe crea uno &quot;snapshot&quot; di tutte le variabili impostate o persistenti in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite Origini dati, i dati offline e online vengono legati tra loro. Non importa quale fonte di dati viene visualizzata per prima.

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
