---
title: contextData
description: Le variabili di dati di contesto ti consentono di definire variabili personalizzate in ogni pagina leggibile dalle regole di elaborazione.
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 1%

---

# contextData

Le variabili di dati di contesto ti consentono di definire variabili personalizzate in ogni pagina leggibile dalle regole di elaborazione. Invece di assegnare esplicitamente i valori alle variabili di Analytics nel codice, puoi inviare dati in variabili di dati di contesto. Le regole di elaborazione accettano quindi i valori delle variabili di dati di contesto e li trasmettono alle rispettive variabili di Analytics. Consulta [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) nella guida utente Admin.

Le variabili di dati contestuali sono utili ai team di sviluppo per raccogliere dati in elementi denominati anziché in variabili numerate. Ad esempio, invece di richiedere ai team di sviluppo di assegnare l’autore della pagina a `eVar10`, puoi richiederne l’assegnazione a `s.contextData["author"]` invece. Un amministratore di Analytics della tua organizzazione può quindi creare regole di elaborazione per mappare le variabili di dati di contesto in variabili di Analytics a scopo di reporting. In definitiva, i team di sviluppo si preoccuperebbero solo delle variabili di dati di contesto anziché delle numerose variabili di pagina offerte dall’Adobe.

## Variabili di dati di contesto tramite Web SDK

Se utilizzi il [**Oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), tutti i campi che non vengono mappati su una variabile Adobe Analytics vengono inclusi automaticamente come variabile di dati di contesto. Puoi quindi utilizzare [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) per assegnare la variabile di dati di contesto alla variabile di Analytics desiderata.

Se utilizzi il [**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), tutte le variabili di dati di contesto risiedono in `data.__adobe.analytics.contextData` come coppie chiave-valore:

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

Il [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) l’interfaccia apparirebbe `c.example_variable` e `c.second_example` nei menu a discesa applicabili.

## Variabili di dati di contesto tramite l’estensione Adobe Analytics

La raccolta dati di Adobe Experience Platform non dispone di una posizione dedicata per impostare le variabili di dati di contesto. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.contextData in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.contextData` La variabile non accetta direttamente un valore. Imposta invece le proprietà di questa variabile su una stringa.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* Le variabili di dati di contesto valide contengono solo caratteri alfanumerici, trattini bassi e punti. L’Adobe non garantisce la raccolta dei dati nelle regole di elaborazione se includi altri caratteri, ad esempio i trattini.
* Non avviare le variabili di dati di contesto con `"a."`. Questo prefisso è riservato e utilizzato da Adobe. Ad esempio, non utilizzare `s.contextData["a.InstallEvent"]`.
* Le variabili di dati di contesto non fanno distinzione tra maiuscole e minuscole. Le variabili `s.contextData["example"]` e `s.contextData["EXAMPLE"]` sono identici.

## Utilizzare le regole di elaborazione per popolare le variabili di analisi

>[!WARNING]
>
>Le variabili di dati di contesto vengono eliminate dopo l’esecuzione delle regole di elaborazione. Se non hai regole di elaborazione attive che inseriscono valori nelle variabili, quei dati vengono persi definitivamente!

1. Aggiorna l’implementazione per impostare i nomi e i valori delle variabili di dati di contesto.
2. Accedi ad Adobe Analytics e vai su Amministratore > Suite di rapporti.
3. Seleziona la suite di rapporti desiderata, quindi vai a Modifica impostazioni > Generale > Regole di elaborazione.
4. Crea una regola di elaborazione che imposta una variabile di Analytics sul valore della variabile di dati di contesto.
5. Salva le modifiche.

Le regole di elaborazione diventano effettive immediatamente dopo il salvataggio. Non si applicano ai dati storici.

## Inviare dati contestuali in una chiamata di tracciamento dei collegamenti

Includi la variabile di dati di contesto come proprietà di `contextData` in [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## Incrementare gli eventi utilizzando le variabili di dati di contesto

Durante la creazione di regole di elaborazione, puoi assegnare variabili di dati di contesto agli eventi.

* Se una variabile di dati di contesto contiene qualsiasi tipo di testo, l’evento viene incrementato di uno.
* Se una variabile di dati di contesto contiene un numero intero, l’evento viene incrementato di tale numero intero.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
