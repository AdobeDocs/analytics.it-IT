---
title: contextData
description: Le variabili di dati di contesto ti consentono di definire variabili personalizzate su ogni pagina che le regole di elaborazione possono leggere.
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# contextData

Le variabili di dati di contesto ti consentono di definire variabili personalizzate su ogni pagina che le regole di elaborazione possono leggere. Invece di assegnare esplicitamente valori alle variabili Analytics nel codice, puoi inviare dati in variabili di dati di contesto. Le regole di elaborazione prendono quindi i valori delle variabili dei dati di contesto e li trasmettono alle rispettive variabili di Analytics. Vedi [Regole di elaborazione](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) nella guida utente Admin.

Le variabili di dati di contesto sono utili per i team di sviluppo per raccogliere i dati in elementi denominati invece che in variabili numerate. Ad esempio, anziché richiedere ai team di sviluppo di assegnare l’autore della pagina a `eVar10`, può richiedere che lo assegni a `s.contextData["author"]` invece. Un amministratore di Analytics nella tua organizzazione può quindi creare regole di elaborazione per mappare le variabili dei dati di contesto in variabili di Analytics a scopo di reportistica. I team di sviluppo si preoccuperebbero in ultima analisi solo delle variabili di dati di contesto, anziché delle numerose offerte di Adobe delle variabili di pagina.

## Variabili di dati di contesto che utilizzano i tag in Adobe Experience Platform

L’interfaccia utente di raccolta dati non dispone di una posizione dedicata per impostare variabili di dati di contesto. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.contextData in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.contextData` non acquisisce direttamente un valore. Imposta invece le proprietà di questa variabile su una stringa.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Le variabili di dati di contesto valide contengono solo caratteri alfanumerici, caratteri di sottolineatura e punti. Adobe non garantisce la raccolta dei dati nelle regole di elaborazione se includi altri caratteri, come i trattini.
* Non avviare le variabili di dati di contesto con `"a."`. Questo prefisso è riservato e utilizzato dall’Adobe. Ad esempio, non utilizzare `s.contextData["a.InstallEvent"]`.
* Le variabili di dati di contesto non sono sensibili all’uso di maiuscole e minuscole. Le variabili `s.contextData["example"]` e `s.contextData["EXAMPLE"]` sono identici.

## Utilizzare le regole di elaborazione per popolare le variabili di analisi

>[!IMPORTANT]
>
>Le variabili di dati di contesto vengono scartate dopo l’esecuzione delle regole di elaborazione. Se le regole di elaborazione non sono attive e inseriscono i valori nelle variabili, i dati andranno perduti definitivamente.

1. Aggiorna l’implementazione per impostare i nomi e i valori delle variabili dei dati di contesto.
2. Accedi ad Adobe Analytics e vai ad Amministratore > Suite di rapporti.
3. Seleziona la suite di rapporti desiderata, quindi vai a Modifica impostazioni > Generale > Regole di elaborazione.
4. Crea una regola di elaborazione che imposta una variabile di Analytics sul valore della variabile di dati di contesto.
5. Salva le modifiche.

Le regole di elaborazione hanno effetto immediatamente dopo il salvataggio. Non si applicano ai dati storici.

## Inviare dati contestuali in una chiamata di tracciamento dei collegamenti

Includi la variabile di dati di contesto come proprietà di `contextData` in [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Incrementa gli eventi utilizzando le variabili di dati di contesto

Quando crei regole di elaborazione, puoi assegnare variabili di dati di contesto agli eventi.

* Se una variabile di dati di contesto contiene qualsiasi tipo di testo, l&#39;evento viene incrementato di uno.
* Se una variabile di dati di contesto contiene un numero intero, l&#39;evento viene incrementato di tale numero intero.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
