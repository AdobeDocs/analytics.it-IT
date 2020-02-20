---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell'utilizzo delle origini dati ID transazione.
translation-type: tm+mt
source-git-commit: c54704bef49a2c3076caac6fe7dd3ec8d40596ef

---


# Origini dati ID transazione

Le origini dati ID transazione consentono non solo di visualizzare i dati online e offline affiancati, ma anche di collegare i dati. Richiede l&#39;utilizzo della [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabile nell&#39;implementazione di Analytics.

Quando inviate un hit online contenente un `transactionID` valore, Adobe crea uno &quot;snapshot&quot; di tutte le variabili impostate o persistenti in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite Origini dati, i dati offline e online vengono legati insieme. Non importa quale origine di dati viene visualizzata per prima.

## Flusso di lavoro complessivo delle origini dati ID transazione

Utilizza il seguente flusso di lavoro generico per iniziare a utilizzare le origini dati ID transazione:

1. Creare un&#39;origine dati (tipo &quot;Generico&quot; e &quot;Origine dati generica (ID transazione)&quot;).
1. Segui la procedura guidata di configurazione dei feed di dati per ottenere un percorso FTP per caricare i dati e scaricare un file modello origini dati.
1. Aggiornate l&#39;implementazione per includere la `transactionID` variabile.
1. Carica un file origini dati sul sito FTP con un `.fin` file.

## Esempio di file di caricamento e codice di implementazione

Se hai caricato il seguente file di origini dati e implementato il seguente codice sul tuo sito, i dati risulterebbero collegati nel reporting. Il file delle origini dati utilizza eVar1 e event1, mentre l&#39;implementazione online utilizza eVar2 e event2. Poiché l&#39;ID transazione corrisponde, è possibile visualizzare i dati event2 per eVar1 e i dati event1 per eVar2.

### Esempio di file

Scarica il modello, aggiorna i valori, quindi caricalo nel percorso FTP delle origini dati:

| `# Generic Data Source (Transaction ID) template file (user: 0 ds_id: 1)` |  |  |  |
|---|---|---|---|
| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Esempio di codice di implementazione

Per una spiegazione più dettagliata sull&#39;ID transazione, consulta [`transactionID`](/help/implement/vars/page-vars/transactionid.md) Nella guida per l&#39;utente Implementa.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
