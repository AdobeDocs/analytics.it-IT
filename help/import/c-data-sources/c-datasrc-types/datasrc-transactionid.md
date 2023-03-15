---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell’utilizzo delle origini dati ID transazione.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Origini dati ID transazione

Le origini dati ID transazione ti consentono non solo di visualizzare affiancati dati online e offline, ma anche di collegarli tra loro. Richiede l&#39;utilizzo di [`transactionID`](/help/implement/vars/page-vars/transactionid.md) nell’implementazione di Analytics.

Quando invii un hit online contenente un `transactionID` Adobe crea un’istantanea di tutte le variabili impostate o mantenute in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite Origini dati, i dati offline e online sono legati tra loro.

Per utilizzare le transazioni, l’hit online con un ID transazione deve essere stato inviato ed elaborato prima dell’invio dei dati dell’origine dati della transazione con tale ID transazione. L’hit online contiene variabili (eVar, ecc.), ma non eventi, presenti nell’hit online salvato con le informazioni dell’ID transazione.

Quando viene inviato un hit dell’origine dati della transazione, l’ID della transazione nell’hit della transazione dell’origine dati cerca le variabili, ecc. (non eventi) associati all’hit online originale con tale ID transazione. In caso di hit di transazione origine dati privo di valore per una variabile trasmessa, vengono utilizzate tali variabili.

## Esempio

Se un hit online con ID transazione 1256 viene passato a e su di esso `evar1=blue`, `evar2=water` e `event1` , quindi i dati della transazione per l&#39;ID transazione 1256 vengono salvati con `evar1=blue`, `evar2=water`. Nessun valore evento viene salvato come parte delle informazioni sulla transazione.

Supponiamo ora che un hit di transazione dell’origine dati venga quindi trasmesso al sistema con l’ID transazione 1256 e `evar1=yellow`, `evar3=mountain` e `event2` impostata. Il sistema trova i dati della transazione salvati e nei set di hit della transazione dell&#39;origine dati `evar2=water` (poiché questo è ciò che è stato impostato sull’hit originale). Non viene impostato `evar1=blue` (come nell’hit originale) perché era presente un valore per `evar1` (giallo) già impostato sull’hit della transazione dell’origine dati.  Pertanto, l’hit della transazione dell’origine dati determina `evar1=yellow`, `evar2=water` (dall’hit online originale) e `evar3=mountain`. Questi 3 valori eVar hanno `event2` set: l’evento dall’hit della transazione dell’origine dati.

Nessun valore dal recupero hit della transazione origine dati `event1` impostato quando viene elaborato l’hit della transazione dell’origine dati.

## Flusso di lavoro generale delle origini dati ID transazione

Utilizza il seguente flusso di lavoro generico per iniziare a utilizzare le origini dati ID transazione:

1. Creare un&#39;origine dati (categoria &quot;Generic&quot; e tipo &quot;Generic Data Source (Transaction ID)&quot;).
1. Segui la procedura guidata di configurazione dell’origine dati per ottenere un percorso FTP per caricare i dati e scaricare un file modello origine dati.
1. Aggiorna l’implementazione per includere `transactionID` variabile.
1. Carica un file di origini dati sul sito FTP con una `.fin` file.

## Esempio di file di caricamento e codice di implementazione

Se hai caricato il seguente file di origini dati e hai implementato il seguente codice sul tuo sito, vedrai i dati collegati nel reporting. Il file delle origini dati utilizza eVar1 ed event1, mentre l’implementazione online utilizza eVar2 ed event2. Poiché l’ID transazione corrisponde, è possibile visualizzare i dati event2 per eVar1 e event1 per eVar2.

### Esempio di file

Scarica il modello, aggiorna i valori, quindi caricalo nel percorso FTP delle origini dati:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Esempio di codice di implementazione

Per una spiegazione più dettagliata sull’ID transazione, consulta [`transactionID`](/help/implement/vars/page-vars/transactionid.md) Nella guida utente Implementa.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
