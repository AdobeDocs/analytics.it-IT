---
title: contextData
description: Le variabili di dati di contesto consentono di definire variabili personalizzate su ogni pagina che le regole di elaborazione possono leggere.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---


# contextData

Le variabili di dati di contesto consentono di definire variabili personalizzate su ogni pagina che le regole di elaborazione possono leggere. Invece di assegnare in modo esplicito valori a  variabili Analytics nel codice, potete inviare dati in variabili di dati di contesto. Le regole di elaborazione quindi prendono in considerazione i valori delle variabili di dati di contesto e li trasmettono nelle rispettive variabili  Analytics. Consulta Regole [di](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) elaborazione nella guida utente di amministrazione.

Le variabili di dati di contesto sono utili per i team di sviluppo per raccogliere i dati in elementi denominati invece che in variabili numerate. Ad esempio, anziché richiedere ai team di sviluppo di assegnare l’autore della pagina a `eVar10`, potete richiedere che venga assegnata `s.contextData["author"]` invece a. Un amministratore Analytics  nella tua organizzazione può quindi creare regole di elaborazione per mappare le variabili dei dati di contesto in variabili di analisi per il reporting. In ultima analisi, i team di sviluppo si preoccuperebbero solo delle variabili di dati di contesto invece delle numerose variabili di pagina offerte da Adobe.

## Variabili di dati di contesto in  Adobe Experience Platform Launch

Launch non dispone di un percorso dedicato per impostare le variabili di dati di contesto. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.contextData in AppMeasurement e Launch editor di codice personalizzato

La `s.contextData` variabile non riceve direttamente un valore. Impostare invece le proprietà di questa variabile su una stringa.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Le variabili di dati di contesto valide contengono solo caratteri alfanumerici, caratteri di sottolineatura e punti. Adobe non garantisce la raccolta dei dati nelle regole di elaborazione se si includono altri caratteri, come i trattini.
* Non avviare variabili di dati di contesto con `"a."`. Questo prefisso è riservato e utilizzato da Adobe. Ad esempio, non utilizzare `s.contextData["a.InstallEvent"]`.
* Le variabili di dati di contesto non fanno distinzione tra maiuscole e minuscole. Le variabili `s.contextData["example"]` e `s.contextData["EXAMPLE"]` sono identiche.

## Utilizzare le regole di elaborazione per compilare le variabili di analisi

>[!IMPORTANT]
>
>Le variabili di dati di contesto vengono eliminate dopo l&#39;esecuzione delle regole di elaborazione. Se non sono attive regole di elaborazione che inseriscono i valori nelle variabili, i dati andranno persi definitivamente.

1. Aggiorna l’implementazione per impostare i nomi e i valori delle variabili di dati di contesto.
2. Accedete ad Adobe  Analytics e andate ad Admin > Suite di rapporti.
3. Selezionate la suite di rapporti desiderata, quindi passate a Modifica impostazioni > Generale > Regole di elaborazione.
4. Creare una regola di elaborazione che imposti una variabile Analytics  al valore della variabile di dati contestuali.
5. Salvare le modifiche.

Le regole di elaborazione diventano effettive immediatamente dopo il salvataggio. Non si applicano ai dati storici.

## Invio di dati contestuali in una chiamata di tracciamento dei collegamenti

Includi la variabile di dati contestuali come proprietà di `contextData` in [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
